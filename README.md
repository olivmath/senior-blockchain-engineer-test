![board](/assets/board.png)

[![built-with openzeppelin](https://img.shields.io/badge/built%20with-OpenZeppelin-3677FF)](https://docs.openzeppelin.com/)
[![Off-chain](https://github.com/olivmath/senior-blockchain-engineer-test/actions/workflows/off-chain.yml/badge.svg?branch=main)](https://github.com/olivmath/senior-blockchain-engineer-test/actions/workflows/off-chain.yml)
[![On-chain](https://github.com/olivmath/senior-blockchain-engineer-test/actions/workflows/on-chain.yml/badge.svg?branch=main)](https://github.com/olivmath/senior-blockchain-engineer-test/actions/workflows/on-chain.yml)

## Table of Contents

1. [ð¬ Understand Problem](#understand-problem)
2. [ð² Collect Data and References](#collect-data-and-references)
3. [ð Design Solution](#design-solution)
4. [â Write Tests and Solution (TDD)](#write-tests-and-solution-tdd)
5. [ð Iterate](#iterate)

## Understand Problem

[Cheap NFT Marketplace](/assets/Cheap-NFT-Marketplace.pdf)

NFT marketplaces often use techniques for reducing transaction fees.
Some of these techniques require users to use these marketplaces with an off-chain sibling system that assist the on-chain pieces. In this case you are tasked with designing and building a simple off-chain system and the on-chain smart-contract to enable cheap auctions. The goal is to enable trades between an ERC721 and a ERC20 with a single on-chain transaction.
The auctions should work as follows

- Owner of the NFT approves all NFTâs to the Marketplace
- Owner of the NFT signs to create an off-chain auction listing with a minimum price
- Bidder approves ERC20 tokens to Marketplace
- Bidder signs a bid for the auction
- If owner approves the bid, signs it back and retrieve to bidder
- Anyone with both signatures can settle the transaction, the owner takes the ERC20 whilst the bidder takes the NFT.

The off-chain system must be written in Node.js and it should not use any persisent storage (all created listings and bids should be stored in memory). It should also support an HTTP interface using express.js to fetch the live listings, bids, and signatures at any given time. The on-chain system should be developed using truffle or hardhat, with a solidity version greater or equal than 0.8

## Collect Data and References

- ð© https://www.linkedin.com/pulse/how-create-nft-marketplace-polygon-codezeros/?trk=organization-update-content_share-article
- â https://etherscan.io/address/0x354EF538265426d223A5faae68C9b0795f0541D9#code
- ð© https://ethereum.stackexchange.com/questions/102660/creating-an-auction-smart-contract-without-storing-the-ether
- â https://www.quicknode.com/guides/solidity/how-to-create-a-dutch-auction-smart-contract#what-is-dutch-auction
- ð© https://ethereum.stackexchange.com/questions/94928/on-chain-vs-off-chain-nft-art-platforms
- ð© https://hackernoon.com/how-to-create-on-chain-and-off-chain-nft-collection-smart-contracts
- ð© https://betterprogramming.pub/handling-nft-presale-allow-lists-off-chain-47a3eb466e44
- ð https://blog.chain.link/how-to-build-an-nft-marketplace-with-hardhat-and-solidity/
- ð https://chambers.com/articles/nft-mechanism-and-legal-issues-of-nft-transactions
- ð https://fauna.com/blog/bridging-on-chain-and-off-chain-data-in-nfts-with-fauna
- ð https://docs.tatum.io/tutorials/how-to-create-a-peer-to-peer-nft-auction
- ð https://nftschool.dev/concepts/non-fungible-tokens/#how-are-nfts-special
- ð https://academy.binance.com/en/articles/how-to-make-your-own-nfts
- ð https://quadrabyte.net/how-to-build-an-nft-marketplace-on-chain/
- ð https://trufflesuite.com/guides/nft-marketplace/
- â https://github.com/ethereum/EIPs/issues/5102
- ð https://www.youtube.com/watch?v=bBQif9IM9Fw
- ð https://www.youtube.com/watch?v=2bjVWclBD_s
- ð https://www.youtube.com/watch?v=kMnfCUvJnHo
- ð https://www.youtube.com/watch?v=nOfFeRZg9oE
- ð https://www.youtube.com/watch?v=7Q5E6RvLlUw
- â https://pt.wikipedia.org/wiki/LeilÃ£o
- â https://www.chainshot.com/courses
- â https://www.pointer.gg/tutorials
- â https://buildspace.so/projects
- ð© https://learn.questbook.xyz

## Design Solution

_Project_
![Design](/assets/design.png)

_Application_
![Application](/assets/archtecture.png)

## Write Tests and Solution (TDD)

[![Off-chain](https://github.com/olivmath/senior-blockchain-engineer-test/actions/workflows/off-chain.yml/badge.svg?branch=main)](https://github.com/olivmath/senior-blockchain-engineer-test/actions/workflows/off-chain.yml)
[![On-chain](https://github.com/olivmath/senior-blockchain-engineer-test/actions/workflows/on-chain.yml/badge.svg?branch=main)](https://github.com/olivmath/senior-blockchain-engineer-test/actions/workflows/on-chain.yml)

## Iterate

- [x] Write, Test, Deploy ERC20 contract on Local.
- [x] Write, Test off-chain post bids.
- [ ] Write, Test, Deploy ERC721 contract on Local.
- [x] Write, Test off-chain post NFT.
- [ ] Write, Test, Deploy Matcher contract on Local.
- [ ] Plug off-chain in on-chain App.
- [ ] Deploy App with Docker-Compose.

_next steps_

- [ ] Enable multiple auctions.
- [ ] Deploy App with Kubernetes for more scalability.
- [ ] Change to Actors Models for more scalability.
