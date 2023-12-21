---
title: 'Book Summary & Reflection - The Anatomy of the Swipe: Making Money Move'
date: 2023-12-20
permalink: /posts/2023/12/20/book-summary-swipe/
tags:
header:
    teaser: false
---

Ever since I got my first credit card, I have been interested in better understanding how card payments work. There are ~276 million card transactions handled everyday [1]. How are these transactions handled? What is the busienss model of the incumbent businesses? What are the major pain points of the current payments system? How would you create a new credit card offering?

A fellow engineer at Capital One recommended I read "The Anatomy of the Swipe: Making Money Move" by Ahmed Siddiqui to better understand the payments industry. Here, I'll summarize my key learnings and reflect on what it means for technologists in finance.

## Overview

There are four parts required to facilitate a card payment:
* A card (physical, virtual, token)
* Merchant
* Payment Network
* Secure internet connection to transmit messages.

When a customer goes to pay at a merchant, a request to approve the transaction is sent in this basic (but not exhaustive) flow: Merchant -> Merchant Acquirer -> Acquirer Processor -> Card Network -> Issuer Processor -> Issuer. 

Definition of Key Players:
* Merchant - business selling the good or service. If they’re physical, they need a machine to read the card. If they’re virtual, they need a payment gateway. Examples of Merchants: Walmart, Costco, and Amazon.
* Merchant Acquirer - Partners with Merchants and provides them the tools and facilities to accept and process card-based payments. Examples of Merchant Acquirer: Chase Paymentech and Global Payments.
* Acquirer Processor - Merchant acquirer’s technology partner to connect with payment network. Usually, acquirer processor will have the hardware to connect to the payment network to request approval of transaction. Examples of Acquirer Processors: Redsys, Monext, Elavon
    - Some merchant aquirers have built this in-house or may rely on a third-party.
* Payment Network (aka Card Scheme) - Provide infrastructure for card-based transactions. Sit between Acquirers and Issuers and pass messages back and forth to enable transaction. Payment networks also set the communication rules and standards. Example of Payment Network: Visa, Mastercard, American Express, Discover
* Issuer Processor - Issuer’s technology parter to connect to the payment networks. This technology provider will usually have hardware in their data center and a fast network connection to the payment network to approve or decline transactions. Example of Issuer Processors: TSYS, Galileo, i2c.
    - Some Issuer's have built this in-house or may rely on a third-party.
    - Note: Capital One has partnered with TSYS to help process their credit cards. 
* Issuer - an Issuer or Issuing Bank’s purpose is to underwrite the user by granting them access to a bank account and potentially access to credit facilities. Ex: JPMorgan Chase, Capital One, Citi, and Wells Fargo.
The issuer will then decide to whether to approve or deny the transaction. If approved, the issuer will place a hold on the funds. Later, at the end of the day, clearing happens and money is moved between customer and merchant. The Merchant will confirm transactions and also include tips, transaction reversals, and refunds. 

## Payment Ecosystem
There are two types of card networks:
* Open Networks (Visa, Mastercard) - There are multiple Merchant Acquirers and Issuers. Card network makes money through fees. 
    - Pros: Good for distribution. Get brand into as many consumers and merchants as possible.
    - Cons: Complex
* Closed Networks (American Express, Discover) - Take their own interchange, Acquirer, and Network Assesment fees. Can adjust fee based on Merchant size. Revenue per swipe is higher. However, total swipe volume is lower since they don’t have tthe network. Visa accounts for ~50% of all purchase volume. American Express accounts for 13% and Discover for 2%.

- For debit cards, each Card Network has a secondary network brand for Pin Debit or Automated Teller Machine (ATM).
    - PIN Debit Network. Visa - Interlink, Visa-Net Debit. Mastercard - Maestro. Discover - Pulse
    - Durbin Amendment - every debit card must have a secondary unaffiliated network.
- ATM Networks. ATM charges user a fee. Issuer of card is charged an Interchange fee by the ATM.
    - ATM Networks - Visa - Plus. Mastercard - Cirrus. Discover - Pulse.
    - "Free" ATM networks - MoneyPass and Allpoint. Only charges the issuing bank. No cost directly charged to customer.

