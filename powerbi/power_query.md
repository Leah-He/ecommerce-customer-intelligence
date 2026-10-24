# Power Query M — Selected Data Transformations

The original report drew on multiple operational sources. Some external data paths are no longer available after the original development environment was decommissioned. The archived queries retain portions of the transformation logic.

The following are **privacy-safe adaptations of the observed M expressions**, with synthetic identifiers and no business data or real phone numbers.

## 1. Customer identifier fallback

The archived transformation preferentially used `customer_phone`, then `receiver_phone`, when either value had at least 11 characters after trimming. The original implementation prefixed the selected raw phone with `P#`; **that is not anonymization** and is not suitable for public customer-level exports.

A privacy-safer conceptual illustration is:

```powerquery
// Demonstration only; the tokenization function is a placeholder.
= Table.AddColumn(Source, "customer_key", each
    let
        buyer = if [customer_phone] = null then "" else Text.Trim(Text.From([customer_phone])),
        receiver = if [receiver_phone] = null then "" else Text.Trim(Text.From([receiver_phone])),
        selected = if Text.Length(buyer) >= 11 then buyer
                   else if Text.Length(receiver) >= 11 then receiver
                   else null
    in
        if selected = null then null else "TOKENIZE_IN_SECURE_ENVIRONMENT"
)
```

This demonstration preserves the selection idea but **does not implement anonymization**. In a real deployment, tokenization must occur in an appropriately controlled environment, and customer/recipient identity mismatches need investigation. Length checks alone do not validate phone numbers.

## 2. Product composite key

The archived query built `product_uid` from source platform, product name, and SKU, using `Text.Trim`, `Text.From`, null handling, and string concatenation.

```powerquery
= Table.AddColumn(
    PreviousStep,
    "product_uid",
    each
        (if [source_platform] = null then "" else Text.Trim(Text.From([source_platform])))
        & "|" &
        (if [product_name] = null then "" else Text.Trim(Text.From([product_name])))
        & "|" &
        (if [sku_name] = null then "" else Text.Trim(Text.From([sku_name])))
)
```

This is a **composite key**, not a guarantee of uniqueness or automatic cross-platform product deduplication. Delimiter collisions, missing values, duplicate names and renamed SKUs require quality checks.

## 3. Data type consistency

The archived `std_order_fact` query also included type conversion for the identifiers:

```powerquery
= Table.TransformColumnTypes(PreviousStep,
    {{"customer_id", type text}, {"product_uid", type text}})
```

## Scope

These examples document selected steps observed in the recovered Power Query editor. They do not claim the full original ETL can be reproduced without the missing sources. Source-specific paths and records are intentionally excluded.
