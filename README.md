# Project overview

This is a Udacity Blockchain Capsotne project to build a decentralized housing product.

You will be minting your own tokens to represent your title to the real estate properties.

Before you mint a token, you need to verify your own the property.

You will use zk-SNARKs to create a verification system which can prove you have title to the property without revealing that specific information on the property.

Once the token has been verified you will place it on a blockchain market place (OpenSea) for others to purchase.

The detail steps of the project is as follows:

1. building of the ERC 721 tokens for the real estate homes

2. compiling and integrating zokrates into the tokens that is just built

  

# Prerequisite

## npm install

-  `npm install`

-  `npm install --save truffle-hdwallet-provider`

-  `npm install lite-server --save-dev`


## Testing

To run truffle tests: In directory eth-contracts/ 
`cd eth-contracts/`
`truffle test test/TestERC721Mintable.js` 
`truffle test test/TestSquareVerifier.js `
`truffle test test/TestSolnSquareVerifier.js`
For all tests: 
`truffle test` 
  

## Implement Zokrates

| Contract Name | Contract Address |

| ------------- | ------------- |

| Step 1: Install Docker | You can find instructions for installing it [here](https://docs.docker.com/install/)|

| Step 2: Run ZoKrates | docker run -v <Your  path  to  zokrates>:/home/zokrates/code -ti zokrates/zokrates /bin/bash|

| Step 3: A Quick Overview of the ZoKrates Process | 1.Compile Program</br> 2.Trusted Setup</br>3.Compute-Witness</br>4.Generate-Proof</br>5.Export-Verifier |

| Step 4: Compile the program written in ZoKrates DSL | cd code/zokrates/code/square/ </br> ~/zokrates compile -i square.code |

| Step 5: Generate the Trusted Setup | ~/zokrates setup |

| Step 6: Compute Witness | ~/zokrates compute-witness -a 3 9 |

| Step 7: Generate Proof | ~/zokrates generate-proof |

| Step 8: Export Verifier | ~/zokrates export-verifier|

  

## Deploying

set metmask mnemonic `.secret` file and place it in `eth-contracts/`

`truffle migrate --network rinkeby --reset`

  

## Mint Tokens

Mint 10 tokens using `scripts/mint.js`

```

export INFURA_KEY="<infura_key>"

export MNEMONIC="<metmask_mnemonic>"

export OWNER_ADDRESS="<my_address>"

export NFT_CONTRACT_ADDRESS="<deployed_contract_address>"

export NETWORK="rinkeby"

node scripts/mint.js

```

  

# Deployed Contracts Info

- Contract Address on Rinkeby Network

  

| Contract Name | Contract Address |

| ------------- | ------------- |

| Migrations | 0x59e4d0589D014798925a93DE7603eE0537dD5637 |

| Verifier | 0x0eAdcE4EE989580951C1D1DB48A36bFA464831d7 |

| SolnSquareVerifier | 0x8da9eAF3dAEA9D35293cB54d574975940D031a37 |

  

- Contract Abi's

```

[ { constant: true,

inputs: [ [Object] ],

name: 'supportsInterface',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: true,

inputs: [ [Object] ],

name: 'getApproved',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: false,

inputs: [ [Object], [Object] ],

name: 'approve',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: true,

inputs: [],

name: 'getSymbol',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: false,

inputs: [ [Object] ],

name: 'setPaused',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: true,

inputs: [],

name: 'getName',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: true,

inputs: [],

name: 'totalSupply',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: false,

inputs: [ [Object], [Object], [Object] ],

name: 'transferFrom',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: false,

inputs: [ [Object], [Object] ],

name: '__callback',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: true,

inputs: [ [Object], [Object] ],

name: 'tokenOfOwnerByIndex',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: false,

inputs: [ [Object], [Object], [Object] ],

name: '__callback',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: false,

inputs: [ [Object], [Object], [Object] ],

name: 'safeTransferFrom',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: true,

inputs: [ [Object] ],

name: 'tokenByIndex',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: false,

inputs: [ [Object], [Object], [Object], [Object] ],

name: 'verifyTx',

outputs: [ [Object] ],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: true,

inputs: [ [Object] ],

name: 'ownerOf',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: true,

inputs: [ [Object] ],

name: 'balanceOf',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: true,

inputs: [],

name: 'getOwner',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: false,

inputs: [ [Object], [Object] ],

name: 'setApprovalForAll',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: false,

inputs: [ [Object], [Object], [Object], [Object] ],

name: 'safeTransferFrom',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: true,

inputs: [],

name: 'getBaseTokenURI',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: true,

inputs: [ [Object] ],

name: 'tokenURI',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: true,

inputs: [ [Object], [Object] ],

name: 'isApprovedForAll',

outputs: [ [Object] ],

payable: false,

stateMutability: 'view',

type: 'function' },

{ constant: false,

inputs: [ [Object] ],

name: 'transferOwnership',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ anonymous: false,

inputs: [ [Object], [Object], [Object] ],

name: 'SolutionAdded',

type: 'event' },

{ anonymous: false,

inputs: [ [Object], [Object], [Object] ],

name: 'Transfer',

type: 'event' },

{ anonymous: false,

inputs: [ [Object], [Object], [Object] ],

name: 'Approval',

type: 'event' },

{ anonymous: false,

inputs: [ [Object], [Object], [Object] ],

name: 'ApprovalForAll',

type: 'event' },

{ anonymous: false,

inputs: [ [Object] ],

name: 'Paused',

type: 'event' },

{ anonymous: false,

inputs: [ [Object] ],

name: 'Unpaused',

type: 'event' },

{ anonymous: false,

inputs: [ [Object], [Object] ],

name: 'ownershipTransferred',

type: 'event' },

{ anonymous: false,

inputs: [ [Object] ],

name: 'Verified',

type: 'event' },

{ constant: false,

inputs:

[ [Object], [Object], [Object], [Object], [Object], [Object] ],

name: 'addSolution',

outputs: [],

payable: false,

stateMutability: 'nonpayable',

type: 'function' },

{ constant: false,

inputs: [ [Object], [Object] ],

name: 'mint',

outputs: [ [Object] ],

payable: false,

stateMutability: 'nonpayable',

type: 'function' } ]

```

- OpenSea MarketPlace Storefront link's

* Marketplace Seller: https://testnets.opensea.io/0xF9C0e027224764f98608d5571327C1DC8A6BF152

* Marketplace Buyers: 

  https://testnets.opensea.io/0x26481dbE79d005F30E62C950505039986a2FA248
  
  https://testnets.opensea.io/0x8CC6EbcBEf90D40CA782E3D011B017EAa5F76608
  
  

# Versions

- Truffle v5.0.36 (core: 5.0.36)

- Solidity v0.5.8 (solc-js)

- Node v10.15.3

- Web3.js v1.2.1

  

# Project Resources

  

*  [Remix - Solidity IDE](https://remix.ethereum.org/)

*  [Visual Studio Code](https://code.visualstudio.com/)

*  [Truffle Framework](https://truffleframework.com/)

*  [Ganache - One Click Blockchain](https://truffleframework.com/ganache)

*  [Open Zeppelin ](https://openzeppelin.org/)

*  [Interactive zero knowledge 3-colorability demonstration](http://web.mit.edu/~ezyang/Public/graph/svg.html)

*  [Docker](https://docs.docker.com/install/)

*  [ZoKrates](https://github.com/Zokrates/ZoKrates)


## Licensing, Authors, Acknowledgements
I would like to thank Udacity for creating a platform to learn and upscale my blockchain skills.

[https://www.bilginkocak.com/](https://www.bilginkocak.com/)
