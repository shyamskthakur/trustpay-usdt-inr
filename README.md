# TrustPay Wallet

Build a professional, premium-looking Android-first mobile application called TrustPay for USDT to INR exchange.

The app should feel like a modern fintech/crypto application: trustworthy, elegant, minimal, fast, secure, and highly polished. Use a premium visual identity rather than a generic crypto-dashboard design.

1. Brand Identity

App name: TrustPay

Create a professional original logo for TrustPay.

Logo direction:

Premium fintech + crypto aesthetic

Clean geometric symbol

Incorporate a subtle trust/security/payment concept

Avoid copying Trust Wallet, Binance, Coinbase, or any existing brand

Logo should work on both light and dark backgrounds

Create an app icon version

Use the logo consistently throughout the application

Suggested visual style:

Dark premium interface with strong contrast

Clean white typography

Subtle gradients and glass/card effects

Elegant green/teal accent color associated with successful transactions and finance

Rounded cards

Soft shadows

Smooth animations

Large readable numbers

Professional fintech-style icons

The UI must look like a real production fintech application, not a basic prototype.

2. Authentication / First Launch

When the user opens the app for the first time, show a premium welcome screen.

Primary CTA:
Create New Wallet

Secondary CTA:
I Already Have a Wallet

For a newly created account, generate a random 12-word recovery phrase.

Important:

Treat the phrase as a recovery credential, not as an ordinary password.

Never display the phrase unnecessarily.

Never expose it in logs.

Provide a secure backup/confirmation flow.

Ask the user to confirm selected words from the recovery phrase before completing setup.

Add a warning explaining that anyone with the recovery phrase can potentially access the account.

The recovery phrase should not be transmitted to the frontend/backend unnecessarily.

Provide biometric/app-lock protection where possible.

For existing users:
Restore Wallet
→ Enter 12-word recovery phrase
→ Validate phrase
→ Open account dashboard

Also provide:

Forgot/need help screen

Security information

Privacy policy

Terms & conditions

3. Home Dashboard

Create a premium dashboard containing:

Header:

TrustPay logo

User/account identifier

Notification icon

Security/profile icon

Main balance card:
Available USDT
Example:
1,250.00 USDT

Below it display the INR equivalent.

Exchange rate:
1 USDT = ₹107 INR

Main actions:

Deposit USDT

Withdraw INR

Transaction History

Add a conversion calculator:

USDT Amount
→ INR Amount

Example:
500 USDT
× ₹107
= ₹53,500

Use real-time frontend calculations based on the configured exchange rate.

4. Deposit USDT

Create a dedicated Deposit USDT page.

Display:

Minimum Deposit
500 USDT

Show a network-selection interface with these five options:

BNB Smart Chain

TRON

Arbitrum

Bitcoin

Solana

Each network should have:

Network name

Network icon

Address

Copy button

QR code

Warning about sending on the correct network

Deposit status

I will later provide the corresponding wallet address and QR code for each network.

Therefore, structure the application so wallet configuration can easily be entered/updated from a secure admin configuration area rather than hard-coded into multiple screens.

Example structure:

BNB Smart Chain
Wallet Address:
[ADMIN-CONFIGURED ADDRESS]

[QR CODE]

[Copy Address]

Repeat this structure for:
TRON
Arbitrum
Bitcoin
Solana

Add a prominent warning:

Only send USDT using the selected network. Sending assets through the wrong network may result in loss of funds.

Deposit flow:

Select Network
→ View Wallet Address / QR
→ User Sends USDT
→ User enters Transaction Hash
→ Deposit submitted
→ Pending verification
→ Approved / Rejected
→ Balance updated

Do not automatically mark a deposit as successful merely because the user entered a transaction hash. The transaction should have a verification/status workflow.

5. Minimum Deposit

The minimum deposit amount is:

500 USDT

If the user enters less than 500 USDT:

Show an inline validation message

