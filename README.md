<p align="left">
  <img alt="Barbotine Arbitrage System Logo" width="30%" height="30%" src="https://cdn.discordapp.com/attachments/876447732259225612/1095369391052443708/bas.svg">
</p>

[![Twitter @nelsodot](https://img.shields.io/twitter/url/https/twitter.com/nelsorex.svg?style=social&label=%20%40nelsorex)](https://twitter.com/nelsorex)
[![GitHub @nelso0](https://img.shields.io/github/followers/nelso0?label=follow&style=social)](https://github.com/nelso0)

## Table of content
* [Features](#features)
* [Demo](#demo)
* [Prerequisites](#prerequis)
* [Installation](#installation)
* [Usage](#usage)
* [Contact](#contact)
* [Real version](#full-version)
<a name="features"/>
 
## Features

* Compatible with almost any exchange (all [ccxt](https://github.com/ccxt/ccxt) exchanges).
* True trading fees support
* Zero-risk (no speculation)
* Full live tracking on Telegram and Discord webhooks
* Permanent live rate display in the terminal

<a name="demo"/>
 
## Demo

Fees are set to 0 for demo purposes.
![Barbotine Arbitrage Bot Demo](https://cdn.discordapp.com/attachments/876447732259225612/1095816511760904322/arbitrage.gif)

[It's running live! Click here to see current opportunities.](https://barbotine.capital/arbitrage-live)

[video demo](https://youtu.be/-HG05ZSeAp8)

<a name="prerequis"/>
 
## Prerequisites

The things you need before installing the software.

* Python 3.9+ (for windows users: if python or pip isn't recognized as a command, make sure you have installed python by checking the box "add to PATH")
* Nothing else lol

<a name="installation"/>
 
## Installation

1. Clone the repository 
```sh
git clone https://github.com/nelso0/barbotine-arbitrage-bot # you can also download the zip file
```
2. Go to the repository you just cloned
```sh
cd barbotine-arbitrage-bot
```
3. Install all the requirements to run the arbitrage system
```sh
pip install -r requirements.txt
```
4. Set your configuration details in [exchange_config.py](exchange_config.py)
5. Run with:
```sh
python run.py
```

<a name="usage"/>
 
## Usage

You can also run it with one line like this:

```sh
python run.py <mode> <symbol-renew-time-minutes> <balance-usdt-to-use> <exchange1> <exchange2> <exchange3> <symbol>
```


* ```<mode>``` = the mode you wanna use among ```fake-money```, ```classic```, and ```delta-neutral```. See #full-version for classic and delta-neutral modes. 
  
  * ```fake-money``` will run the bot with the balance-usdt-to-use you put, with a virtual balance, just to test.
  * ```classic``` will run the bot with real USDT.
  * ```delta-neutral```will run the bot with real USDT also, but in a delta-neutral situation. (a bit less profits but you won't loose a cent if the crypto you're using dump in 5 minutes (for very very careful people).
  
  
  
* ```<symbol-renew-time-minutes>``` = the timeframe you wanna use to switch symbol. If you put 60, it will renew the symbol each hour. Note that the new symbol is automatically selected by the [best_symbol.py](best-symbol.py) script if you don't put a {symbol}. Default: 15



* ```<balance-usdt-to-use>``` = how to be clearer? 


* ```<exchange1,2,3>``` = the three exchanges you want to use among all the CCXT-compatible exchanges. Default: binance okx kucoin (All the 3 have to be correctly configured in [exchange_config.py](exchange_config.py)).


* ```<symbol>``` = Every time it renews, it sells all the crypto and rebuy the crypto asset at the new price. 

Note: you can put a minimum profit in USD or % in [exchange_config.py](exchange_config.py). The bot will only take the trade if the profit is > (superior) to your value.

Examples:

```sh
python run.py fake-money 15 500 binance okx kucoin EOS/USDT    # run the system with 500 USDT and renew symbol every 15 minutes, with binance okx and kucoin
```
```sh
python run.py classic 15 1000 binance phemex bybit SOL/USDT   # run the system with 1000 USDT on binance phemex and bybit on SOL/USDT continuously (change the symbol to SOL/USDT each 15 minutes).
```
```sh
python run.py delta-neutral 60 750 okx cryptocom huobi BTC/USDT   # run the system in a delta-neutral situation with 750 USDT and renew the symbol each hour, on okx crypto.com and huobi. Note that with same amount of USDT, the delta-neutral mode will have 2/3 of the profits of the classic mode because it has less liquidity to invest in arbitrage opportunities.
```

## Contact

If you have any questions or you want to discuss of the bot with me, let's talk!

Discord: nelso#1800

Email: [nelso@barbotine.capital](mailto:nelso@barbotine.capital)

<a name="full-version"/>
 
## Full version

There is also a full version which operates with real dollars.

Most of the time, the more volatile a crypto asset is, the more opportunities there are (because exchanges struggle more to have the same price). 

You can now buy the source code of that real version!
Link: [barbotine.capital/arbitrage](https://barbotine.capital/arbitrage)

I also made a new trading (scalping) bot! As I want people to discover it, you can buy a bundle of Barbotine Arbitrage + Scalping for a very reduced price, [here](https://barbotine.capital/purchase-arbitrage)
