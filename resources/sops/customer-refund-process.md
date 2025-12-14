# Customer Refund Process SOP

## Purpose
This document outlines the standard operating procedure for handling customer refund requests through Stripe.

---

## Scope
Applies to all team members authorized to process refunds for customer payments.

---

## Prerequisites
- Access to Stripe Dashboard or API
- Access to customer communication tools
- Understanding of refund policies

---

## Refund Process Steps

### Step 1: Receive and Log Refund Request
1. Document the customer's refund request including:
   - Customer name and email
   - Payment/Invoice ID
   - Reason for refund
   - Date of original purchase
2. Acknowledge receipt to the customer within 24 hours

### Step 2: Verify the Transaction
1. Locate the payment in Stripe using:
   - Customer email: `customers:email:"customer@example.com"`
   - Payment Intent ID: `pi_xxxxx`
   - Invoice ID: `in_xxxxx`
2. Confirm the payment status is `succeeded`
3. Verify the payment is within the refund eligibility window (typically 90-180 days)

### Step 3: Evaluate Refund Eligibility
Review the request against refund policy criteria:

| Reason | Full Refund | Partial Refund | No Refund |
|--------|-------------|----------------|-----------|
| Duplicate charge | Yes | - | - |
| Service not delivered | Yes | - | - |
| Technical issues | Yes | Possible | - |
| Customer dissatisfaction | Possible | Possible | Possible |
| Subscription cancellation | Prorated | Prorated | - |
| Fraudulent charge | Yes | - | - |
| Policy violation by customer | - | - | Yes |

### Step 4: Process the Refund
1. Navigate to the payment in Stripe Dashboard or use API
2. Select refund type:
   - **Full refund**: Refunds entire payment amount
   - **Partial refund**: Specify amount in cents (e.g., $10.00 = 1000)
3. Select refund reason:
   - `duplicate` - Duplicate charge
   - `fraudulent` - Fraudulent charge
   - `requested_by_customer` - Customer requested
4. Add internal notes documenting the decision
5. Submit the refund

### Step 5: Notify the Customer
Send confirmation email including:
- Refund amount
- Expected processing time (5-10 business days)
- Reference number
- Contact information for questions

### Step 6: Document and Close
1. Update customer record with refund details
2. Log the refund in tracking system
3. Mark the refund request as resolved

---

## Refund Timelines

| Card Network | Refund Processing Time |
|--------------|------------------------|
| Visa | 5-7 business days |
| Mastercard | 5-7 business days |
| American Express | 5-10 business days |
| Discover | 5-10 business days |

---

## Escalation Procedures
Escalate to management if:
- Refund amount exceeds $500
- Customer disputes the resolution
- Potential fraud is suspected
- Refund request is outside standard policy

---

## Important Notes
- Refunds can only be issued to the original payment method
- Stripe fees are returned for full refunds, but not for partial refunds
- Refunds may take additional time to appear on customer statements
- Always document the reason for refund decisions

---

## Related Resources
- Stripe Refund Documentation: https://stripe.com/docs/refunds
- Company Refund Policy
- Customer Service Guidelines

---

*Last Updated: December 2024*
*Document Owner: Customer Operations Team*
