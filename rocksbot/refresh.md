---
label: Refreshing server info
tags: [discord, nft, integration]
order: 5
authors:
  - name: Igor Klepacki
    email: igor@licenserocks.de
    link: https://twitter.com/igorklepacki
    avatar:
---

In order to refresh Discord server info _(avatar, name, ...)_ available on your **CreatorsHub** instance we got your covered. You simply need to execute `/refresh` command. 
!!!info

the `/refresh` command can only be used by guild members with either **Administrator** permission or **Guild Owner** status.

!!!

To begin, please navigate to any channel where bot has permissions to view messages, type `/refresh` in chat box input and follow further instructions. The auto-suggestions window should pop up from the top of the chat input.

Now, the `/refresh` command accepts two parameters:

- `creators-hub-url`, which is base URL[^1] of your **CreatorsHub** instance.
- `creators-hub-secret`, which is secret key used for verification that you're authorized to refresh the **CreatorsHub** info.

!!!secondary :bulb: **Tip**

when typing command parameters, press <kbd>tab</kbd> to quickly navigate cursor to the next parameter.

!!!

Simply pass these parameters, then click <kbd>enter</kbd> to submit the command. The bot should respond with one of these statuses:

- 🟩 green colored embed message, which description would be: _"Successfully refreshed server info"_ . You've just refreshed server info 🥂
- 🟥 red colored one with: _"Could not refresh this server info"_. In most cases, the reason for failure is invalid `creators-hub-secret`.

[^1]: _the base URL is nothing else but link to the website, without any subpages or query parameters. For example, if my **CreatorsHub** instance is available on the `marketplace.my-super-cool-domain.com`, it is the base URL_
