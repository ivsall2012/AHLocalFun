This app is on AppStore [LocalFun](https://itunes.apple.com/us/app/localfun/id1203165607?ls=1&mt=8)

You can use this app to post short audio/video on a map within certain ranges based on your current location. 
My main idea is to help people expose themselves to their environments through some funny audios and videos.

Test Account: localFunTestUserFB@gmail.com
Password: localfuntestuserfb
<img src="https://github.com/ivsall2012/AHLocalFun/blob/master/ScreenShot_2.png">


### Demo
This demo is showing you the debug version of the app which can generate fake datas: https://youtu.be/N16goXMKiAc (3 minutes)

Some explanation for buttons on the screen:

Bottom left corner: The earth-liked icon is for “My Posts" which you can see your own posts and some settings.

Bottom middle: You can record audios and videos in there.

Botton right corner: Navigate user location again and fetch data based on new location.

Pay attention to the top of the screen. There are two layers on the map: one is “Small” level which shows posts within 1.5 miles centered to you, the other “Huge” level is for posts within 3 miles. And those two levels don’t share same posts.  


### A Few Words
For me, this project is really big. From idea resorting, how to place buttons, what icons to use, map and small/huge two-layer geo searches, networking, server and particularly audio and video recording/playing stuff. Then the app was rejected three times by AppStore and they asked me provide Terms && Services, Privacy Policy and Rules in the app to prevent sensitive contents, which was a lot of work.

It was a marathon! I’m glad I made it!!

### Tech Stack
1. For media manipulation: Audio Engine(pitch shift) and other AVFoundation classes. Plus SCRecorder for video recording and its video filters.
2. For database and server: I use Firebase to store all users’ data and fetch contents by geolocations. All local datas are stored in CoreData.
3. For the map, I use Apple’s map — it’s prettier than Google Map.

### What can this app do specifically?
1. Audio and video recording. 
    1. For audio, you have 8 seconds and turn it into a high pitch chipmunk or low pitch Darth Vader(Batman?) or yourself. For video, it’s standard, though with some filters. I didn’t implement the recorder from ground up. I use SCRecorder which is a wrapper of AVFoundation. But still, it took up a large portion of the development time!
2. Display those user-generated contents. 
    1. The map on the app, has two layers. One is called “Small”, the other is “Huge”, which represents 1.5 miles and 3 miles radiuses of content display areas centered to your location.
    2. Each layer can display 15 contents at a time. If you finish playing a content, then it will be removed from your map and fill up with an older content.
    3. All posts will be expired after two days.
    4. If you wanna skip and play much older contents, you can shake it off and older contents will fill up automatically
    5. For each content, it’s displayed with user’s Facebook avatar(you can only login with Facebook)
3. Play those contents.
    1. When you press any of those people’s face(their Facebook avatar) on the map, you can play either an audio or video.
    2. You can like the post and check who likes them.
    3. Or you can block the user by pressing the middle bars-icon while you’re playing it.
4. See your posts.
    1. You can see your posts at “My Posts” by clicking the earth-liked icon on the bottom left corner.
    2. And you can delete your own post delete them too.
    3. You can also check the Terms && Services, Privacy Policy and unblock users by pressing the gear icon on the top right corner.
