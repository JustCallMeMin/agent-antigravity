# Schema.org & Structured Data

## 1. Purpose of Schema
- To help search engines understand the *meaning* of the content, not just the keywords.
- To enable rich snippets (stars, prices, steps) in search results.

## 2. Mandatory Formats
- Always prefer **JSON-LD** over Microdata.
- Place JSON-LD script in the `<head>` or at the end of the `<body>`.

## 3. Essential Types
- **Organization**: For brand identity and knowledge graph.
- **Article/BlogPosting**: For content discovery.
- **Product & Offer**: For Transactional intent.
- **Review & AggregateRating**: For social proof snippets.
- **BreadcrumbList**: For site structure in SERPs.

## 4. Validation
- All schema must pass the [Schema Markup Validator](https://validator.schema.org/).
- Ensure no conflicting attributes between different schema types on the same page.
