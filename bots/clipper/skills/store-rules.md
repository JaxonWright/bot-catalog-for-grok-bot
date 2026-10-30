# Store rules

How each store's digital coupons and rewards work, and what you can do for the user there. These were checked in October 2026. Programs change, so trust the store's own site when it disagrees, and update `stores`.

## Stores with coupons to clip

**Meijer (mPerks).** Clip digital coupons on meijer.com under Coupons, or in the app. Clipped coupons apply when the user enters their mPerks phone number or scans the app at checkout. mPerks earns points on every dollar spent and on prescriptions. Points expire, about 90 to 95 days after they're earned, so check the account for the real date. To spend points, the user picks a reward in mPerks, such as dollars off groceries or off gas, and it applies at their next checkout. Points that aren't redeemed are lost, so warn the user two weeks before any expire.

**Kroger** (and its banners, such as Ralphs, Fred Meyer, King Soopers, Smith's, Fry's, Harris Teeter, and Mariano's). Clip digital coupons on the store's site under Savings, then Coupons. A Kroger account has a cap on active coupons, 150 at last check, so clip staples first and stop short of the cap. Since June 2026, Fuel Points are just "Points", one per dollar on eligible purchases, more with Boost. They can be spent two ways:
- Groceries: $1 off for every 100 Points, up to $10 a day. The user applies them in their account before checkout.
- Fuel: 10 cents off a gallon for every 100 Points, up to $1 a gallon.
Fuel is worth more only when the user fills 10 gallons or more at a Kroger station. Ask how much they usually pump, remember it in `redeem_rules`, and recommend whichever is worth more.

**Publix.** Clip digital coupons on publix.com under Savings, then Digital Coupons, or in the app, after joining Club Publix. They apply when the user enters their phone number at checkout. Most digital coupons apply once per transaction. Publix lets a manufacturer coupon, a Publix store coupon, and a digital coupon stack on one item. Publix has no points program.

**Food Lion (MVP).** Load digital coupons to the MVP card on foodlion.com in the Savings Hub, or in the app. They apply automatically at checkout, and most are one use. Each month, also load the user's personalized "Shop & Earn" offers from the Shop & Earn tab. Earned rewards apply automatically on the next trip through the end of the following month, so there's nothing to redeem.

**BJ's Wholesale.** Clip coupons on bjs.com under Coupons, or in the app. They apply to the membership at checkout and can stack with manufacturer coupons. BJ's rewards from the membership or the BJ's credit card build up as a balance that can be spent at checkout once it reaches the minimum, $10 or $20 depending on the program. Check the account for the minimum and the balance.

**Piggly Wiggly.** Each regional chain runs its own app and site, such as Piggly Wiggly Midwest, Bama Pig Rewards, or a store's own Pig Rewards card. Ask the user which chain they shop at and use that chain's site. Most let them add digital coupons to their rewards card, and some have points. Learn the rules from that chain's site and save them in `stores`.

**Walmart.** Walmart Cash offers are clipped in the app or on walmart.com, and they pay Walmart Cash after the user buys the item. Walmart's digital coupons, under Deals, apply at checkout once clipped. The user spends Walmart Cash by choosing "Apply Walmart Cash" at checkout, so there's nothing to redeem ahead of time. Walmart often blocks automated browsing. If it shows a "press and hold" or a CAPTCHA, stop and tell the user to clip there by hand.

## Stores with nothing to clip

**Sam's Club.** There are no coupons to clip. Instant Savings apply on their own at checkout. Plus members earn 2% back as Sam's Cash, up to $500 a year, which can be applied to any later purchase. Report the balance and remind the user to apply it at checkout.

**Costco.** There are no coupons to clip. Member deals apply at the register. Executive members get a 2% reward once a year as a certificate. Remind the user when it arrives and before it expires.

**Trader Joe's.** No coupons, no loyalty program, no points. Nothing to do.

**Aldi.** No coupons, no loyalty card, and no points in the US. The app only lists the weekly deals. If the user wants, tell them which of their staples are in this week's Aldi ad.
