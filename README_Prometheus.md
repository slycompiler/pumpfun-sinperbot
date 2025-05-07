# Prometheus: Add README for pumpfun-sinperbot

## Project Overview

FSSB (Fast Solana Sniper Bot) is a specialized cryptocurrency trading bot designed specifically for the Solana blockchain. The bot focuses on automatically detecting and trading new token pools on the Raydium decentralized exchange, providing traders with a competitive edge in the fast-moving crypto market.

### Core Purpose
The primary objective of FSSB is to enable rapid token acquisition by identifying and executing trades on newly created liquidity pools before they become widely available on standard trading interfaces. This provides users with the potential to enter trades at the earliest possible moment.

### Key Features
- **Real-time Pool Detection**: Monitors and listens for new token pools in the USDC/SOL trading pairs
- **Automated Trading**: Executes buy orders on newly created token pools with configurable parameters
- **Advanced Filtering**: 
  - Liquidity range filtering (minimum and maximum pool sizes)
  - Token verification checks (burn and renouncement status)
- **Risk Management**: 
  - Built-in stop-loss and take-profit mechanisms
  - Configurable trading amount and token selection
- **Selective Trading**: Option to trade only pre-approved tokens via a snipe list

### Technical Advantages
Implemented in TypeScript, the bot offers a lightweight and performant solution for Solana token sniping, with flexible configuration options to suit different trading strategies.

## Getting Started, Installation, and Setup

### Prerequisites
- [Node.js](https://nodejs.org/en/download) (latest LTS version recommended)
- Solana wallet with SOL for transaction fees
- USDC or WSOL tokens for trading

### Quick Start
1. Clone the repository:
```bash
git clone https://github.com/CryptoTechZoo/fssb-fast-solana-sniper-bot.git
cd fssb-fast-solana-sniper-bot
```

2. Install dependencies:
```bash
npm install
```

3. Configure the environment:
- Copy `.env.copy` to `.env`
- Edit `.env` with your specific configuration
  - Add your wallet private key
  - Configure RPC endpoints
  - Set trading parameters (token symbol, buy amount, etc.)

4. Run the bot:
```bash
npm run fssb
```

### Configuration Parameters
Key configuration parameters in the `.env` file include:
- `MY_PRIVATE_KEY`: Your Solana wallet private key
- `RPC_ENDPOINT`: HTTPS RPC endpoint (paid services recommended for better performance)
- `RPC_WEBSOCKET`: Websocket RPC endpoint
- `TOKEN_SYMB`: Trading pair (USDC or WSOL)
- `BUY_AMOUNT`: Amount used to buy each new token
- `USE_SNIPEDLIST`: Enable buying only tokens from `snipedlist.txt`
- `MINT_IS_RENOUNCED`: Buy only if token mint is renounced
- `MIN_POOL_SIZE` and `MAX_POOL_SIZE`: Liquidity pool size filters
- `TAKE_PROFIT` and `STOP_LOSS`: Trading strategy parameters

### Optional Configuration
- Customize auto-sell settings in `.env`:
  - `AUTO_SELL`: Enable/disable automatic selling
  - `MAX_SELL_RETRIES`: Maximum sell attempt retries
  - `AUTO_SELL_DELAY`: Delay before selling tokens

### Snipe List
To target specific tokens:
1. Set `USE_SNIPEDLIST=true` in `.env`
2. Add token mint addresses to `snipedlist.txt`, one per line

### Notes
- Ensure you have USDC or WSOL in your wallet before running
- Bot operates in real-time, sniping new Raydium token pools
- Use a dedicated wallet with funds you can afford to lose