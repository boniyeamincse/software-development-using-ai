# 09 - Ecommerce Workflows

## The Purchase Lifecycle
1. **Discovery**: Customer searches and browses products.
2. **Commitment**: Item added to cart; System checks stock.
3. **Transaction**: Customer initiates checkout; Gateway authorizes payment.
4. **Allocation**: Order marked "Paid"; Inventory reserved in Warehouse.
5. **Logistics**: Warehouse picks/packs item; Shipping label generated via API.
6. **Delivery**: Tracking ID shared with customer; Status updated to "Delivered."

## Refund & Return Workflow
1. Customer initiates return via portal.
2. Support agent reviews photos/reason and approves "RMA."
3. Customer ships item back; Logistics confirms receipt.
4. System triggers automated refund via original payment gateway.
5. Inventory restocked automatically.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
