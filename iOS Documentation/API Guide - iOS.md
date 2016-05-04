#iOS API Guide

Table Of Contents
<!-- TOC depth:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [ooVooClient Interface](#oovooclient-interface)
	- [sharedInstance](#sharedinstance)
	- [setLogger](#setlogger)
	- [setLogLevel](#setloglevel)
	- [applicationDidEnterBackground](#applicationDidEnterBackground)
	- [applicationWillResignActive](#applicationWillResignActive)
	- [applicationWillEnterForeground](#applicationWillEnterForeground)
	- [applicationDidBecomeActive](#applicationDidBecomeActive)
	- [authorizeClient](#authorizeclient)
	- [getSdkVersion](#getsdkversion)
	- [isSslVerifyPeer](#issslverifypeer)
	- [IsAuthorized](#isauthorized)
	- [ApplicatioToken](#applicatiotoken)
	- [Account](#account)
	- [AVChat](#avchat)
	- [Messaging](#messaging)
	- [PushService](#pushservice)
	- [ooVooClientLogger](#oovooclientlogger)
		- [onLog](#onlog)
- [ooVooAccount](#oovooaccount)
	- [login](#login)
	- [logout](#logout)
	- [uid](#uid)
	- [state](#state)
	- [delegate](#oovooaccount_delegate)
	- [ooVooAccountDelegate](#oovooaccountdelegate)
		- [didAccountLogIn](#didaccountlogin)
		- [didAccountLogOut](#didaccountlogout)
- [ooVooAVChat](#oovooavchat)
	- [join](#join)
	- [leave](#leave)
	- [sendData](#senddata)
	- [registerPlugin](#registerplugin)
	- [unregisterPlugin](#unregisterplugin)
	- [isResolutionSupported](#isresolutionsupported)
	- [AudioController](#audiocontroller)	
	- [VideoController](#videocontroller)
	- [isDataChannelPermit ](#isdatachannelpermit )
	- [delegate](#oovooavchat_delegate)
	- [ooVooAVChatDelegate](#oovooavchatdelegate)
		- [didParticipantJoin](#didparticipantjoin)
		- [didParticipantLeave](#didparticipantleave)
		- [didConferenceStateChanged](#didconferencestatechanged)
		- [didReceiveData](#didreceivedata)
		- [didConferenceError](#didconferenceerror)
		- [didNetworkReliabilityChange](#didnetworkreliabilitychange)
		- [didSecurityState](#didsecuritystate)
- [ooVooAudioController](#oovooaudiocontroller)
	- [setConfig](#audio_setconfig)
	- [getConfig](#audio_getconfig)
	- [initAudio](#initaudio)
	- [unInitAudio](#uninitaudio)
	- [isPlaybackMuted](#isplaybackmuted)
	- [setPlaybackMute](#setplaybackmute)
	- [isRecordMuted](#isrecordmuted)
	- [setRecordMuted](#setrecordmuted)
	- [hold](#hold)
	- [unhold](#unhold)
	- [getEffectsList](#audio_geteffectslist)
	- [delegate](#oovooaudiocontroller_delegate)
	- [ooVooAudioControllerDelegate](#oovooaudiocontrollerdelegate)
		- [didAudioTransmitStateChange](#didaudiotransmitstatechange)
		- [didAudioReceiveStateChange](#didaudioreceivestatechange)		
- [ooVooVideoController](#oovoovideocontroller)
	- [setConfig](#video_setconfig)
	- [getConfig](#video_getconfig)
	- [getDevicesList](#video_getdeviceslist)
	- [getEffectsList](#video_geteffectslist)
	- [bindVideoRender](#bindvideorender)
	- [unbindVideoRender](#unbindvideorender)
	- [registerRemoteVideo](#registerremotevideo)
	- [unregisterRemoteVideo](#unregisterremotevideo)
	- [startTransmitVideo](#starttransmitvideo)
	- [stopTransmitVideo](#stoptransmitvideo)
	- [isVideoTransmited](#isvideotransmited)
	- [openCamera](#opencamera)
	- [closeCamera](#closecamera)
	- [openPreview](#openpreview)
	- [closePreview](#closepreview)
	- [sizeToCameraResolutionLevel](#sizetocameraresolutionlevel)
	- [getActiveDevice](#getactivedevice)
	- [setActiveDevice](#setactivedevice)
	- [delegate](#oovoovideocontroller_delegate)
	- [ooVooVideoControllerDelegate](#oovoovideocontrollerdelegate)
		- [didCameraStateChanged](#didcamerastatechanged)
		- [didVideoTransmitStateChanged](#didvideotransmitstatechanged)
		- [didRemoteVideoStateChanged](#didremotevideostatechanged)
		- [didVideoPreviewStateChanged](#didvideopreviewstatechanged)
- [ooVooEffect](#oovooeffect)
	- [effectName](#effectname)
	- [effectID](#effectid)
	- [iconUrl](#iconurl)
	- [category](#category)
	- [purchaseID](#purchaseid)
	- [getProperty](#getproperty)
- [ooVooDevice](#oovoodevice)
	- [deviceName](#devicename)
	- [deviceID](#deviceid)
- [ooVooVideoDevice](#oovoovideodevice)
	- [isResolutionSupported](#isresolutionsupported)
	- [isFront](#isfront)
	- [getAvailableResolutions](#getavailableresolutions)
- [ooVooParticipant](#oovooparticipant)
	- [participantID](#participantid)
	- [type](#type)
- [ooVooVideoData](#oovoovideodata)
	- [getPlane](#getplane)
	- [getPlanePitch](#getplanepitch)
	- [data](#data)
	- [dataLength](#datalength)
	- [width](#width)
	- [height](#height)
	- [colorFormat](#colorformat)
	- [planeCount](#planecount)
- [ooVooVideoFrame](#oovoovideoframe)
	- [videoData](#videodata)
	- [width](#width)
	- [height](#height)
	- [frameNumber](#framenumber)
	- [isKeyFrame](#iskeyframe)
	- [isMirror](#ismirror)
	- [rotationAngle](#rotationangle)
	- [deviceRotationAngle](#devicerotationangle)
	- [colorFormat](#colorformat)
- [ooVooVideoRender ](#oovoovideorender)
	- [onProcessVideoFrame](#onprocessvideoframe)
- [ooVooVideoPanel](#oovoovideopanel)
	- [ooVooFitMode](ooVoofitmode)
	- [isVideoRenderStarted](#isvideorenderstarted)
	- [videoFittingMode](#videofittingmode)
	- [videoOrientationLocked](#videoorientationlocked)
	- [videoOrientationChangesAnimated](#videoorientationchangesanimated)
	- [didVideoRenderStart](#didvideorenderstart)
	- [didVideoRenderStop](#didvideorenderstop)
- [ooVooMessaging](#oovoomessaging)
	- [sendMessage](#sendmessage)
	- [sendAcknowledgement](#sendacknowledgement)
	- [connect](#connect)
	- [disconnect](#disconnect)
	- [isConnected](#isconnected)
	- [delegate](#oovoomessaging_delegate)
- [ooVooMessagingDelegate](#oovoomessagingdelegate)
	- [didMessageReceive](#didmessagereceive)
	- [didMessageReceiveAcknowledgement](#didmessagereceiveacknowledgement)
	- [didConnectivityStateChange](#didconnectivitystatechange)
- [ooVooMessage](#oovoomessage)
	- [initMessage](#initmessage)
	- [initMessageWithData](#initmessagewithdata)
	- [initMessageWithArrayUsers](#initmessagewitharrayusers)
	- [from](#msg_from)
	- [to](#msg_to)
	- [body](#msg_body)
	- [messageId](#msg_messageid)
	- [timestamp](#msg_timestamp)	
- [ooVooPushService](#oovoopushservice)
	- [subscribe](#subscribe)
	- [unSubscribe](#unsubscribe)
	- [sendPushMessage](#sendpushmessage)
- [ooVooPushNotificationMessage](#oovoopushnotificationmessage)
	- [initMessageWithArrayUsers](#initmessagewitharrayusers)
	- [to](#pnm_to)
	- [body](#pnm_body)
	- [property](#pnm_property)
	- [messageId](#pnm_messageId)		
- [Enumerators](#enumerators)
	- [ooVooAVChatState](#oovooavchatstate)
	- [ooVooDeviceState](#oovoodevicestate)
	- [ooVooAudioRouteType](#oovooaudioroutetype)
	- [ooVooVideoControllerConfigKey](#oovoovideocontrollerconfigkey)
	- [ResolutionLevel](#resolutionlevel)
	- [ooVooAudioControllerConfigKey](#oovooaudiocontrollerconfigkey)
	- [ooVooAVChatRemoteVideoState](#oovooavchatremotevideostate)
	- [ooVooAVParticipantType](#oovooavparticipanttype)
	- [ooVooColorFormat](#oovoocolorformat)
	- [ooVooMessageAcknowledgeState](#oovooMessageacknowledgestate)
	- [ooVooMessagingConnectivityState](#oovoomessagingconnectivitystate)

<!-- /TOC -->

# ooVooClient Interface
## sharedInstance
The method creates single ooVooClient instance.

**Return a value:** return singleton ooVooClient object.

### The application must call the methods below to work properly SDK.
**applicationDidEnterBackground**  
**applicationWillResignActive**  
**applicationWillEnterForeground**  
**applicationDidBecomeActive**  

## setLogger
The method associates a logging object with the SDK.

**Parameters**:

Attribute | Type                | Requirements | Description
--------- | ------------------- | ------------ | -----------------
logger Id | **[ooVooClientLogger](#oovooclientlogger)** | Required     | The log recipient


## setLogLevel
Use this method to specify the verbosity of log messages you wish to receive and handle on the client end.

**Parameters**:

Attribute | Type       | Requirements | Description
--------- | ---------- | ------------ | ------------------------------------------------
level     | **[LogLevel](#loglevel)** | Required     | The minimal level of log messages to be received


## getSdkVersion
The method allows to get current version of SDK.

**Return a value:** return string SDK version.

## authorizeClient
Authorize access to ooVooClient API.

**Parameters**:

Attribute         | Type              | Requirements | Description
----------------- | ----------------- | ------------ | -------------------------------
application_token | **NSString * **   | Required     | The application token got after
completion        | **[CompletionHandler](#completionhandler)** | Required     | Answer result callback


## Properties

### IsAuthorized
Atomic and read only property. Return if current client is authorized.

**Return**: 
Returns authorization status: true for yes otherwise false.

### Account
Gets ooVoo SDK Account service. Use Account object to perform operations such as: login account, logout , get user id ...

**Return a value:**

Type         |  Description
------------ | -------------------------------------------------
**[ooVooAccount](#oovooaccount)** |  Returns object to the ooVoo SDK Account service


### AVChat
Gets AVChat object of the ooVoo SDK AV Service. Use ooVoo SDK AV Service to create Audio or Video chat session.

Type       | Description
---------- | ------------------------------------------------
**[ooVooAVChat](#oovooavchat)** | Returns object to ooVoo AVChat service


### Messaging
Gets Messaging object of the ooVoo SDK Messaging Service. Use ooVoo SDK Messaging Service to send and receive text messages. 
**Return a value:**

Type       	  | Description
------------- | -----------------------
**[ooVooMessaging](#oovoomessaging)** | Returns object to ooVoo Messaging service.

### PushService
Gets Push object of the ooVoo SDK Push Service. Use ooVoo SDK Push Service to send iOS/Android push notifications.

Type       	  | Description
------------- |-----------------------
**[ooVooPushService](#oovoopushsrvice)** | Returns object to ooVoo Push service.


### sslVerifyPeer
The property allows to set/get SSL verification for server connection.

Type         | Requirements | Description
------------ | ------------ | ---------------------------------
**BOOL**     | Required    	| Define SSL verification flag.


## ooVooClientLogger 
### onLog
Callback function that should handle the log from SDK.

**Parameters**:

Attribute | Type         | Requirements | Description
--------- | ------------ | ------------ | ---------------------------------
Level     | **[LogLevel](#loglevel)**    | Required     | The log level, error, debug, info
Log       | **NSString* **   | Required     | Answer result callback


# ooVooAccount 

## login
The method allows you to login with an your existing user.

**Parameters**:

Attribute  | Type                | Requirements | Description
---------- | ------------------- | ------------ | ----------------------------------------
UserID     | **NSString* **   | Required     | The account unique id, no less 6 symbols
completion | **[CompletionHandler](#completionhandler)**   | Required     | Answer result callback


## logout
The method allows to perform logout for the current user.


### delegate
Set the property in order to receive completion events of ooVooAccount service such as login, loguot.

Type             	 | Description
-------------------- | -----------------------------------------------------
**[ooVooAccountDelegate](#oovooaccountdelegate)** | user object, which implements ooVooAccountDelegate 


### uid
Read only property which allows to get current logged in user id.

Type             	 | Description
-------------------- | ----------------
**NSString* **		 | The user id

### state
Read only property which allows to get current login state.

Type             	 | Description
-------------------- | ----------------
**[AccountState](#accountstate)**| The login state

####AccountState
This enum type specify the login state.

Name 	| Description
------- | ------------
**AccountLoggedIn** | The user logged in
**AccountLoggedOut**| The user logged out


## ooVooAccountDelegate

### didAccountLogIn
The event occurs when user performs login.

**Parameters**:

Attribute    | Type         | Description
------------ | ------------ | -----------
account      | **[ooVooAccount](#oovooaccount)** | This is ooVooAccount instance.

### didAccountLogOut
The event occurs when user performs logout.

**Parameters**:

Attribute    | Type         | Description
------------ | ------------ | -----------
account      | **[ooVooAccount](#oovooaccount)** | This is ooVooAccount instance.


# ooVooAVChat 
## join
The method allows to perform a A/V conference call.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -------------
*cid*   | **NSString* ** | Conference id
*userData*  | **NSString* ** | Any custom user's information. It is optioanl and can be null. This data will be received on remote side on callback [didParticipantJoin](#didparticipantjoin)


## leave
The method allows to perform a leave from conference call.

## sendData
The method allows sending a limited binary data to specifies participant in the conference call.

**Parameters:**

Attribute  | Type         | Description
---------- | ------------ | ------------------------
*uid*      | **NSString* ** | User id
*data*     | **NSData* ** | The binary data to send.

## sendData
The method allows sending a limited binary data to all participants in the conference call.

**Parameters**:

Attribute  | Type         | Description
---------- | ------------ | ------------------------
*data* | **NSString* ** | The binary data to send.

>Sending data is limited for 1KB per second, for the text messages use [ooVooMessaging](#oovoomessaging) service API. 

## registerPlugin
The method allows registering a plugin implementation for use in AVChat.

**Parameters**:

Attribute     | Type                 | Description
--------------| -------------------- | ------------------------
*plugin*      | **[ooVooPluginFactory](#oovoopluginfactory)** | Plugin for registration.
*completion*  | **[CompletionHandler](#CompletionHandler)**  | Completion handler for receive result of register plugin

## unregisterPlugin
The method allows un-registering a plugin for use in AVChat.

**Parameters**:

Attribute  | Type         | Description
---------- | ------------ | ------------------------
*plugin* | **[ooVooPluginFactory](#oovoopluginfactory)**  | Plugin for unregistration.


## isResolutionSupported
The method allows checking if a given resolution level is supported in the current call.

**Parameters**:

Attribute        | Type              				| Description
---------------- | ------------------------ | ------------------------------
*resolution*     | **[ResolutionLevel](#resolutionlevel)** | This is a level of resolution.

**Return a value:** 

Type     | Description
-------- | -----------
**BOOL** | return YES, if requested resolution is supported in current call, otherwise NO

## Properties

### AudioController
Gets audio controller. Use audio controller to perform audio operations.


**Return a value:** 

Type		   | Description
------------------ | -----------
**[ooVooAudioController](#oovooaudiocontroller)**| Returns the interface of a audio controller.

### VideoController

Gets read only video controller. Use video controller to perform video operations such as: open camera, open preview....

**Return a value:**

Type		   | Description
------------------ | -----------
**[ooVooVideoController](#oovoovideocontroller)**| Returns the interface of a video controller.


### isDataChannelPermit
The read only property allows to check if data channel feature is enabled in the conference call.

**Return a value:** 

Type            |  Description
--------------- |  ---------------------------------------------
**BOOL**		|  Returns boolean value, if you can send a data in a call.

### delegate
The property must to be set for id<ooVooAVChatDelegate> in order to receive completion events of AVChat methods such as join, leave...

**Parameters**:

Attribute    | Type             | Description
------------ | ---------------- | -----------------------------------------------------
*delegate* | **[ooVooAVChatDelegate](#oovooavchatdelegate)** | user object, which implements ooVooAVChatDelegate

**Return a value:** N/A

## ooVooAVChatDelegate

### didParticipantJoin
Event occurs when participant joined to the current AV chat session.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | -----------
*participant* | **[ooVooParticipant](#oovooparticipant)** | This participant added to conference.
*user_data*   | **NSString* ** | User data


### didParticipantLeave
Event occurs when participant left form the current AV chat session.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | -----------
*participant* | **[ooVooParticipant](#oovooparticipant)**  |  This participant is disconnected from the conference.


### didConferenceStateChanged
Event occurs when user joined or disconnected from conference.

**Parameters**:

Attribute   | Type         | Description
----------- | ------------ | ------------------------------------------------
*state*     | **[ooVooAVChatState](#oovooavchatstate)** | Enumerator which indicates conference new state.
*code* 	    | **[sdk_error](../SDK%20Error%20Codes.md)** | Conference error code


### didReceiveData
Event occurs when user receive data from remote participants. See [sendData](#senddata) method.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -----------
*uid*   | **NSString* ** | The sender user ID..
*data*  | **NSData* **   | The received data. 

### didConferenceError
Event occurs when conference error is received.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | ------------------------------------------------
*code* 	  | **[sdk_error](../SDK%20Error%20Codes.md)**  | Conference error code


### didNetworkReliabilityChange
Event occurs when network reliability change.

**Parameters**:

Attribute     | Type         | Description
------------- | ------------ | ------------------------------------------------
*scope* 	  | **NSString* **  | The score of the network reliability

>Score value can be one of the following: 0 - Undefined , 1 - Poor , 2 - Low  3 - Good, 4 - Excellent

### didSecurityState
Event occurs when user changed security  mode.

**Parameters**:

Attribute     | Type      | Description
------------- | --------- | ------------------------------------------------
*is_secure*   | **bool**  | The flag represents if the connection is secure or not.



# ooVooAudioController

### <a name="audio_setconfig"></a>setConfig
The method allows setting audio sessings.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
*val*     | **NSString* **              | Value
*key*     | [ooVooAudioControllerConfigKey](#oovooaudiocontrollerconfigkey) | The configuration option

**Return a value:** N/A

### <a name="audio_getconfig"></a>getConfig
The method allows getting current audio sessings

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
*key*   | [ooVooAudioControllerConfigKey](#oovooaudiocontrollerconfigkey) | The configuration option

**Return a value:** value of chosen configuration.

### initAudio
The async method initialize audio record/playback module. It's recommended to call this method before calling [join](#join) method.

**Parameters:**

Type                    | Name     | Description
----------------------- | -------- | ------------------------------------------------------
**[CompletionHandler](#completionhandler)** | completion | The async listener which allows  getting request result.


### unInitAudio
The async method allows to perform un-init audio record/playback module. It's recommended to call this method before calling "leave" the method.

**Parameters:**

Type                    | Name     | Description
----------------------- | -------- | ------------------------------------------------------
**[CompletionHandler](#completionhandler)** | completion | The async listener which allows  getting request result.


### setPlaybackMute
The method allows setting playback (incoming stream) state to mute or unmute.

**Parameters**:

Attribute       | Type     | Requirements | Description
--------------- | -------- | ------------ | ----------------------------------------
*state* 		| **BOOL** | Required     | State flag TRUE for mute otherwise FALSE

### isPlaybackMuted
The method allows checking playback current state.

**Return a value:**

Type     | Description
-------- | ---------------------------------------------------------
**BOOL** | Returns boolean value of the playback current state 


### setRecordMuted
The method allows setting record (outgoing stream) state to mute or unmute.

**Parameters**:

Attribute  | Type     | Requirements | Description
---------- | -------- | ------------ | ----------------------------------------
*state*  | **BOOL** | Required     | State flag TRUE for mute otherwise FALSE

### isRecordMuted
The method allows checking record current state.

**Return a value:**

Type    | Description
------- | --------------------------------------------------
**BOOL** | Returns boolean value about of the state a record.

### hold
The method allows setting the audio in hold mode.

### unhold
The method allows returning audio from hold mode.

## <a name="audio_geteffectslist"></a>getEffectsList
Get list of available audio effects.

**Return a value:**

Type        | Description
----------- | --------------------------
**NSArray** | Available effect list of id<[ooVooEffect](#oovooeffect)>

### <a name="oovooaudiocontroller_delegate"></a>delegate
Must to set property in order to receive events of AudioContoller

**Parameters**:

Attribute    | Type                      | Description
------------ | ------------------------- | --------------------------------------------------------------
*delegate*   | **id<[ooVooAudioControllerDelegate](#ooVooAudioControllerDelegate)>** | user object, which implements ooVooAudioControllerDelegate 

## ooVooAudioControllerDelegate

### didAudioTransmitStateChanged
Event fired when audio transmit state was changed.

**Parameters**:

Attribute     | Type     | Description
------------- | -------- | ------------------------
*state*     | **BOOL**   | Audio transmit new state
*code* 	  | **[sdk_error](../SDK%20Error%20Codes.md)** | Error code

**Return a value:** no result.

### didAudioReceiveStateChanged
Event fired when audio receive state was changed.

Parameters:

Attribute     | Type     | Description
------------- | -------- | -----------------------
*state*     | **BOOL**   | Audio receive new state
*code* 	  | **[sdk_error](../SDK%20Error%20Codes.md)** | Error code


### didAudioHold
Event fired when audio in hold mode.

### didAudioUnHold
Event fired when audio back form hold mode.


## ooVooVideoController 

### <a name="video_setconfig"></a>setConfig
User can set configuration of the following: active video device, resolution, FPS, effect.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
*val*    | **NSString* **                  | A new config value
*key*    | **[ooVooVideoControllerConfigKey](#oovoovideocontrollerconfigky)** | The configuration option


### <a name="video_getconfig"></a>getConfig
User can find configuration of the following: capture device, resolution, FPS, effect.

**Parameters**:

Attribute | Type                       | Description
--------- | -------------------------- | --------------------
*key*   | **[ooVooVideoControllerConfigKey](#oovoovideocontrollerconfigky)** | Configuration option

**Return a value:** value of chosen configuration

### getDevicesList
Get list of avalible video devices

**Return a value:**

Type        | Description
----------- | --------------------------
**NSArray** | Available video device list of id<[ooVooDevice](#oovoodevice)>


### getEffectsList
Get available effect list

**Return a value:**

Type        | Description
----------- | --------------------------
**NSArray** | Available effects list of id<[ooVooEffect](#oovooeffect)>

### bindVideoRender
The method allows to add the specified video stream at a particular VideoView from a particular user in conference.

**Parameters**:

Attribute  | Type          | Description
---------- | ------------- | --------------
*uid*    | **NSString* **  | Specifies the user ID to which belongs to the video stream.
*render* | **[VideoRender](#videorender)** | Defines the VideoView in which will be show video stream.


### unbindVideoRender
The method allows to remove the specific video stream at a particular VideoView from a particular user in conference.

**Parameters**:

Attribute  | Type          | Description
---------- | ------------- | --------------
*uid*    | **NSString* **  | Specifies the user ID to which belongs to the video stream.
*render* | **[VideoRender](#videorender)** | Defines the VideoView in which will be removed video stream.

### registerRemoteVideo
The method allows to agree getting video stream from a particular user.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -----------
*uid*   | **NSString* ** | Specifies the ID of the user who agrees to receive a video stream.

### unregisterRemoteVideo
The method allows to stop receive a video stream from a particular user.

**Parameters**:

Attribute | Type         | Description
--------- | ------------ | -----------
*uid*   | **NSString* ** | Specifies the user ID from which prohibits receive a video stream.

### startTransmitVideo
The method allows to start transmit video.

### stopTransmitVideo
The method allows to stop transmit video.


### isVideoTransmited
The method allows to check if the video is transmitted at the moment.

**Return a value:**

Type    | Description
------- | -----------------------------------------------------
**BOOL** | Returns the boolean value about local video transmission .

### openCamera
The method allows to initialize the camera for use.

### closeCamera
The method allows finalize to use the camera.

## openPreview
The method allows to start get the video captures from camera. Camera must be opened before opening preview.

## closePreview
The method allows to stop get the video captures from camera.

## sizeToCameraResolutionLevel
The method allows to get the resolution level from size of video.

**Parameters**:

Attribute 	| Type            | Description
----------- | ----------------| --------------------
*width*     | **int**     	  | This width of video.
*height*    | **int**     	  | This height of video.

**Return a value:**

Type             		|  Description
----------------------- | ----------------------------------------------
**[ResolutionLevel](#resolutionlevel)** | Returns an enum of resolution level.

## activeDevice
Get/Set the current active video device.

Type                       | Description
-------------------------- | --------------------
**[ooVooVideoDevice](#oovoovideodevice)** | The active video device.


### <a name="oovoovideocontroller_delegate"></a>delegate

Must set the property in order to receive events of the ooVooVideoController

Type                      | Description
------------------------- | -----------------------------
**id<[ooVooVideoControllerDelegate](#oovoovideocontrollerdelegate)>** | user object, which implements | ooVooVideoControllerDelegate 


## ooVooVideoControllerDelegate 

### didCameraStateChange
Event fired when system detects that camera state has been changed.

**Parameters**:

Attribute   | Type       | Description
----------- | ---------- | ----------------
*state*     | **[ooVooDeviceState](#ooVooDeviceState)** | The video device new state
*devId*     | **NSString* ** | Current device ID
*width*     | **const int**  | This width of video.
*height*    | **const int**  | This height of video.
*fps*       | **onst int**   | This Frame Per Second of video.
*code* 	    | **[sdk_error](../SDK%20Error%20Codes.md)** | The error code of the action.


### didVideoTransmitStateChange
Event fired when video transmit state has been changed.

**Parameters**:

Attribute   | Type           | Description
----------- | -------------- | ------------------------
*state*     | **BOOL**       | Video transmit new state
*devId*     | **NSString* ** | Device ID
*code* 	    | **[sdk_error](../SDK%20Error%20Codes.md)** | The error code of the action.


### didRemoteVideoStateChange
Event fired when remote user video transmit state has been changed.

**Parameters**:

Attribute   | Type         | Description
----------- | ------------ | ------------------------
*uid*       | **NSString* ** | Remote user id
*state*     | **[ooVooAVChatRemoteVideoState](#oovooavchatremotevideostate)** | Video transmit new state
*width*     | **const int**  | This width of video.
*height*    | **const int**  | This height of video.
*code* 	  	| **[sdk_error](../SDK%20Error%20Codes.md)**  | The error code of the action.


### didVideoPreviewStateChange
Event fired when preview video state has been changed.

**Parameters**:

Attribute   | Type          | Description
----------- | ------------- | ------------------------
*state*     | **BOOL**      | Video transmit new state
*devId*     | **NSString* ** | Device ID
*code* 	    | **[sdk_error](../SDK%20Error%20Codes.md)** | The error code of the action.





# ooVooEffect 

### effectName
Read only property. 

Type      | Description
--------- | --------------------------
**NSString* ** | The effect name


### effectID
Read only property. 

Type      | Description
--------- | --------------------------
**NSString* ** | The effect id


### iconUrl
Read only property.

Type      | Description
--------- | --------------------------
**NSString* ** | The icon URL

### category
Read only property.

Type      | Description
--------- | --------------------------
**NSString* ** | This is a category of the effect


### purchaseID
Read only property. 

Type      | Description
--------- | --------------------------
**NSString* ** | This is ID for each unique purchase id of the effect.


### getProperty
The method allows geting effect property by property key name.

**Parameters:**

Attribute     | Type     | Description
------------- | -------- | -----------------------
*key*         | **NSString* ** | Property key name

**Return a value:** 

Type        | Description
----------- | --------------------------
**NSString* ** | The property value


## ooVooDevice 

### deviceID
Read only property.

Type      | Description
--------- | --------------------------
**NSString* ** | The device id

### deviceName
Read only property. 

Type      | Description
--------- | --------------------------
**NSString* ** | The device display name


## ooVooVideoDevice 

### getAvailableResolutions
The method allows getting a list of available resolutions for this device.

**Return a value:**

Type      | Description
--------- | --------------------------
**NSArray* ** | Returns avalible resolution list of [ResolutionLevel](#resolutionlevel).

### isResolutionSupported
The method allows to check, if the given resolution level is supported by this device.

**Parameters**:

Attribute        | Type              				| Description
---------------- | ------------------------ | ------------------------------
*resolution*   | **[ResolutionLevel](#resolutionlevel)**       | This is a level of resolution.


**Return a value:** 

Type      | Description
--------- | --------------------------
**BOOL**  | return YES if supported by the requested resolution, otherwise NO

### isFront
The method allows to check, if this is a front camera.

**Return a value:** 

Type      | Description
--------- | --------------------------
**BOOL**  | return YES if this is a front camera, otherwise NO


## ooVooParticipant 

### participantID
Read only property. 

Type      | Description
--------- | --------------------------
**NSString* ** | The type of participant

### type
Read only property. 

Type      | Description
--------- | --------------------------
**[ooVooAVParticipatType](#oovooavparticipatype)** | The type of participant

## ooVooVideoData 

### getPlane
The method allows to obtain a pointer to a specific plane.

**Parameters**:

Attribute | Type 	| Description
--------- | ------  | ---------------
*index*   | **int** | This index of plane. 

**Return a value:** 

Type      | Description
--------- | --------------------------
**void* ** | A pointer of indeterminate type.

### getPlanePitch
The method allows to obtain a pitch on a specific plane.

**Parameters**:

Attribute | Type 	| Description
--------- | ------  | ---------------
*index*   | **int** | This index of plane.

**Return a value:** 

Type      | Description
--------- | --------------------------
**int**   | The pitch of the plane.


### data
Read only property. 

Type      | Description
--------- | --------------------------
**NSData* ** | The video image data.


### dataLength
Read only property.

Type      | Description
--------- | --------------------------
**int**   | The length of the video image data.

### width
Read only property.

Type      | Description
--------- | --------------------------
**int**   | The width of the video image.

### height
Read only property.

Type      | Description
--------- | --------------------------
**int**   | The height of the video image.

### colorFormat
Read only property.

Type      | Description
--------- | --------------------------
**[ooVooColorFormat](#oovoocolorformat)**   | The color format of the video image data.

### planeCount
Read only property.

Type      | Description
--------- | --------------------------
**int**   | The planes count in the video image data.


## ooVooVideoFrame 

### videoData
Read only property.

Type      | Description
--------- | --------------------------
**[ooVooVideoData](#oovoovideodata)** | The video image data object

### width
Read only property.

Type      | Description
--------- | --------------------------
**int**   | The width of the video frame.

### height
Read only property.

Type      | Description
--------- | --------------------------
**int**   | The height of the video frame.

### frameNumber
Read only property.

Type      | Description
--------- | --------------------------
**short**   | The sequence number of the video frame.

### isKeyFrame
Read only property.

Type      | Description
--------- | --------------------------
**BOOL**  | Returns YES if the frame is keyframe, otherwise NO.

### isMirror
Read only property.

Type      | Description
--------- | --------------------------
**BOOL**  | Returns YES if the frame is mirrored, otherwise NO.

### rotationAngle
Read only property.

Type      | Description
--------- | --------------------------
**int**   | The angle to rotate the video frame. 0 is not rotation needed for rendering.  


### deviceRotationAngle
Read only property.

Type      | Description
--------- | --------------------------
**int**   | The current rotation angle of the device when the video frame was captured or should be rendered.


### colorFormat
Read only property.

Type      | Description
--------- | --------------------------
**[ooVooColorFormat](#oovoocolorformat)**   | The color format of the video frame.


## ooVooVideoRender 

### onProcessVideoFrame
The method allows to obtain video frame and you can process this video frame. In addition perform before coding the video frame or after decoding the video frame.

**Parameters**:

Attribute | Type 	 | Description
--------- | ------ | ---------------
*frame* | **[ooVooVideoFrame](#oovoovideoframe)** | This video frame for processing.


## ooVooVideoPanel

### videoFittingMode
The property allows to get/set fit mode for video panel (default "FillUp").

Type      | Description
--------- | --------------------------
**[ooVooFittingMode](#oovoofittingmode)** | The video fitting mode

### videoOrientationLocked
The property allows to get/set status if orientation changes events used for fraw video on a video panel (default "NO").

Type      | Description
--------- | --------------------------
**BOOL**  | YES, if orientation is locked, otherwise NO. 

### videoOrientationChangesAnimated
The property allows to get/set status if video animated on oreintation changes (default "YES")

Type      | Description
--------- | --------------------------
**BOOL**  | YES, if orientation changes is animated, otherwise NO.


### didVideoRenderStart
The callback can be override by developer for monitor state when video was start to draw on a video panel


### didVideoRenderStop
The callback can be override by developer for monitor state when video was stop to draw on a video panel

#### isVideoRenderStarted
The property allows getting status of the video rendering.

Type      | Description
--------- | --------------------------
**BOOL**  | YES, if video render has been started, otherwise NO.


##ooVooFittingMode
Enum define a values for how to fit video in video panel

 Name     | Description
 -------- | ---------------------------------
  **FillUp**  | Display the video frame on full video panel surface , video frame may cropped, depends on video aspect ratio and video panel size.
  **AutoBoxing** |  Display the video in letterboxing or pillarbox mode, depends on video aspect ratio and video panel size.


---


# ooVooMessaging 
 
### connect
The method start connect to messaging service

**Return a value:** no result, calback [didConnectivityStateChange](#didconnectivitystatechange) will fire.


### disconnect
The method start disconnect to messaging service

**Return a value:** no result, calback [didConnectivityStateChange](#didconnectivitystatechange) will fire.

### isConnected

Type    | Description
--------| -------------------
**BOOL** | true mean that sender connected to messaging service, false not connected

### sendMessage
The method allows to send text message to user(s). In order to send message you have to be connected to the Messaging service. 

**Parameters**:

Attribute 		    | Type 	 			| Description
------------------- | ----------------- | ---------------
*message* 			| **[ooVooMessage](#ooVooMessage)* **  | This a text message for other users.
*completion*   		| **[CompletionHandler](#completionhandler)** | The handler notifies about operation completion


### sendAcknowledgement
The method allows to get a status of send acknowledgement of a text message.

**Parameters**:

Attribute    	  | Type 	 			          | Description
----------------- | ----------------------------- | ---------------
*state*   		  | **[ooVooMessageAcknowledgeState](#oovoomessageacknowledgestate)** | This a status of acknowledgement.
*message*   	  | **[ooVooMessage](#ooVooMessage)* **| This a text message for other users.
*completion*   	  | **[CompletionHandler](#completionhandler)**| The handler notifies about operation completion


### delegate
Must to set id<ooVooMessagingDelegate> in order to receive completion events of ooVooMessage.

**Parameters**:

Type     | Description
-------- | -----------------------------------------------------
**[ooVooMessagingDelegate](#oovoomessagingdelegate)** | user object, which implements ooVooMessage 


## ooVooMessagingDelegate 

### didMessageReceive
Event fired when a text message was received.

**Parameters**:

Attribute     | Type     | Description
------------- | -------- | ------------------------
*message*     | **[ooVooMessage](#oovoomessage)* **   | This a message was received.


### didMessageReceiveAcknowledgement
Event fired when was received acknowledgement that the text a message delivered or readed by user.

**Parameters**:

Attribute     | Type     | Description
------------- | -------- | ------------------------
*state*       | **[ooVooMessageAcknowledgeState](#oovoomessageacknowledgestate)**  | This a text message was received.
*messageId*   | **NSString* **   | This ID of message.


### didConnectivityStateChange
Event fired when was  connectivity state was changed.

**Parameters**:

Attribute     | Type     | Description
------------- | -------- | ------------------------
*state*       | **[ooVooMessagingConnectivityState](#oovoomessagingconnectivitystate)**   | This a connectivity state.
*code*        | **[sdk_error](../SDK%20Error%20Codes.md)**   | The error code.
*description* | **NSString* ** | The error code desciption, can be null


## ooVooMessage

### initMessage
The method allows to initialize the ooVooMessage.

**Parameters**:

Attribute 	| Type 	 		| Description
----------- | ------------- | ---------------
*to*   		| **NSString* **| The recipient ID .
*body*  	| **NSString* **| The message body. Limited to 1kB

**Return a value:** returns a new instance of ooVooMessage.

### initMessageWithArrayUsers
The method allows to initialize the ooVooMessage with multimple recipients.

**Parameters**:

Attribute | Type 	 	  | Description
--------- | ------------- | ---------------
*to**     | **NSArray* ** | The list of recipient IDs 
*body**   | **NSString* **| This a text message

### initMessageWithData
The method allows to initialize the ooVooMessage with multimple recipients.

**Parameters**:

Attribute 	| Type  	 | Description
----------- | ---------- | ---------------
*to*   		| **NSArray* ** | The list of recipient IDs 
*body*      | **NSData * ** | The message body in a binary format. Limited to 1kB

**Return a value:** returns a new instance of ooVooMessage.


### from
Read only property.

Type  	 	   | Description
-------------- | ---------------
**NSString* ** | The sender ID.

### to
Read only property.

Type  	 	   | Description
-------------- | ---------------
**NSString* ** | The recipient ID.

### body
Read only property.

Type  	 	   | Description
-------------- | ---------------
**NSString* ** | The message body.


### messageId
Read only property.

Type  	 	   | Description
-------------- | ---------------
**NSString* ** | The registered ID of the message


### timestamp
Read only property.

Type  	 	   | Description
-------------- | ---------------
**uint64_t**   | A time of last operation with a message


---


# ooVooPushService 

### subscribe
The method allows to subscribe on push notification events.

**Parameters**:

Attribute 	   | Type 	 			| Description
-------------- | ------------------ | ---------------
*token*  	   | **NSString* **     | The APNS token
*deviceUid*    | **NSString* **     | This device ID of user.
*completion*   | **[CompletionHandler](#completionhandler)** | The handler notifies about operation completion


### unSubscribe
The method allows to un-subscribe from push notification events.

**Parameters**:

Attribute 	  |	Type 	 	   | Description
------------- | -------------- | ---------------
*token*  	  | **NSString* ** | The APNS token
*deviceUid*   | **NSString* ** | This device ID of user.
*completion*  | **[CompletionHandler](#completionhandler)** | The handler notifies about operation completion

### sendPushMessage
Use for sending push messages

**Parameters**:

Attribute 	  | Type 	 					  | Description
------------- | ----------------------------- | ---------------
*message*     | **[ooVooPushNotificationMessage](#oovoopushnotificationmessage)** | This a text message for other users.
*completion*  | **[CompletionHandler](#completionhandler)** | The handler notifies about operation completion

## ooVooPushNotificationMessage

### initMessageWithArrayUsers
The method allows to initialize the ooVooPushNotificationMessage with multiple recipients.

**Parameters**:

Attribute 		| Type 	 			| Description
--------------- | ----------- | ---------------
*to_list*		| **NSString* **| This a array of users, for receive a text message.
*body*   		| **NSString* **| This a body of text message.
*property*   	| **NSString* **| This a property.
*ttl*   		| **unsigned int** | This a timeout in seconds afterwards the message should not be sent.

### from
Read only property.

Type  	 	   | Description
-------------- | ---------------
**NSString* ** | The sender ID.

### to
Read only property.

Type  	 	   | Description
-------------- | ---------------
**NSString* ** | The recipient ID.

### body
Read only property.

Type  	 	   | Description
-------------- | ---------------
**NSString* ** | The message body.


### messageId
Read only property.

Type  	 	   | Description
-------------- | ---------------
**NSString* ** | The registered ID of the message



# Enumerators

### ooVooAVChatState
This enum type is a special data type that enables define about existing conference states.
Used in the method [didConferenceStateChanged](#didconferencestatechanged)

Name 		| Description
----------- | --------------------------------
ooVooAVChatStateJoined      | Local participant was joined to the conference
ooVooAVChatStateDisconnected| Local participant left from the conference.
ooVooAVChatStateConnecting  | Local participant is joining to the conference
ooVooAVChatStateDisconnecting | Local participant is leaving the conference


### ooVooAudioControllerConfigKey
The enum used in the methods [setConfig](#audio_setconfig)/[getConfig](#audio_getconfig) for define configuration of audio

Name      | Description
 --------- | -----------------------------------------
**ooVooAudioControllerConfigKeyRenderDeviceId** | Get/Set active audio playback device 
**ooVooAudioControllerConfigKeyCaptureDeviceId** | Get/Set active audio capture device
**ooVooAudioControllerConfigKeyAudioSetMode** | Get/Set audio mode
**ooVooAudioControllerConfigKeyEffectId** | Get/Set audio effect


### ooVooDeviceState
The enum used in the method [didCameraStateChange](#didcamerastatechange)

Name 		| Description
----------- | --------------------------------
ooVooNotCreated | The initial state 
ooVooTurningOn | Video device begins opening. The [openCamera](#opencamera) in process 
ooVooTurnedOn | Video device opened and ready for use. The [openCamera](#opencamera) is complited
ooVooTurningOff | Video device begins closing. The [closeCamera](#closecamera) in process 
ooVooTurnedOff | Video device begins closing. The [closeCamera](#closecamera) is complited
ooVooRestarting | Video device begins to restart due to configuration changes
ooVooOnHold | Video device is poused by Hold or by sysytem request. 


### ooVooVideoControllerConfigKey
The enum used in the methods [setConfig](#video_setconfig)/[getConfig](#video_getconfig) for define configuration of video

Name | Description
---- | ----------------- 
***ooVooVideoControllerConfigKeyCaptureDeviceId*** | Gets/Sets active video device   
***ooVooVideoControllerConfigKeyResolution*** | Gets/Sets active video resolution.  
***ooVooVideoControllerConfigKeyFps*** | Gets/Sets active video FPS  
***ooVooVideoControllerConfigKeyEffectId*** | Gets\Sets active video effect.


### ResolutionLevel
This enum type is a special data type that enables define about existing a resolution levels.
The enum used in the methods [setConfig](#video_setconfig)/[getConfig](#video_getconfig) for define configuration of video

Name | Description
---- | -----------------
***ResolutionLevelNotSpecified*** | This resolution level is not defined.  
***ResolutionLevelLow*** | Low quality resolution level. Used for bad network connection. 3G ...  
***ResolutionLevelMed*** | Medium quality resolution level. Used for good network connection. 4G,LTE,Wifi,LAN  
 ***ResolutionLevelHigh*** | High quality resolution level. Used for good network connection. LTE,Wifi,LAN  
***ResolutionLevelHD*** | HD quality resolution level. Used for high network connection. 4G,LTE,Wifi,LAN  


## ooVooAVChatRemoteVideoState
The enum used in the method [didRemoteVideoStateChange](#didremotevideostatechange) for define when remote video state has changed.

Name      | Description
--------- | -----------------
***ooVooAVChatRemoteVideoStateStated***  | The remote video started,
***ooVooAVChatRemoteVideoStateStopped*** | The remote video stopped, 
***ooVooAVChatRemoteVideoStatePaused***  | The remote video paused by QOS/hold, 
***ooVooAVChatRemoteVideoStateResumed*** | The remote video resumed by QOS/hold.


## ooVooAVParticipantType
This enum type is a special data type that enables define about existing a types of participant.
Currently only ooVooAVParticipantTypeVOIP value is used.

## ooVooColorFormat
This enum type is a special data type that enables define about existing color formats

Name        | Description
----------- | -------------------
    YV12    | Planar Y, V, U (4:2:0) (note V,U order!)
    NV12    | Planar Y, merged U->V (4:2:0)
    NV21    | Planar Y, merged V->U (4:2:0) (note V,U order!)
    YUY2    | Composite Y->U->Y->V (4:2:2)
    UYVY    | Composite U->Y->V->Y (4:2:2)
    YUV420  | Planar Y, U, V
    RGB32   | Composite R->G->B->A
    RGB24   | Composite R->G->B
    BGR32   | Composite B->G->R->A
    BGR24   | Composite B->G->R
    GRAY    | Luminance component only.
    YUV420A | Planar Y, U, V, Alpha
    YUV444A | Planar Y, U, V, Alpha
    GRAYA   | Luminance with Alpha
    SURFACE | GPU surface


## ooVooMessageAcknowledgeState
This enum type is a special data type that enables define about existing message acknowledge state
Used in the method [sendAcknowledgement](#sendacknowledgement) and in event [didMessageReceiveAcknowledgement](#didmessagereceiveacknowledgement)

Name       | Description
---------- | ---------------------------------
**Delivered**  | State that the message was delivered to the recipient
**Readed**	| State that a message was readed by recipient 

## ooVooMessagingConnectivityState
This enum type is a special data type for connectivity events. Using in event [didConnectivityStateChange](#didconnectivitystatechange)

Name             | Description
---------------- | ---------------------------------
**Connected**    | State that sender connected to messaging service
**Disconnected** | State that sender disconnected from messaging service  


## Types

## CompletionHandler
typedef void (^CompletionHandler)([SdkResult](#sdkresult) *result);

## SdkResult

### Result
Read only property.

Type  	 	   | Description
-------------- | ---------------
**[sdk_error](../SDK%20Error%20Codes.md)** | The error code.

### userInfo
Read only property.

Type  	 	     | Description
---------------- | ---------------
**NSDictionary** | The error description

