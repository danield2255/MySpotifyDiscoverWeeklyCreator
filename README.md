# Spotify Discover Playlist Creator By Genre
This is a collection of notebooks that will create 'Discover Weekly' style playlists for your Spotify account based on the top genres you listen to, creating **one playlist per genre.** This solves the problem of listening to many different genres of music, but only having one discover weekly playlist that is trying to account for all of your recent listening. If you listen to drastically different genres for different listening purposes, your discover weekly might not reflect any of those particular genres the best that they can. This repository solves the problem by tracking your listening, taking note of the genres you listened to, and delivering playlists which try to have songs similar to the kinds of you listened to by genre. 

The notebooks in this repo use the LastFM API and the Spotify API. LastFM is needed because it can track listening over time, and also has genre tags attached to song tracks. Spotify has limited ability to get recent listening (only 50 songs back) and does not provide genre labels to songs. 

To be able to run some of the wrapper functions which call Spotipy functions, you will need the Spotipy package installed. Instructions on how to get it are [here](https://spotipy.readthedocs.io/en/2.16.1/#installation). 

## Instructions
1. First we need LastFM to start tracking our listening on Spotify. Follow [this guide](https://community.spotify.com/t5/Spotify-Answers/How-can-I-connect-Spotify-to-Last-fm/ta-p/4795301) to connect LastFM to Spotify. Now just listen to music as you usually do! (Think about waiting about a week to let LastFM to collect your listening data, but it will now track your listening from now on) 

2. Sign up for a 'Spotify for Developers' account at https://developer.spotify.com/dashboard/
- Navigate to your dashboard and select "Create an app".
- Create your app with a name and description. This is just to get the Spotify API credentials. 

3. Save your Client ID and Client Secret ID as environment variables as "spotifyClientId" and "spotifyClientSecret" on your computer. Or you can save them to paste into the notebooks if you prefer
- [Instructions to set environment variables on Windows](https://docs.oracle.com/en/database/oracle/r-enterprise/1.5.1/oread/creating-and-modifying-environment-variables-on-windows.html#GUID-DD6F9982-60D5-48F6-8270-A27EC53807D0)
- [Instructions to set environment variables on Mac](https://medium.com/@youngstone89/setting-up-environment-variables-in-mac-os-28e5941c771c)

4. Get LastFM API credentials at https://secure.last.fm/login?next=/api/account/create
- Repeat step 3 to save in your environment as "LAST_FM_USER_AGENT" and "LAST_FM_KEY"

5. Run the cells of "LastFmDataRetrieval.ipynb" in order to get your listening data in a csv file. 

6. Run the cells of "SpotifyDiscoverWeeklyByGenre.ipynb" in order to create the new playlists in your Spotify account. 

There are a few extra notebooks for some insights on your listening on Spotify, but they don't add any data or any content to Spotify. 

Hope you enjoy the playlists you get! 
