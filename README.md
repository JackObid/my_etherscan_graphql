# GraphQL With Etherscan APIs

## Recap of Bounty
Based on the GraphQL with REST API module, you have learnt how to wrap multiple REST API endpoints into a single GraphQL API for more efficient querying. 

In the previous bounty, you have wrapped multiple etherscan API endpoints under a GraphQL API. In this quest, we will be expanding on the functionalities of the GraphQL API to track the key metrics of the Ethereum network

- Get Ether Balance for a Single Address (https://docs.etherscan.io/api-endpoints/accounts#get-ether-balance-for-a-single-address)
- Get Total Supply of Ether (https://docs.etherscan.io/api-endpoints/stats-1#get-total-supply-of-ether) 

## Getting Started
1. Sign up for a new Etherscan account to generate your API key if you do not have one. 
2. Proceed to clone the git repository 
3. Create a new .env file and create a `ETHERSCAN_API` key variable to insert your Etherscan API key value
4. Run the `$npm install` command to install the necessary dependencies
5. Run the `$node index.js` command to initialise the GraphQL server and run your queries

# GraphQL With Etherscan APIs

## Getting Started

To get started using the GraphQL Etherscan API, follow these steps:

1. Clone this repository
2. Run `npm install` to install dependencies
3. Create an Etherscan API key (explained below)
4. Start the Apollo server (explained below)
5. Make GraphQL queries against the server (example below)

## Benefits of using GraphQL API

Wrapping the Etherscan REST APIs in a GraphQL API provides the following benefits:

- Query multiple related resources in a single API call
- Strong typing system
- Intuitive query language
- Built-in documentation

## Create an Etherscan API Key

To use the Etherscan APIs, you'll need an API key. Follow these steps:

1. Sign up for an Etherscan account at https://etherscan.io/register
2. Go to https://etherscan.io/myapikey to generate an API key
3. Add the API key to a `.env` file as `ETHERSCAN_API=your_api_key`

## Overview of GraphQL Etherscan API endpoints

The GraphQL API wraps the following Etherscan REST endpoints:

- `etherBalanceByAddress` - Get ETH balance for an address
- `totalSupplyOfEther` - Get total ETH supply
- `latestEthereumPrice` - Get latest ETH price
- `blockConfirmationTime` - Get estimated block confirmation time

See the `schema.graphql` file for details.

## How to run Apollo Server

Starting the Apollo GraphQL Server:

1. Open your terminal on VSCode
2. Run the following command to start the server: `node index.js`
3. Upon successful startup, you should see this message: 🚀 Server ready at http://localhost:9000/
4. Access the Apollo Server by navigating to http://localhost:9000 on your browser

## Sample GraphQL Query

Below is a sample GraphQL query to fetch the necessary data from Etherscan
```graphql
query {
  etherBalanceByAddress {
    message
    result
  }
  totalSupplyOfEther {
    message
    result
  }
  latestEthereumPrice {
    message
    result {
      ethbtc
      ethusd
      ethusd_timestamp
    }
  }
  blockConfirmationTime {
    message
    result
  }
}
```