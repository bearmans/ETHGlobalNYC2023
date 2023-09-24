### bSqare

bSqare is a staking application for event attendance. It is an injected plugin to luma, eventbrite, partyful etc that enables event hosters to set aside some or all tickets for people willing to "stake" for their spot at an event. 

While anecdotal, we believe that staked attendees have a significantly higher attendance rate. The higher barrier to entry also allows a host to infer a higher level of interest in their event, which can help with customer/attendee segregation.This means that event planners can more easily plan for actual attendees (preventing oversubscription) as well as ensure that their most interested attendees can be prioritized if desired.


#### Technology

To allow easy modifications and composability for our app, we use a NEAR BOS front-end. Our main contract is stored on Arbitrum and we incorporate an Aleo sub-contract which provides a ZK-verifiable hash as a "receipt" for payment either to the main contract, a desired alternative or subcontract, and also direct-pay Web2 solutions such as PayPal, Zelle, etc (credit card support is not designed for or intended).


#### Considerations

We intentionally designed this application to be easily extensible and modifiable to support as wide of use-cases as possible. While we provide a Arbitrum contract for a base-case, our interoperable reciept model ensures that our stack can be used across whichever currency, chain, or payment method a host wants to use for their event.

Our model is generally host-biased, as we require a host to provide a verification key for attendance and so assume they actually provide one. The default outcome of putting up stake gives the host access to stake after a set period (assumes non-attendance without proof of such). Attendance reciepts provide a set amount of hash-keys to "unlock" an attendee's stake (proof of attendance). This generally requires the host to do the actual work of distributing these keys to attendees and do the actual work of verifying the staked attendees are present, whichever format that might take.

We'd like to build tools to map these keys to for instance NFC tags so these can be handed out. We'd also like to add functionality to give hosts control of certain other parameters (default behaviors of the contract, etc).


#### ETHGlobalNYC 2023 Outcomes

**Unfortunately, as we were working to mentor and collaborate with other hackers at the event, we didn't have much time to build out our actual MVP. This design readme and the file structure are the sum total of our output for this hackathon. We'd like to continue work at a later date!**