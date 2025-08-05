# Retirement of this cordova-plugin-youtube-video-player fork

**Announcement**: As of August 2025, active development of my fork of `cordova-plugin-youtube-video-player` has ceased. This repository is no longer maintained, at this present time, and I don't recommend using this plugin for new projects due to the following issues:

- **Unreliable Functionality**: The plugin encounters YouTube URL errors, likely due to outdated dependencies (e.g., `YouTubeAndroidPlayerApi.jar`, `XCDYouTubeKit`).
- **Compatibility Issues**: It compiles with Node.js 18 but fails with Node.js 20, which is required by modern frameworks like Capacitor 7.0.0 and will be the way moving forward in the distant future.
- **Lack of Maintenance**: The plugin is no longer actively updated, making it unsuitable for modern Android (API 34+) and iOS applications.
- **Lack of Maintenance**: I don't have time, and there is a better alternative for the moment.

## Recommended Alternative: @capacitor/app-launcher

I would recommend switching to `@capacitor/app-launcher` for opening YouTube videos in the native YouTube app (or a browser fallback). Benefits include:
- Compatibility with modern Capacitor projects (Node.js 20+, Android 14, iOS).
- Support for YouTube Premium features (ad-free playback, background play) when users are logged in.
- Seamless app return using deep links.
- Simplified setup with minimal dependencies.

### Installation
```bash
npm install @capacitor/app-launcher
npx cap sync
```

For more information: https://capacitorjs.com/docs/apis/app-launcher

------------------------

And now for the original notice.....

# Cordova YoutubeVideoPlayer Plugin

This has been updated to work for Ionic 6 as at 2022 April 25th.

I'm taking not credit for these changes, but needed to find a solution that was going to work for me. Others may find it helpful though.

You can read more of the process in getting to these updates here:
https://stephenmonro.wordpress.com/2022/04/13/getting-youtube-videos-to-play-again-in-ionic5/

Specific updates for Ionic 6.

## Installation - Updated for 2022

```sh
cordova plugin add https://github.com/vrdriver/CordovaYoutubeVideoPlayer
```

## Simple Usage for Angular

The Usual imports for your module and ts files:

```import { YoutubeVideoPlayer } from '@ionic-native/youtube-video-player/ngx';```

The addition for your constructor:

```constructor( public youtube:YoutubeVideoPlayer ) {}```

Then, in your TS file, use this code to play a video:

```this.youtube.openVideo('dQw4w9WgXcQ');   //opens video with videoId```
   

## Other information from the original fork

**Play Youtube Videos in a native Video Player on Android &amp; iOS.**
**This fork works on Android 6, and does not force landscape mode on Android.**


Original iOS plugin uses **XCDYouTubeKit** by Cédric Luthi:  
https://github.com/0xced/XCDYouTubeKit

This repository now uses updated code at: https://github.com/vrdriver/XCDYouTubeKit

Android version (up to 4.4) uses **OpenYoutubeActivity** by Keyes Labs:  
https://code.google.com/p/android-youtube-player

Android version (5.0+) uses YouTube Android Player API:
https://developers.google.com/youtube/android/player/reference/com/google/android/youtube/player/YouTubePlayer

Android with YouTube App Version 111662130 requires a workaround to resolve an App issue:
https://code.google.com/p/gdata-issues/issues/detail?id=8244



## Usage

```javascript
YoutubeVideoPlayer.openVideo('YOUTUBE_VIDEO_ID', function(result) { console.log('YoutubeVideoPlayer result = ' + result); });
```

For Android 5.0+ you will need to add the following to config.xml

```xml
<preference name="YouTubeDataApiKey" value="[YOUR YOUTUBE API]" />
```
with your own YouTube Key.

If you are using Capacitor, you'll potentially get a gradle error that will leave after you open the project and gradle files are built. The other thing is that you may need to add the following line to your Android project:
Android/local.properties:

    YOUTUBE_API_KEY="YOUR_YOUTUBE_API_KEY"


 For more information: https://developers.google.com/youtube/v3/getting-started

The callback is called when the video window is closed.  (Work in Progress - should be working for IOS).

## Original Authors

**Adrien Glitchbone**

+ [https://twitter.com/glitchbone](https://twitter.com/glitchbone)
+ [http://github.com/Glitchbone](http://github.com/Glitchbone)

**d0cz**
+ [http://github.com/d0cz](http://github.com/d0cz)

**trakout**
+ [https://github.com/trakout](https://github.com/trakout)

## License

CordovaYoutubeVideoPlayer is available under the MIT license. See the [LICENSE](LICENSE) file for more information.  
XCDYouTubeKit is available under the MIT license.  
OpenYoutubeActivity is available under the Apache License 2.0.  