Flow of Payments within the Payment Ecosystem

|                           | Merchant  | Acquiring Bank    | Card Network  | Issuing Bank  | Customer  |
| ---                       | :---:     | :---:             | :---:         | :---:         | :---:     |
| Payment                   | +         |                   |               |               | -         |
| Acquirer Fee              | -         | +                 |               |               |           |
| Network Assessment Fee    | -         |                   | +             |               |           | 
| Interchange               | -         |                   |               | +             |           | 
| Rewards                   |           |                   |               | -             | +         |

Note: "Rewards" was added by me. What I find fascinating about this diagram is that every player in the ecosystem is incentivized to participate (i.e. every player has a "+"). I wonder - what are the costs of such a payment ecosystem?

## Authorizations
- Authorization - happens at moment of swipe, dip, or tap at payment terminal. Action places hold of funds on the cardholder’s account or may decline transaction.
- Credit cards are often Dual-message Signature transaction - Authorization (message one) happens at the time of swipe. Followed up by Clearing (message two) happens in bulk at end of the night. Sometimes, Clearing message is different from Authorization if tip is included.

## Clearing

- Clearing - The term “Clearing" used primarily by Issuers. Also called “Capture” by Merchant Acquirers. Clearing happens at the end of the day. Merchant will include tips, transaction reversals, and returns. Merchant confirms transactions are valid and funds are ready to be settled.
- Settlement - actual movement of money from cardholder’s bank account (Issuing Bank) to the Merchant’s bank account (Acquiring Bank). Typically happens via Fedwire.
- Card Network does not send the full amount. Card Network will
    - keep a percentage for itself as the Network Assessment Fee
    - take a percentage and pass it on to the card Issuer as the Interchange Fee
- Merchant Acquirer charges merchant an Acquirer fee too. This is charged at the end of the month.

## Chargeback

- Chargeback - when a cardholder doesn’t recognize a charge on a card, they may request their money back through the Issuing Bank. Chargebacks may used when goods and services have not been provided by the Merchant, but the Merchant refuses a refund.
    - Chargeback cost merchants $25-35 per transaction. Often, merchants will eat the cost of low-value transactions.
- Merchants are encouraged to keep their chargeback rate below 1%. Otherwise, Card Network may remove the merchant.

To help fight fraud and reduce the number of chargebacks, there are a number of technologies in play:
- EMV Chip Card - Originally stood for “Europay, Mastercard, Visa” which established the technical standard of encoding card data onto a secure chip on a card. These cards are “dipped” into card terminals. Secured far more secure then data stored on a magnetic strip.
    - Merchants that have implemented this standard are not liable for fraud. The issuing bank must eat the cost of fraud here.
- 3D Secure - Standard for offering cardholders more security in online transactions. Involves the use of a one-time PIN or passcode.

## Banks

- Banks have 3 purposes - Issue cards. Serve as Acquiring Banks to merchants. Facilitate movement of real money.
    - Only banks can issue credit cards. If you would like to issue a card and you are not a bank, then you must partner with a bank.
- New challenger banks are disrupting the field. They partner with small banks not subject to Durbin Amendment and its limits on interchange. Neo-banks make money off deposits and debit card interchange.
    - Note: Mobile has enabled these neo-banks to proliferate. Many consumers no longer care about the proximity of a physical bank branch when they can access the bank's app in their pocket. Neobanks compete with traditional banks with various features such as 2-day early payday, better underwriting models for underbanked groups (ex: Karat credit card for content creators), and interest-free secured credit cards.

## Taking Payments

- Independent Sales Organization (ISO) - ISO is granted a license to sell Merchant acquiring services from a Merchant Acquirer
- Payment Facilitator (PF or PayFac) - Layer on top of a Merchant Acquirer. Payment facilitators can onboard very quickly and offer out-of-the-box hardware and software to enable a merchant to take payment.
    - Advantages: Fast setup. Fixed pricing. Managed Fraud.
    - Drawback: Being a sub-merchant. Fixed pricing can be expensive.
