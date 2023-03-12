## Yamaha Custom
The official integration for older yamaha network receivers does not implement play_media for anything that 
is not network radio. Since I like to automatically set it to play music from a server, I copied the code 
over and made it a custom integration. I also pull my own version of rxv (the library doing all the actual 
work on talking with the receiver) because you have to specify a song when you start a playlist with the 
original version.

Configuration wise it should be able to do what the official documentation says, but I did keep the old volume logic in 
because the new one refused to work with my receiver.

````
media_player:
- platform: yamaha_custom
  name: "Yamaha Receiver"
  host: 123.0.0.1
  volume_min: -80.0
  volume_max: 16.5
  source_ignore:
    - "AUX"
    - "AV1"
  source_names:
    AV4: "PC Audio"
````