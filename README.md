SpotifyAPI-NET
==============

An API for the Spotify-Client, written in .NET  
Look at the example provided in the Repo


Following 3 files will be needed for all features:
+ SpotifyAPI.dll
+ Newtonsoft.Json.dll (Will be merged into SpotifyAPI.dll in the official Releases using ILMerge)
+ nircmd.dll (Used to Mute & UnMute Spotify)

Usage:
==============  
### SpotifyAPI
#####void Connect()
> Connects the SpotifyAPI to the Spotify Client (Needs to be called before making calls, Spotify has to run)

#####void Update()  
> Updates Information about Tracks etc.

#####void RunSpotify()
> Runs Spotify (Client has to run for API Calls)

#####void RunSpotifyWebHelper()
> Runs SpotifyWebHelper (Client has to run for API Calls)

#####static Boolean IsSpotifyRunning()
> Returns true, if Spotify is running

#####static Boolean IsSpotifyWebHelperRunning()
> Returns true, if SpotifyWebHelper is running

#####static Boolean IsValidSpotifyURL(String SpotifyURL)
> Returns true, if the provided Spotify URL is working (Not working yet)

#####MusicHandler GetMusicHandler()
> Returns the MusicHandler

#####EventHandler GetEventHandler()
> Returns the EventHandler

### SpotifyMusicHandler
#####void Play()  
> Play "button"

#####void Pause()
> Pause "button"

#####void Skip() 
> Skip Track

#####void Previous() 
> Previous Track

#####void SetTrack(String SpotifyURI)
> Plays the provided URI

#####double GetVolume()
> Returns the current volume (0.00 - 1.00)

#####Boolean IsAdRunning()
> Returns true, if an AD is running

#####double GetTrackPostion()
> Returns the current position of the Track

#####void Mute()
> Mutes Spotify (Requires nircmd.dll)

#####void UnMute()
> Unmutes Spotify (Requires nircmd.dll

#####Boolean IsPlaying() 
> Returns true, if Spotify is playing atm

#####Track GetCurrentTrack() 
> Returns the current Track

#####StatusResponse GetStatusResponse() 
> Returns the StatusResponse, which contains all Information gathered by the Call


### Track
#####String GetName()
> Returns Track-Name

#####String GetArtist()
> Returns Artist

#####String GetAlbum()
> Returns Album-name

#####String GetAlbumArtURL(AlbumArtSize size)
> Returns the URL of the Albumart based on the choosen size

#####Bitmap GetAlbumArt(AlbumArtSize size)
> Returns a Bitmap of the Albumart based on the choosen size

#####Bitmap GetAlbumArtAsync(AlbumArtSize size)
> Returns a Bitmap of the Albumart based on the choosen size asynchronously

### EventHandler
#####Event OnTrackChange 
> Triggered, when the Track gets changed

#####Event OnPlayStateChange
> Triggered, when Spotify's Play/Pause-State changes

#####Event OnVolumeChange
> Triggered, when the volume gets changed

#####Event TrackTimeChangeEventHandler
> Triggered, when the current trackposition changes

#####void ListenForEvents(Boolean listen)
> Should it listen for events?

#####void SetSynchronizingObject(ISynchronizeInvoke obj)
> Sets the synced object, so no Invoke is required (Events doesnt get called from the Main-Thread)
