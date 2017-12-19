---
layout: page
title: Videos
permalink: /videos
---

{% assign video_data = site.data.videos %}

{% for video in video_data.playlists %}

{% if video.title %}
## Playlist: {{ video.title }}
{% endif %}
{% include youtubePlayer.html list=video.list %}
{% assign link = "https://www.youtube.com/playlist?list=" | append: video.list %}
#### **{% include external_link.html text='View on YouTube' link=link %}**
<br>

{% endfor %}


{% for video in video_data.videos %}

{% if video.title %}
## {{ video.title }}
{% endif %}
{% include youtubePlayer.html id=video.id notitle=true %}
{% assign link = "https://www.youtube.com/watch?v=" | append: video.id %}
#### **{% include external_link.html text='View on YouTube' link=link %}**
<br>

{% endfor %}