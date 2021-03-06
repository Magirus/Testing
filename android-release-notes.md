#Android Release Not1.26.0.39969 

##3rd Party SDK Versions

    Millennial 5.0.1 
    Inmobi 3.7.0
    Greystripe 2.2.0
    Admob 6.4.1
    JumpTap 2.5.0
    
##1.30

**1.30.0.43294**

###Public API Changes
None.

###Updated Ad Networks
None.
	
###Additional Notable Changes
- Fixed the position of the skip option for videos
- Fixed HTML5 videos only playing audio
- Fixed incorrect order of callbacks for house/direct interstitial ads
- Increased COPPA compliance with Admob update

##1.29

**1.29.0.42664**

###Public API Changes
None.

###Updated Ad Networks
None.
	
###Additional Notable Changes
- Added eCPM floors for Admob
- Fixed bug where mraid interstitial can't return application to portrait mode after forceOrientation
- Fixed bug where Millennial banners didn't display properly on tablets
- Introduced ability to show image interstitial ads as view overlay based interstitials with translucent background.  

##1.28

**1.28.0.42252**

###Public API Changes
None.

###Updated Ad Networks
None.
	
###Additional Notable Changes
- Fixed bug where NullPointerException due to not being able to start activity would cause fatal crash in app
- Fixed bug where BurstlyAnimatedBanner would not refresh on certain instances
- Fixed bug where ads would not show on device in spite of valid proxy responses
- Fixed bug where images were not scaling down like they did in SDK version 1.26
- Improved BurstlyBaseScriptAdaptor class by removing separation from Banner and Interstitial instances
- Fixed bug where new ads were requested while offerwall was being displayed
- Improved third party network integration by removing ThirdPartyLifecycle adaptor class

##1.27

**1.27.0.40928**

###Public API Changes
None.

###Updated Ad Networks
Greystripe 2.1.0 -> 2.2.0  
Millennial 4.6.0 -> 5.0.1  
JumpTap 2.4.1.2 -> 2.5.0.0
	
###Additional Notable Changes
- Resolved issue where close button was hidden in landscape for video offers
- Resolved issue where video offers were not visible when launched from GL View
- Fixed bug with retina feed banners not resizing properly
- Fixed bug where incorrect zone ID could potentially be sent for tracking impressions
    
##1.26

**1.26.0.39778**

###Public API Changes
None.

###Updated Ad Networks
Inmobi 3.6.2 -> 3.7.0
	
###Additional Notable Changes
- Stability improvements and code optimizations
    
##1.25

**1.25.0.38784**

###Public API Changes
None.

###Updated Ad Networks
None.
	
###Additional Notable Changes
- Added version number to crash logs
- Improved logging for debug purposes

##1.24

**1.24.0.38159**

###Public API Changes
None.

###Updated Ad Networks

Inmobi 3.6.0 -> 3.6.2  
Admob 6.3.1 -> 6.4.1
	
###Additional Notable Changes
- Resolved ClassCastException affecting custom decorators used on offerwalls
- Fixed auto-caching re-request loop on empty zones
- Improved stability with Admob update
- Passing network name for server side partners in event listeners
- Log warnings when ads refresh when a banner is not visible
- BurstlyView ID/Name no longer required to be unique

##1.23

**1.23.0.37501**

###Public API Changes

- Exposed method ***setLayoutParams()*** on BurstlyBanner/BurstlyAnimatedBanner view objects

###Updated Ad Networks

Greystripe 2.0.1 -> 2.1.0  
Admob 6.3.0 -> 6.3.1
	
###Additional Notable Changes
- Fixed issue with view-based interstitials not obeying the Activity's orientation
- Added handling for several low occurrence null pointer exceptions
- Fixed bug with Inmobi interstitials not tracking clicks
- Fixed issues affecting android 3.2.1 users on missing currency page
- Fixed issue with open gl context loss for view-based interstitials
- Updated Admob to fix null pointer exception crash

##1.22

**1.22.0.36712**

###Public API Changes
- Allow to pass in custom params to 3rd party SDKs using method

        setCustomParamsForNetwork(String networkName, Map<String, ?> params);
- Deprecated old API methods 

###Updated Ad Networks
None.

###Additional Notable Changes
- Performance improvements and minor bug fixes  
       
##1.21

**1.21.0.36510**

###Public API Changes
- Added JUMPTAP to BurstlyIntegrationModeAdNetworks
- Moved com.burstly.conveniencelayer package into com.burstly.lib package

###Updated Ad Networks
JumpTap 2.1.11.1 -> 2.4.1.2  
Admob 6.2.1 -> 6.3.0  

