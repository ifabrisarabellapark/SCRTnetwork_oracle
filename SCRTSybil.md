# Team Name: BalloonBox

## Project Description 
Project name: SCRTSybil

SCRTSybil is an oracle for credit score checks. The objective of SCRTSybil is to return a quantifiable, yet private and partially-encrypted credit score for SCRT network users allowing to categorize users by credibility and trustworthiness within the ecosystem. Credit checks will incentivize the activity of new, yet trusted and verified SCRT network users, while also affirming the reputation of long-standing users.
Users will need to authenticate themselves via their Ledger or Keplr wallet to access the SCRTSybil Web2 app for starting the scoring process. After completing the necessary steps their score is computed and sent to a smart contract generator which packages their score alongside some basic information that will be encrypted when being published to the network. Users then have their ‘profiles’ stored and accessible on SCRT for anyone to request their credit score by specifying their public address as an identifier/primary key which binds the user account to their score and related attributes of the score. Various key types will decrypt different pieces of information about the users depending on who the score requester is and whether the user endorses the access request.   
 
## Problem / Solution  
How can one validate the trustworthiness of blockchain users, while maintaining user privacy? Our project consists in building a SCRT oracle, called SCRTSybil, for decentralized credit scoring. We will build TLS connections from on-chain validator enclaves to APIs, creating private credit check scores for secret contracts. These APIs will aggregate a user’s credit data from web3 (wallet balance and transaction history in at least 2 cryptocurrency exchange platforms of their choice, e.g., Coinbase, Binance, etc.) with web2 data (bank account balance, credit history, recent activity, liquidity, etc. through Plaid). The credit check outcome will be quantified via a credit scoring algorithm we will design. This algorithm integrates web2 and web3 validation of a user’s financial standing. Validated private data feed, i.e., the actual credit score will be stored on-chain and can be accessed via a privately issued secret key. 

## Detailed Product Description 

