# SSL Expiry Reminder

[![dependencies Status](https://david-dm.org/mskian/ssl-expiry-reminder/status.svg)](https://david-dm.org/mskian/ssl-expiry-reminder)  

SSL Expiry Reminder - Get SSL Expiry Notification remainder on Telegram and Gotify  

![SSL Expiry Reminder](https://raw.githubusercontent.com/mskian/ssl-expiry-reminder/master/Screenshot.png)  

## Requirements

- Node 8X LTS or 10X LTS
- `yarn` for Managing the Packages - Installation - <https://yarnpkg.com/en/docs/install>
- Bash to Run the Automated Tasks
- Telegram Bot - <https://core.telegram.org/bots>
- Gotify API - <https://gist.github.com/the-mcnaveen/2788985648490e7b3af24647247ed4e7#gistcomment-2996497>

## Installation

- Clone this Respo via Git

```bash
git clone https://github.com/mskian/ssl-expiry-reminder.git
cd ssl-expiry-reminder
npm install
```

- Used as CLI

```bash
npm link
```

#### (OR)

- Install via `npm`

```bash
npm install -g ssl-expiry-reminder
```

```bash
$ checkssl -h
Usage: checkssl [options]

Options:
  -V, --version                             output the version number
  -d, --domain <domain name>                Add domain without http/https
  -g, --gotify <GOTIFY API URL>             Gotify URL with Application Key
  -t, --telegram <Telegram API URL>         Telegram API URL with your Bot Key
  -c, --chatid <Telegram Chat ID>           Telegram Channel ID or Chat ID
  -r, --remainder <Enter the Day Remaining 1 to 365>  Enter the Remaining Day to Get SSL Expiry Remainder Alert
  -h, --help                                output usage information
```

- Next Store your Telegram & Gotify APIs by using this Below Command lines

```bash
$ Register Gotify API with URL
checkssl -g https://push.example.com/message?token=XXXXXXXXXXXXXXX
```

```bash
$ Register Telegram API URL and Botkey
checkssl -t https://api.telegram.org/bot<YOUR BOT API KEY>/sendMessage
```

```bash
$ Register Telegram your Chat id or Channel id
checkssl -s 123456789
```

- Testing - Execute the Script

```bash
checkssl -d example.com
```

## Usage

- Just Run the Bash file `sslcheck.sh`

```bash
chmod +x sslcheck.sh
```

```bash
./sslcheck.sh
```

- Replace mine Sites domain with your's <https://raw.githubusercontent.com/mskian/ssl-expiry-reminder/master/sslcheck.sh>
- Create Cron job for Automate checking

## Customization

- Change SSL remainder Day Remaining (Default is 5 days)
- Add your Own 👇 Example

```bash
checkssl -r 2
```

## Storage

- you API Key's and URL's are stored on your Disk in `JSON File` Example File - <https://github.com/mskian/ssl-expiry-reminder/blob/master/config-example.json>
- Folder name - `ssl-expiry-reminder-nodejs` and File Name `config.json`
- You **No need** to create this File and Folder it will Automatically Generate & Store your Data's

Linux - `~/.config` in Home  
Windows - `%APPDATA%` Folder  
macOS - `~/Library/Application Support`  

## Library

SSL Checker NPM Module - <https://www.npmjs.com/package/ssl-checker>

## Changelogs

v0.0.1

- Revamped the Entire Script
- Version Changes
- Converted to CLI by using `commander` Module
- replace `.env` with `conf` <https://github.com/sindresorhus/conf>
- Add extra validation
- Published in NPM
- Now Easy to use and Manage

v0.0.1-beta

- Revamp
- using Axios for Telegram instead of `telegram-bot-api` Module
- Proper Input and Output Validation
- Correct the version Number in `package.json`

v0.0.2-beta

- Update dependencies
- Migrate SSL Checker Module to Latest JSON response

## License

MIT
