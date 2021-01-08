# Lavaclient Queue Support

> A lavaclient plugin that makes it easy to integrate spotify searching into any project.

- **✅ verified**: This is a verified Lavaclient plugin.

[Support](https://discord.gg/vuJxnYk)
&bull; [Github](https://github.com/lavaclient/plugins/tree/master/packages/spotify)

## Installation

```bash
npm install @lavaclient/spotify
```

## Setup

> This example only works with lavaclient 3.x.x

```ts
import { Manager } from "lavaclient";
import { SpotifyPlugin, SpotifyTrack } from "@lavaclient/spotify";

const manager = new Manager([], {
  plugins: [
    new SpotifyPlugin({
      clientId: "spotify client id",
      clientSecret: "spotify client secret",
      autoResolveYoutubeVideos: false, // whether you want to automatically search for the youtube equivalent.
    })
  ],
  ...
});

// example: in a command or something.
if (manager.spotify.isSpotifyLink(query)) {
  const item = await manager.spotify.load(query)
  if (item instanceof SpotifyTrack) {
    const track = await item.resolveYoutubeTrack()
    await player.play(item)
  }
}
```

If you need any support join <https://discord.gg/vuJxnYk>.

---

##### Disclaimer

Leaving the "autoResolveYoutubeVideos" option on is prune to you getting banned from youtube, unless you have IP
rotation set up. However it's much slower.

melike2d &copy; 2020 - 2021