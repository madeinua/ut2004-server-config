This repository contains the ut2004.ini file, which is the heart of your Unreal Tournament 2004 server. Changing these settings affects how the game runs, how players connect, and how mods interact with the engine.

## UT2004.ini configuration

### Connection & Network

`Port=7877` This is the primary game server port. Players will connect using your IP and this port.

Example: `12.34.567.890:7877`

`RedirectToURL` This is crucial for "Fast Download" (Redirect). If a player joins and doesn't have the required maps or mods, the game will download them from this URL instead of the slow game port.

### Modding & Packages (Optional)

The following entries are context-dependent. They are only required if you have specific mods or mutators installed on your server.

#### ServerActors

These are scripts that run in the background of the server (e.g., announcers, unpause tools).

Example: `ServerActors=UnPause.UnPause`
Example: `ServerActors=MonsterAnnouncer.MA_ServerActor`

#### ServerPackages

These tell the server which files must be sent to the client (player) so they can see/hear modded content.

Example: `ServerPackages=UTCompv18bK`

### Server Identity & Security

`ServerName` The name that appears in the public server browser. Make it catchy.

`AdminName` The nickname of the server administrator.

`AdminPassword` Required. You must set this to log in as an administrator in-game (using the adminlogin command). Don't leave this blank if you want control over your server.

### Web Administration

You can manage your server through a browser using the built-in WebAdmin tool.

`ListenPort=8076` This defines the web interface port.

Access URL: `http://12.34.567.890:8076/ServerAdmin/`

Note: Ensure this port is open in your firewall to allow remote access.

### Security Note
* **Passwords:** Ensure you change `AdminPassword` in `[Engine.AccessControl]` immediately.
* **WebAdmin:** If you don't use the Web Interface, set `bEnabled=False` in `[UWeb.WebServer]`.
* **Access Control:** Keep your `xadmin.ini` file private as it contains administrative credentials.

### IMPORTANT
A Note on Customization:
Configuration in UT2004 is highly modular. Most parameters depend heavily on the specific mods, mutators, and game files installed. Each line should be reviewed individually when adding new content to ensure compatibility and stability.