- How do payment facilitators make money? Revenue from Software or Hardware. Revenue from each transaction. Pay Merchant Acquirer the Acquirer fee. Pay card Issuer’s interchange. Pay Network network assessment fees. PF can aggregate transactions and negotiate low Acquirer fees.
- Using a Merchant Acquirer
    - Advantages: Being a Direct Merchant. Hardware and Software options. Interchange Plus Pricing. Can use flat fee or Interchange Plus. Faster Funds settlement.
    - Disadvantages: More paperwork. Mange fraud directly.
- How do Merchant Acquirers make money? Revenue from Hardware. Revenue from each transaction.
- Payment Service Provider - Aggregator of payment methods. Allows website to get paid via debit card, mobile wallets, and financing schemes such as Buy Now, Pay Later.

## Making Payments

- Co-Brand Partner - typically a brand or company marketing the card.
- Program Manager - manages the day-to-day operations of the card program including settlement, fraud management, and maintaining the relationship of the Issuing Bank, card manufacturer, card network, and cardholder.
    - Makes money by getting portion of interchange
- Issuer Processor - connection between card and network. Needs to parse an ISO8583 message (standard card transmission) and respond in 3 seconds. Licenses a piece of hardware from the Network commonly referred to as a Mastercard Interface Processor (MIP) for Mastercard and a VisaNet Integrated Processing (VIP) for Visa.
    - Also responsible for integration with co-brand. May provide alerts or ability to turn on/off card. Issuer Processors provides APIs and documentation.
    - Makes money as a utility based on number of cards or on each transaction.
- JIT Funding - Forward details from card swipe for approval.
- Issuing Bank - works with Program manager to provide the settlement and bank accounts
    - Makes money by possibly charging Program Manager fees for setting up bank accounts, performing compliance audits, and general oversight. Issuing Bank also sponsors BIN. Card networks only give BIN to banks.

## Know Your Customer (KYC)

- KYC - Practice in banking or finance used to attach identity to a user of a product
- For a better user experience, you should progressively ask for more and more information from the customer on a need-to-know basis. This step is critical especially for underbanked customers.

## Credit vs Debit Card

- 23% of millennials don’t carry credit cards (TD Bank’s Annual Consumer Spending Survey)
    - Prefer credit cards for simplicity of seeing spending balance
    - Note: I believe there's an opportunity here to help millenials / generation Z better to better understand and feel secure with their money. The increased costs of higher education (and their associated student loans), increased cost of living, and skepticism towards social safety nets such as Social Security are contributing factors to feeling anxious about one's personal finance.
- Some industries such as travel prefer credit cards because funds are guaranteed by the Issuing Bank

## Interchange

- Durbin Amendment - Banks with assets greater than \\$10 billion are regulated for Interchange fees. Regulated Issuers get \\$0.21 + 0.05% of the transaction amount + \\$0.01 for fraud.
- Merchants who clear faster qualify for lower Interchange rates.
- Track 3 data - Some merchants provide receipt level details (Track 3 Data) to card networks. When this data is provided, lower interchange is charged.

Other solutions for merchants to lower interchange fees:

- Private label cards - Some merchants offer their own cards to use at the store. These cards only work at the store that issued the card. Benefits include direct access to customer spending data, reserves spot in customer wallet, no interchange paid to issuer, little or no fees paid to acquirer, brand loyalty.
- Co-Brand Cards - Brand partners with an issuing bank and card network. For example, Amazon partnered with Chase and Visa to create an Amazon credit card. Since Amazon arranges this deal, they will typically get lower network assessment fees with the network and lower interchange with the issuing bank. The brand and issuing bank can also earn interchange on transactions outside of brand.

## Moving Money without Card Networks

