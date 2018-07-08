# STEEM Witness Update HTML Tool

## Features
- HTML for ease of use in any modern browser.
- Portability, can be saved on a USB stick.
- AES-256 encryption of the active key for safe storage in the configuration file.
- Selectable public signing keys.
- Selectable RPC nodes.
- Witness disabling.

## Requirements
- Steem-JS
- Crypto-JS
- JQuery
- Bootstrap
- Font Awesome

Since the fix hasn't been reviewed and merged yet by Steemit's developers, you can either use the included `steem.min.js` I built, or build your own. I have used the latest Steem-JS v0.7.1 on Ubuntu 16.04:

Install the latest NodeJS v10.x (10.6 at time of this release)
```
sudo apt-get purge -y --auto-remove nodejs npm
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
```
***
Install Steem-JS
```
git clone https://github.com/steemit/steem-js.git
cd steem-js
curl https://patch-diff.githubusercontent.com/raw/steemit/steem-js/pull/390.patch | git apply
npm install
```
***
Then copy `/dist/steem.min.js` into the same folder as the html file.

## Setup
`git clone https://github.com/Jolly-Pirate/witness-update-html.git` or download the zipped files.

## Configuration
- Copy the `config.json.example` and save it as `config.json` in the same folder as the HTML file.
- Open `config.json` in a plaintext editor and modify it with your settings. Follow the JSON format to add or remove values.

For the `wif` parameter, you have two options: either use your private active key, or encrypt it with a password then store it in the config file. I highly recommend you do the latter, which brings us to the following steps:
- Open the HTML file in a browser.
- Go to the **Encryption Tool** tab, paste your witness private active key, set a **strong** password and click **Encrypt**. The encrypted string will change everytime you click the button because of the random salt; don't worry, the password will decrypt the strings just fine.
- Click **Decrypt** to test the decryption.
- Select the encrypted text and paste it as the `wif` value in the `config.json`.

## Usage
It's straighforward and self-explanatory. 
- Refresh the HTML page or go to the **Broadcast Command** tab.
- Enter your decryption password (leave blank if your active key is in plaintext).
- Click **Load Settings**, select the public signing key you wish to use (or enter it manually).
- Click **Broadcast** or **Disable Witness**, depending on your needs.

I encourage every witness to learn and understand how things are done manually **first** (cli_wallet, compiling, etc) before using convenience tools like this one. I hope you like it.

## Disclaimer
I'm not responsible for any bugs, misuse or potential bad outcome. I have tested the code extensively and didn't find any issues. Nevertheless, unmerged pull requests are experimental so use at your own risk. When the fix is approved, I'll update the repo to enable the `<script src="https://cdn.steemjs.com/lib/latest/steem.min.js"></script>` line, instead of `<script src="steem.min.js"></script>`.
