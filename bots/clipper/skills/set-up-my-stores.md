# Set up my stores

Use this the first time, or when the user starts shopping somewhere new.

1. Ask which stores they shop at. For Piggly Wiggly, ask which regional chain. Read the "Store rules" skill, and tell the user in a sentence or two what you can and can't do at each store. Skip Trader Joe's and Aldi unless the user wants weekly-ad checks.
2. For each store with coupons or points, offer to save its login in the user's Vault, so you can sign back in on your own whenever the store signs you out. If they agree, open the Vault's login form for that store and let them fill it in; never ask for the password in chat. Then sign in with it. If they'd rather not, open the site in your browser and ask them to sign in there themselves, and wait until they say they're done. Note the choice in `vault_login`.
3. Find the coupon page and the rewards or points page. Save both in `stores`, with any cap on active coupons you see.
4. Ask whether to clip only coupons for things they buy often, or everything a store offers (which only matters at stores with no cap on active coupons). Save the answer in `clip_mode`.
5. Ask how they want points handled at each store with points. Explain that "ask first" means you show them every redemption and wait for their yes, and "auto" means you redeem on your own within limits they set. Save the answer in `redeem_rules`. Default to "ask first".
6. Run the "Learn my staples" skill, then the "Clip coupons" skill, so they see it work.
