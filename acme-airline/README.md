# ACME Airline

## Case Study

ACME Airline is a regional airline that has been around for some time and grown rapidly over that past few years. Most of the business that ACME receives is by way of its business partners such as travel agents and websites sell cheap air tickets. This rapid expansion as affect ACME's ability to provide optimal services to its customers and partners. Due to this, ACME has started to see a rapid decline in sales over the past couple of years.

After a survey insights into the decline in business hinted to a number of reason listed below.

- Unhappy partners claimed
  - They had no visibility into commission payments.
  - Information was stale and don't have up to date information on flight schedules and changes. This made it had for them to sell tickets to customers.
  - ACME's systems were outdated and antiquated.
- Customers complained about
  - Unexpected flight delays and cancelations.
  - Reservation can sometimes get lost.
  - Poor customer service as staff have a hard time retrieving information.

As an architect you should look for a technology that can provided a "A seamless Collaboration Platform with no boundaries". This is where Blockchain comes in, more specifically this Hyperledger Fabric for creating a `Business Network` that should enable efficient `B2B collaboration` leading to `better client and customer experience`.

### What can Hyperledger do

- The network will consist of 3 layers
  - The underlying fabric layer which houses the blockchain and ultimately manages the communication and structure between the businesses and internally to ACME as data is needed both internally and externally.
    - This chain keeps track of `States` (mutable as transactions occur) and `Transactions` (immutable).
    - This layer defines where data is stored and who can act on it. (e.g. Who can initiate a transaction and who can verify it before sending to be finalized over the network? Who creates the block and who verifies that the block is 100% correct? )
    - This layer definition also keeps track of security elements.
  - The Business Application layer [`This repository!`]
    - How are data/models defined and how should those be handled
  - The application layer
    - How do we expose that data in a user friendly manner (via web apps and endpoints) that users or developers can build on to create efficient,  reliable aesthetically pleasing interfaces between participants?
