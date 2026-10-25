# Subscription sweep

Use this when running a subscription check-up: find every recurring charge, flag likely cancellations, and report them in a table with cancel links.

## 1. Gather
- **Bank and cards:** from the Finance connector (read-only), pull about 13 months of transactions from every cash and credit-card account. Find merchants that repeat on a weekly, monthly, quarterly, or annual cadence. Leave out transfers, card payments, payroll, and one-off purchases. List utilities, phone/internet, and insurance separately.
- **Email:** search the user's email read-only for receipts, renewals, "your plan", trials, price changes, and cancellation confirmations. Use the Gmail or Outlook connector, or, for other providers, a read-only search in the browser.
- **Statements:** read any bank or card statements (PDF or CSV) the user drops in chat.
- **Hidden names:** a charge often shows a payment processor's or parent company's name instead of the service, or comes through an app store or payment service like Google Play, Apple, or PayPal. Match those charges to receipt emails. When the user names a service or an amount, search the transactions for that exact amount before saying a charge isn't there.
- **Never invent a charge.** Every row must tie to a real transaction, email, or statement line.

## 2. Ledger
Keep a CSV ledger with these columns: service, amount, cycle, monthly_equiv, next_renewal, last_seen_usage, price_change, status, cancel_url, source. Update it every sweep so you can say what changed since last time.

## 3. Sort by how likely the user is to cancel
Decide the reasons yourself from the data:
- **Likely cancel:** duplicates or overlaps (two AI assistants, two music or cloud storage services, overlapping streaming), weekly billing that costs much more than monthly, recent price increases, trials that just turned paid, or nothing used lately.
- **Worth a look:** expensive or rarely used, annual renewals due in the next 60 days, or a cheaper bundle is available.
- **Probably keep:** essential, cheap, or clearly in use.

## 4. Report
- Start with the total monthly spend, plus a one-line note on what changed since the last sweep.
- Then one markdown table per group, with columns Service | Cost | Cycle | Next charge | Why | Cancel. In the Cancel column, link to the company's official cancel page or help article, and only use URLs you verified come from that company.
- Add a short list of annual renewals coming up in the next 60 days.
- Then offer to cancel any of them on the user's behalf with a multi-select question.
- If nothing is worth flagging, send just a one-line total.

## 5. Cancelling (only services the user names)
- Cancel only services the user approves by name in chat, and do exactly what they approved.
- Decline retention offers, pauses, discounts, and downgrades unless the user says otherwise.
- Use the secure in-chat form for logins. If the site clears what the form filled, hand the screen to the user so they can sign in.
- Screenshot the final confirmation and send it to the user. Then check the email for the confirmation message and update the ledger.
- If a site's own cancel flow fails, offer the user a support email or a phone number. Show any message to a company before it goes out, and if you can't send from that inbox, give the user the text to copy. A card-issuer merchant block is a last resort.
- If a cancellation can only happen in a phone app, give the exact steps instead.
- Never move money, never sign up for anything, and never accept offers.
