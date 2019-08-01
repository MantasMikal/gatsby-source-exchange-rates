# gatsby-source-exchange-rates

Source plugin for pulling currency exchange rates into Gatsby from [Exchange Rates API](https://exchangeratesapi.io)

## Install

```npm i gatsby-source-exchange-rates```

```yarn add gatsby-source-exchange-rates```

## How to use

```javascript
// In your gatsby-config.js
module.exports = {
  plugins: [
    {
      resolve: `gatsby-source-exchange-rates`,
      options: {
        latest: {
          base: 'EUR'
        }
      }
    },
  ],
}
```

## Query

```graphql
query MyQuery {
  allExchangeRates {
    edges {
      node {
        latest {
          rates {
            ILS
            INR
          }
        }
      }
    }
  }
}
```

## Examples

1. Get latest exchange rates between two currencies

```javascript
// In your gatsby-config.js
module.exports = {
  plugins: [
    {
      resolve: `gatsby-source-exchange-rates`,
      options: {
        latest: {
          symbol: 'EUR, GBP'
        }
      }
    },
  ],
}
```

2. Get historical rates for a time period.

```javascript
// In your gatsby-config.js
module.exports = {
  plugins: [
    {
      resolve: `gatsby-source-exchange-rates`,
      options: {
        history: {
          base: 'EUR',
          start_at: '2019-01-01',
          end_at: '2019-02-01'
        }
      }
    },
  ],
}
```

3. Get historical rates for a time period between two currencies.

```javascript
// In your gatsby-config.js
module.exports = {
  plugins: [
    {
      resolve: `gatsby-source-exchange-rates`,
      options: {
        history: {
          symbol: 'EUR, GBP',
          start_at: '2019-01-01',
          end_at: '2019-02-01'
        }
      }
    },
  ],
}
```