- ACH
    - Over 82% of electronic payments in the US are ACH (Automated Clearing House)
    - ACH is a technology offered by the “Clearing House,” which is a nonprofit organization. This is a network of banks that have come together to enable movement of money interbank through the use of bank account and routing number. This is a batch process.
    - Efficient and inexpensive. However, it’s not the fastest. Since it’s a batch process, there are “cutoff windows”
    - Direct Deposit - type of ACH transfer that typically comes from an employer into an employee’s bank account. Employers would give Fed NACHA file to transfer the funds. This NACHA file is often sent earlier but funds are only moved on effective date. However, some banks are willing to loan money for 2 days once they see the NACHA file from the employer.
    - NACHA is pushing for faster payments by offering Same-Day ACH
- Peer-to-Peer and ACH
    - Venmo - Debits the sender but needs to float funds for a couple days.
    - Zelle - Groups of banks share a ledger. Money moves quickly and does not wait for “settlement”.
- Wire Transfer
    - Way to move money (usually large dollar amounts) from one bank to another securely and quickly by using account and routing numbers of the sending and recieving banks.
    - In the US, the Federal reserve provides Fedwire which is the primary way to wire funds between banks. This is the supported by almost every bank. The Clearing House also provides a wire service called Clearing House Interbank Payments System (CHIPS).
    - Movement of money is instant. However, humans need to confirm that money has moved.
- Real-time Payments
    - Wire transfers are used for large transfer, but can also be applied to smaller payments. Main barrier is that cost of wire is high because humans need to confirm money movement.
    - Real-Time Payments (RTP) - way to push money within seconds by sending money directly to a bank account offered by The Clearing House.
    - Cost is capped to $0.045 per transfer

## How do you create a credit card? 
As an engineer working within the Card division at Capital One, I have thorougly enjoyed learning about the various parts of the payment ecosystem. I don't know a lot about payements yet, but I am learning more everyday. 

One observation that I've had is that most of the innovation happens on either end of the swipe — closest to the merchant or customer. The underlying core infrastructure often remains stagnant on old technology (however, this is changing too. re: peer-to-peer payments, decentralized ledgers, blockchain). At Capital One, the company is focused on the customer side of payments. One driving question I've been asking myself is, "What valuable niches exist in the market and how can Capital One design a credit card for that niche?" 

There are many ways to spot niches in the market. You can divide the market up into new to credit, mainstreet, premium, and ultra-premium. You can look at consumer vs. business cardholders. Or, you can also look at the payment market from the merchant side too and examine co-brand opportunities. 

Once you have identified the niche, you need to create a monetized product to cater to those consumers. At Capital One, there are two main sources for revenue in credit cards: credit card interest (16.6 billion USD in 2022) and interchange fees (4.6 billion USD in 2022) [2]. The credit card must offer the consumers compelling benefits in order to 1) use the credit card (interchange fees) and 2) revolve and eventually pay off a credit card balance (net interest income). 

Now, you need to create the credit card. This involves designing the credit card benefits, advertising the card, handling customer applications, underwriting each application, obtaining capital to loan, and servicing the card. Fortunately, Capital One (and other credit card companies) are platform companies and they have already built a lot of the tools in-house. They benefit from economies of scale. They have low-cost to access capital through their own customer deposits. They have advertising partnerships with top athletes. They have pre-existing web, mobile, and physical channels for applying and servicing a card. Lastly, they are a brand to whom you would search for other financial products such as another credit card, a high-yield checking/savings account, or a car loan. 

Similar to how AWS has become the platform to power the web, Capital One needs to become the platform for consumer financial products. As software engineers, software will play a critical role in 1) automate processes such as application, issuing virutal cards, underwriting each application, analyzing fraud risk, and marketing new cards and 2) analyzing large amounts of data to better underwrite and create additional financial products. 

Sources:

[1] The Federal Reserve Payments Study: 2022 Triennial Initial Data Release. [https://www.federalreserve.gov/paymentsystems/fr-payments-study.htm](https://www.federalreserve.gov/paymentsystems/fr-payments-study.htm)

[2] 2022 Capital One Annual Report. [https://www.capitalone.com/investor/financials/annual-report/](https://www.capitalone.com/investor/financials/annual-report/)