Disable the submit button

Clearly display the minimum amount

Example:
Minimum deposit is 500 USDT.

6. USDT → INR Conversion

Configured exchange rate:

1 USDT = ₹107 INR

Example calculations:

500 USDT = ₹53,500
1,000 USDT = ₹107,000
2,000 USDT = ₹214,000

Create an attractive exchange calculator with:

USDT input

INR output

Exchange rate display

Fee section if fees are later configured

Final receivable amount

Continue button

Keep the exchange rate configurable from the admin panel instead of hard-coding it throughout the app.

7. Withdrawal / INR Payout

Create a Withdraw INR page.

Allow users to select:

UPI

Fields:

UPI ID

Account holder name

Amount

IMPS

Fields:

Account holder name

Bank account number

IFSC code

Bank name

Amount

Before submission show a confirmation screen:

Withdrawal Amount
₹XX,XXX

USDT Used
XXX USDT

Exchange Rate
₹107 / USDT

Final INR Amount
₹XX,XXX

Then:
Confirm Withdrawal

8. Withdrawal Status

After withdrawal submission, create a professional order-tracking screen.

Order statuses:

Submitted
→ Verification
→ Processing
→ Payment Sent
→ Completed

Also support:

Failed

Rejected

Cancelled

Additional verification required

Display the order ID prominently.

Example:

Order #TP-000123

Status:
Processing

Estimated processing target:
Approximately 15 minutes

Do not represent the 15-minute processing target as an unconditional guarantee. Clearly communicate that processing may depend on verification, banking/payment rails, network conditions, or other operational factors.

9. Transaction History

Create a complete transaction history page.

Each transaction card should show:

Order ID

Date/time

Transaction type

USDT amount

INR amount

Network/payment method

Status

Filters:

All

Deposits

Withdrawals

Completed

Pending

Failed

Clicking a transaction opens a detailed transaction page.

10. Order Details

Detailed order page should show:

Order ID
Date
Time
Transaction type
USDT amount
Exchange rate
INR amount
Network/payment method
Blockchain transaction hash where applicable
Processing status
Timeline

For blockchain deposits, provide a button:

View Transaction

This should open the appropriate blockchain explorer only after the correct explorer URL is configured.

11. Notifications

Create an in-app notification center for:

Deposit submitted

Deposit verified

Deposit rejected

Withdrawal submitted

Withdrawal processing

Withdrawal completed

Withdrawal failed

Security alerts

Account/login events

Use professional notification cards with appropriate icons and timestamps.

12. Profile & Security

Create a premium profile/security page containing:

Account identifier

Recovery phrase management

Biometric lock

Change app PIN

Active sessions

Security alerts

Terms & Conditions

Privacy Policy

Support

Never show the recovery phrase immediately on the profile page. Require strong re-authentication before displaying any sensitive recovery information.

13. Support

Create an in-app support center with:

FAQ

Deposit help

Withdrawal help

Transaction issue

Contact support

Order-specific support

Allow users to select an order when contacting support.

Example:

Need help with Order #TP-000123?

14. Admin Dashboard

Build a secure admin interface for TrustPay.

Admin should be able to manage:

Exchange Rate

Current:
₹107 / USDT

Allow admin to change this value.

Minimum Deposit

Current:
500 USDT

Allow admin to change this value.

Wallet Networks

Manage:

BNB Smart Chain wallet address

BNB Smart Chain QR code

TRON wallet address

TRON QR code

Arbitrum wallet address

Arbitrum QR code

Bitcoin wallet address

Bitcoin QR code

Solana wallet address

Solana QR code

Orders

Admin can view:

Pending deposits

Verified deposits

Pending withdrawals

Completed withdrawals

Failed orders

Rejected orders

Admin can update order statuses according to the configured verification/payment workflow.

Users

Admin can view:

User/account identifier

Registration date

Account status

Transaction history

Verification state

Do not expose users' recovery phrases to administrators.

