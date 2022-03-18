---
label: Introduction
tags: [discord, nft, integration]
order: 4
authors:
  - name: Igor Klepacki
    email: igor@licenserocks.de
    link: https://twitter.com/igorklepacki
    avatar:
---

# Introduction

**RocksBot** is an Discord Bot that acts as an integration layer between Discord platform and **CreatorsHub** instance.

## Inviting the bot

Adding **RocksBot** to your guild is really uncomplicated. All you need to do is either (find bot invite button in a panel?) or [click here](https://discord.com/). The hyperlink in both scenarios should redirect to the Discord's website with pop-up window informing about bot's required permissions and interactive select menu.

Choose your server in previously mentioned select menu and proceed. Now, after solving Discord's CAPTCHA, the bot should be visible on the members list of your guild 🥂.

## Verifying & connecting

In order to prevent spam and malicious usage, there is user friendly mechanism that ensures us that nothing wrong is going on 🙏

!!!info

the `/verify` command can only be used by guild members with either **Administrator** permission or **Guild Owner** status.

!!!

To start the verification, please navigate to any channel where bot has permissions to view messages, type `/verify` in chat box input and follow further instructions. The auto-suggestions window should pop up from the top of the chat input.

Now, the `/verify` command accepts two parameters:

- `creators-hub-url`, which is base URL[^1] of your **CreatorsHub** instance.
- `creators-hub-secret`, which is secret key used for verification that you're authorized to connect the **RocksBot** with **CreatorsHub**

!!!secondary  :bulb: **Tip**

when typing command parameters, press <kbd>tab</kbd> to quickly navigate cursor to the next parameter.

!!!

Simply pass these parameters, then click <kbd>enter</kbd> to submit the command. The bot should respond with one of these statuses:

- 🟩 green colored embed message, which description would be: *"Successfully verified this guild"* . From now on, your guild is verified 🥂
-  🟥 red colored one with: *"Could not verify this guild"*. In most cases, the reason for failure is invalid `creators-hub-secret`.

!!!

server verification is one time action - once you verify your guild, you don't need to do it again!

!!!

[^1]: *the base URL is nothing else but link to the website, without any subpages or query parameters. For example, if my **CreatorsHub** instance is available on the `marketplace.my-super-cool-domain.com`, it is the base URL* 

