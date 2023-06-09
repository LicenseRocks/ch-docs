---
label: Discord integration hands-on
tags: [faq]
authors:
  - name: Chris Talkowski
    email: chris@licenserocks.de
    avatar: 
    link: 
---

# Discord integration hands-on

## What is Discord and How It Facilitates Real-Time Communication and Community Building

Discord is a highly popular communication platform that enables the creation of communities and facilitates real-time voice, video, and text conversations. Originally designed for gamers to communicate during gameplay, Discord has now evolved to encompass diverse interests and communities beyond gaming.

On Discord, users can engage in conversations within servers through text-based channels or participate in voice and video chats. These channels are organized based on different topics or purposes, making it easy for users to navigate and find relevant discussions. Additionally, users can send direct messages to individuals or create group chats for more focused conversations.

## Using NFTs to Control Access to Private Discord Channels

If you have successfully purchased an NFT that includes an Access Token feature, you can easily link your license.rocks marketplace account to your Discord account. This enables Discord to verify your NFTs and grant you access to private channels on our server. To establish this connection, click the "Connect to Discord" button in your private section on the marketplace. Discord will then prompt you to allow the connection, with no confidential information being shared with us. We provide Discord with information about the NFTs you currently own, allowing Discord to automatically assign specific roles that grant you access to private channels.

## Data Privacy of the Integration

Our integration with Discord does not save any login credentials data. Discord functions as a standalone application and adheres to its own privacy policies to ensure data security.

## Illustrative Use Case of NFT-Enabled Discord Channels

For instance, let's consider the Discord server "MelodyVerse," dedicated to music enthusiasts, artists, and fans. MelodyVerse offers a wide range of channels for discussions, music sharing, collaborations, and exclusive content from artists.

Closed or private channels within MelodyVerse can serve as platforms for artists to directly interact with their fans, share updates, previews of upcoming songs, behind-the-scenes content, and engage in exclusive discussions.

By implementing token gating to these channels, MelodyVerse fosters a stronger connection between artists and fans. It incentivizes user engagement, rewards active participation, and provides a dedicated platform for artists to interact with their most loyal followers.

Access to these exclusive channels is granted exclusively to owners of specific NFTs.

## Inviting RocksBot to Your Guild

**RocksBot** A Discord Bot for Discord-**CreatorsHub** Integration 

## Inviting RocksBot to Your Guild

Bringing RocksBot into your guild is a straightforward process. You have two options: either locate the bot invite button in a panel or click the provided hyperlink [click here](https://discord.com/api/oauth2/authorize?client_id=950680187627012136&scope=applications.commands+bot&permissions=8). This link will redirect you to Discord's website, where a pop-up window will appear, providing information about the required permissions for the bot. You can also use an interactive select menu to choose your server. After completing Discord's CAPTCHA, the bot will appear on your guild's member list.

## Verification and Connection Process

To ensure the prevention of spam and malicious usage, we have implemented a user-friendly verification mechanism.

!!!info

The `/verify`command can only be used by guild members with **Administrator** permission or **Guild Owner** status.

!!!

To initiate verification, navigate to any channel where the bot has message-viewing permissions and type `/verify` in the chat box. Follow the instructions that appear in the auto-suggestions window above the chat input.

The `/verify`command requires two parameters:

`creators-hub-url`: This is the base URL[^1] of your **CreatorsHub** instance.
`creators-hub-secret`: This secret key is used to verify that you are authorized to connect **RocksBot** with **CreatorsHub**. You can obtain the secret key from the [license.rocks](https://license.rocks) support team after setting up the instance.

!!!

**Pro Tip**: When entering command parameters, press <kbd>tab</kbd> to quickly move the cursor to the next parameter.

!!!

Simply provide these parameters and press <kbd>enter</kbd> to submit the command. **RocksBot** will respond with one of the following statuses:

🟩 Green-colored embed message: _"Successfully verified this guild."_ This indicates that your guild has been successfully verified.
🟥 Red-colored embed message: _"Could not verify this guild."_ This typically means that the `creators-hub-secret` is invalid.

!!!

Please note that server verification is a one-time action. Once your guild is verified, there is no need to repeat the process.

!!!

[^1]: _The base URL refers to the website link without any subpages or query parameters. For example, if your **CreatorsHub** instance is available at `marketplace.my-super-cool-domain.com`, that is the base URL_ to be used.