SCRTSybil Oracle Model
![SCRTSybil Oracle Model](https://github.com/BalloonBox-Inc/SCRTnetwork_oracle/blob/main/images/SCRTSybil_oracle.png)

SCRTSybil Architecture
![SCRTSybil Architecture](https://github.com/BalloonBox-Inc/SCRTnetwork_analytics/blob/main/images/SCRTSybil_architecture.png)



#### Components

1. **GUI**: user logs into SCRTSybil web application through third party authenticators. Users will then log into their SCRT wallet, and also have at their disposal a profile and account balance. The front end will be built on React.js.
 
2. **Restful API**: Python (Flask) + webhook framework with public APIs that can be used. In most cases, we will use OAuth, and in all other cases, we will use a one-time-only key. This environment will manage the integration among wallet, external parties, credit score module, and the smart contract compiler.
 
3. **Credit Score Module**: credit score algorithm integrating at least these 5 weighted metrics. Metrics were adapted from the factors used by the three largest American consumer credit reporting agencies: Equifax, Experian, and TransUnion. 
Transaction History (txn counts + txn volume) 
Number and types of bank accounts/wallets owned
Ratio of used liquidity / available liquidity for each account
Length of account history
Recent (last 21 days) account activity
A machine learning module will be built with SciKit-Learn Python library + Flask for web framework. Output score on 300-900 non-linear numerical scale with associated qualitative scale: Excellent/Good/Fair/Below average/Poor.
 
4. **Smart Contract Compiler**: With the support of CosmWasm, this compiler will process statements written in Python and turn them into Rust smart contracts.
 
5. **Node**: The node will be built on Raspberry Pi 4 (8GB) computers (per node) and managed in Dockerized environments with the hardware installed on-site. The node will all be open-sourced.
 
## Go-to-Market plan
We are building a credit scoring on SCRT as base-layer infrastructure for a series of use cases where individuals or businesses may verify potential customers for extending credit, P2P lending, or vetting a potential employee with financial background checks.
The go-to-market plan is two-fold:

1. Transaction fees & Request Fees. Users requesting to view a person’s credit score will need to be issued with a key to access that user’s smart contract stored on SCRT. This will require a fraction of SCRT as a transaction fee for exercising that key on the smart contract. For companies requesting scores for people, we can make the model comparable with the current $10 fee for an Equifax report in Canada.

2. Self-run credit scores. If an individual wants to know their own credit score and how they rank on the SCRT network in terms of ‘credibility’, we will charge a fee in SCRT (less than the fee to a score requester as above) for computing the score. This will be a fee that the user pays in-wallet to SCRTSybil, however, the score is not necessarily published as a smart contract. 

Our core goal is to initially provide tools for building financial ecosystems on SCRT as the network gains traffic and user adoption. We believe in the value of having a public network with the option and flexibility of data encryption and ultimately believe that mainstream tools for financial services like credit scores will be of the first major requirements for service providers on SCRT.  
 
## Value capture for Secret Network ecosystem
A credit check oracle is both a clear value proposition for existing SCRT holders and an incentive for new or prospective users. First, a SCRT credit check oracle will increase Secret Network usability by validating users’ reputation (measured in terms of credit check), and thus will create trust toward users who have been verified by the oracle. Secondly, the oracle promotes interoperability and accessibility for the Secret Network by connecting the chain to crypto exchange platforms. Lastly, SCRTSybil enriches the ecosystem by leveraging on the privacy-preserving smart contracts which are distinctive of the Secret network. We believe the community needs a credit check oracle as soon as possible. SCRTSybil aims to provide that. 
 
## Team Members
* Michael Brink
* Matteo Mortelliti
* Yuchen Lin
* Mayllon Miranda
* Irene Fabris
* Hongbin Lin
* Yoon Kim

## Team Website	
* https://www.balloonbox.io/
 
## Team’s experience
All team members of PolkaBox are from Balloon Box, a FinTech company specialized in building industry-agnostic data science solutions from design through launch. Our team is experienced in developing WebApps for crypto asset management and we are currently engaged in designing dashboards for the visualization of cross-blockchain bridge transactions, specifically for ERC20 tokens. Our team members are proficient in Python, C++, Java, Javascript, and other object-oriented and development languages. 
 
Our team consists of the following roles:
- Product Architect (Full product architecture) 
- Full Stack Engineer (Core framework)
- Designer (WebApp)
- Backend Engineer (APIs, database structure, DevOps)
- Data Scientist (x2) (Credit Score algorithm + build)
- Product Manager (Community, articles, GitHub house-keeping, managing public PRs)
 
## Team Code Repos
- https://github.com/BalloonBox-Inc BalloonBox official repository
- https://github.com/MichaelBrink Michael Brink
- https://github.com/mattdm3 Matteo Mortelliti
- https://github.com/yul761 Yuchen Lin
- https://github.com/m3mayllon Mayllon Miranda
- https://github.com/irene-bbox Irene Fabris
- https://github.com/BalloonBox-Hongbin Hongbin Lin 
- https://github.com/yoon-bbox Yoon Kim
 
## Team LinkedIn Profiles
* https://www.linkedin.com/in/michael-brink-680b3767/ Michael Brink
* https://www.linkedin.com/in/matteo-mortelliti/ Matteo Mortelliti
* https://www.linkedin.com/in/foggysalmon/ Yuchen Lin
* https://www.linkedin.com/in/mayllon-miranda-8aa9b0163/ Mayllon Miranda
* https://www.linkedin.com/in/irenefabris/ Irene Fabris
* https://www.linkedin.com/in/hongbinlin/ Hongbin Lin
* https://www.linkedin.com/in/imyoonkim/ Yoon Kim
 
## Development Roadmap :nut_and_bolt:
### Overview

- **Total Estimated Duration:** 16 weeks
- **Full-Time Equivalent (FTE):** 3.5
- **Total Costs:** 175,000 USD


Our team will require 4 months to complete this project. We intend to have 2 developers full-time, 2 data scientists full-time, and 1 UX/UI designer part-time, a product architect, and a project manager.

We can receive payments in 3 disbursements, one at the beginning of the grant, one after completion of Milestone 1, and the last one after the completion of Milestone 2. 

We would be willing to consider part payment in SCRTs, up to 50%. The grant can be paid to either of the following addresses:
- BTC address: bc1qz36smg7zg9d2de7qurj9a49fetemavta39a9zp
- ETH address: 0x3ffA0e66091742a867430D140E36826c06ba19Be
- SCRT address: secret18qeg7lx63wkqvy9e295slufvch5rfel2v23tsu
 
### Milestone 1 - APIs, Database, Integration, Credit Score Algorithm
- **Estimated duration:** Week 1-6
- **Costs:** 50,000 USD


| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | Provide inline documentation of the code. |
| 1. | API module | Build APIs to selected validators (Coinbase, Binance, Plaid, etc.) | 
| 2. | Database | Set up data dump into PostgreSQL post-fetching. |
| 3. | Data Integration | Overlay web2 with web3 validation data for each API. |
| 3. | ML Module | Deploy an ML model to calculate unser credit score. |
 
 
 
### Milestone 2 - Node, Smart Contract Compiler
- **Estimated duration:** Week 7-12
- **Costs:** 50,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide inline documentation of the code. |
| 0c. | Test Guide | Run unit tests to ensure functionality and robustness of core functions (~70%). |
| 1. | Node | Spin up SCRT network node via Raspberry Pi 4.  |
| 2. | Smart Contract Compiler | Write a smart contract in Rust to encrypt the calculated credit score to SCRT chain. |
 
 
### Milestone 3 - WebApp: framework + UI 
- **Estimated duration:** Week 13-16
- **Costs:** 30,000 USD


| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | We will provide inline documentation of the code for the WebApp framework. |
| 1. | Framework | Implement SCRT wallet Login, personal info input, hover+select+OAuth2 in chosen validator |
| 2. | UI Module | We will refine WebApp aesthetic and functionality. |
| 3. | Tutorial | We will publish a video tutorial that walks a user through the SCRTSybil WebApp instructing them on how to get their credit score calculated. | 
 
 
## Additional Information :heavy_plus_sign:

#### Why SCRT

1. **How did you hear about the SCRT Network Grants?** We heard through the Secret Network Webpage.

2. **Have you ever applied for other grants?** Yes, we have applied for another grant to fund an entirely different project proposal for a different ecosystem. 

3. **Why did we apply for this grant?** We, at BalloonBox, are a team of developers excited about the future of decentralized technologies, and we want to contribute to building it! We think that the SCRT network is rapidly and innovatively unlocking the full value of decentralized applications by leveraging the computational privacy of Trusted Execution Environments (TEEs) and secret contracts to design Secret Apps preserving users’ privacy. We value the novelty of privacy-preserving smart contracts and their scalability potential which make SCRT a network that is uniquely set apart from other ecosystems. Specifically, we are submitting a proposal under the ‘‘Ecosystem’’ category because we want to build tools to expand the Secret Network and improve general usability. We hope our Credit Score Check to be the first of many such tools.  
 
 
#### Scope and Limitations
We will develop a simple 3-pages WebApp for users to retrieve their credit scores. Although we aim to scale up the WebApp for numerous and diverse use cases in the near future, for this first initial grant we will limit the App to three pages: (1) user login into Secret Network wallet via Ledger; (2) enter user’s personal information; (3) choose your preferred web2/web3 validators and calculate your credit score. We mocked up three UI prototypes, one for each page respectively, to give you a clear idea of our vision. Please, find the UI prototypes [here](https://github.com/BalloonBox-Inc/SCRTnetwork_oracle/tree/main/UI%20prototypes).
Initially, the WebApp for the SCRTSybil Oracle will only allow user authentication to their Secret Network Wallet via Ledger. In the future possibility of applSCRTSybilying for and receiving a second grant, we plan to enable login into the Secret Network wallet via other platforms. 
 
 
#### Future Plans

1. **Image processing** 
   - Integrate image processing for KYC authentication, e.g., reading in customer’s passports, driving license, medical service card.


2. **Auxiliary & Novel Use Cases**

   Developing an oracle for credit score checks automatically satisfies this auxiliary use case:

    - personal information integrity validation: do the user’s first and last name match across different platforms (Coinbase, Binance, Plaid, etc.)?
   
   Furthermore, we’ve designed our oracle to easily scale up to use cases that we consider relevant to the Secret Network:
   
    - credit score check for Anti-Money Laundering (AML)
   
    - credit score check to support loan application for university/post-secondary education (in such case validators should include a diverse set of eLearning Platforms, e.g., Coursera, LinkedIn Learning, Udacity, CloudAcademy, Udemy, DataCamp. An academic institution may want a credit score for a prospective student based on financial history but also academic history. For this use case, we could skew the algorithm weightings towards oAuth, where eLearning Platforms prove/disprove self-study courses.

    - third party (e.g., banks, financial institutions) request issuing of Secret private keys to validate user’s credibility 


3. **More Credit Check Providers**
   - Expand our validators pool (Coinbase, Binance, Stripe, Plaid) including more consolidated and emerging cryptocurrency exchanges (Kraken, crypto.com, Gemini, Bitstamp, MetaMask, etc.). For the moment, we will exclude decentralized exchanges like Bisq that do not require any KYC. We want to base our credit scoring algorithm to be anchored on platforms that validate the user identity.  


4. **Implement Credit Score Templates**
   - Imagine a third party requesting to issue a Secret private key to access a user’s credit score. Third parties may be Real and Personal Property Insurance Companies, Loan Agencies, Banks, Health Care Providers, and more. A bank will likely require a granular check on a user’s financial standing, while a Health Care Provider will require in-depth medical records for a patient. Similarly, an individual wanting to loan a friend money will value USD velocity in a US bank account far more than identity and this may require a credit model more skewed on historical throughput for a checking account. We want to design credit score templates with pre-set data granularities (i.e., more or fewer fields to be hashed out) depending on who is the third party requesting to access the credit score. In the long run, we envisage monetizing the smart contract generator to build credit score templates based on the needs of the third party. That is, the smart contract generator will serve as a template builder which we build privately for corporations or as community projects for user-level use cases.

