# PROJECT PHOENIX EGG - Autonomous Micro-Economy

## Overview
A fully automated, event-driven micro-economy system proving the Autonomy Engine's economic loop. Implements 5 parallel NFT arbitrage strategies on Polygon with <$50 capital.

## Architecture
- **Multi-Strategy Engine**: 5 independent strategies each with $10 allocation
- **Event-Driven**: No polling - uses WebSocket subscriptions and Firestore listeners
- **Atomic Execution**: Buy→List→Swap operations bundled for safety
- **3-Wallet System**: Hot ($40), Warm ($8), Egg ($2+profits)

## Strategies
1. **Trait Arbitrage**: 3 high-volume NFT collections, 1-4hr horizon
2. **Listing Sniping**: New mints <24h old, <30min horizon
3. **Collection Floor**: 5 medium-volume collections, 4-12hr horizon
4. **Bid-Ask Spread**: Top 10 collections by volume, <1hr horizon
5. **Gas-Aware Arbitrage**: Any opportunity when gas < 10 gwei

## Infrastructure
- Runtime: Google Cloud Functions Gen2
- Database: Firebase Firestore