---
author: 
  name: "Henrique Oliveira"
title: Subscribe to Youtube RSS Feeds
date: 2024-09-04T22:18:37+02:00
type: "posts"
categories:
    - Programming
tags:
    - Python
    - YouTube
    - Videos
    - RSS
# math: katex
draft: false
---
## What is the main purpose?

I don't have the YouTube app installed on my Android devices (nor do I use it directl
so in order to watch my favourite channels, I use alternative front-ends such as
`LibreTube` and `NewPipe`.

### YouTube (Google) being an evil Corp

Recently, YouTube is making efforts to stop services such as Invidious and Piped
from working, and their later attempts (as of August 2024) are succeeding...
At least public-faced Piped instances are displaying `"Sign in to confirm that you're not a bot"`,
and videos are not being listed (at least with some of the creators I follow).

I can (and have been) using NewPipe, as it does not use a proxy (`Piped` or `Invidious` instances)
to load content, but the interface is not as neat as LibreTube's interface... and I'm a sucker for
good-looking interfaces (specially when in Android they have Material You support).

LibreTube team is very aware of this problem, but has no way of dealing with it...
So they created a way to circumvent and "directly fetch video playback information from
YouTube without using Piped", but as far as I can tell the updates on the channels are still from Piped.

> I'm not even going to start talking about the privacy concerns of loading videos directly
> from the YouTube servers...

### My plan

So I've learned that I can use RSS to discover newly released videos from my favourite channels,
and with that I get an update in my go-to Android RSS feed client `Read You` (YES, it does
support Material You).

So, as of now, I use RSS to get updates on the channels, and watch them on LibreTube.

## How to use RSS with YouTube channels

YouTube doesn't make it easy... they want you to use their ecosystem as much as possible,
so getting a RSS feed isn't as simple as copying a link.

This is a typical YouTube channel URL (Linus Tech Tips channel):
`https://www.youtube.com/channel/UCXuqSBlHAE6Xw-yeJA0Tunw`

And this is the URL compatible with RSS:
`https://www.youtube.com/feeds/videos.xml?channel_id=UCXuqSBlHAE6Xw-yeJA0Tunw`

So, as you've probably already figured out, the way to get this URL for RSS is to simply swap `/channel/`
with `/feeds/videos.xml?channel_id=`.


### Automation in the Importing Process

I could import all my channels into the RSS feed client by swapping the URL, but that can easily become a
very tedious process, so I created a way to automate this.

The core idea of this automation is to create a `.opml` file (used by RSS feed clients) with all the data
about the name of the feed, the URL, and other things...

#### Steps to Reproduce

1. I exported the subscriptions to a file (.json) - this works both in NewPipe or LibreTube
(export type: NewPipe).
2. Then I ran the script that follows.
3. Finally, I imported the .opml file (output of the script) into my RSS feed client app.
4. Enjoy YouTube subscriptions via RSS (until, I hope soon, Piped Team finds a way to circumvent
YouTube's attempts to block everything).

#### Python script

```python
import json
import xml.etree.ElementTree as ET

# Extracts channel ID from a YouTube URL
def extract_channel_id(url):
    if 'channel/' in url:
        return url.split('channel/')[-1]
    return None

# Creates the OPML tree structure from subscriptions
def create_opml(subscriptions):
    opml = ET.Element('opml', version='2.0')
    
    # Adding title
    ET.SubElement(ET.SubElement(opml, 'head'), 'title').text = 'YouTube Subscriptions RSS'
    body = ET.SubElement(opml, 'body')

    for sub in subscriptions:
        channel_id = extract_channel_id(sub['url'])
        if channel_id:  # Only include valid channel URLs
            rss_url = f"https://www.youtube.com/feeds/videos.xml?channel_id={channel_id}"
            ET.SubElement(body, 'outline', text=sub['name'], type='rss', xmlUrl=rss_url, htmlUrl=sub['url'])

    return ET.ElementTree(opml)

# Converts JSON to OPML format
def json_to_opml(json_file, opml_file):
    with open(json_file, 'r') as f:
        data = json.load(f)

    subscriptions = data.get('subscriptions', [])
    opml_tree = create_opml(subscriptions)

    with open(opml_file, 'wb') as f:  # Use 'wb' to ensure proper encoding
        opml_tree.write(f, encoding='UTF-8', xml_declaration=True)

# Example usage
json_to_opml('subscriptions.json', 'subscriptions.opml')
```

For running the code, modify the last line to specify the proper path and naming for the input and output files.
Then run: `python3 name-of-the-script.py`.

It will generate a .opml file that you can freely import into your RSS feed client of choice. :)