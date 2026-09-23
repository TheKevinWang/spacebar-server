<p align="center">
  <img width="100" src="https://raw.githubusercontent.com/spacebarchat/spacebarchat/master/branding/png/Spacebar__Icon-Rounded-Subtract.png" />
</p>
<h1 align="center">Spacebar Server — Discord Compatibility &amp; Local Testing</h1>

## About this fork

This fork of [Spacebar](https://github.com/spacebarchat/server) focuses on
**Discord client compatibility and reliable local integration testing**. It grew
out of work to make real Discord client libraries work with a self-hosted
Discord-compatible server during local testing of Discord C2 profiles such as
[Discordx](https://github.com/TheKevinWang/discordx).

That work exposed practical gaps in Gateway heartbeats, multipart attachment
uploads, and client handling of Gateway and REST responses. The purpose of this
fork is to turn those findings into focused, tested compatibility fixes that
also help other bot and client developers.

### Compatibility work and current status

Our local test environment already uses a heartbeat handler overlay and
client-side workarounds for attachment uploads and response compatibility.
**Those runtime changes have not yet been ported into this public fork.** Its
server implementation currently matches upstream; the fork-specific changes so
far are its documentation and contribution policy.

The initial areas for evaluating and porting general-purpose fixes are:

- Gateway heartbeat handling before identification completes.
- Multipart file uploads that include attachment metadata in `payload_json`.
- READY and REST response compatibility with existing Discord client libraries.

The local workarounds are starting points for investigation. A server-side fix
needs its own reproduction and regression coverage before it is included here.

### Maintenance and contributions

We aim to keep this fork up to date with upstream Spacebar while maintaining
small, reviewable compatibility changes. **AI-generated and AI-assisted
contributions are welcome**, with contributors responsible for reviewing their
changes and providing relevant validation.

Please use [this fork's issues](https://github.com/TheKevinWang/spacebar-server/issues)
and [pull requests](https://github.com/TheKevinWang/spacebar-server/pulls), and read
our [contribution guide](CONTRIBUTING.MD). This fork is maintained independently;
its AI contribution policy does not apply to the upstream project. Upstream
project and community links are retained below for reference.

<p align="center">
  <a href="https://matrix.to/#/#spacebar:rory.gay">
    <img src="https://img.shields.io/matrix/spacebar%3Arory.gay?server_fqdn=matrix.rory.gay&fetchMode=summary&logo=matrix&logoColor=fffffff&label=Matrix" />
  </a>
  <a href="https://fermi.chat/invite/spacebar?instance=spacebar.chat">
    <img src="https://api.old.server.spacebar.chat/api/guilds/1006649183970562092/shield.svg" />
  </a>
  <a href="https://discord.gg/ZrnGQP6p3d">
    <img src="https://img.shields.io/discord/806142446094385153?color=7489d5&logo=discord&logoColor=ffffff&label=Discord" />
  </a>
  <img src="https://img.shields.io/static/v1?label=Status&message=Development&color=blue">
  <a title="Crowdin" target="_blank" href="https://translate.spacebar.chat/"><img src="https://badges.crowdin.net/fosscord/localized.svg"></a>
   <a href="https://opencollective.com/spacebar">
    <img src="https://opencollective.com/spacebar/tiers/badge.svg">
  </a>
</p>

## [About](https://spacebar.chat)

Spacebar/server is a Discord backend re-implementation and extension.
We aim to reverse engineer and add additional features to the Discord backend, while remaining completely backwards compatible with existing bots, applications, and clients.

This repository contains:

- [API Request/Response Types](/src/schemas)
- [Spacebar HTTP API server](/src/api)
- [WebSocket Gateway server](/src/gateway)
- [HTTP CDN server](/src/cdn)
- [WebRTC server](/src/webrtc)
- [Utility and Database Models](/src/util)
- [Spacebar Admin API (C#)](/extra/admin-api/Spacebar.AdminApi)
- [HTTP CDN server (C#)](/extra/admin-api/Spacebar.Cdn)
- [Various other C# utilities](/extra/admin-api)

## [Documentation](https://docs.spacebar.chat)

And with documentation on how to set up your own server [here](https://docs.spacebar.chat/setup/server), docs to set up either client [here](https://docs.spacebar.chat/setup/clients/), and docs about bots [here](https://docs.spacebar.chat/setup/bots/)

## [Contributing](CONTRIBUTING.MD)

## Clients

You _should_ be able to use any client designed for Discord.com to connect to a Spacebar instance.
However, some incompatibilities still exist between Spacebar and Discord. For this reason, not every client will connect.  
We recommend using [Fermo](https://fermo.sovr.top/login?instance=spacebar.chat) as a solid starting point on your adventure in the SpaceBar!
You can explore other clients with the [Spacebar Explorer](https://spacebar-explorer.sovr.top/clients).
