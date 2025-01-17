# Crypto Arbitrage Bot

## Overview
A high-performance automated trading system that identifies and executes arbitrage opportunities across multiple cryptocurrency exchanges using asyncio for concurrent operations.

## Features
- Real-time price monitoring across multiple exchanges (Coinbase Pro, Kraken, OKX, KuCoin)
- Automated arbitrage detection using Bellman-Ford algorithm
- Asynchronous operations for efficient API interactions
- Comprehensive risk management system
- Rate limiting and exchange API protection
- Advanced error handling and logging
- Position monitoring and management

## Prerequisites
- Python 3.8+
- Active API keys for supported exchanges
- Sufficient balance in trading accounts

## Installation

### Clone Repository
```bash
git clone https://github.com/saadusmanii/CryptoArbBot.git
cd crypto-arbitrage-bot
```

### Install Dependencies
```bash
pip install -r requirements.txt
```

### Configure API Keys
1. Create config file:
```bash
cp config.example.py config.py
```

2. Add exchange credentials:
```python
COINBASEPRO_API_KEY = "your_api_key"
COINBASEPRO_SECRET = "your_secret"
KRAKEN_API_KEY = "your_api_key"
KRAKEN_SECRET = "your_secret"
# Add other exchange credentials
```

## Usage
Start the bot:
```bash
python main.py
```

## Configuration

### Exchange Settings
Modify exchange_configs in `main.py`:
```python
exchange_configs = {
    "coinbasepro": ExchangeConfig(
        trading_fee=Decimal('0.005'),
        withdrawal_fee=Decimal('0.0'),
        min_order_size=Decimal('0.0001'),
        max_order_size=Decimal('1.0'),
        rate_limit=3
    ),
}
```

### Risk Parameters
- `min_order_size`: Minimum trade size
- `max_order_size`: Maximum trade size
- `rate_limit`: API calls per second
- Trading and withdrawal fees
- Slippage estimates

## Safety Features
- Balance verification before trades
- Position size optimization
- Slippage estimation
- Rate limiting
- Comprehensive error handling
- Position monitoring
- Stop-loss capabilities

## Logging
Uses Python's logging module:
```
YYYY-MM-DD HH:MM:SS - LoggerName - Level - Message
```

## Technical Architecture

### Price Fetching System
- Asynchronous price updates
- Rate-limited API calls
- Error handling for failed requests

### Arbitrage Detection
- Bellman-Ford algorithm implementation
- Fee consideration in calculations
- Negative cycle detection

### Trade Execution
- Order placement with safety checks
- Position sizing
- Balance verification

### Risk Management
- Dynamic position sizing
- Slippage estimation
- Balance monitoring
- Stop-loss implementation


## Disclaimer
This bot is provided for educational purposes only. Cryptocurrency trading carries significant risks. Use this software at your own risk. The author is not responsible for any financial losses incurred while using this bot.
