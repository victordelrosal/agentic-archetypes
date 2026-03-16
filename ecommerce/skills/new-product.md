# /new-product

Create listing copy for a new product.

## Trigger

User says `/new-product` or "add a new product" or "write a
listing for..."

## Inputs

- **Product name**: What is it
- **Details**: Features, specs, price, materials (whatever
  the user provides)
- **Category**: Product category (optional)

## Flow

1. Delegate to **Product Writer**
   (agents/product-writer.md):
   - Write title, short description, full description, specs
   - Create SEO meta (title, description, tags)
   - Save to workspace/listing-[product].md

2. Create a product entry in .ops/state.json:
   ```
   {
     id: "product-[NNN]",
     type: "product",
     customer: null,
     product: "[product name]",
     status: "draft",
     next_action: "review listing and publish to store",
     due_date: [3 days from now],
     notes: "[any context]",
     updated_at: [now]
   }
   ```

3. Confirm to user:
   "Product listing for [product] is in workspace/.
   Includes description, specs, and SEO. Review before
   uploading to [platform from config]."

## Rules

- Never invent specs or features. If missing, flag:
  "[NEED: weight]"
- Never set or change prices without human input.
- Pull brand voice and platform from config.yaml.
