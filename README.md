# DTN-docs
Distributed Trade Network

### How to verify transactions

1. Transparent and credible permissioned blockchain ledger.

  TigerWit togther with our partners, regulators, users will set up a permissioned blockchain Ledger (At first, it will be a beta version) by open source software [Hyperledger Fabric](https://github.com/hyperledger/fabric). Only by collect  enough endorsement that signed by member of  permissioned blockchain, the transaction can be record on the chain. Once it record, it cannot be modified anymore. We support that: our users can apply to become `ordinary member` of the  permissioned blockchain. And some users can be a `permissioned member` atfter they finish the high level KYC audit.


2. Security of privacy protection
  For privacy thinking, We only record the `digest` of the transaction on the blockchain ledger.  `Digest` generated by hash algorithm. Any change will lead to differet value of the `digest`, thus,  ensure the consistency of original transaction data and digest. And Also ensure simplification of data.

3. Two-way authentication transaction data
  We offer the following way to enable users to verify transaction data.

Original transaction data to the Digest: users can calculate the digest value `V1` by the common hash algorithm we published on the website.  And then they can visit any node of blockchain query service that deployed in the blockchain node to verify if `V1` exist. 


Digest to original transaction data: users can visit any node of blockchain query service that deployed in the blockchain node to query their transactions history data. selcet digest `V2` one of the history data, go to offical website query  the  original transaction data of `V2` to verify that if data has been modified.



