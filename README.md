# Accept Bitcoin on your Drupal Store using BTCPay Server

Introducing BTCPay Server payment plugin for [Drupal Commerce 2.x](https://www.drupal.org/project/commerce). Drupal Store owners can now accept payments using Bitcoin and other cryptocurrencies directly through BTCPay Server without any third-party intermediary.

BTCPay Server supports a range of cryptocurrencies, with the potential for future extensions. The currently supported options include:

- BTC (Bitcoin)
- Bitcoin 2nd later lightning network for fast and zero/low-fee transactions
- Altcoins with full node integration including coins like Monero (XMR) and Litecoin (LTC).
- Other Major Altcoins: Supported through plugins via platforms such as [Trocador](https://docs.btcpayserver.org/Trocador/), [SideShift](https://docs.btcpayserver.org/SideShift/), and FixedFloat.

Start accepting Bitcoin and other cryptocurrencies directly in your Drupal store securely and with ease. Visit the [project page on Drupal.org](https://drupal.org/project/commerce_btcpay)

## Demo store
A Drupal Commerce demo store connected with a (testnet) BTCPay Server where you can try the checkout (Bitcoin + Lightning Network) can be found here:   
[http://drupal.demo.btcpay.tech](http://drupal.demo.btcpay.tech/)

## Requirements

* BTCPay Server ([self hosted or 3rd party](https://docs.btcpayserver.org/deployment/deployment) or [quick start with a testserver](https://docs.btcpayserver.org/btcpay-basics/tryitout))
* Drupal Commerce 2.x installed ([installation guide](https://docs.drupalcommerce.org/commerce2/developer-guide/install-update/installation))  
* Drupal: [configured and writable private file system](https://www.drupal.org/docs/8/core/modules/file/overview#content-accessing-private-files)

## Installation and configuration Guid for BTCPay Server-Drupal Commerce Integration

Ready to accept Bitcoin on your Drupal Store? Follow this comprehensive guide to install and configure the BTCPay Drupal Commerce module. For a visual walkthrough check out our installation and configuration screencast:

[![BTCPay Server - Drupal Commerce 2.x quick walkthrough](https://img.youtube.com/vi/XBZwyC2v48s/mqdefault.jpg)](https://youtube.com/watch?v=XBZwyC2v48s)


### Quick setup steps

#### Generate pairing code on BTCPay server
1.  **Create and configure a store:** You would need to setup a BTCPay server instance and create a store. If you do not have one you can click [here](https://docs.btcpayserver.org/btcpay-basics/gettingstarted#creating-btcpay-store) to provide a walkthrough.
2.  **Access Tokens:** Once you have your BTCPay Server instance setup and store created, navigate to the store settings and select "**Access Tokens**"
3.  Create a new token by clicking on **[Create a new token]**
4.  **Label:** enter some label (eg. my store)
5.  **Public key:** this needs to be left **empty**
6.  **Facade:** "merchant"
7.  click on **[Request pairing]**
8.  on next screen choose your configured store in** Pair to** select dropdown and click on **[approve]**
9.  note down the displayed 7-digit code at the top status message, e.g. "d7afaXr"   
 (you will need that code below on gateway configuration, see below)

#### Commerce BTCPay: Installation + configuration
1.  install module: `composer require drupal/commerce_btcpay`
2.  enable the module: `drush en commerce_btcpay -y`
3.  make sure you have configured [private file system](https://www.drupal.org/docs/8/core/modules/file/overview#content-accessing-private-files) (needed to store encrypted public+private key)
4.  Commerce BTCPay configuration (**Commerce -> Configuration -> Payment -> Payment gateways**): 
5.  add payment method "BTCPay"
    * **Mode**: Test or Live (you can configure both individually)
    * **Test/Live server host**: enter your URL without https:// prefix e.g. btcpay.yourserver.com (note valid SSL certificate needed)
    * **Test/Live Paring code**: enter the 7-digit pairing code from BTCPay "Access tokens" page
    * Click **Save** to finalize the setup.  
      You should see a message that the tokens were successfully created.

## Status
**This module is currently in alpha stage but has proven stable without issues.**    
Future updates and releases will be available on the [project page on drupal.org](https://drupal.org/project/commerce_btcpay)

## About BTCPay Server
>[BTCPay Server](https://btcpayserver.org/) is a self-hosted, open-source cryptocurrency payment processor know for its security, privacy, and censorship resistance.

It's free to use and allows you to become your own payment processor. 
**To get a full overview check out our [documentation](https://docs.btcpayserver.org).**

## Compatible with BitPay API
BTCPay was created to be a alternative to 3rd party payment provider [BitPay](https://bitpay.com). Therefore BTCPay is invoice API compatible and you can use this payment plugin also with the official BitPay API and sites if you want. But the power of BTCPay is that you can become your own payment provider. 

Teaser, future versions of this plugin will be based on the BTCPay Server Greenfield API which is much more powerful and allows more features.


## Get Support
You can open an issue on our [Github repository](https://github.com/btcpayserver/commerce_btcpay/issues) or join us on [Telegram](https://t.me/btcpayserver) or [Mattermost chat](http://chat.btcpayserver.org/)