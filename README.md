# HIVE Witness Update HTML Tool

## Features
- HTML for ease of use in any modern browser.
- Portability, can be saved on a USB stick.
- AES-256 encryption of the active key for safe storage in the configuration file.
- Selectable public signing keys.
- Selectable RPC nodes.
- Witness disabling.

## Requirements
- Hive-JS
- Crypto-JS
- JQuery
- Bootstrap
- Font Awesome

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
I'm not responsible for any bugs, misuse or potential bad outcome. I have tested the code extensively and didn't find any issues.
