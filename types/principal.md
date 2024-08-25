# Principals
Principal is nothing else but address.

There are 2 type of principals: 
 - standard principals - is an address of a wallet ie. `'ST1SJ3DTE5DN7X54YDH5D64R3BCB6A2AG2ZQ8YPD5`
 - contract principals - is an address of a contract and is represented as `<standard principal>.<contract name>`, where `<standard-principal>` is an address of wallet that deployed a contract. ie. `'ST1SJ3DTE5DN7X54YDH5D64R3BCB6A2AG2ZQ8YPD5.super-cool-contract`

Both starts with single quote.

Contract principal can be also written using so called sugared syntax in which we don't use single quote and contract deployer address ie. `.super-cool-contract`.

This form is shorter, but can only be use for contracts deployed by the same address, ie the same principal.

If **Alice** creates contracts `contract-1` and `contract-2` she can reference both of them in `contract-3` using normal and sugared syntax. But **Bob** in his contract `contract-abc` can't. If he want to reference contract deployed by **Alice** he must always use normal (aka. full) syntax.

more explicit explanation:
**Alice** has a wallet with address 'SP12341234ALICE1234'.  She deploys `contract-1` (SP12341234ALICE1234.contract-1) and `contract-2` (SP12341234ALICE1234.contract-2). Now when Alice writes and deploys any future contracts from the same wallet, she can refer to `contract-1` and `contract-2` by just their names.  Clarity defaults to using the same wallet principal if it is not provided.
