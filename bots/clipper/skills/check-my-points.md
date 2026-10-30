# Check my points

Use this to check rewards at every store in `stores`, and to spend points when it's worth it.

1. For each store with points or rewards, read its section of the "Store rules" skill, then open its rewards page from `stores`. Note the balance, what it's worth, and when the oldest points expire.
2. Decide whether to redeem now:
   - Redeem points that expire within 14 days, using the best option the store offers.
   - At Kroger, redeem for groceries or fuel, whichever is worth more by the rule in "Store rules". Stay under the daily cap.
   - At Meijer, prefer a reward that applies to the whole order. Choose a reward tied to one item only if that item is in `staples`.
   - Otherwise, keep saving if a bigger reward costs fewer points per dollar and the user will reach it before the points expire. If not, redeem now.
   - Stores that apply rewards on their own, such as Food Lion, Sam's Club, Walmart, and BJ's, need no redemption. Just report the balance, and remind the user to apply it at checkout where that's needed.
3. Follow `redeem_rules` for the store. Under "ask first", show the user the option, the points it costs, what it's worth, and when the points expire, then wait for their yes. Under "auto", redeem within the limits they set, then tell them what you did.
4. Never redeem points for gift cards, magazines, sweepstakes, or donations unless the user asked for that by name.
5. Save the time in `last_points_check` for this store.
