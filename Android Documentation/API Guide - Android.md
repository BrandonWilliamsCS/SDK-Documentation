# Android API Guide

Table of Contents

<!-- TOC depth:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Introduction](#introduction)
- [ooVooClient](#oovooclient)
	- [setContext](#setcontext)
	- [getSdkVersion](#getsdkversion)
	- [setLogger](#setlogger)
	- [setLogLevel](#setloglevel)
	- [isDeviceSupported](#isdevicesupported)
	- [isTablet](#istablet)
	- [sharedInstance](#sharedinstance)
	- [authorizeClient](#authorizeclient)
	- [isAuthorized](#isauthorized)
	- [getAccount](#getaccount)
	- [getAVChat](#getavchat)
	- [getMessaging](#getmessaging)
	- [getPush](#getpush)
	- [setSslPeerVerify](#setsslpeerverify)
	- [isSslPeerVerify](#issslpeerverify)
- [LoggerListener](#loggerlistener)
- [Account](#account)
	- [login](#login)
	- [logout](#logout)
	- [getID](#getid)
- [AVChat](#avchat)
	- [join](#join)
	- [leave](#leave)	
	- [isDataChannelPermit](#isdatachannelpermit)
	- [sendData](#senddata)
	- [registerPlugin](#registerplugin)
	- [unregisterPlugin](#unregisterplugin)
	- [getAvailableResolutions](#getavailableresolutions)
	- [isResolutionSupported](#isresolutionsupported)
	- [getVideoController](#getvideocontroller)
	- [getAudioController](#getaudiocontroller)
	- [setListener](#setlistener)
	- [ConferenceState](#conferencestate)
- [AVChatListener](#avchatlistener)
	- [onParticipantJoined](#onparticipantjoined)
	- [onParticipantLeft](#onparticipantleft)
	- [onConferenceStateChanged](#onconferencestatechanged)
	- [onReceiveData](#onreceivedata)
	- [onConferenceError](#onconferenceerror)
	- [onNetworkReliability](#onnetworkreliability)
	- [onSecurityState](#onsecuritystate)
- [Participant](#participant)
	- [getID](#participantgetid)
	- [getType](#participantgettype)
- [ParticipantType](#participanttype)	
- [AudioController](#audiocontroller)
	- [setConfig](#audio_setconfig)
	- [getConfig](#audio_getconfig)
	- [initAudio](#initaudio)
	- [uninitAudio](#uninitaudio)
	- [setPlaybackMuted](#setplaybackmuted)
	- [isPlaybackMuted](#isplaybackmuted)
	- [setRecordMuted](#setrecordmuted)
	- [isRecordMuted](#isrecordmuted)
	- [getAudioRouteController](#getaudioroutecontroller)
	- [getEffectList](#geteffectlist)
	- [setAudioRouteMode](#setaudioroutemode)
	- [setListener](#setlistener)
	- [AudioConfigKey](#audioconfigkey)
	- [AudioRouteMode](#audioroutemode)	
- [AudioControllerListener](#audiocontrollerlistener)
	- [onAudioTransmitStateChanged](#onaudiotransmitstatechanged)
	- [onAudioReceiveStateChanged](#onaudioreceivestatechanged)
	- [onMicrophoneStateChange](#onmicrophonestatechange)
	- [onSpeakerStateChange](#onspeakerstatechange)		
- [AudioRouteController](#audioroutecontroller)
	- [getRoutes](#getroutes)
	- [setRoute](#setRoute)
	- [setListener](#setlistener)
- [AudioRouteControllerListener](#audioroutecontrollerlistener)
	- [onAudioRouteChanged](#onaudioroutechanged)
- [AudioRoute](#audioroute)
	- [getName](#getname)
	- [getRouteId](#getrouteid)
	- [isActive](#isactive)
- [VideoController](#videocontroller)
	- [getConfig](#video_getconfig)
	- [setConfig](#video_setconfig)
	- [openCamera](#opencamera)
	- [closeCamera](#closecamera)
	- [openPreview](#openpreview)
	- [closePreview](#closepreview)
	- [bindRender](#bindrender)
	- [unbindRender](#unbindrender)
	- [getDeviceList](#getdevicelist)
	- [getEffectList](#geteffectlist)
	- [startTransmit](#starttransmit)
	- [stopTransmit](#stoptransmit)
	- [isTransmited](#istransmited)
	- [registerRemote](#registerremote)
	- [unregisterRemote](#unregisterremote)
	- [sizeToResolutionLevel](#sizetoresolutionlevel)
	- [setListener](#setlistener)
	- [~~setActiveDevice~~](#setactivedevice)
	- [~~getActiveDevice~~](#getactivedevice)
	- [~~setActiveResolution~~](#setactiveresolution)
	- [~~getActiveResolution~~](#getactiveresolution)
	- [~~setFps~~](#setfps)
	- [~~getFps~~](#getfps)
	- [~~setActiveEffect~~](#setactiveeffect)
	- [~~getActiveEffect~~](#getactiveeffect)
	- [ResolutionLevel](#resolutionlevel)
	- [VideoConfigKey](#videoconfigkeys)
- [VideoControllerListener](#videocontrollerlistener)
	- [onCameraStateChanged](#oncamerastatechanged)
	- [onRemoteVideoStateChanged](#onremotevideostatechanged)
	- [onTransmitStateChanged](#ontransmitstatechanged)
	- [onVideoPreviewStateChanged](#onvideopreviewstatechanged)
	- [onCameraChanged](#oncamerachanged)
	- [RemoteVideoState](#remotevideostate)
- [ooVooCameraState](#oovoocamerastate)
- [VideoDevice](#videodevice)
 	- [getID](#getid)
	- [getName](#getname)
	- [getAvailableResolutions](#getavailableresolutions)
	- [isResolutionSupported](#isresolutionsupported)
- [VideoPanel](#videopanel)
	- [VideoPanel Constructor](#videopanelconstructor)
	- [setVideoFittingMode](#setVideoFittingMode)
	- [setVideoOrientationLocked](#setVideoOrientationLocked)
	- [setVideoOrientationChangesAnimated](#setVideoOrientationChangesAnimated)
	- [takeScreenShot](#takescreenshot)
	- [FittingMode](#fittingmode)
	- [setVideoRenderStateChangeListener](#setVideoRenderStateChangeListener)	
- [ScreenshotTakeListener](#ScreenshotTakeListener)
	- [onScreenshotReady](#onScreenshotReady)
- [VideoRenderStateChangeListener](#VideoRenderStateChangeListener)
	- [onVideoRenderStart](#onVideoRenderStart)
	- [onVideoRenderStop](#onVideoRenderStop)
- [VideoRender](#videorender)
	- [onProcessVideoFrame](#onprocessvideoframe)	
- [VideoFrame](#videoframe)
	- [getColorFormat](#getcolorformat)
	- [getData](#getdata)
	- [getDeviceRotationAngle](#getdevicerotationangle)
	- [getFrameNumber](#getframenumber)
	- [getHeight](#getheight)
	- [getRotationAngle](#getrotationangle)
	- [getTime](#gettime)
	- [getWidth](#getwidth)
	- [isKeyFrame](#iskeyframe)
	- [isMirror](#ismirror)
- [VideoData](#videodata)
	- [getColorFormat](#getcolorformat)
	- [getData](#getdata)
	- [getDataLength](#getdatalength)
	- [getHeight](#getheight)
	- [getPlane](#getplane)
	- [getPlanePitch](#getplanepitch)
	- [getPlanesCount](#getplanescount)
	- [getWidth](#getwidth)
- [Effect](#effect)
	- [getCategory](#getcategory)
	- [getIconUrl](#geticonurl)
	- [getID](#getid)
	- [getName](#getname)
	- [getPurchaseId](#getpurchaseid)
	- [getProperty](#getproperty)
- [Messaging](#messaging)
	- [connect](#connect)
	- [disconnect](#disconnect)
	- [isConnected](#isconnected)
	- [sendMessage](#sendmessage)
	- [sendAcknowledgement](#sendacknowledgement)
	- [setListener](#setlistener)
- [MessagingListener](#messaginglistener)
	- [onMessageReceive](#onmessagereceive)
	- [onMessageAcknowledgementReceived](#onmessageacknowledgementreceived)
	- [onConnectivityStateChange](#onConnectivityStateChange)
- [ConnectivityState](#connectivitystate)
- [MessageAcknowledgeState](#messageacknowledgestate)
- [Message](#message)
	- [Message(String to, String body)](#msgconstructor1)
	- [Message(ArrayList&lt;String&gt; to_list, String body)](#msgconstructor2)
	- [getID](#getid)
	- [getBody](#getbody)
	- [getTimestamp](#gettimestamp)
	- [getFrom](#getfrom)
	- [getTo](#getto)
- [Push](#push)
	- [subscribe](#subscribe)
	- [unsubscribe](#unsubscribe)
	- [send](#send)
- [PushNotificationMessage](#pushnotificationmessage)
	- [PushNotificationMessage (ArrayList&lt;String&gt; to, String payload, String prop)](#pnmsgc1)
	- [PushNotificationMessage (ArrayList&lt;String&gt; to, String payload)](#pnmsgc2)
	- [getPayload](#getpayload)
	- [getProperty](#getproperty)	
- [ooVooSdkResultListener](#oovoosdkresultlistener)
	- [onResult](#onresult)
- [ooVooSdkResult](#oovoosdkresult)
	- [getResult](#getresult)
	- [getDescription](#getdescription)
	- [getUserInfo](#getuserinfo)
- [PluginFactory](#pluginfactory)
	- [createPluginInstance](#createplugininstance)	
- [GLPerformanceUtils](#glperformanceutils)
	- [getCurrentCpuFrequency](#getcurrentcpufrequency)
	- [getEnableThreshold](#getenablethreshold)
	- [getNumCore](#getnumcore)
	- [getPerfValue](#getperfvalue)
	- [isTegraDetected](#istegradetected)

<!-- /TOC -->

# Introduction
***ooVoo*** provides a rich application framework that allows you to build innovative apps for mobile devices in a Java language environment. This document provide details about how to use SDK using ooVoo's various APIs. This document allows to get full info about public API.

# ooVooClient

### setContext
The static method. The calling context being used to instantiate the ooVoo Client.


Parameters

Type        | Name | Description
----------- | ---- | ------------------------
**Context** | ctx  | Application context.

### getSdkVersion
The static method allows to get SDK version.

**Return a value:**

Type       |  Description
---------- | -----------------------
**String** |  Returns version of SDK.

### setLogger
The static method sets listener which allows to get SDK logs by provided log level.

**Parameters:**

Type               | Name     | Description
------------------ | -------- | -------------------------------------------------
**[LoggerListener](#loggerlistener)** | listener | The async listener which allows to get SDK logs.
**[LogLevel](#loglevel)**       | level    | Logging level. 


### setLogLevel
The static method allows to set a log level for the SDK.

**Parameters:**

Type         | Name  | Description
------------ | ----- | -----------------
**[LogLevel](#loglevel)** | level | Logging level.

>You can set the levels to one of the following: **None, Fatal, Error, Warning, Info, Debug, Trace.**. See [LoggerListener](#loggerlistener)

### isDeviceSupported
The static method allows to define if ooVoo SDK support this device. ooVoo SDK supports only devices with ARM NEON instruction Set.

**Return a value:**

Type          | Description
------------- | ------------------------------------------------
**boolean**   | Returns true if supported.

### isTablet
The static method allows to detect if this a device is tablet.

**Return a value:**

Type        | Description
----------- | --------------------------------------------------
**boolean** | Returns boolean value, if this a device is tablet.


### sharedInstance
The static method. Gets singleton reference to SDK ooVoo Client. Note: You need to call [setContext](#setcontext) before using this method else exception will throws.

**Return a value**:

Type            |  Description
--------------- |  --------------------------------------
**ooVooClient** |  Singleton reference to SDK ooVoo Client


### authorizeClient
The method allows to authorize access to ooVooClient SDK. This is async method, event will raised on main thread.

**Parameters:**

Type                       | Name            | Description
-------------------------- | --------------- | ---------------------------------------------------------
**String**                 | app_token       | The application token obtained after registration on site http://developer.oovoo.com
**[ooVooSdkResultListener](#oovoosdkresultlistener)** | result_receiver | The async listener which allows to get result on request.


```java
import com.oovoosdk.api.ooVooClient;
    ...
    public class MyApplication extends Application implements LoggerListener{
    ...
    private ooVooClient ovclient = null;
    public static final String	APP_TOKEN = "YOUR APP TOKEN";
    ..
    public void onCreate(){
        ...
        ooVooClient.setContext(this);
        ooVooClient.setLogger(this, LogLevel.Debug);
        ovclient = ooVooClient.sharedInstance();
        ovclient.authorizeClient(APP_TOKEN, new ooVooSdkResultListener() {
        		@Override
        		public void onResult(ooVooSdkResult result) {
          		if (result.getResult() == sdk_error.OK) {
             			// You are authorized and can use SDK!
          		}
          		else
          		{
            			//Oops, you are not authorized , you can see reason of error by call result.getDescription()
          		}
    			});
        
        ...
    }
```
### isAuthorized
The method allows define if was performed ooVoo SDK authorizing.

**Return a value:**

Type          | Description
------------- | ------------------------------------------------
**boolean**   | Returns true if was performed authorizing.

### getAccount
Gets ooVoo SDK Account service. Use Account object to perform operations such as: login account, logout , get user id ...

**Return a value:**

Type         |  Description
------------ | -------------------------------------------------
**[Account](#account)** |  Returns object to the ooVoo SDK Account service

### getAVChat
Gets AVChat object of the ooVoo SDK AV Service. Use ooVoo SDK AV Service to create Audio or Video chat session.

**Return a value:**

Type       | Description
---------- | ------------------------------------------------
**[AVChat](#avchat)** | Returns object to ooVoo client AVChat service


### getMessaging
Gets Messaging object of the ooVoo SDK Messaging Service. Use ooVoo SDK Messaging Service to send and receive text messages. 
**Return a value:**

Type       	  | Description
------------- | -----------------------
**[Messaging](#messaging)** | Returns module of Messaging.

### getPush
Gets Push object of the ooVoo SDK Push Service. Use ooVoo SDK Push Service to send iOS/Android push notifications.

**Return a value:**

Type       	  | Description
------------- |-----------------------
**[Push](#push)** | Returns module of Push.


### setSslPeerVerify
The native method allows to set checking for of a secure connection.
An SSL certificate - a unique digital signature necessary for the organization of a secure connection between the client and the server.

**Parameters:**

Type        | Name | Description
----------- | ---- | ------------------------
**boolean** | state  | true - Define a secure connection.


### isSslPeerVerify
The native method allows to check if this a connection used a SSL verification.

**Return a value:**

Type        | Description
----------- | --------------------------------------------------
**boolean** | Returns Boolean value, if this a connection is a secure.
   
# LoggerListener

###LogLevel
This enum type is a special data type that enables define current log level.

Name 	| Description
------- | ------------------------------------------------------------
 Fatal  | Traces only fatal errors
 Error  | Traces errors and fatal errors 
 Warning| Traces warnings , errors and fatal errors 
 Info 	| Traces informations logs, warnings , errors and fatal errors 
 Debug  | Traces all levels including debug information 
 Trace  | Traces all levels with very ditails information, not suggested for release
 None   | Disable log trace 

### OnLog
The method allows to get all events from lower level of SDK. Note: must provide an implementation for this method.

**Parameters:**

Type         | Name    | Description
------------ | ------- | -----------------------------------
**[LogLevel](#loglevel)** | level   | This is a log level in format enum.
**String**   | tag     | This is ID of message.
**String**   | message | This is a body message.   
    
---

# Account
### login
The method allows you to login with an your existing user.

**Parameters:**

Type                       | Name     | Description
-------------------------- | -------- | ---------------------------------------------------------
**String**                 | uid      | The ID an existing user in your app.
**[ooVooSdkResultListener](#oovoosdkresultlistener)** | listener | The async listener which allows to get result on request.

### logout
The method allows to perform logout for the current user.

### getID
The method allows to get logged in user id.

**Return a value:**

Type       | Description
---------- | -------------------
**String** | Returns login user ID.

---

# AVChat

### join
The method allows to perform a A/V conference call.

**Parameters:**

Type       | Name    | Description
---------- | ------- | -------------------------------------------------------
**String** | confid  | The conference id to join
**String** | userData| Any custom user's information. It is optioanl and can be null. This data will be received on remote side on callback [onParticipantJoined](#onparticipantjoined)  

### leave
The method allows to perform a leave from conference call.


### isDataChannelPermit
The method allows to check if data channel feature is enabled in the conference call.

**Return a value:**

Type            |  Description
--------------- |  ---------------------------------------------
**boolean**		|  Returns boolean value, if you can send a data in a call.

### sendData
The method allows sending a limited binary data to specifies participant in the conference call.

**Parameters:**

Type   | Name | Description
------ | ---- | -------------------------------------------------
**String** | uid  | Specifies the user, to which the data is sent
**byte[]** | data | The binary data to send.

**Return a value:**

Type      | Description
--------- | -------------------------------
**[sdk_error](../SDK%20Error%20Codes.md)** | Returns a status about sending.


### sendData
The method allows sending a limited binary data to all participants in the conference call.

**Parameters:**

Type   | Name | Description
------ | ---- | ------------------------
**byte[]** | data  | The binary data to send.

**Return a value:**

Type      | Description
--------- | -------------------------------
**[sdk_error](../SDK%20Error%20Codes.md)** | Returns a status about sending.

>Sending data is limited for 1KB per second, for the text messages use [Messaging](#messaging) service API. 

### registerPlugin
The method allows registering a plugin implementation for use in AVChat.

**Parameters:**

Type          | Name   | Description
------------- | ------ | --------------------------------------------------------------------
**[PluginFactory](#pluginfactory)** | plugin | Plugin factory implementation to register 
**[ooVooSdkResultListener](#oovoosdkresultlistener)**|completion| The calback interface for register plugin result


### unregisterPlugin
The method allows un-registering a plugin for use in AVChat.

**Parameters:**

Type          | Name   | Description
------------- | ------ | --------------------------------------------------------------------
**[PluginFactory](#pluginfactory)** | plugin | The interface allow to cancel custom plugin to our SDK


### getAvailableResolutions
The method allows to get available a resolution level list in current call.

**Return a value:**

Type            			   | Description
------------------------------------------ | ---------------------------------------------
**ArrayList&lt;[ResolutionLevel](#resolutionlevel)&gt;** | Returns a list resolutions.

### isResolutionSupported
The method allows checking if a given resolution level is supported in the current call.

**Parameters:**

Type          			| Name   | Description
----------------------- | ------ | --------------------------------------------------------------------
**[ResolutionLevel](#resolutionlevel)** | level  | This is a resolution for checking.

**Return a value:**

Type    | Description
------- | ---------------------------------------------
**boolean** | Returns boolean value, If there is support for the requested resolution.

### getVideoController
The method allows getting the video controller. Use video controller to perform video operations such as: open camera, open preview.... 

**Return a value:**

Type		   | Description
------------------ | -----------
**[VideoController](#videocontroller)**| Returns the interface of a video controller.|

### getAudioController
The method allows getting the audio controller interface.

**Return a value:**

Type            | Description
--------------- | ---------------------------------------------
**[AudioController](#audiocontroller)** | Returns the interface of an audio controller.

### setListener
The method allows setting a handler for receiving conference state events.

**Parameters:**

Type           | Name     | Description
-------------- | -------- | ------------------------------------------------------------------------------
**[AVChatListener](#avchatlistener)** | listener | A listener which allows receiving conference state events.


## AVChatListener

### onParticipantJoined
The method allows receiving the event that a participant joined to the current AV chat session.

**Parameters:**

Type        | Name        | Description
----------- | ----------- | -----------------------------------------------------------
**[Participant](#participant)** | participant | This is identification of the joined participant.
**String**      | userData    | This is user's custom information but data can be null.


### onParticipantLeft
The method allows receiving the event that a participant left from the current AV chat session.

**Parameters:**

Type        | Name        | Description
----------- | ----------- | -----------------------
**[Participant](#participant)**  | participant | This is identification of the left participant
 

### onConferenceStateChanged
The method allows receiving the event about changing sassion state.

**Parameters:**

Type            | Name      | Description
--------------- | --------- | -----------------------------------------------------------
**[ConferenceState](#conferencestate)** | state     | This is enum conference state.
**[sdk_error](../SDK%20Error%20Codes.md)**       | errorCode | This is an error code about changing a state of conference.

### onReceiveData
The method allows receiving data that had been sent to the user. See [sendData](#senddata) method.

**Parameters:**

Type       | Name   | Description
---------- | ------ | -----------------
**String** | uid    | The sender user ID..
**byte[]** | data   | The received data.  


### onNetworkReliability
The method allows to receive an information about network state.

**Parameters:**

Type | Name  | Description
---- | ----- | ------------------------
**int**  | score | This is a network state.  

  
>Score value can be one of the following: 0 - Undefined , 1 - Poor , 2 - Low  3 - Good, 4 - Excellent


### onSecurityState
The method allows checking an information about connection security state.

**Parameters:**

Type 	     | Name  	  | Description
------------ | ---------- | ------------------------
**boolean**  | isSecure   | The flag represents if the connection is secure or not.


### ConferenceState
This enum type is a special data type that enables define about existing conference states.

Name 		| Description
----------- | --------------------------------
Joined      | Local participant was joined to the conference
Disconnected| Local participant left from the conference.
Connecting  | Local participant is joining to the conference
Disconnecting | Local participant is leaving the conference

## Participant

### getID
The method allows getting participant ID.


**Return a value:**

Type   | Description
------ | ---------------------------
**String** | Returns the participant ID.

### getType
The method allows getting type of the participant.

**Return a value:**

Type            | Description
--------------- | ------------------------
**[ParticipantType](#participanttype)** | Returns type of connect.

### ParticipantType
This enum type is a special data type that enables define about existing a types of participant.

**Enum values:** ***VoIP*** - Currently only VoIP client is defined.

---

# AudioController

### <a name="audio_setconfig"></a>setConfig
The method allows setting audio sessings
**Parameters:**

Type	       | Name      | Description
-------------- | --------- | -----------------------------------------
**[AudioConfigKey](#audioconfigkey)** | key 	   | This is property key
**String** | value | property value

### <a name="audio_getconfig"></a>getConfig
The method allows getting current audio sessings

**Parameters:**

Type	       | Name      | Description
-------------- | --------- | -----------------------------------------
**[AudioConfigKey](#audioconfigkey)** | key 	   | This is property key

**Return a value:** **String** , property value.

### setAudioRouteMode
The method allows setting audio route mode before initializing the audio.

**Parameters:**

Type	       | Name      | Description
-------------- | --------- | -----------------------------------------
**[AudioRouteMode](#audioroutemode)** | mode 	   | This is mode for audio routes.


### initAudio
The async method initialize audio record/playback module. It's recommended to call this method before calling [join](#join) method.

**Parameters:**

Type                    | Name     | Description
----------------------- | -------- | ------------------------------------------------------
**[ooVooSdkResultListener](#oovoosdkresultlistener)** | completion | The async listener which allows  getting request result.


### uninitAudio
The async method allows to perform un-init audio record/playback module.

**Parameters:**

Type                    | Name     | Description
----------------------- | -------- | --------------------------------------------
**[ooVooSdkResultListener](#oovoosdkresultlistener)** | completion | The async listener which allows to get result on request.

### setPlaybackMute
The method allows setting playback (incoming stream) state to mute or unmute. 

**Parameters:**

Type    | Name  | Description
------- | ----- | ---------------------------------------------------------
boolean | state | Defines boolean value for new state. True - mute , False - unmute

### isPlaybackMuted
The method allows checking playback current state.

**Return a value:**

Type    | Description
------- | ---------------------------------------------------------
**boolean** | Returns boolean value of the playback current state 


### setRecordMuted
The method allows setting record (outgoing stream) state to mute or unmute.


Type    | Name  | Description
------- | ----- | --------------------------------------------------
**boolean** | state | Defines boolean value for the new state.

### isRecordMuted
The method allows checking record current state.

**Return a value:**

Type    | Description
------- | --------------------------------------------------
**boolean** | Returns boolean value about of the state a record.


### getAudioRouteController
The method allows getting audio route manager manager object.


**Return a value:**

Type                 | Description
-------------------- | ----------------------------
**[AudioRouteController](#audioroutecontroller)** | Returns audio route manager.

### setListener
The method allows setting handler for receiving audio controller events.

**Parameters:**

Type                    | Name     | Description
----------------------- | -------- | ------------------------------------------------------------------------------
**[AudioControllerListener](#audiocontrollerlistener)** | listener | The async listener which allows to set handler for receiving conference event.

###AudioConfigKey
Audio controller config keys enum

Name      | Description
 --------- | -----------------------------------------
**kAudioCfgRenderDeviceId** | Get/Set active audio playback  
**kAudioCfgCaptureDeviceId** | Get/Set active audio capturer
**kAudioCfgAudioSetMode** | Get/Set audio mode
**kAudioCfgEffectId** | Get/Set audio effect
**kAudioCfgMixEnable** | Get/Set audio mic mode  

### AudioRouteMode
This enum type is a special data type that enables define about existing an audio modes.

Name       | Description
 --------- | -----------------------------------------
*AudioRouteModeVoiceChat* | The audio playback will start with audio directed to earpiece. This mode suitable for voice calls.
*AudioRouteModeVideoChat*  | The audio playback will start with audio directed to speaker. This mode suitable for video calls.  


## AudioControllerListener
### onAudioTransmitStateChanged
The method allows to receive the event listener, that an audio transmitter has been changed.

**Parameters:**

Type      | Name  | Description
--------- | ----- | --------------------------------------------------------
**boolean**   | state | The new audio record state. True - muted , False - unmuted
**[sdk_error](../SDK%20Error%20Codes.md)** | error | This is an error code about changing.


### onAudioReceiveStateChanged
The method allows receiving the playback state event.

**Parameters:**

Type      | Name  | Description
--------- | ----- | --------------------------------------------------------
**boolean**   | state | The new audio playback state. True - muted , False - unmuted
**[sdk_error](../SDK%20Error%20Codes.md)** | error | This is an error code about changing.


### onMicrophoneStateChange
The method allows receiving the recorder device status event.

**Parameters:**

Type      | Name  | Description
--------- | ----- | ------------------------------------------------
**boolean**   | on    | The recorder device status. True - ON , False - OFF.
**[sdk_error](../SDK%20Error%20Codes.md)** | error | This is an error code about changing.


### onSpeakerStateChange
The method allows receiving the playback device status event.

**Parameters:**

Type      | Name  | Description
--------- | ----- | ---------------------------------------------
**boolean**   | on    | The playback device status. True - ON , False - OFF.
**[sdk_error](../SDK%20Error%20Codes.md)** | error | This is an error code about changing.




## AudioRouteController

### getRoutes
The method allows to get list available of audio routes.

**Return a value:**

Type                 | Description
-------------------- |  ----------------------------
**ArrayList&lt;[AudioRoute](#audioroute)&gt;** | Returns list of audio routes.


### setRoute
The method allows to select an audio route.

**Parameters:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
**[AudioRoute](#audioroute)** 	| route | Audio route for setting.

### setListener
The method allows to set handler for receiving the event from the audio route controller.

**Parameters:**

Type                    | Name     | Description
----------------------- | -------- | ------------------------------------
**[AudioRouteControllerListener](#audioroutecontrollerlistener)** | listener | The async listener which allows to set handler for receiving the event.  


## AudioRouteControllerListener

### onAudioRouteChanged

The method allows to receive the event listener, that an audio route has been changed.

**Parameters:**

Type      | Name  | Description
--------- | ----- | --------------------------------------------------------
**[AudioRoute](#audioroute)** | old_route | This is show previous position of audio route.
**[AudioRoute](#audioroute)** | new_route | This is show current position of audio route.

## AudioRoute

### getName
The method allows getting name of audio route.

**Return a value:**

Type                 | Description
-------------------- | ----------------------------
**String** 			 | Returns name of audio route .

### getRouteId
The method allows to get ID of audio route.

**Return a value:**

Type                 | Description
-------------------- | ----------------------------
**int** 			 | Returns ID of audio route .

### isActive
The method allows to check if current route is active.

**Return a value:**

Type                 | Description
-------------------- | ----------------------------
**boolean** 		 | Returns true if audio route is active.

---

## VideoController


### <a name="video_getconfig"></a>getConfig

The method allows to get configuration according to with a key.

**Parameters:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
**[VideoConfigKey](#videoconfigkey)** | key | Key of the video configuration.

**Return a value:**

Type         | Description
------------ | ----------------------------
**String** 	 | Returns configuration key.

### <a name="video_setconfig"></a>setConfig

The method allows to set configuration according to with a key.

**Parameters:**

Type                 | Name | Description
-------------------- | ---- | ----------------------------
**[VideoConfigKey](#videoconfigkey)** | key | Key of the video configuration.

**Return a value:** no result.

### openCamera
The method allows to initialize the camera for use.

**Parameters:**

Type     | Name   | Description
-------- | ------ | -------------------------------------------------------------
**Activity** | parent | Defines the activity with which will be to interact a camera.

### closeCamera
The method allows finalize to use the camera.

### openPreview
The method allows to start get the video captures from camera. Camera must be opened before opening preview.

### closePreview
The method allows to stop get the video captures from camera.

### bindRender
The method allows to add the specified video stream at a particular VideoView from a particular user in conference.

**Parameters:**

Type             | Name   | Description
---------------- | ------ | -----------------------------------------------------------
**String**       | uid    | Specifies the user ID to which belongs to the video stream.
**[VideoRender](#videorender)**  | render | Defines the VideoView in which will be show video stream.

### unbindRender
The method allows to remove the specific video stream at a particular VideoView from a particular user in conference.

**Parameters:**

Type             | Name   | Description
---------------- | ------ | ------------------------------------------------------------
**String**       | uid    | Specifies the user ID to which belongs to the video stream.
**[VideoRender](#videorender)**| render | Defines the VideoView in which will be removed video stream.

### registerRemote
The method allows to agree getting video stream from a particular user.

**Parameters:**

Type   | Name | Description
------ | ---- | ------------------------------------------------------------------
**String** | uid  | Specifies the ID of the user who agrees to receive a video stream.


### unregisterRemote
The method allows to stop receive a video stream from a particular user.

**Parameters:**

Type       | Name | Description
---------- | ---- | ------------------------------------------------------------------
**String** | uid  | Specifies the user ID from which prohibits receive a video stream.

## startTransmit
The method allows to start transmit video.


## stopTransmit
The method allows to stop transmit video.


### isTransmited
The method allows to check if the video is transmitted at the moment.

**Return a value:**

Type    | Description
------- | -----------------------------------------------------
**boolean** | Returns the boolean value about local video transmission.

### getDeviceList
The method allows to get a list all of cameras on device.

**Return a value:**

Type             | Description
---------------- | ---------------------------------------
**Array&lt;[VideoDevice](#videodevice)&gt;** | Returns array all of cameras on device.

 
### getEffectList
The method allows to get available effect list for video.

**Parameters:** without parameters.

**Return a value:**

Type             | Description
---------------- | ----------------------------------------------
**Array&lt;[Effect](#effect)&gt;** | Returns array all available effects for video.

### sizeToResolutionLevel
The method allows to get the resolution level from size of video.

**Parameters:**

Type       | Name   | Description
---------- | ----   | ------------------------------------------------------------------
**int**    | width  | This is a width of video.
**int**	   | height | This is a height of video.

**Return a value:**

Type             		|  Description
------------------------------- | ----------------------------------------------
**[ResolutionLevel](#resolutionlevel)** | Returns an enum of resolution level.

### setListener
The method allows to set handler for receiving conference event from video controller.

**Parameters:**

Type                     | Name     | Description
------------------------ | -------- | -------------------------------
**[VideoControllerListener](#videocontrollerlistener)** | listener | The async listener which allows to set handler for receiving conference event.


### setActiveDevice 
The method allows to define type of camera for current use, a front camera or a back camera.

**The method is depricated**
Instead use method [setConfig](#video_setconfig)

```java
	selectCamera(MyCameraInfo.CameraFacingFront);
```

```java
    public enum MyCameraInfo {
        CameraFacingBack {
            public String toString() {
                return "BACK";
            }
        },
        CameraFacingFront {
            public String toString() {
                return "FRONT";
            }
        }
    }
    public void selectCamera(MyCameraInfo info) {
        
        // find device by name
        VideoDevice device = null;
        ArrayList<VideoDevice> list = ovclient.getAVChat().getVideoController().getDeviceList();
        for (VideoDevice d : list) {
            if (info.toString() == device.getName()) {
                device = d;
                break;
            }
        }
        if (device != null) {
            // select camera
            ovclient.getAVChat().getVideoController().setConfig(VideoController.VideoConfigKey.kVideoCfgCaptureDeviceId, device.getID());
        }
    }
```

### getActiveDevice
The method allows to get the type of camera used at the moment.

**The method is depricated**
Instead use:
```java
	...
 	VideoDevice device = getDevice(ovclient.getAVChat().getVideoController().getConfig(VideoConfigKey.kVideoCfgCaptureDeviceId));
 	...

 	public VideoDevice getDevice( String device_id ){
        if( device_id != null ) {
            ArrayList<VideoDevice> devices = ovclient.getAVChat().getVideoController().getDeviceList();
            if( devices != null ) {
                for( VideoDevice device : devices ) {
                    if( device.getID().equalsIgnoreCase( device_id )) {
                        return device;
                    }
                }
            }
        }
        return null;
    }
```


### setActiveResolution
The method allows to define the specific resolution for a camera.

**The method is depricated**
Instead use method [setConfig](#video_setconfig)
```java
 videoController.setConfig(VideoConfigKey.kVideoCfgResolution,ResolutionLevelMed);
```

### getActiveResolution
The method allows to get the resolution current the camera in uses.

**The method is depricated**
Instead use method [getConfig](#video_getconfig)
```java
videoController.getConfig(VideoConfigKey.kVideoCfgResolution);
```

###setFps
The method allows to define the frames per second for a video.

**The method is depricated**
Instead use method [setConfig](#video_setconfig)
```java
 videoController.setConfig(VideoConfigKey.kVideoCfgFps,"15");
```

###getFps
The method allows to get the frames per second for a video.

**The method is depricated**
Instead use method [getConfig](#video_getconfig)
```java
 String fps_value = videoController.getConfig(VideoConfigKey.kVideoCfgFps);
 int fps = Integer.parseInt(fps_value.trim());
```

###setActiveEffect
The method allows to define the effect for a video.

**The method is depricated**
Instead use method [setConfig](#video_setconfig)
```java
videoController.setConfig(VideoConfigKey.kVideoCfgEffectId, effect.getID());
```

###getActiveEffect
The method allows to get the effect for a video.

**The method is depricated**
Instead use method [getConfig](#video_getconfig)

```java
	...
 	Effect effect = getEffect(ovclient.getAVChat().getVideoController().getConfig(VideoConfigKey.kVideoCfgEffectId));
 	...

 	public Effect getEffect( String effect_id ) {
  		if( effect_id != null ) {
        	ArrayList<Effect> effects = ovclient.getAVChat().getVideoController().getEffectList();
            if( effects != null ) {
                for( Effect effect : effects ) {
                        if( effect.getID().equalsIgnoreCase( effect_id )) {
                            return effect;
                        }
                    }
            }
            return null;
        }
```

### ResolutionLevel
This enum type is a special data type that enables define about existing a resolution levels.

Name | Description
---- | -----------------
***ResolutionLevelNotSpecified*** | This resolution level is not defined.  
***ResolutionLevelLow*** | Low quality resolution level. Used for bad network connection. 3G ...  
***ResolutionLevelMed*** | Medium quality resolution level. Used for good network connection. 4G,LTE,Wifi,LAN  
 ***ResolutionLevelHigh*** | High quality resolution level. Used for good network connection. LTE,Wifi,LAN  
***ResolutionLevelHD*** | HD quality resolution level. Used for high network connection. 4G,LTE,Wifi,LAN   

### VideoConfigKey
This enum type is a special data type that enables define about existing keys for video configuration.

Name | Description
---- | ----------------- 
***kVideoCfgCaptureDeviceId*** | Gets/Sets active video device   
***kVideoCfgResolution*** | Gets/Sets active video resolution.  
***kVideoCfgFps*** | Gets/Sets active video FPS  
***kVideoCfgEffectId*** | Gets\Sets active video effect.


## VideoControllerListener

### onRemoteVideoStateChanged
 The method allows to receive the event listener, when remote video state has been changed.

**Parameters:**

Type             | Name   | Description
---------------- | ------ | ---------------------------------------------------
**String**           | uid    | This is a user id of remote video.
**[RemoteVideoState](#remotevideostate)** | state  | This is new remote video state.
**int**              | width  | This is a width resolution of video.
**int**              | height | This is a height resolution of video.
**[sdk_error](../SDK%20Error%20Codes.md)**        | error  | This is an error code about changing in conference.

 
### onCameraStateChanged
The method allows to get the event listener, when camera state has been exchanged.

**Parameters:**

Type      | Name     | Description
--------- | -------- | ---------------------------------------------------
**[ooVooCameraState](#oovoocamerastate)**   | state    | This is new camera state.
**String**    | deviceId | The active video device ID.
**int**       | width    | The width of video resolution.
**int**       | height   | The height of video resolution.
**int**       | fps      | The actual video FPS.
**[sdk_error](../SDK%20Error%20Codes.md)** | error    | The error code of the action.

### onTransmitStateChanged
The method allows to get the event listener, when video transmit state has been exchanged.

**Parameters:**

Type      | Name  | Description
--------- | ----- | ---------------------------------------------------
**boolean**   | state | This is new video transmit state (ON/OFF).
**[sdk_error](../SDK%20Error%20Codes.md)** | error | The error code of the action.


### onVideoPreviewStateChanged
The method allows to get the event listener, when preview video state has been exchanged.

**Parameters:**

Type      | Name  | Description
--------- | ----- | ---------------------------------------------------
**boolean**   | state | This is new preview video state (ON/OFF).
**[sdk_error](../SDK%20Error%20Codes.md)** | error | The error code of the action.


### onCameraChanged
The method allows to get the event listener, when active device has been exchanged.

**Parameters:**

Type      | Name      | Description
--------- | --------- | ---------------------------------------------------
**String**    | deviceId  | The video device ID.
**[sdk_error](../SDK%20Error%20Codes.md)** | errorCode | The error code of the action.


### RemoteVideoState
This enum type is a special data type that enables define about existing a status from the an outside and an incoming video.

Name      | Description
--------- | -----------------
***RVS_Started*** | The remote video started,
***RVS_Stopped*** | The remote video stopped, 
***RVS_Paused***  | The remote video paused by QOS/hold, 
***RVS_Resumed*** | The remote video resumed by QOS/hold.

###ooVooCameraState
This enum type specify the video device state

Name      | Description
--------- | -----------------
CameraNotCreated | The initial state 
CameraOpening | Video device begins opening. The [openCamera](#opencamera) in process 
CameraOpened | Video device opened and ready for use. The [openCamera](#opencamera) is complited
CameraClosing | Video device begins closing. The [closeCamera](#closecamera) in process 
CameraClosed | Video device begins closing. The [closeCamera](#closecamera) is complited
CameraRestarting | Video device begins to restart due to configuration changes
CameraPaused | Video device is poused by Hold or by sysytem request. 

## VideoDevice

### getID
The method allows to get ID of the device.

**Return a value:**

Type       | Description
---------- | -------------------
**String** | The device ID.

### getName
The method allows getting display name of the device.

**Return a value:**

Type | Description  
-----| -------------------  
**String** | The device name.  

### getAvailableResolutions
The method allows getting a list of available resolutions for this device.

**Return a value:**

Type      | Description
--------- | --------------------------
**ArrayList&lt;[ResolutionLevel](#resolutionlevel)&gt;** | Returns a list resolutions.

### isResolutionSupported
The method allows to check, if the given resolution level is supported by this device.

**Parameters:**

Type  | Name | Description
----- | ---- | ---------------------------
**[ResolutionLevel](#resolutionlevel)** | level  | This is a resolution for checking.

**Return a value:**

Type    | Description
------- | ---------------------------------------------
**boolean** | Returns boolean value, If there is support for the requested resolution.


## VideoPanel
The default implimentation of [VideoRender](#videorender)

### Constructors:

### VideoPanel(Context context)
Create a new instance of VideoPanel

**Parameters:**

Type          | Name     | Description
------------- | -------- | ---------------------------------
**Context**   | context  | This is activity context where the panel will attached

**Return a value:** new instance of VideoPanel.

### VideoPanel(Context context, AttributeSet attrs)

**Parameters:**

Type          | Name     | Description
------------- | -------- | ---------------------------------
**Context**   | context  | This is activity context where the panel will attached
**AttributeSet** | set   | This is attribute set for create the video panle

**Return a value:** new instance of VideoPanel.  

###takeScreenshot
Request to screenshot from the video panel, the method works in async mode. 

**Parameters:**

Type             | Name     | Description
---------------- | -------- | ---------------------------------
**[ScreenshotTakeListener](#screenshottakelistener)**   | listener  | Screenshot receiver listener

###takeScreenshot
Request to screenshot from the video panel with specific format and quality, the method works in async mode.

**Parameters:**

Type             | Name     | Description
---------------- | -------- | ---------------------------------
**CompressFormat**   | format  | Result format for screenshot
**int**   | quality  | Qualityfor screenshot
**[ScreenshotTakeListener](#screenshottakelistener)**   | listener  | Screenshot receiver listener

###setVideoOrientationChangesAnimated
Define if video panel will listen for orientation changes or not

**Parameters:**

Type          | Name     | Description
------------- | -------- | ---------------------------------
**boolean**   | state    | On/off orientation change listennig


###setVideoOrientationLocked
Define how video panel will draw orientation changes

**Parameters:**

Type          | Name   | Description
------------- | ------ | ---------------------------------
**boolean**   | state  | On/off animate mode for orientation changes


###setVideoFittingMode
Define how video panel will draw video in fit mode or no

**Parameters:**

Type             | Name     | Description
---------------- | -------- | ---------------------------------
**[FittingMode](#fittingmode)**   | state  | On/off fit mode

###setVideoRenderStateChangeListener
The method allows to set handler for receiving video rendering state events.

**Parameters:**

Type             | Name     | Description
---------------- | -------- | ---------------------------------
**[VideoRenderStateChangeListener](#videorenderstateChangelistener)**   | listener  | Callback receiver


##FittingMode
Enum define a values for how to fit video in video panel

 Name     | Description
 -------- | ---------------------------------
  **FillUp**  | Display the video frame on full video panel surface , video frame may cropped, depends on video aspect ratio and video panel size.
  **AutoBoxing** |  Display the video in letterboxing or pillarbox mode, depends on video aspect ratio and video panel size.

##VideoRenderStateChangeListener

###onVideoRenderStart
Called when first video packet will ready to draw

###onVideoRenderStop
Called when video will stop drawed


##ScreenshotTakeListener
Callback received for screenshot

###onScreenshotReady

**Parameters:**

Type         | Name     | Description
------------ | -------- | ---------------------------------
**Bitmap**   | screenshot  | Screenshot image

##VideoRender

###onProcessVideoFrame
The method allows to receive the event listener, before coding video frame or after decoding video frame.

**Parameters:**

Type             | Name     | Description
---------------- | -------- | ---------------------------------
**[VideoFrame](#videoframe)**   | frame  | This is the video frame


##VideoFrame

### getColorFormat
The method allows to get color format of video frame.

**Return a value:**

Type       | Description
---------- | -------------------
**[ColorFormat](#colorformat)** | A color format.

### getData
The method allows to get object of VideoData and with via this object it possible to get more information about a video frame.

**Return a value:**

Type       | Description
---------- | -------------------
**VideoData** | Returns the object VideoData.

### getDeviceRotationAngle
The method allows to get the rotation angle of device.

**Return a value:**

Type    | Description
------- | -------------------
**int** | Returns a rotation angle of device.

### getFrameNumber
The method allows to get the number of video frame.

**Return a value:**

Type       | Description
---------- | -------------------
**short**  | Returns a number of frame.

### getHeight
The method allows to get height of the video frame.

**Return a value:**

Type    | Description
------- | -------------------
**int**	| Returns height of the video frame.

### getRotationAngle
The method allows to get the angle of camera.

**Return a value:**

Type       | Description
---------- | -------------------
**int**    | Returns a angle of camera.

### getTime
The method allows to get absolute value of time receiving video frame.

**Return a value:**

Type     | Description
-------  | -------------------
**long** | Returns a time receiving video frame.

### getWidth
The method allows to get width of the video frame.

**Return a value:**

Type     | Description
-------  | -------------------
**int**  | Returns width of the video frame.

### isKeyFrame
The method allows to get if the current video frame is key.

**Return a value:**

Type        | Description
----------- | -------------------
**boolean** | Returns boolean, value if this video frame is key.

### isMirror
The method allows to check if video frame which you received in a mirror reflection.

**Return a value:**

Type        | Description
----------- | -------------------
**boolean** | Returns boolean value, if true video is a mirror reflection.


## VideoData

### getColorFormat
The method allows to get color format of video data.

**Return a value:**

Type        | Description
----------- | -------------------
**[ColorFormat](#colorformat)**  | Returns a color format.

### getData
The method allows to get the array of video data.

**Return a value:**

Type        | Description
----------- | -------------------
**byte[]**  | Returns the array of bytes.

### getDataLength
The method allows to get the size of array with video data.

**Return a value:**

Type        | Description
----------- | -------------------
**int** 	| Returns the data length.

### getHeight
The method allows to get height of the video data.

**Return a value:**

Type        | Description
----------- | -------------------
**int** 	| Returns height of the video data.

### getPlane
The method allows to get the plane of video frame.

**Parameters:**

Type       | Name | Description
---------- | ---- | -------------------
**int**    | num  | Number of plane.

**Return a value:**

Type        | Description
----------- | -------------------
**int** 	| Returns pointer of the video data.

### getPlanePitch
The method allows to get a size array of plane.

**Parameters:**

Type       | Name | Description
---------- | ---- | -------------------
**int**    | num | Number of plane.

**Return a value:**

Type        | Description
----------- | -------------------
**int** 	| Returns a size array of plane.

### getPlanesCount
The method allows to get the number of planes.

**Return a value:**

Type        | Description
----------- | -------------------
**int** 	| Returns a number of planes.

### getWidth
The method allows to get width of the video data.

**Return a value:**

Type        | Description
----------- | -------------------
**int** 	| Returns width of the video data.

##ColorFormat

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

---

##Effect

### getCategory
The method allows to get category of the effect.

**Return a value:**

Type        | Description
----------- | -------------------
**String**  | Returns a category of the effect.

### getIconUrl
The method allows to get URL to icon for the effect.

**Return a value:**

Type        | Description
----------- | -------------------
**String**  | Returns URL to icon for the effect.

### getID
The method allows to get unique ID of the effect.

**Return a value:**

Type        | Description
----------- | -------------------
**String**  | Returns ID of the effect.

### getName
The method allows to get name of the effect.

**Return a value:**

Type        | Description
----------- | -------------------
**String**  | Returns name of the effect.

### getPurchaseId
The method allows to get unique static ID of the effect.

**Return a value:**

Type        | Description
----------- | -------------------
**String**  | Returns static ID of the effect.

### getProperty
The method allows to get effect propery by key

**Parameters:**

Type       | Name | Description
---------- | ---- | -------------------
**String** | key  | The property key name

**Return a value:**

Type        | Description
----------- | -------------------
**String**  | The property value

---

# Messaging


### connect
The method start connect to the messaging service

**Return a value:** no result, calback [onConnectivityStateChange](#onconnectivitystatechange) will fire.


### disconnect
The method start disconnect from the messaging service

**Return a value:** no result, calback [onConnectivityStateChange](#onconnectivitystatechange) will fire.

### isConnected

**Return a value:**

Type    | Description
--------| -------------------
**boolean** | true mean that sender connected to messaging service, false not connected

### sendMessage
The method allows to send text message to user(s) and receive a

**Parameters:**

Type                      | Name      | Description
------------------------- | --------- | ----------------------------------------------
**[Message](#message)**   | message   | The message object contain a body and list of recipients.
**[ooVooSdkResultListener](#oovoosdkresultlistener)**    | listener  | Callback receiver

```java
	  ovclient.getMessaging().sendMessage(message,new ooVooSdkResultListener() {
	      @Override
	         public void onResult(ooVooSdkResult sdkResult) {
	         if (sdkResult.getResult() == sdk_error.OK) {
	         	    //The message was sent successful
	         }
	         else
	         {
	         	//The message sed faild
	         }
	      }
	    }
	 });
```

### sendAcknowledgement
The async method allows sending text message acknowledgement state

**Parameters:**

Type                      | Name     | Description
------------------------- | -------- | ----------------------------------------------
**[MessageAcknowledgeState](#messageacknowledgestate)** |	state    | The new state for acknowledge
**[Message](#message)** |	message  | Received message form other user 
**[ooVooSdkResultListener](#oovoosdkresultlistener)** | listener | Callback response


### setListener
The method allows to set handler for receiving messaging event from SDK.

**Parameters:**

Type           | Name     | Description
-------------- | -------- | ------------------------------------------------
**[MessagingListener](#messaginglistener)** | listener | The async listener which allows to set handler for receiving the events about status changes from module messaging.

## MessagingListener

### onMessageReceive
The method allows to receive the event listener, when obtained a message.

**Parameters:**

Type             | Name     | Description
---------------- | -------- | ---------------------------------
**[Message](#message)** | message  | This is a message was received  

 
### onMessageAcknowledgementReceived
The method allows to receive the event listener, when obtained a message with acknowledgement.
**Parameters:**

Type                             | Name       | Description
-------------------------------- | ---------- | ---------------------------------
**[MessageAcknowledgeState](#messageacknowledgestate)**      | state      | This is acknowledgement state 
**String**                       | messageID  | The message ID   

 
### onConnectivityStateChange
The method allows to receive the event about connection state.
**Parameters:**

Type                             | Name       | Description
-------------------------------- | ---------- | ---------------------------------
**[ConnectivityState](#connectivitystate)** | state  | This is connectivity state 
**[sdk_error](../SDK%20Error%20Codes.md)**  | error  | The error code
**String**                       | description | The error description , can be null  

  
### ConnectivityState 
This enum type is special data type for enables define about existing status of connection of the sender.

Name             | Description
---------------- | ---------------------------------
**Connected**    | State that sender connected to messaging service
**Disconnected** | State that sender disconnected from messaging service  


### MessageAcknowledgeState
This enum type is a special data type that enables define about existing status a messages of recipient.

Name       | Description
---------- | ---------------------------------
**Delivered**  | State that the message was delivered to the recipient
**Readed**	| State that a message was readed by recipient  


## Message

### Constructors:

###<a name="msgconstructor1"></a>Message(String to, String message) 

Construct a new instance of Message  , InstantiationException will be throw if recipients ID is null or empty or/and message is null

 **Parameters:**

Type      | Name      | Description
--------- | --------- | ----------------------------------------------
**String**    | to    | The recipient ID .
**String**    | body  | Message body limited to 1kB

**Return a value:** new Message class instance.

###<a name="msgconstructor2"></a>Message(ArrayList&lt;String&gt; to_list, String message)
Construct a new instance of Message , InstantiationException will be throw if list of recipients is null or empty or/and message is null

 **Parameters:**

Type                      | Name      | Description
------------------------- | --------- |-----------------------------------------------
**ArrayList&lt;String&gt;**         | to_list   | The recipient ID list .
**String**                    | body   | Message body limited to 1kB

**Return a value:** new Message class instance.

### Message(Message message) 
Copy constructor , InstantiationException will be throw if in message is null.

 **Parameters:**

Type       | Name      | Description
---------- | --------- |-----------------------------------------------
**Message**    | message   | The message from copy to a new instance

**Return a value:** new copied Message class instance.

### getFrom 
The method allows to get sender ID.

 **Return a value:**

 Type          | Description
 ------------- | -------------------------
 **String**    | Sender user ID.

### getTo
The method allows to get user ID of the receiver.

**Return a value:**

 Type          | Description
 ------------- | -------------------------
 **String**    | Receiver user ID.

### getTimestamp
The method allows to get a time of last operation.

**Return a value:**

 Type          | Description
 ------------- | -------------------------
 **long**      | Last operation time with the instance.

### getID
The method allows to get registered ID of the message.

**Return a value:**

 Type          | Description
 ------------- | -------------------------
 **String**    | The message uniq ID.

### getBody
The method allows to get body of the message.

**Return a value:**

 Type          | Description
 ------------- | -------------------------
 **String**    | The message body.


# Push

### subscribe

The method allows to subscribe to push service.

**Parameters:**

Type                      | Name             | Description
------------------------- |----------------- | -----------------------------------
**String**                    | token            | The GCM token
**String**                   | uniq_device_uid  | The uniq device ID
**[ooVooSdkResultListener](#oovoosdkresultlistener)**    | completion       | Callback receiver

### unsubscribe
The method allows to unsubscribe from push service.

**Parameters:**

Type                      | Name             | Description
------------------------- |----------------- | ---------------------------------------------------
**String**                    | token            | The GCM token
**String**                    | uniq_device_uid  | The uniq device ID
**[ooVooSdkResultListener](#oovoosdkresultlistener)**    | completion         | Callback receiver

### send
Use for sending push messages

**Parameters:**

Type                      | Name              | Description
------------------------- | ----------------- | ---------------------------------------------------
**[PushNotificationMessage](#pushnotificationmessage)**   | message           | Message to send
**[ooVooSdkResultListener](#oovoosdkresultlistener)**    | completion          | Callback receiver

## PushNotificationMessage

### Constructors:
###<a name="pnmsgc1"></a>PushNotificationMessage(ArrayList&lt;String&gt; users, String payload, String property)
Construct a new instance of the PushNotificationMessage.

 **Parameters:**

 Type                      | Name              | Description
 ------------------------- | ----------------- | -----------------------------------
 **ArrayList&lt;String&gt;**         | users             | List of recipients
 **String**                    | payload           | Message payload
 **String**                    | property          | Message property

 **Return a value:** New instance of PushNotificationMessage .

###<a name="pnmsgc2"></a>PushNotificationMessage(ArrayList&lt;String&gt; users, String payload)
 Construct a new instance of PushNotificationMessage.

 **Parameters:**

 Type                      | Name              | Description
 ------------------------- | ----------------- | ---------------------------------------------------
 **ArrayList&lt;String&gt;**         | users           | List of recipients
 **String**                    | payload           | Message payload

 **Return a value:** New instance of PushNotificationMessage .

### getPayload
The method allows to get a message with data payload.

**Return a value:**

Type        | Description
----------- | ----------------------------------
**String**  | Return message payload.

### getProperty
The method allows to get a property of message.

**Return a value:**

Type        | Description
----------- | ----------------------------------
**String**  | Return the message property.


## PluginFactory

### createPluginInstance
The method allows to create a custom plugin and integrate him in ooVoo SDK.

**Return a value:**

Type       | Description
---------- | -------------------
**long**   | Returns unique ID of instance.

## ooVooSdkResultListener

### onResult
The method allows to get all events from lower level of SDK.

**Parameters:**

Type               | Description
------------------ | ----------------------------------------------------------
**[ooVooSdkResult](#oovoosdkresult)** | The async listener which allows to get result on requests.

## ooVooSdkResult

### getResult
The method allows to get a result on a request.


Type              | Description
----------------- | --------------------------------
**[sdk_error](../SDK%20Error%20Codes.md)** | Returns the result on a request.

### getDescription
The method allows to get a description on a request.

**Return a value:**

Type           | Description
-------------- | -------------------------------------
**String**	   | Returns the description on a request.

### getUserInfo
The method allows to get additional information on a request.

**Return a value:**

Type                            | Description
------------------------------- | ------------------------------------------------
**Hashtable&lt;String, Object&gt;** | Returns the additional information on a request.


## GLPerformanceUtlis
Utility allows getting advanced device information.

### getCurrentCpuFrequency
The method allows to get the current frequency of CPU in Hz.

**Return a value:**

Type    | Description
------- | ----------------------------------
**int** | Returns frequency in Hz.

### getEnableThreshold
The method allows to get the maximum time for perform action with the current resolution. If the return value from getPerfValue is bigger than the value from getEnableThreshold, GPU buffer reading for that resolution is not suggested to be used in the app.

**Return a value:**

Type     | Description
-------- | ----------------------------------
**long** | Returns suggested value about the acceptable threshold in microseconds.

### getNumCore
The method allows to get the number of the CPU core.

**Return a value:**

Type        | Description
----------- | ----------------------------------
**int**		| Returns the number of cores.

### getPerfValue
The method allows to get the test result for specific resolution. CIF would only be tested if the VGA cannot meet the "suggested enable threshold" If the resolution was not been test function will return -1.

**Parameters:**

Type        | Name | Description
----------- | ---- | ----------------------------------
**String**  | resolution | Available resolution VGA_PERFORMANCE/CIF_PERFORMANCE

**Return a value:**

Type        | Description
----------- | ----------------------------------
**long** 	| Returns average time in microsecond of GPU buffer reading.

### isTegraDetected
The method allows detecting the tegra device type

**Return a value:**

Type   		| Description
----------- | ----------------------------------
**boolean** | Returns boolean value if this is Tegra device.

