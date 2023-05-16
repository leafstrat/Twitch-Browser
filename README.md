# Twitch Browser

This script uses `curl` to request Twitch's public GraphQL API to get a list of the current streams per category of your choosing. It uses `jq` to parse the JSON data from the API into single lines to feed into `dmenu`.

Data is diplayed in a [dmenu](https://wiki.archlinux.org/title/dmenu) list, with the stream's viewer count, streamer username, stream title, and stream tags. 

You can fuzzy search with dmenu for the words you're interested in or use the arrow keys to navigate through the list. 
Press return when you've decided on a stream to watch. This launches an `mpv` command: `mpv twitch.tv/username`. 
Which uses `yt-dlp` to get the proper streaming URL.

I built this so I could browse the [Software and Game Development](https://www.twitch.tv/directory/game/Software%20and%20Game%20Development) streams without visiting Twitch, as such this is the default category when you first use the script. But I have included all the popular categories [in a file](https://github.com/leafstrat/Twitch-Browser/blob/main/categories) and an easy way to switch between them for user convenience.

#### Installing yt-dlp:
[Installation · yt-dlp/yt-dlp Wiki · GitHub](https://github.com/yt-dlp/yt-dlp/wiki/Installation)

#### Installing dependencies:
```
sudo apt-get install curl jq dmenu mpv
```

#### Useage:
Navigate to the downloaded git repository.

Launch via `browse` in your terminal or by clicking on this file.

#### Functionality:
Using dmenu:
- Switch the stream category by selecting the entry `[ category]`
- Switch the stream sorting order by selecting `[  sorting]`
- Open the config file in your preferred system editor `[   config]`

## Config file:
`dmenu_lines="20"` how many dmenu rows of streams to display at once

`dmenu_color_text="#999"` dmenu text color

`dmenu_color_background="#111"` dmenu background

`dmenu_color_selected_text="red"` dmenu highlighted line text color

`dmenu_color_selected_background="black"` dmenu highlighted line text background

`dmenu_font="Monospace-9"` dmenu font-name and font-size

`twitch_language="\"EN\""` choose which language you want for your streams, change to `""` for no preferred language

`keywords="python\|linux\|cpp"` streams containing these keywords are placed at the top of the list

`mpv_options=""` optional configurations to send with the mpv instance that opens the stream URL

`open_chat=""` yes OR `""`, if enabled this opens the streamer's chatroom in the browser specified below

`browser_choice="chromium-browser"` 

`browser_options="--new-window"` optional configurations to send with the browser instance that opens the chat URL

[browse_demo.webm](https://github.com/leafstrat/Twitch-Browser/assets/4014775/aa32571b-3724-40a2-8404-b861fe2f61e8)