15. Database Structure

Create a clean backend schema with appropriate relationships.

Suggested tables/collections:

users

id

created_at

status

security_settings

wallet_networks

id

network_name

asset

wallet_address

qr_code

active

exchange_settings

exchange_rate

minimum_deposit

updated_at

deposits

id

user_id

network

amount

transaction_hash

status

created_at

verified_at

withdrawals

id

user_id

method

amount_usdt

amount_inr

exchange_rate

payout_details

status

created_at

completed_at

transactions

id

user_id

type

amount

status

reference_id

created_at

notifications

id

user_id

title

message

read

created_at

16. Security

Security should be treated as a first-class requirement.

Implement:

Secure authentication/session handling

Biometric/app PIN protection where supported

Server-side validation

Input validation

Rate limiting

Secure handling of transaction hashes

Audit logging for admin actions

No sensitive data in frontend logs

No recovery phrase in analytics/logging

Role-based admin permissions

Secure environment variables for backend secrets

Do not store private keys or users' recovery phrases in plaintext on the server.

17. UX Requirements

The entire app should feel extremely polished.

Use:

Smooth page transitions

Skeleton loaders

Empty states

Confirmation dialogs

Toast notifications

Haptic feedback where supported

Form validation

Loading states

Error states

Success animations

Professional transaction timelines

Design for one-handed Android usage.

Primary navigation:
Home | Deposit | Withdraw | History | Profile

Use modern typography and consistent spacing.

Avoid:

Cheap-looking gradients

Excessive neon crypto styling

Cluttered dashboards

Generic Bootstrap-style layouts

Fake cryptocurrency price charts

Unnecessary animations

18. Error Handling

Include polished error messages for cases such as:

Incorrect recovery phrase
Invalid amount
Below minimum deposit
Invalid wallet address
Wrong network selected
Invalid transaction hash
Duplicate transaction hash
Withdrawal information incomplete
Withdrawal unavailable
Session expired
Server error
Network unavailable

Messages should explain the issue clearly and provide the next action.

19. Important Configuration

Create a centralized configuration system so these values are easy to update:

EXCHANGE_RATE = 107 INR per USDT

MIN_DEPOSIT = 500 USDT

PROCESSING_TARGET = approximately 15 minutes

NETWORKS:

BNB Smart Chain

TRON

Arbitrum

Bitcoin

Solana

Wallet addresses and QR images will be supplied later.

Do not invent wallet addresses.

20. Premium Screens to Build

Create all of these screens:

Splash Screen

Welcome Screen

Create Wallet

Recovery Phrase Backup

Recovery Phrase Confirmation

Restore Wallet

PIN/Biometric Setup

Login/Unlock

Home Dashboard

Deposit Network Selection

Deposit Wallet Address

Deposit QR Screen

Deposit Confirmation

Deposit Status

USDT → INR Calculator

Withdraw INR

UPI Withdrawal

IMPS Withdrawal

Withdrawal Confirmation

Withdrawal Processing

Order Complete

Transaction History

Transaction Details

Notifications

Profile

Security

Support

FAQ

Admin Login

Admin Dashboard

Admin Orders

Admin Users

Admin Wallet Networks

Admin Exchange Settings

21. Final Quality Requirement

Generate the application as a cohesive premium fintech product called TrustPay.

The first impression should resemble a high-end financial application.

Focus heavily on:
trust + security + simplicity + premium UI + clear transaction status + excellent mobile UX.

Use realistic sample data only for UI previews and clearly distinguish test/demo data from real transaction data.

Build the application architecture so real blockchain transaction verification, authentication, payment processing, notifications, and production wallet configuration can be connected securely later rather than pretending those systems are already functional.

This project was built with [Lovable](https://lovable.dev).

**Live app**: https://trustpay-usdt-inr.lovable.app

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/732e506b-de1e-4f1e-b0dc-3c28afecc502).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
