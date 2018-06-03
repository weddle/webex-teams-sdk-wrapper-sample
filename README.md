# Webex Teams Android SDK Wrapper Sample

## Embed video calling capabilities into your Android App in just a few lines of code

This Simple Test application demonstrates the Webex Teams Android SDK Wrapper.

The Webex Teams Android SDK Wrapper is an unofficial convenience library written on top of the Webex Teams Android SDK.  It provides a simple way to add Webex Teams video calling into your Android application.  This library provides a drop in Activity class that can be used to start a Webex Teams video call, without needing to understand the details of the underlying Webex Teams SDK.

This aplication demonstrates how to incorporate the wrapper into an Android application without having to worry about the underlying Webex Teams Android SDK.

The wrapper handles layout of the video streams for local and remote participants, the call setup process, in call functionality such as muting, as well as hanging up the call.

This sample application demonstrates starting the Call activity with an Intent and passing in the TeamsID to call as well as the Guest Token (JWT) to authenticate the call.

## Requirements

Download or clone this repository and import it into Android Studio as a new project.  This application's build.gradle will dynamically pull in the Webex Teams Android SDK Wrapper using JitPack.

You will need to sync gradle after the project imports.  You may see warnings and or errors initially, but resync gradle and build the app.  To test the app, you will need a valid Webex Teams JWT and and TeamsID to call.

This sample application has been tested on a Google Pixel and a Samsung Galaxy S7 Edge.

## Implementation
The Webex Teams SDK Wrapper uses an Activity as a drop in to display the Video call.  The Call Activity is started by passing an intent with a Guest Token (JWT) and the TeamsID to call.

You can look at the sample MainActivity to see how this is done.  In this case, the onClick listener invokes the SparkCall activity by intent.

```
Intent intent = new Intent(MainActivity.this, SparkCall.class);
intent.putExtra(SparkCall.INTENT_CALLEE, mCallEdit.getText().toString());
intent.putExtra(SparkCall.INTENT_JWT, mTokenEdit.getText().toString());

startActivity(intent);
```

In this example, the call is started based on the contents of two EditText fields.

The Call activity will return control back to your activity in the event of a call failure or a hangup event.


## License
Webex Teams Android SDK Wrapper Sample is available under the MIT license. See the LICENSE file for more info.
