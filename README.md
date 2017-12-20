# react-native-vlc

### Add it to your project

Add "react-native-vlc": "https://github.com/bavuvanet/react-native-vlc.git" in package.json
Run yarn install

#### iOS

- add `pod 'MobileVLCKit-unstable', '3.0.0a44'` in Podfile
- `pod install` inside ./ios/ folder
- `rnpm link react-native-vlc-player`
- also you must disable bitcode option in target build settings
- also you must add `libstdc++.6.0.9.tbd` to `Linked Framework and Libraries`

#### Android

- in settings.gradle change:

  `new File(rootProject.projectDir, '../node_modules/react-native-vlc-player/android')`

  to

  `new File(rootProject.projectDir, '../node_modules/react-native-vlc-player/android/vlc')`
- in *MainApplication.java* you need to import `com.rusmigal.vlcplayer.VLCPlayerPackage` instead of `com.vlcplayer.VLCPlayerPackage`

## Usage

```
<VLCPlayer
    ref='vlcplayer'
    paused={this.state.paused}
    style={styles.vlcplayer}
    source={{uri: this.props.uri, initOptions: ['--codec=avcodec']}}
    onVLCProgress={this.onProgress.bind(this)}
    onVLCEnded={this.onEnded.bind(this)}
    onVLCStopped={this.onEnded.bind(this)}
    onVLCPlaying={this.onPlaying.bind(this)}
    onVLCBuffering={this.onBuffering.bind(this)}
    onVLCPaused={this.onPaused.bind(this)}
 />

```
### Properties
source.initOptions - only for iOS
rate - only for iOS
snapshotPath - only for iOS

### Callbacks
onBuffering - only for iOS

## Static Methods

`seek(seconds)`

```
this.refs['vlcplayer'].seek(0.333);
```

`snapshot(path)`

```
this.refs['vlcplayer'].snapshot(path);
```
