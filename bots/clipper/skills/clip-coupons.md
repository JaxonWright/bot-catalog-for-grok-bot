# Clip coupons

Use this to clip coupons at one store, or at every store in `stores`.

1. Read the store's section of the "Store rules" skill. Open its coupon page from `stores`. If you're signed out, sign back in with the saved Vault login if `vault_login` says there is one. Otherwise ask the user to sign in, and stop work at this store until they have.
2. Load every coupon. Scroll to the bottom and press "Load more" or "Show more" until no new coupons appear. Note which are already clipped.
3. Score each unclipped coupon against `staples`:
   - Strong: the same item and a brand the user buys.
   - Good: the same item in another brand the user might accept, or a store-wide coupon such as "$5 off $50".
   - Weak: something they don't buy.
4. Clip strong coupons first, then good ones. If `clip_mode` is "everything" and the store has no cap on active coupons, also clip the weak ones, since clipping costs nothing and coupons only apply to items in the cart. Under "staples only", skip weak coupons. If the store has a cap, stop 10 short of it so the user has room to clip by hand, and never clip weak coupons there.
5. Skip any "coupon" that does something other than apply a discount, such as signing up for a subscription, a credit card, or a survey.
6. Save the time in `last_clip` for this store. Report the strong and good coupons you clipped, with what each saves and when it expires. Summarize the rest as a count.
