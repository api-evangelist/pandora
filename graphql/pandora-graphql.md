# Pandora ERC-404 GraphQL

## Description

Pandora ERC-404 is an experimental mixed ERC-20/ERC-721 token standard developed by Pandora Labs Org. It enables native liquidity and fractionalization of NFTs by combining both standards into a single contract. Holders of one full ERC-20 token unit automatically receive an ERC-721 NFT, while fractional ERC-20 holdings do not carry an associated NFT.

No native hosted GraphQL subgraph is currently published by Pandora Labs Org. The schema in this directory is a conceptual GraphQL SDL derived directly from the on-chain contract interface (IERC404, ERC721Events, ERC20Events) published at https://github.com/Pandora-Labs-Org/erc404. Operators deploying their own ERC-404 tokens may index these events using The Graph Protocol or a compatible indexer.

## Endpoint

No canonical public endpoint. Indexers wishing to expose this data via GraphQL may deploy a subgraph using The Graph Protocol:

- Studio: https://thegraph.com/studio/
- Hosted Service: https://api.thegraph.com/subgraphs/name/{account}/{subgraph-name}

## Contract Addresses (Pandora Token — Ethereum Mainnet)

- Token contract: 0x9E9FbDE7C7a83c43913BddC8779158F1368F0413

## Documentation and Source

- GitHub (ERC-404 v2 spec): https://github.com/Pandora-Labs-Org/erc404
- GitHub (ERC-404 v1 / Pandora launch): https://github.com/Pandora-Labs-Org/erc404-legacy
- ERC draft: https://github.com/Pandora-Labs-Org/ERCs

## Schema Notes

The schema covers four main entity types derived from contract state and events:

- **Token** — each ERC-721 NFT token, owner, and fractional status
- **Account** — wallet addresses with both ERC-20 and ERC-721 balances
- **ERC20Transfer** — ERC-20 Transfer events (fungible amount moves)
- **ERC721Transfer** — ERC-721 Transfer events (NFT moves, identified by encoded token id)
- **ERC20Approval** — ERC-20 allowance approvals
- **ERC721Approval** — ERC-721 per-token approvals
- **ApprovalForAll** — operator approvals for all NFTs of an owner
