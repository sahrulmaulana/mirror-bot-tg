This is a Telegram Bot written in Python for mirroring files on the Internet to your Google Drive or Telegram. Based on [python-aria-mirror-bot](https://github.com/lzzy12/python-aria-mirror-bot)

# Features:

## If you Like My work Star the repo and Follow me on Github

# Features:
## By [RyzXD](https://github.com/ryz-code)
- Mirror logs
- Leech logs
- Source link button
- Database Support for leech logs
- Sending Leeched files and Mirror links in user's PM
- Added Gdtot Support back
- Appdrive Support
- Change commands directly from config.env
- Auto Delete All Bot Related Message in AUTO_DELETE_UPLOAD_MESSAGE_DURATION duration
- View File in PM button
- Engine stats in status
- Statistics button in status
- 4 GB upload for Premium users
- BOT PM
- FORCE BOT PM
- Change Start buttons from config.env
- And many more little changes can't remember
## By [anasty17](https://github.com/anasty17)
In each single file there is a major change from base code, it's almost totaly different. Here some of features and fixes that I remember.
### qBittorrent
- Qbittorrent support
- Select files from Torrent before and while downloading
- Seed torrents to specific ratio and time
### Aria2c
- Select files from Torrent before and while downloading
- Seed torrents to specific ratio and time
- Netrc support
- Direct link authentication for specific link while using the bot (it will work even if only username or password)
- Improve aria.sh
- Fix all download listener functions and status
### Leech
- Leech support
- Splitting
- Thumbnail for each user
- Set upload as document or as media for each user
### Google
- Stop duplicates for all tasks except yt-dlp tasks
- Download G-Drive links
- Counting files/folders from Google Drive link
- Search in multiple Drive folder/TeamDrive
- Recursive Search (only with `root` or TeamDrive ID, folder ids will be listed with non-recursive method)
- Use Token.pickle if file not found with Service Account, for all Gdrive functions
- List result in html file instead of telegraph or telegram message to avoid limits by @junedkh
- Random Service Account at startup
### Status
- Clone Status
- Extract Status
- Archive Status
- Seed Status
- Status Pages for unlimited tasks
- Ability to cancel upload/clone/archive/extract/split
- Cancel all buttons for choosing specific tasks status to cancel
- Fix flooding issues
- Fix overall upload and download speed
### Yt-dlp
- Switch from youtube-dl to yt-dlp and fix all conflicts
- Yt-dlp quality buttons
- Support for download live streams
- Ability to use specific yt-dlp arg for each task
- Fix download progress
### Database
- SQL Database support
- Save leech settings including thumbnails in database
- Save sudo and authorized users
- Incomplete task notifier to get incomplete task messages after restart
### Torrents Search
- Torrent search support
- Search on torrents with Torrent Search API
- Search on torrents with variable plugins using qBittorrent search engine
### Archives
- Zip instead of tar
- Using 7-zip tool to extract all supported files
- Extract rar, zip and 7z within folder or splits with or without password
- Zip file/folder with or without password
### RSS
- Rss feed. Based on this repository [rss-chan](https://github.com/hyPnOtICDo0g/rss-chan)
- Filter added and all functions have been improved
### Overall
- Docker image support for linux `amd64, arm64/v8, arm/v7, s390x`
- Update bot at startup and with restart command using `UPSTREAM_REPO`
- Mirror/Leech/Watch/Clone/Count/Del by reply
- Mirror/Leech/Clone multi links/files with one command
- Custom name for all links except torrents. For files you should add extension except yt-dlp links
- Extensions Filter for the files to be uploaded/cloned
- View Link button. Extra button to open index link in broswer instead of direct download for file
- Almost all repository functions have been improved and many other details can't mention all of them
- Many bugs have been fixed

## From Base and other Repositories
- Mirror direct download links, Torrent, Mega.nz and Telegram files to Google Drive
- Copy files from someone's Drive to your Drive
- Download/Upload progress, Speeds and ETAs
- Mirror all youtube-dl supported links
- Docker support
- Uploading to Team Drive
- Index Link support
- Service Account support
- Delete files from Drive
- Multiple Trackers support
- Shell and Executor
- Add sudo users
- Extract password protected files
- Extract these filetypes
  > ZIP, RAR, TAR, 7z, ISO, WIM, CAB, GZIP, BZIP2, APM, ARJ, CHM, CPIO, CramFS, DEB, DMG, FAT, HFS, LZH, LZMA, LZMA2, MBR, MSI, MSLZ, NSIS, NTFS, RPM, SquashFS, UDF, VHD, XAR, Z, TAR.XZ
- Direct links Supported:
  >mediafire, letsupload.io, hxfile.co, anonfiles.com, bayfiles.com, antfiles, fembed.com, fembed.net, femax20.com, layarkacaxxi.icu, fcdn.stream, sbplay.org, naniplay.com, naniplay.nanime.in, naniplay.nanime.biz, sbembed.com, streamtape.com, streamsb.net, feurl.com, upload.ee, pixeldrain.com, racaty.net, 1fichier.com, 1drv.ms (Only works for file not folder or business account), uptobox.com and solidfiles.com

# How to deploy?

## Prerequisites

- Tutorial Video from A to Z:
  - Thanks to [Wiszky](https://github.com/vishnoe115)
 <p><a href="https://youtu.be/IUmq1paCiHI"> <img src="https://img.shields.io/badge/See%20Video-black?style=for-the-badge&logo=YouTube" width="160""/></a></p>

### 1. Installing requirements

- Clone this repo:
```
git clone https://github.com/sahrulmaulana/ryz-mirror-bot mirrorbot/ && cd mirrorbot
```
- For Debian based distros
```
sudo apt install python3 python3-pip
```
Install Docker by following the [official Docker docs](https://docs.docker.com/engine/install/debian/)

- For Arch and it's derivatives:
```
sudo pacman -S docker python
```
- Install dependencies for running setup scripts:
```
pip3 install -r requirements-cli.txt
```

------

### 2. Setting up config file

```
cp config_sample.env config.env
```
- Remove the first line saying:
```
_____REMOVE_THIS_LINE_____=True
```
Fill up rest of the fields. Meaning of each field is discussed below:

**1. Required Fields**

- `BOT_TOKEN`: The Telegram Bot Token that you got from [@BotFather](https://t.me/BotFather). `Str`
- `GDRIVE_FOLDER_ID`: This is the Folder/TeamDrive ID of the Google Drive Folder or `root` to which you want to upload all the mirrors. `Str`
- `OWNER_ID`: The Telegram User ID (not username) of the Owner of the bot. `Int`
- `DOWNLOAD_DIR`: The path to the local folder where the downloads should be downloaded to. `Str`
- `DOWNLOAD_STATUS_UPDATE_INTERVAL`: Time in seconds after which the progress/status message will be updated. Recommended `10` seconds at least. `Int`
- `AUTO_DELETE_MESSAGE_DURATION`: Interval of time (in seconds), after which the bot deletes it's message and command message which is expected to be viewed instantly. **NOTE**: Set to `-1` to disable auto message deletion. `Int`
- `AUTO_DELETE_UPLOAD_MESSAGE_DURATION`: Interval of time (in seconds), after which the bot deletes it's message and command message which is expected to be viewed instantly. **NOTE**: Set to `-1` to disable auto upload message deletion. `Int`
- `TELEGRAM_API`: This is to authenticate your Telegram account for downloading Telegram files. You can get this from https://my.telegram.org. `Int`
- `TELEGRAM_HASH`: This is to authenticate your Telegram account for downloading Telegram files. You can get this from https://my.telegram.org. `Str`

**2. Optional Fields**
- `BOT_PM`: - set it`True` if you want to send mirror links and leeched files in user's PM, Default is `False`.
- `FORCE_BOT_PM`: - set it `True` if True all mirrored links and leeched files will be send directly in PM, Mirrored links will not get sent in Current chat and source message will be deleted immediately after mirror/leech is complete, AUTO_DELETE_UPLOAD_MESSAGE_DURATION will not apply on it.
- `IS_TEAM_DRIVE`: Set `True` if uploading to TeamDrive. Default is `False`. `Bool`
- `DATABASE_URL`: Your SQL Database URL. Follow this [Generate Database](https://github.com/anasty17/mirror-leech-telegram-bot/tree/master#generate-database) to generate database. Data will be saved in Database: auth and sudo users, leech settings including thumbnails for each user, rss data and incomplete tasks. **NOTE**: If deploying on heroku and using heroku postgresql delete this variable from **config.env** file. **DATABASE_URL** will be grabbed from heroku variables. `Str`
- `AUTHORIZED_CHATS`: Fill user_id and chat_id of groups/users you want to authorize. Separate them by space. `Str`
- `SUDO_USERS`: Fill user_id of users whom you want to give sudo permission. Separate them by space. `Str`
- `IGNORE_PENDING_REQUESTS`: Ignore pending requests after restart. Default is `False`. `Bool`
- `USE_SERVICE_ACCOUNTS`: Whether to use Service Accounts or not. For this to work see [Using Service Accounts](https://github.com/anasty17/mirror-leech-telegram-bot#generate-service-accounts-what-is-service-account) section below. Default is `False`. `Bool`
- `INDEX_URL`: Refer to https://gitlab.com/ParveenBhadooOfficial/Google-Drive-Index. `Str`
- `STATUS_LIMIT`: Limit the no. of tasks shown in status message with buttons. **NOTE**: Recommended limit is `4` tasks. `Str`
- `STOP_DUPLICATE`: Bot will check file in Drive, if it is present in Drive, downloading or cloning will be stopped. (**NOTE**: File will be checked using filename not file hash, so this feature is not perfect yet). Default is `False`. `Bool`
- `CMD_INDEX`: commands index number. This number will added at the end all commands. `Str`
- `TORRENT_TIMEOUT`: Timeout of dead torrents downloading with qBittorrent and Aria2c in seconds. `Str`
- `EXTENSION_FILTER`: File extensions that won't upload/clone. Separate them by space. `Str`
- `INCOMPLETE_TASK_NOTIFIER`: Get incomplete task messages after restart. Require database and (supergroup or channel). Default is `False`. `Bool`
- `UPTOBOX_TOKEN`: Uptobox token to mirror uptobox links. Get it from [Uptobox Premium Account](https://uptobox.com/my_account).

### Update
- `UPSTREAM_REPO`: Your github repository link, if your repo is private add `https://username:{githubtoken}@github.com/{username}/{reponame}` format. Get token from [Github settings](https://github.com/settings/tokens). So you can update your bot from filled repository on each restart. `Str`.
  - **NOTE**: Any change in docker or requirements you need to deploy/build again with updated repo to take effect. DON'T delete .gitignore file. For more information read [THIS](https://github.com/anasty17/mirror-leech-telegram-bot/tree/master#upstream-repo-recommended).
- `UPSTREAM_BRANCH`: Upstream branch for update. Default is `master`. `Str`

### Mirror
- `MIRROR_LOGS`: - Chat id of channels/groups where you want to store Mirror logs, ***NOTE*** Add bot in Mirror logs channel/group as Admin.
- 
### Leech
- `LEECH_LOG`: - Chat id of channel/group where leeched files will be uploaded, **NOTE:** only put 1 channel/group id starts with -100xxxxxxxxx, ***NOTE*** add bot in that channel/group as Admin, if you leave this empty bot will sent leech files in current chat.
- `LEECH_SPLIT_SIZE`: Size of split in bytes. Default is `2GB`. Default is `4GB` if your account is premium. `Str`
- `AS_DOCUMENT`: Default type of Telegram file upload. Default is `False` mean as media. `Bool`
- `EQUAL_SPLITS`: Split files larger than **LEECH_SPLIT_SIZE** into equal parts size (Not working with zip cmd). Default is `False`. `Bool`
- `CUSTOM_FILENAME`: Add custom word to leeched file name. `Str`
- `USER_SESSION_STRING`: To download/upload from your telegram account. If you own premium account. To generate session string use this command `python3 generate_string_session.py` after mounting repo folder for sure. `Str`. **NOTE**: You can't use bot with private message. Use it with supergroup or channel.

### Telegraph ui
- `TITLE_NAME`: Title name for Telegraph pages (while using /list command)
- `AUTHOR_NAME`: = Author name for Telegraph pages
- `AUTHOR_URL`: = Author URL for Telegraph page

### GDTOT
- `CRYPT`: Cookie for gdtot google drive link generator. Follow these [steps](https://github.com/arshsisodiya/helios-mirror/tree/master#gdtot-cookies).

### Appdrive
- `APPDRIVE_EMAIL`: - Your Appdrive account email
- `APPDRIVE_PASS`: - Your Appdrive account password

### Size Limits
- `TORRENT_DIRECT_LIMIT`: To limit the Torrent/Direct mirror size. Don't add unit. Default unit is `GB`.
- `ZIP_UNZIP_LIMIT`: To limit the size of zip and unzip commands. Don't add unit. Default unit is `GB`.
- `CLONE_LIMIT`: To limit the size of Google Drive folder/file which you can clone. Don't add unit. Default unit is `GB`.
- `MEGA_LIMIT`: To limit the size of Mega download. Don't add unit. Default unit is `GB`.
- `STORAGE_THRESHOLD`: To leave specific storage free and any download will lead to leave free storage less than this value will be cancelled. Don't add unit. Default unit is `GB`.

### qBittorrent/Aria2c
- `BASE_URL_OF_BOT`: Valid BASE URL where the bot is deployed to use qbittorrent web selection. Format of URL should be `http://myip`, where `myip` is the IP/Domain(public) of your bot or if you have chosen port other than `80` so write it in this format `http://myip:port` (`http` and not `https`). This Var is optional on VPS and required for Heroku specially to avoid app sleeping/idling. For Heroku fill `https://yourappname.herokuapp.com`. Still got idling? You can use http://cron-job.org to ping your Heroku app. `Str`
- `SERVER_PORT`: Only For VPS, which is the **BASE_URL_OF_BOT** Port. `Str`
- `WEB_PINCODE`: If empty or `False` means no more pincode required while qbit web selection. `Bool`
  - **Qbittorrent NOTE**: If your facing ram exceeded issue then set limit for `MaxConnecs`, decrease `AsyncIOThreadsCount` in qbittorrent config and set limit of `DiskWriteCacheSize` to `32`.

### RSS
- `RSS_DELAY`: Time in seconds for rss refresh interval. Recommended `900` second at least. Default is `900` in sec. `Str`
- `RSS_COMMAND`: Choose command for the desired action. `Str`
- `RSS_CHAT_ID`: Chat ID where rss links will be sent. If using channel then add channel id. `Str`
- `RSS_USER_SESSION_STRING`: To send rss links from your telegram account. Instead of adding bot to channel then linking the channel to group to get rss link since bot will not read command from itself or other bot. To generate session string use this command `python3 generate_string_session.py` after mounting repo folder for sure. `Str`. **NOTE**: Don't use same session string as `USER_SESSION_STRING`.
  - **RSS NOTE**: `DATABASE_URL` and `RSS_CHAT_ID` is required, otherwise all rss commands will not work. You must use bot in group. You can add the bot to a channel and link this channel to group so messages sent by bot to channel will be forwarded to group without using `RSS_USER_STRING_SESSION`.

### Private Files
- `ACCOUNTS_ZIP_URL`: Only if you want to load your Service Account externally from an Index Link or by any direct download link NOT webpage link. Archive the accounts folder to ZIP file. Fill this with the direct download link of zip file. `Str`. If index need authentication so add direct download as shown below:
  - `https://username:password@example.workers.dev/...`
- `TOKEN_PICKLE_URL`: Only if you want to load your **token.pickle** externally from an Index Link. Fill this with the direct link of that file. `Str`
- `MULTI_SEARCH_URL`: Check `drive_folder` setup [here](https://github.com/anasty17/mirror-leech-telegram-bot/tree/master#multi-search-ids). Write **drive_folder** file [here](https://gist.github.com/). Open the raw file of that gist, it's URL will be your required variable. Should be in this form after removing commit id: https://gist.githubusercontent.com/username/gist-id/raw/drive_folder. `Str`
- `YT_COOKIES_URL`: Youtube authentication cookies. Check setup [Here](https://github.com/ytdl-org/youtube-dl#how-do-i-pass-cookies-to-youtube-dl). Use gist raw link and remove commit id from the link, so you can edit it from gists only. `Str`
- `NETRC_URL`: To create .netrc file contains authentication for aria2c and yt-dlp. Use gist raw link and remove commit id from the link, so you can edit it from gists only. **NOTE**: After editing .nterc you need to restart the docker or if deployed on heroku so restart dyno in case your edits related to aria2c authentication. `Str`
  - **NOTE**: All above url variables used incase you want edit them in future easily without deploying again or if you want to deploy from public fork. If deploying using cli or private fork you can leave these variables empty add token.pickle, accounts folder, drive_folder, .netrc and cookies.txt directly to root but you can't update them without rebuild OR simply leave all above variables and use private UPSTREAM_REPO.

### MEGA
- `MEGA_API_KEY`: Mega.nz API key to mirror mega.nz links. Get it from [Mega SDK Page](https://mega.nz/sdk). `Str`
- `MEGA_EMAIL_ID`: E-Mail ID used to sign up on mega.nz for using premium account. `Str`
- `MEGA_PASSWORD`: Password for mega.nz account. `Str`

### Buttons
- `VIEW_LINK`: View Link button to open file Index Link in browser instead of direct download link, you can figure out if it's compatible with your Index code or not, open any video from you Index and check if its URL ends with `?a=view`. Compatible with [BhadooIndex](https://gitlab.com/ParveenBhadooOfficial/Google-Drive-Index) Code. Default is `False`. `Bool`
- `SOURCE_LINK`: -  set it `True` if you want to get Source Link of Mirrored/Cloned file,  Default is `False`.
- 
### Torrent Search
- `SEARCH_API_LINK`: Search api app link. Get your api from deploying this [repository](https://github.com/Ryuk-me/Torrent-Api-py). `Str`
  - Supported Sites:
  >1337x, Piratebay, Nyaasi, Torlock, Torrent Galaxy, Zooqle, Kickass, Bitsearch, MagnetDL, Libgen, YTS, Limetorrent, TorrentFunk, Glodls, TorrentProject and YourBittorrent
- `SEARCH_LIMIT`: Search limit for search api, limit for each site and not overall result limit. Default is zero (Default api limit for each site). `Str`
- `SEARCH_PLUGINS`: List of qBittorrent search plugins (github raw links). I have added some plugins, you can remove/add plugins as you want. Main Source: [qBittorrent Search Plugins (Official/Unofficial)](https://github.com/qbittorrent/search-plugins/wiki/Unofficial-search-plugins). `Str`

------

### 3. Getting Google OAuth API credential file and token.pickle

**NOTES**
- Old authentication changed, now we can't use bot or replit to generate token.pickle. You need OS with a browser.
- Windows users should install python3 and pip. You can find how to install and use them from google or from this [telegraph](https://telegra.ph/Create-Telegram-Mirror-Leech-Bot-by-Deploying-App-with-Heroku-Branch-using-Github-Workflow-12-06) from [Wiszky](https://github.com/vishnoe115) tutorial.
- You can ONLY open the generated link from `generate_drive_token.py` in local browser.

1. Visit the [Google Cloud Console](https://console.developers.google.com/apis/credentials)
2. Go to the OAuth Consent tab, fill it, and save.
3. Go to the Credentials tab and click Create Credentials -> OAuth Client ID
4. Choose Desktop and Create.
5. Publish your OAuth consent screen App to prevent **token.pickle** from expire
6. Use the download button to download your credentials.
7. Move that file to the root of mirrorbot, and rename it to **credentials.json**
8. Visit [Google API page](https://console.developers.google.com/apis/library)
9. Search for Google Drive Api and enable it
10. Finally, run the script to generate **token.pickle** file for Google Drive:
```
pip3 install google-api-python-client google-auth-httplib2 google-auth-oauthlib
python3 generate_drive_token.py
```
------

## Deploying on VPS

**IMPORTANT NOTES**:
1. You must set `SERVER_PORT` variable to `80` or any other port you want to use.
2. To clear the container (this will not affect on the image):
```
sudo docker container prune
```
3. To delete the images:
```
sudo docker image prune -a
```
4. Check the number of processing units of your machine with `nproc` cmd and times it by 4, then edit `AsyncIOThreadsCount` in qBittorrent.conf.
5. You can add `CONFIG_FILE_URL` variable using docker and docker-compose, google it.

------

### Deploying on VPS Using Docker

- Start Docker daemon (SKIP if already running):
```
sudo dockerd
```
- Build Docker image:
```
sudo docker build . -t mirror-bot
```
- Run the image:
```
sudo docker run -p 80:80 mirror-bot
```
- To stop the image:
```
sudo docker ps
```
```
sudo docker stop id
```

----

### Deploying on VPS Using docker-compose

**NOTE**: If you want to use port other than 80, change it in [docker-compose.yml](https://github.com/anasty17/mirror-leech-telegram-bot/blob/master/docker-compose.yml) also.

```
sudo apt install docker-compose
```
- Build and run Docker image:
```
sudo docker-compose up
```
- After editing files with nano for example (nano start.sh):
```
sudo docker-compose up --build
```
- To stop the image:
```
sudo docker-compose stop
```
- To run the image:
```
sudo docker-compose start
```
- Tutorial video from Tortoolkit repo for docker-compose and checking ports
<p><a href="https://youtu.be/c8_TU1sPK08"> <img src="https://img.shields.io/badge/See%20Video-black?style=for-the-badge&logo=YouTube" width="160""/></a></p>

------

## Deploying on Heroku
<p><a href="https://github.com/anasty17/mirror-leech-telegram-bot/tree/heroku"> <img src="https://img.shields.io/badge/Deploy%20Guide-blueviolet?style=for-the-badge&logo=heroku" width="170""/></a></p>

------

# Extras

## Bot commands to be set in [@BotFather](https://t.me/BotFather)

```
mirror - or /m Mirror
zipmirror - or /zm Mirror and upload as zip
unzipmirror - or /uzm Mirror and extract files
qbmirror - or /qm Mirror torrent using qBittorrent
qbzipmirror - or /qzm Mirror torrent and upload as zip using qb
qbunzipmirror - or /quzm Mirror torrent and extract files using qb
leech - or /l Leech
zipleech - or /zl Leech and upload as zip
unzipleech - or /uzl Leech and extract files
qbleech - or /ql Leech torrent using qBittorrent
qbzipleech - or /qzl Leech torrent and upload as zip using qb
qbunzipleech - or /quzl Leech torrent and extract using qb
clone - Copy file/folder to Drive
count - Count file/folder of Drive
ytdl - or /y Mirror yt-dlp supported link
ytdlzip - or /yz Mirror yt-dlp supported link as zip
ytdlleech - or /yl Leech through yt-dlp supported link
ytdlzipleech - or /yzl Leech yt-dlp support link as zip
leechset - Leech settings
setthumb - Set thumbnail
status - Get Mirror Status message
btsel - select files from torrent
rsslist - or /rl List all subscribed rss feed info
rssget - or /rg Get specific No. of links from specific rss feed
rsssub - or /rs Subscribe new rss feed
rssunsub - or /rus Unsubscribe rss feed by title
rssset - or /rst Rss Settings
list - Search files in Drive
search - Search for torrents with API
cancel - Cancel a task
cancelall - Cancel all tasks
del - Delete file/folder from Drive
log - Get the Bot Log
shell - Run commands in Shell
restart - Restart the Bot
stats - Bot Usage Stats
ping - Ping the Bot
help - All cmds with description
```
------

## UPSTREAM REPO (Recommended)

- `UPSTREAM_REPO` variable can be used for edit/add any file in repository.
- You can add private/public repository link to grab/overwrite all files from it.
- You can skip adding the privates files like token.pickle or accounts folder before deploying, also no need to add variables direct links except **config.env**, simply fill `UPSTREAM_REPO` private one in case you want to grab all files including private files.
- If you added private files while deploying and you have added private `UPSTREAM_REPO` and your private files in this private repository, so your private files will be overwritten from this repository. Also if you are using URL variables like `TOKEN_PICKLE_URL` then all files from those variables will override the private files that added before deploying or from private `UPSTREAM_REPO`.
- If you filled `UPSTREAM_REPO` with the official repository link, then be carefull incase any change in requirements.txt your bot will not start after restart. In this case you need to deploy again with updated code to install the new requirements or simply by changing the `UPSTREAM_REPO` to you fork link with that old updates.
- In case you you filled `UPSTREAM_REPO` with your fork link be carefull also if you fetched the commits from the official repository.
- The changes in your `UPSTREAM_REPO` will take affect only after restart.
- `UPSTREAM_BRANCH` don't ever fill heroku here.

------

## Bittorrent Seed

- Add `d:ratio:time` perfix along with leech or mirror cmd.
- Using `d` perfix alone will lead to use global options for aria2c or qbittorrent.

### Qbittorrent
- Global options: `MaxRatio` and `GlobalMaxSeedingMinutes` in qbittorrent.conf, `-1` means no limit, but you can cancel manually.
  - **NOTE**: Don't change `MaxRatioAction`.

### Aria2c
- Global options: `--seed-ratio` (0 means no limit) and `--seed-time` (0 means no seed) in aria.sh.

------

## Using Service Accounts for uploading to avoid user rate limit

>For Service Account to work, you must set `USE_SERVICE_ACCOUNTS` = "True" in config file or environment variables.
>**NOTE**: Using Service Accounts is only recommended while uploading to a Team Drive.

### 1. Generate Service Accounts. [What is Service Account?](https://cloud.google.com/iam/docs/service-accounts)
Let us create only the Service Accounts that we need.

**Warning**: Abuse of this feature is not the aim of this project and we do **NOT** recommend that you make a lot of projects, just one project and 100 SAs allow you plenty of use, its also possible that over abuse might get your projects banned by Google.

>**NOTE**: If you have created SAs in past from this script, you can also just re download the keys by running:
```
python3 gen_sa_accounts.py --download-keys $PROJECTID
```
>**NOTE:** 1 Service Account can upload/copy around 750 GB a day, 1 project can make 100 Service Accounts so you can upload 75 TB a day or clone 2 TB from each file creator (uploader email).

#### Two methods to create service accounts
Choose one of these methods

##### 1. Create Service Accounts in existed Project (Recommended Method)
- List your projects ids
```
python3 gen_sa_accounts.py --list-projects
```
- Enable services automatically by this command
```
python3 gen_sa_accounts.py --enable-services $PROJECTID
```
- Create Sevice Accounts to current project
```
python3 gen_sa_accounts.py --create-sas $PROJECTID
```
- Download Sevice Accounts as accounts folder
```
python3 gen_sa_accounts.py --download-keys $PROJECTID
```

##### 2. Create Service Accounts in New Project
```
python3 gen_sa_accounts.py --quick-setup 1 --new-only
```
A folder named accounts will be created which will contain keys for the Service Accounts.

### 2. Add Service Accounts

#### Two methods to add service accounts
Choose one of these methods

##### 1. Add Them To Google Group then to Team Drive (Recommended)
- Mount accounts folder
```
cd accounts
```
- Grab emails form all accounts to emails.txt file that would be created in accounts folder
- `For Windows using PowerShell`
```
$emails = Get-ChildItem .\**.json |Get-Content -Raw |ConvertFrom-Json |Select -ExpandProperty client_email >>emails.txt
```
- `For Linux`
```
grep -oPh '"client_email": "\K[^"]+' *.json > emails.txt
```
- Unmount acounts folder
```
cd ..
```
Then add emails from emails.txt to Google Group, after that add this Google Group to your Shared Drive and promote it to manager and delete email.txt file from accounts folder

##### 2. Add Them To Team Drive Directly
- Run:
```
python3 add_to_team_drive.py -d SharedTeamDriveSrcID
```
------

### Generate Database

**1. Using Railway**
- Go to [railway](https://railway.app) and create account
- Start new project
- Press on `Provision PostgreSQL`
- After creating database press on `PostgresSQL`
- Go to `Connect` column
- Copy `Postgres Connection URL` and fill `DATABASE_URL` variable with it

**2. Using Heroku PostgreSQL**
<p><a href="https://dev.to/prisma/how-to-setup-a-free-postgresql-database-on-heroku-1dc1"> <img src="https://img.shields.io/badge/See%20Dev.to-black?style=for-the-badge&logo=dev.to" width="160""/></a></p>

**3. Using ElephantSQL**
- Go to [elephantsql](https://elephantsql.com) and create account
- Hit `Create New Instance`
- Follow the further instructions in the screen
- Hit `Select Region`
- Hit `Review`
- Hit `Create instance`
- Select your database name
- Copy your database url, and fill `DATABASE_URL` variable with it

------

## Multi Search IDs
To use list from multi TD/folder. Run driveid.py in your terminal and follow it. It will generate **drive_folder** file or u can simply create `drive_folder` file in working directory and fill it, check below format:
```
DriveName folderID/tdID or `root` IndexLink(if available)
DriveName folderID/tdID or `root` IndexLink(if available)
```
-----

## Yt-dlp and Aria2c Authentication Using .netrc File
For using your premium accounts in yt-dlp or for protected Index Links, create .netrc file according to following format:

**Note**: Create .netrc and not netrc, this file will be hidden, so view hidden files to edit it after creation.

Format:
```
machine host login username password my_password
```
Example:
```
machine instagram login anas.tayyar password mypassword
```
**Instagram Note**: You must login even if you want to download public posts and after first try you must confirm that this was you logged in from different ip(you can confirm from phone app).

**Youtube Note**: For `youtube` authentication use [cookies.txt](https://github.com/ytdl-org/youtube-dl#how-do-i-pass-cookies-to-youtube-dl) file.

Using Aria2c you can also use built in feature from bot with or without username. Here example for index link without username.
```
machine example.workers.dev password index_password
```
Where host is the name of extractor (eg. instagram, Twitch). Multiple accounts of different hosts can be added each separated by a new line.

-----
