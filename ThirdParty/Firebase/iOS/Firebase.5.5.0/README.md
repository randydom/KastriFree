# Firebase iOS SDKs

This directory contains the full Firebase distribution, packaged as static
frameworks that can be integrated into your app.

# Integration Instructions

Each Firebase component requires several frameworks in order to function
properly. Each section below lists the frameworks you'll need to include
in your project in order to use that Firebase SDK in your application.

To integrate a Firebase SDK with your app:

1. Find the desired SDK in the list below.
2. Make sure you have an Xcode project open in Xcode.
3. In Xcode, hit `⌘-1` to open the Project Navigator pane. It will open on
   left side of the Xcode window if it wasn't already open.
4. Drag each framework from the "Analytics" directory into the Project
   Navigator pane. In the dialog box that appears, make sure the target you
   want the framework to be added to has a checkmark next to it, and that
   you've selected "Copy items if needed". If you already have Firebase
   frameworks in your project, make sure that you replace them with the new
   versions.
5. Drag each framework from the directory named after the SDK into the Project
   Navigator pane. Note that there may be no additional frameworks, in which
   case this directory will be empty. For instance, if you want the Database
   SDK, look in the Database folder for the required frameworks. In the dialog
   box that appears, make sure the target you want this framework to be added to
   has a checkmark next to it, and that you've selected "Copy items if needed."

   *Do not add the Firebase frameworks to the "Embed Frameworks" Xcode build
   phase. The Firebase frameworks are not embedded dynamic frameworks, but are
   (static frameworks)[https://www.raywenderlich.com/65964/create-a-framework-for-ios]
   which cannot be embedded into your application's bundle.*

6. If the SDK has resources, go into the Resources folders, which will be in
   the SDK folder. Drag all of those resources into the Project Navigator, just
   like the frameworks, again making sure that the target you want to add these
   resources to has a checkmark next to it, and that you've selected "Copy items
   if needed".
7. Add the -ObjC flag to "Other Linker Settings":
  a. In your project settings, open the Settings panel for your target
  b. Go to the Build Settings tab and find the "Other Linker Flags" setting
     in the Linking section.
  c. Double-click the setting, click the '+' button, and add "-ObjC" (without
     quotes)
8. Drag the `Firebase.h` header in this directory into your project. This will
   allow you to `#import "Firebase.h"` and start using any Firebase SDK that you
   have.
9. If you're using Swift, or you want to use modules, drag module.modulemap into
   your project and update your User Header Search Paths to contain the
   directory that contains your module map.
10. You're done! Compile your target and start using Firebase.

If you want to add another SDK, repeat the steps above with the frameworks for
the new SDK. You only need to add each framework once, so if you've already
added a framework for one SDK, you don't need to add it again. Note that some
frameworks are required by multiple SDKs, and so appear in multiple folders.

The Firebase frameworks list the system libraries and frameworks they depend on
in their modulemaps. If you have disabled the "Link Frameworks Automatically"
option in your Xcode project/workspace, you will need to add the system
frameworks and libraries listed in each Firebase framework's
<Name>.framework/Modules/module.modulemap file to your target's or targets'
"Link Binary With Libraries" build phase.

"(~> X)" below means that the SDK requires all of the frameworks from X. You
should make sure to include all of the frameworks from X when including the SDK.

NOTE: If you are upgrading FirebaseAnalytics from before Firebase 5.5.0,
      `FirebaseNanoPB` has been renamed to `MeasurementNanoPB`. After you add
      `MeasurementNanoPB` to your project, please remove `FirebaseNanoPB` to avoid
      potential symbol collisions.

## Analytics
  - FirebaseAnalytics.framework
  - FirebaseCoreDiagnostics.framework
  - FirebaseCore.framework
  - FirebaseInstanceID.framework
  - GoogleAppMeasurement.framework
  - MeasurementNanoPB.framework
  - GoogleUtilities.framework
  - nanopb.framework
## ABTesting (~> Analytics)
  - FirebaseABTesting.framework
  - Protobuf.framework
## AdMob (~> Analytics)
  - GoogleMobileAds.framework
## Auth (~> Analytics)
  - FirebaseAuth.framework
  - GTMSessionFetcher.framework
## Crash (~> Analytics)
  - FirebaseCrash.framework
  - GoogleToolboxForMac.framework
  - Protobuf.framework
## Database (~> Analytics)
  - FirebaseDatabase.framework
  - leveldb-library.framework
## DynamicLinks (~> Analytics)
  - FirebaseDynamicLinks.framework
## Firestore (~> Analytics)
  - BoringSSL.framework
  - FirebaseFirestore.framework
  - Protobuf.framework
  - gRPC.framework
  - gRPC-Core.framework
  - gRPC-ProtoRPC.framework
  - gRPC-RxLibrary.framework
  - leveldb-library.framework

  You'll also need to add the resources in the
  Resources directory into your target's main
  bundle.
## Functions (~> Analytics)
  - FirebaseFunctions.framework
  - GTMSessionFetcher.framework
## Invites (~> Analytics)
  - FirebaseDynamicLinks.framework
  - FirebaseInvites.framework
  - GTMOAuth2.framework
  - GTMSessionFetcher.framework
  - GoogleAPIClientForREST.framework
  - GoogleSignIn.framework
  - GoogleToolboxForMac.framework
  - Protobuf.framework

  You'll also need to add the resources in the
  Resources directory into your target's main
  bundle.
## Messaging (~> Analytics)
  - FirebaseMessaging.framework
  - Protobuf.framework
## MLModelInterpreter (~> Analytics)
  - FirebaseMLCommon.framework
  - FirebaseMLModelInterpreter.framework
  - GTMSessionFetcher.framework
  - tensorflow_lite.framework
## MLVision (~> Analytics)
  - FirebaseMLCommon.framework
  - FirebaseMLVision.framework
  - GTMSessionFetcher.framework
  - GoogleAPIClientForREST.framework
  - BarcodeDetector.framework
  - TextDetector.framework
  - FaceDetector.framework
  - LabelDetector.framework
  - GoogleMobileVision.framework
  - GoogleToolboxForMac.framework
  - Protobuf.framework

  You'll also need to add the resources in the
  Resources directory into your target's main
  bundle.
## MLVisionBarcodeModel (~> Analytics)
  - FirebaseMLVisionBarcodeModel.framework
  - GTMSessionFetcher.framework
  - BarcodeDetector.framework
  - TextDetector.framework
  - FaceDetector.framework
  - LabelDetector.framework
  - GoogleMobileVision.framework
  - GoogleToolboxForMac.framework
  - Protobuf.framework

  You'll also need to add the resources in the
  Resources directory into your target's main
  bundle.
## MLVisionFaceModel (~> Analytics)
  - FirebaseMLVisionFaceModel.framework
  - GTMSessionFetcher.framework
  - BarcodeDetector.framework
  - TextDetector.framework
  - FaceDetector.framework
  - LabelDetector.framework
  - GoogleMobileVision.framework
  - GoogleToolboxForMac.framework
  - Protobuf.framework

  You'll also need to add the resources in the
  Resources directory into your target's main
  bundle.
## MLVisionLabelModel (~> Analytics)
  - FirebaseMLVisionLabelModel.framework
  - GTMSessionFetcher.framework
  - BarcodeDetector.framework
  - TextDetector.framework
  - FaceDetector.framework
  - LabelDetector.framework
  - GoogleMobileVision.framework
  - GoogleToolboxForMac.framework
  - Protobuf.framework

  You'll also need to add the resources in the
  Resources directory into your target's main
  bundle.
## MLVisionTextModel (~> Analytics)
  - FirebaseMLVisionTextModel.framework
  - GTMSessionFetcher.framework
  - BarcodeDetector.framework
  - TextDetector.framework
  - FaceDetector.framework
  - LabelDetector.framework
  - GoogleMobileVision.framework
  - GoogleToolboxForMac.framework
  - Protobuf.framework

  You'll also need to add the resources in the
  Resources directory into your target's main
  bundle.
## Performance (~> Analytics)
  - FirebasePerformance.framework
  - GTMSessionFetcher.framework
  - GoogleToolboxForMac.framework
  - Protobuf.framework
## RemoteConfig (~> Analytics)
  - FirebaseABTesting.framework
  - FirebaseRemoteConfig.framework
  - Protobuf.framework
## Storage (~> Analytics)
  - FirebaseStorage.framework
  - GTMSessionFetcher.framework

# Samples

You can get samples for Firebase from https://github.com/firebase/quickstart-ios:

    git clone https://github.com/firebase/quickstart-ios

Note that several of the samples depend on SDKs that are not included with
this archive; for example, FirebaseUI. For the samples that depend on SDKs not
included in this archive, you'll need to use CocoaPods.

# Versions

The frameworks in this directory map to these versions of the Firebase SDKs in
CocoaPods.

           CocoaPod           | Version
----------------------------- | -------
BoringSSL                     | 10.0.5
Firebase                      | 5.5.0
FirebaseABTesting             | 2.0.0
FirebaseAnalytics             | 5.1.0
FirebaseAuth                  | 5.0.3
FirebaseAuthInterop           | 1.0.0
FirebaseCore                  | 5.1.0
FirebaseCrash                 | 3.1.0
FirebaseDatabase              | 5.0.2
FirebaseDynamicLinks          | 3.0.2
FirebaseFirestore             | 0.13.0
FirebaseFunctions             | 2.1.0
FirebaseInstanceID            | 3.2.0
FirebaseInvites               | 3.0.0
FirebaseMLCommon              | 0.11.0
FirebaseMLModelInterpreter    | 0.11.0
FirebaseMLVision              | 0.11.0
FirebaseMLVisionBarcodeModel  | 0.11.0
FirebaseMLVisionFaceModel     | 0.11.0
FirebaseMLVisionLabelModel    | 0.11.0
FirebaseMLVisionTextModel     | 0.11.0
FirebaseMessaging             | 3.1.0
FirebasePerformance           | 2.1.0
FirebaseRemoteConfig          | 3.0.1
FirebaseStorage               | 3.0.0
GTMOAuth2                     | 1.1.6
GTMSessionFetcher             | 1.2.0
Google-Mobile-Ads-SDK         | 7.31.0
GoogleAPIClientForREST        | 1.3.5
GoogleAppMeasurement          | 5.1.0
GoogleMobileVision            | 1.5.0
GoogleSignIn                  | 4.1.2
GoogleToolboxForMac           | 2.1.4
GoogleUtilities               | 5.2.1
Protobuf                      | 3.6.0
TensorFlowLite                | 0.1.7
gRPC                          | 1.13.0
gRPC-Core                     | 1.13.0
gRPC-ProtoRPC                 | 1.13.0
gRPC-RxLibrary                | 1.13.0
leveldb-library               | 1.20
nanopb                        | 0.3.8

