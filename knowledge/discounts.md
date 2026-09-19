---
type: Document
title: Discount Policy and Promotional Offers
description: Authoritative rules, eligibility requirements, and dynamic calculation logic for discounts including the Buy 4 Get 1 Free offer.
status: stable
order: 6
generated: { by: "human:you", at: 2026-09-18T18:45:00Z }
ksor:
  audience: [public]
  approval: { by: "human:you", at: 2026-09-18T18:45:00Z }
---

Promotional discount structure and computational rules for E-commerce Mall orders. These rules govern automated checkout systems, manual cart adjustments, and customer service explanations.

## Buy 4, Get 1 Free Offer

The E-commerce Mall runs an active store-wide **Buy 4, Get 1 Free** promotion across all qualifying products in Shoes, Men's Clothes, Women's Clothes, Kids Clothes, and Accessories.

### Promotion Rules

1. **Qualification Threshold**: A customer must select and add at least 5 eligible products to their cart in a single transaction (4 paid items + 1 free promotional item).
2. **Cheapest Item Free**: The lowest-priced eligible product among every group of 5 qualifying items in the cart is automatically discounted to 0 PKR (100% discount on that item).
3. **Multiples and Stacking**:
   - For every 5 eligible items purchased, 1 free item is granted.
   - 5 to 9 items: 1 cheapest item free.
   - 10 to 14 items: 2 cheapest items free.
   - 15 to 19 items: 3 cheapest items free.
4. **Dynamic Cart Recalculation**:
   - The discount is not static; it must be immediately recalculated whenever any cart event occurs.
   - Events triggering recalculation: adding an item, removing an item, increasing or decreasing item quantities, or applying coupon codes.
   - If a cart with 5 items has an item removed, the cart count drops to 4 items and the free item promotion is instantly removed.
   - If a new lower-priced item is added to an existing qualifying set, the system dynamically shifts the free item status to the new cheapest item.

### Calculation Examples

#### Example A: 5 Distinct Items

A customer adds 5 items to their cart:
- Formal Leather Oxford Shoes: 6,800 PKR
- Slim Fit Denim Jeans: 3,800 PKR
- Silk Satin Blouse: 3,400 PKR
- Reversible Leather Belt: 1,850 PKR
- Boys Dino Graphic T-Shirt: 1,100 PKR

**Calculation**:
- Total Items: 5
- Eligible sets of 5: 1 set
- Items ranked by price (ascending): 1,100 PKR, 1,850 PKR, 3,400 PKR, 3,800 PKR, 6,800 PKR
- Free Item: Boys Dino Graphic T-Shirt (1,100 PKR)
- Gross Subtotal: 16,950 PKR
- Discount Applied: -1,100 PKR
- Net Subtotal Payable: 15,850 PKR

#### Example B: Cart Modification (Adding a Cheaper Item)

Continuing from Example A, the customer adds:
- Cotton Flannel Pajama Set: 1,950 PKR
- Minimalist RFID-Blocking Leather Wallet: 900 PKR (sale price)

The cart now has 7 items. The single lowest-priced item among the 7 is the Minimalist RFID-Blocking Leather Wallet at 900 PKR. The system updates the discount from 1,100 PKR to 900 PKR, and the Boys Dino T-Shirt reverts to its regular paid price.