###Additional Notable Changes
- Updated Auto-caching to cache interstitials when created
- Fixed bug with volume buttons closing interstitials 
- Fixed bug with javascript methods not being called on version 4.2+ devices for apps that were compiled with target version set to 17+
- Fixed bug for clicks not being tracked for script ads
- Fixed MRAID 2.0 bug: Custom close button does not work in expanded container with custom width and height
- Added log warning for incorrect zone requests based on ad-type
- Minor bug fixes
    
##1.20

**1.20.0.35106**

###Public API Changes
None.

###Updated Ad Networks
None.

###Additional Notable Changes
- Fixed Null Pointer crash when OS kills backgrounded app on interstitial display
- onHide callback now being called for interstitials
- Fixed dismiss full screen callback called twice for OfferWalls bug
- Fixed adSize big that caused no fill for newly created zones
- Fixed bug allowing you to click banner multiple times
- Clicking visit site during video ad will launch site immediately instead of waiting for video to conclude
- Fixed incorrect order of callbacks for cached ORMA/MRAID interstitials 
- Renamed Jackson JSON library to avoid naming conflicts
- Skip button on videos now displayed from the beginning of video if the video is destination of another ad
- Fixed bug for getChange and getOldBalance when didUpdate currency callback is triggered by increaseBalance or decreaseBalance method
    
##1.19

**1.19.0.34236**

###Public API Changes
IDecorator interface has changed to allow script caching, therefore a new method is used to decorate script creatives. The following method was added:
  
    View decorate(View adView, IOverlayContainer shownOverlay);
    
Instead of calling activity.finish() upon clicking your close button, you must use: 
	
	shownOverlay.hideOverlayed();
	
###Updated Ad Networks
None.

###Additional Notable Changes
- Refactor script creatives to be shown as a view instead of Activity based representation
- Implement default Close Decorator
- Implement prefetching for MRAID
- Re implement decorator for new script interstitials implementation
- Fixed video player crash on kindle fire gen 1
- Move download tracking into Burstly.init method
- Fixed videos stop displaying when suspend bug
- Video creatives muted when the device is silenced to vibrate mode

##1.18

###Public API Changes
Added support for multiple currencies on SDK level. These changes affect ICurrencyListener callabacks and the currency manager increaseBalance, decreaseBalance, and getBalance methods. See [Android Rewards Currency Management](http://quickstart.skyrocketapp.com/android-guide#Rewards-Currency-Management) for more info.

###Updated Ad Networks
InMobi 3.5.3 -> 3.6.0

###Additional Notable Changes
- Bug Fix: There are no callbacks 'PresentFullScreen and DismissFullScreen' after clicked House/Direct text with destination type 'video' and 'website'
- Bug Fix: There are no callbacks 'adNetworkPresentFullScreen/adNetworkDismissFullScreen' for Ormma ad
- Bug Fix: There is no onHide() callback in Show Precached flow for ORMMA and MRAID
- Bug Fix: There are no Present and Dismiss callbacks for Millennial and InMobi
- Bug Fix: Ormma interstitial incorrectly displayed after rotation
- Implement MRAID 2.0
- Will not show visit site button if no click link is provided
- InMobi Android Jelly Bean SDK Update

##1.17

###Public API Changes
None.

###Updated Ad Networks
Smaato removed  
Greystripe 2.0-> 2.0.1  
AdMob 6.0.1->6.2.1  

###Additional Notable Changes
- MRAID 1.0 Support

##1.16
###Manifest Changes
The BurstlyFullscreenActivity manifest entry now requires the "configChanges" flag "screenSize".  The new activity entry should look like this:

        <!-- Burstly ================================================= -->
        <activity
            android:name="com.burstly.lib.component.networkcomponent.burstly.BurstlyFullscreenActivity"
            android:configChanges="keyboard|keyboardHidden|orientation|screenSize"
            android:theme="@android:style/Theme.NoTitleBar.Fullscreen" />

In addition Greystripe has changed their manifest entry to be the following:

        <!-- Greystripe ============================================== -->
        <activity
            android:name="com.greystripe.sdk.GSFullscreenActivity"
            android:configChanges="keyboard|keyboardHidden|orientation" />

And Millenial's Activity tags should look like:

        <!-- Millenial ================================================= -->       
        <activity 
            android:name="com.millennialmedia.android.MMActivity" 
            android:theme="@android:style/Theme.Translucent.NoTitleBar"
            android:configChanges="keyboardHidden|orientation|keyboard"/>
        <activity android:name="com.millennialmedia.android.VideoPlayer" 
            android:theme="@android:style/Theme.NoTitleBar.Fullscreen"
            android:configChanges="keyboardHidden|orientation|keyboard"/>

###Public API Changes
None.

###Updated Ad Networks
Medialets SDK removed  
Greystripe 1.6.1-> 2.0  
Inmobi 3.5.0 -> 3.5.3  

###Additional Notable Changes
- Millenial adNetworkDismissFullScreen fix  
- Rare BurstlySdk.shutDown crash fix  
- Rewards Wall user experience improvements  
