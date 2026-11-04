User story: Place a brokerage trade
As a brokerage customer,
I want to buy or sell a security using a clear trading ticket,
so that I can review my order before submitting it and receive confirmation that it was received.
Business requirements
- Provide separate, clearly labeled Buy and Sell actions. The customer should not have to interpret a generic “Trade” action.
- Support market and limit orders.
- Display the relevant security and pricing information, including the last price, bid, and ask.
- Allow the customer to enter the order quantity and view the estimated order cost.
- For a limit order, allow the customer to enter a limit price and select from the order durations and qualifiers supported for the initial release.
- Provide an order review screen where the customer can verify the details and return to edit the order before submission.
- After submission, display an order-received confirmation that includes a reference number. The confirmation must not imply that the order has executed.
- Provide a usable mobile experience, including when the on-screen keyboard is present.
Acceptance criteria
1. Select an action
- Given a customer opens the trading ticket,
  When they choose an action,
  Then they can clearly identify whether they are buying or selling.
2. Enter a market order
- Given a customer selects a market order,
  When they enter the order details,
  Then the ticket displays the quantity, relevant pricing information, and estimated cost.
- The ticket does not present extended-hours choices. The group discussed market orders as day orders only.
3. Enter a limit order
- Given a customer selects a limit order,
  When they enter the order details,
  Then they can enter a limit price and select the applicable supported duration and qualifiers.
- The available choices and their rules must be confirmed against the Pershing API and the agreed initial-release scope.
4. Review and edit
- Given a customer has entered an order,
  When they proceed to review,
  Then they see the security, Buy or Sell action, order type, quantity, applicable limit price and duration, and estimated cost.
- The customer can return to edit the order before submitting it.
5. Receive confirmation
- Given a customer submits an order,
  When the order is received,
  Then the confirmation displays an order reference number that can be used to distinguish it from other orders.
- The confirmation states that the order was received, without representing it as executed.
Open decisions and dependencies
1. Pershing API: Confirm the available order durations and qualifiers, and which combinations apply to market and limit orders.
2. Good-till-date: Decide whether to include it in the initial release. Ben noted it would require a date field and validation for an acceptable business day.
3. Quantity entry: The mockup discussion referenced shares and dollar amounts, but the call did not establish the supported combinations. Confirm scope and API support before finalizing acceptance criteria.
4. Order management: Document order status, filtering, and transaction history separately or link them to this story. The customer needs a way to check execution status after submission.