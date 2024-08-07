## Welcome to 0xchat

Welcome to 0xChat⚡️

0xchat is a secure chat app built on the [Nostr protocol](https://github.com/nostr-protocol/nips). It prioritizes security, featuring private key login, encrypted private chats and contacts, encrypted group chats, and lightning payments([Cashu](https://cashu.space/)). Additionally, it also offers an open communication platform through public channels.

0xchat Download links:

  - [0xchat on Appstore](https://apps.apple.com/app/0xchat/id1637607169)
  - [0xchat on Testflight](https://testflight.apple.com/join/AjdJFBmU)
  - [0xchat on Google play](https://play.google.com/store/apps/details?id=com.oxchat.nostr)
  - [0xchat APK download](https://github.com/0xchat-app/0xchat-app-main/releases)

![](https://github.com/0xchat-app/.github/blob/main/profile/banner.jpeg)

## Features

**No Registration Required**

As a chat client based on the [Nostr protocol](https://github.com/nostr-protocol/nips), we only require the creation of a Nostr account to log in; there is no need to register through a phone number, email, or any other means. You must safeguard your nsec key, as it allows you to control your own data. Additionally, your Nostr account is compatible with other Nostr clients.

**Secure DM**

Currently, we support three types of direct messages (DMs), Please review the provided links for a deeper understanding of each DM type:

- NIP-04 DM

[NIP-04 DM](https://github.com/nostr-protocol/nips/blob/master/04.md) is the most widely used DM type in nostr, but it is not our recommended option currently because NIP-04 is not private in terms of DMs. Even though the content is encrypted, it leaks a lot of metadata. We do not use this DM type by default but are compatible with NIP-04 DM from other nostr clients.

- Gift-Wrapped DM

[Gift-Wrapped DM](https://github.com/nostr-protocol/nips/blob/master/17.md) is our default and recommended DM type. By using Gift-Wrapped for event messages, it minimizes metadata leakage. Not only is the message content encrypted, but the sender and the timestamp are also concealed. Moreover, the encryption algorithm employed is the latest audited [NIP-44](https://github.com/nostr-protocol/nips/blob/master/44.md) algorithm.

- Secret DM

[Secret Chat](https://github.com/0xchat-app/0xchat-core/blob/main/doc/secretChat.md) is our third DM type, an extension of the Gift-Wrapped DM. Since Gift-Wrapped DM does not support forward secrecy, if a user's private key is compromised, all DM messages could be recovered. Therefore, we added a [NIP-101](https://github.com/water783/nips/blob/nip101/101.md) key exchange protocol to ensure each message session uses a different receiver key, securing forward secrecy. Additionally, we have incorporated the option to select a fixed relay for these sessions, allowing messages to be transmitted through a single trusted relay for both parties.

If you wish to recover your private chat messages on a different Nostr client or new device, we recommend using our default Gift-Wrapped DM. For more confidential conversations, you can initiate a Secret Chat with your friend, which requires their consent to establish a secret chat session. Please note that without backing up your chat database, you cannot retrieve historical messages if you switch devices or Nostr clients.


**Private Group**

For private groups, we use the [NIP-17](https://github.com/nostr-protocol/nips/blob/master/17.md) chat room to support group member management. In this setup, group messages are processed through gift-wrapping and sent to all group members, ensuring that messages are received only by group members.

Since our private group chats do not use a shared group private key, each group message is individually encrypted and sent to group members. This approach is not ideal for large groups. After testing, we found that the 0xchat app, using a multi-threading approach, can support private groups well with fewer than 100 members.

**Relay Group**

For open/closed groups, we implemented [NIP-29](https://github.com/nostr-protocol/nips/blob/master/29.md). In an open group, anyone can join, while in a closed group, administrative approval is required. Group owners or administrators can manage permissions, add or remove group members, and send group notes. This setup supports large group chats.

Although non-group members cannot retrieve group messages, relay group messages are not encrypted. If content privacy is needed, please create a private group.

**Open Channels**

We also provide an open channels feature, compatible with other nostr clients. These channels are public, allowing anyone to join and speak, with message content visible to all. This feature is primarily aimed at fostering community and enhancing chat enjoyment.

**Audio & Video Call**

We also offer E2EE audio and video call functionalities between contacts. Signaling communication is conducted through Nostr relay using [NIP-100](https://github.com/jacany/nips/blob/webrtc/100.md), with actual audio and video calls facilitated via ICE servers. 

If you wish to protect your privacy further, you have the option to set up your own relay and ICE services. Within the 0xchat app, you can select these self-hosted services for your relay and ICE interactions. By doing so, both signaling and ICE services will only pass through your own infrastructure.


**Push Notifications**

0xchat proposes a [push notification](https://github.com/0xchat-app/0xchat-core/blob/main/doc/nofitications.md) method for Nostr, where the push configuration is set up by sending DM messages to the push server. The push server then forwards the notifications to the corresponding distributor, which is responsible for relaying the push messages to the app.

In the latest Android version, we have integrated [Unifiedpush](https://unifiedpush.org/) with an embedded FCM distributor, also allowing users to select their preferred distributor in the settings.

**Lightning Payment ⚡️**

For lightning payment, we have integrated a Cashu wallet into the app, utilizing the Lightning Network for ecash deposits and withdrawals. Within the app, users can send Ecash to friends and group members. The Ecash is stored locally, anonymizing ownership and effectively protecting user privacy.

If you want to learn more about Cashu, please check [here](https://cashu.space/).


**Badge Collections**

Finally, we offer a badge collection feature, where you can obtain badges of different levels by making donations to us. You can set these badges as your profile picture and also enjoy the corresponding privileges.


## Future Enhancements

We continuously aim to improve and enhance the features. Stay tuned for future updates!

Some important planned features:

- [x] Threads, mentions, reactions
- [x] Zap Red Envelopes between friends
- [x] P2P audio/video calling
- [x] Private group
- [x] Cashu wallet Integration
- [x] Public/Private notes
- [x] Open/Closed groups
- [ ] Audio/video chat room
- [ ] Desktop&Tablets versions

