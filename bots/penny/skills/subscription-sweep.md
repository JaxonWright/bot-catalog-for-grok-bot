# Subscription sweep

Use this when running a subscription check-up: find every recurring charge, flag likely cancellations, and report them in a table with cancel links.

Load the Cursor-managed `subscription-management` skill alongside this one. Its rules win wherever the two differ, especially for cancelling, refunds, price checks, and trials.

## 1. Gather
- **Bank and cards:** from the Finance connector (read-only), pull about 13 months of transactions from every cash and credit-card account. Find merchants that repeat on a weekly, monthly, quarterly, or annual cadence. Leave out transfers, card payments, payroll, and one-off purchases. List utilities, phone/internet, and insurance separately.
- **Email:** search the user's email read-only for receipts, renewals, "your plan", trials, price changes, and cancellation confirmations. Use the Gmail or Outlook connector, or, for other providers, a read-only search in the browser.
- **Statements:** read any bank or card statements (PDF or CSV) the user drops in chat.
- **Hidden names:** a charge often shows a payment processor's or parent company's name instead of the service, or comes through an app store or payment service like Google Play, Apple, or PayPal. Match those charges to receipt emails. When the user names a service or an amount, search the transactions for that exact amount before saying a charge isn't there.
- **One row per charge:** a receipt and its card transaction are one row with both sources. Two transactions or two receipts with different order numbers are two rows, even for the same amount on the same day. Leave out a row its source doesn't show in full.
- **Never invent a charge.** Every row must tie to a real transaction, email, or statement line. Leave newsletters and mailing lists out; this is paid subscriptions only.

## 2. Ledger
Keep a CSV ledger with these columns: service, amount, cycle, monthly_equiv, next_renewal, last_seen_usage, price_change, public_price, status, cancel_url, source. Update it every sweep so you can say what changed since last time.

## 3. Sort by how likely the user is to cancel
Decide the reasons yourself from the data:
- **Duplicate:** the same service billing twice for the same period (two accounts, emails, or cards). Put these first, with the charges that show it, and offer a refund for the extra charge.
- **Overlap:** only when a plan page opened read-only shows one plan already includes the other (a family plan covering the user's own plan, a bundle). Similar names aren't an overlap.
- **Likely cancel:** weekly billing that costs much more than monthly, recent price increases, trials that just turned paid, or two services doing the same job.
- **Worth a look:** expensive, annual renewals due in the next 60 days, or a cheaper bundle is available.
- **Probably keep:** essential, cheap, or clearly in use.
- Quiet email alone isn't proof something is unused; say "no recent activity seen" rather than "unused."

## 4. Report
- Start with the total monthly spend, plus a one-line note on what changed since the last sweep.
- Then one markdown table per group, with columns Service | Cost | Cycle | Next charge | Why | Cancel. In the Cancel column, link to the company's official cancel page or help article, and only use URLs you verified come from that company.
- Add a short list of annual renewals coming up in the next 60 days, and offer a renewal price check for each (section 6).
- Then offer to cancel any of them on the user's behalf with a multi-select question. A pick there is not the cancel yes; each cancellation still gets its own confirmations.
- If nothing is worth flagging, send just a one-line total.

## 5. Cancelling (only services the user names)
Follow `subscription-management` "Read or cancel a named subscription", one service at a time:
- Read the billing page first (plan, price, next charge, whether access lasts until then) and screenshot it.
- Ask one question card naming the service, plan, price, and date before opening the cancel page.
- At a retention offer (discount, pause, free time, downgrade), stop and ask on its own card with the renewal price and end date. Recommend declining unless the user said otherwise. Never take an offer without their answer.
- At the final confirm page, stop and ask on its own card naming the service, plan, and the date access ends. Click confirm only after that yes.
- Call it cancelled only when a confirmation page or email says so and names the end date. Send the screenshot, update the ledger, and save the service, plan, end date, and link to memory. If it says pending or processing, use those words.
- Use the secure in-chat form for logins. If the site clears what the form filled, hand the screen to the user so they can sign in.
- If a site's own cancel flow fails, give the support email or the phone number with hours and menu path. Show any message to a company before it goes out. A card-issuer merchant block is a last resort.
- If a cancellation can only happen in a phone app, give the exact steps instead.
- Never move money, and never sign up for anything or accept offers unless the user asks for a specific trial (section 7).

## 6. Renewal price checks
For an annual or other big renewal coming up, follow `subscription-management` "Watch a renewal price": read the price the user pays, the next charge date, and the current public price of the same plan, with screenshots. Say if they pay more than the public price or more than last time. Offer a routine two days before the renewal that messages only if the price or date changed.

## 7. Refunds and trials
- **Refunds** (a duplicate charge, or a renewal they forgot to cancel): follow `subscription-management` "Ask for a refund". Read the service's refund policy and ways to ask, let the user pick one, and draft any email or form for their OK before it goes out. A refund doesn't cancel the plan.
- **Free trials** the user asks to try: follow `subscription-management` "Try it, don't pay for it". Read the terms, get a yes on the renewal price and end date, then cancel while access lasts or set a reminder two days before it bills.
