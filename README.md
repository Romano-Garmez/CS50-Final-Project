# Harvard CS50 Final Project: Spotify Status
#### Video Demo: https://youtu.be/Yc1qeze1bso

#### Description:
A web app to display your currently playing song on Spotify. Allows you to skip songs, play/pause, and like/unlike. Analyzes album artwork to choose background and foreground color to match the image. Polls every two seconds to refresh the display to show your currently playing song. Scales to the size of your display using dynamic layout.

![Always This Late](https://i.imgur.com/iub38zU.jpg)

![Swim](https://i.imgur.com/HElS7Fv.jpg)

![R U Mine?](https://i.imgur.com/p05nO9v.jpg)

### Implementation:
I started my project by setting up a basic site to show raw JSON of my Spotify data utilizing [Spotipy](https://github.com/plamere/spotipy), an open source Spotify Python API. Later on, I wrote some javascript to poll the Spotify API every two seconds to check for changes. If the song has changed, the page is refreshed with the new info.

I compute the color palette using a javascript library called [ColorThief](https://github.com/lokesh/color-thief) which grabs the dominant color for the background, and a contrasting alternate color from the palette for the text. 

I use [Google Material Symbols](https://material.io/blog/introducing-symbols) for the playback control icons. This allows for easy scaling to different screen sizes without needing separate images.

### Files:
* app.py: Python code for Flask server. Backend, logs you in, polls Spotify API
* static/styles.css: Visual customizations, uses Bootstrap
* templates/currently_playing.html: Main web page, shows album art, song details and playback controls
* templates/layout.html: Template page, imports Bootstrap, runs polling code
* templates/login.html: Sign-in page
* templates/not_playing.html: Displayed if no song currently playing
