#CyanogenModOTA
A simple OTA REST Server for CyanogenMod OTA Updater System Application

##How to use
Just <code>git clone</code> this repo (or [download it](https://github.com/androidarmv6/CyanogenModOTA/archive/master.zip)) and upload all the files to your preferred directory on your server.

You just have to be sure that is running PHP and Memcached.

After, upload all your ZIP files that you get after you build the ROM on the <code>_builds, _deltas, _last</code> directory.

##and after?
Just follow the rest of the tutorial on [my personal blog post](http://blog.julianxhokaxhiu.com/entry/how-the-cm-ota-server-works-and-how-to-implement-and-use-ours) where I explain how to override the build server on your ROM.

##What about Debug?
I've implemented a [simple script made for NodeJS](https://github.com/julianxhokaxhiu/CyanogenModOTAUnitTest) that you clone and use it.

##Do you support Delta updates?
- YES! Diff here: [hudson](https://github.com/androidarmv6/hudson/compare/master...ota)
- build_env/envsetup.sh exports keys: export OTA_PACKAGE_SIGNING_KEY=build_env/keys/platform
- For more information: build/target/product/security/README

##Changelog
- 1.2.6: CMUpdater:only list updates for current channel. No more mix of channels. Remove unnecessary chars from device param.
- 1.2.5: Provide 25% stable build if all channels are requested, Update flight engine to v1.2.5
- 1.2.4: Update flight engine to v1.2
- 1.2.3: Final. Reduce memcache usage. Add example nginx config.
- 1.2.2: Offer new updates only if development or release channel is selected
- 1.2.1: Offer stable channel only if source_incremental provided
- 1.2: Allow incremental updates only for the same channel, Always include stable(release) channel
- 1.1.1.1: Final version, get timestamp from ro.build.date.utc
- 1.1.1: Performance improvements for md5sum
- 1.1: Add support for incremental changelog (limit param)
- 1.0: The first stable version
- 0.3: Enabled support for delta updates
- 0.2: Refactored a lot of code + boost MD5 calculation + added support for **Delta Updates** (<code>/api/v1/build/get_delta</code>)
- 0.1: First implementation of the server. Only the <code>/api</code> call is implemented right now.

Enjoy :)
