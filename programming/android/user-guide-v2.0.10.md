---
layout: default-layout
title: Dynamsoft Document Normalizer for Android - User Guide
description: This is the user guide of Dynamsoft Document Normalizer for Android SDK.
keywords: user guide, android
needAutoGenerateSidebar: true
needGenerateH4Content: true
noTitleIndex: true
permalink: /programming/android/user-guide-v2.0.10.html
---

# Getting Started with Android

In this guide, you will learn step by step on how to build a document normalization application with Dynamsoft Document Normalizer Android SDK.

> Read more on [Dynamsoft Document Normalizer Features](https://www.dynamsoft.com/document-normalizer/docs/core/introduction/index.html)

- [Getting Started with Android](#getting-started-with-android)
  - [Requirements](#requirements)
  - [Build Your First Application](#build-your-first-application)
    - [Create a New Project](#create-a-new-project)
    - [Add the SDK](#add-the-sdk)
      - [Add the Library Manually](#add-the-library-manually)
      - [Add the Library via Maven](#add-the-library-via-maven)
    - [Initialize License](#initialize-license)
    - [MainActivity for Realtime Document Normalization](#mainactivity-for-realtime-document-normalization)
      - [Initialize Camera Module](#initialize-camera-module)
      - [Initialize Capture Vision Router](#initialize-capture-vision-router)
      - [Add a Captured Result Receiver and Filter](#add-a-captured-result-receiver-and-filter)
      - [Start and Stop Video Document Normalization](#start-and-stop-video-document-normalization)
      - [Additional Steps in MainActivity](#additional-steps-in-mainactivity)
    - [ResultActivity for Displaying the Normalized Image](#resultactivity-for-displaying-the-normalized-image)
      - [Display the Normalized Image](#display-the-normalized-image)
    - [Build and Run the Project](#build-and-run-the-project)

## Requirements

- Supported OS: Android 5.0 (API Level 21) or higher.
- Supported ABI: **armeabi-v7a**, **arm64-v8a**, **x86** and **x86_64**.
- Development Environment: Android Studio 2022.2.1 or higher.

## Build Your First Application

In this section, let's see how to create a HelloWorld app for normalizing documents from camera video input.

>Note:
>
> - Android Studio 2022.2.1 is used here in this guide.
> - You can get the source code of the HelloWorld app from the following link
>   - [Java](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/android/HelloWorld/AutoNormalize){:target="_blank"}.
>   - [Kotlin](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/android/HelloWorld/AutoNormalizeKt){:target="_blank"}.

### Create a New Project

1. Open Android Studio, select **File > New > New Project**.

2. Choose the correct template for your project. In this sample, we use **Empty Activity**.

3. When prompted, choose your app name 'HelloWorld' and set the **Save** location, **Language**, and **Minimum SDK** (we use 21 here).
    > Note:
    >
    > - With **minSdkVersion** set to 21, your app is compatible with more than 94.1% of devices on the Google Play Store (last update: March 2021).

### Add the SDK

There are two ways to add the SDK into your project - **Manually** and **Maven**.

#### Add the Library Manually

1. Download the SDK package from the <a href="https://download2.dynamsoft.com/ddn/dynamsoft-document-normalizer-android-2.0.10.zip" target="_blank">Dynamsoft website</a>. After unzipping, You can find the following **aar** files under the **Dynamsoft\Libs** directory:

   | File | Description | Mandatory/Optional |
   |:-----|:------------|:-------------------|
   | `DynamsoftDocumentNormalizer.aar` | The Dynamsoft Document Normalizer module extracts structural information from document images, including document boundaries, shadow areas, and text areas. It uses this information to generate normalized document images through processes such as deskewing, shadow removal, and distortion correction. | Mandatory |
   | `DynamsoftCore.aar`  | The Dynamsoft Core module lays the foundation for Dynamsoft SDKs based on the DCV (Dynamsoft Capture Vision) architecture. It encapsulates the basic classes, interfaces, and enumerations shared by these SDKs. | Mandatory |
   | `DynamsoftCaptureVisionRouter.aar` | The Dynamsoft Capture Vision Router module is the cornerstone of the Dynamsoft Capture Vision (DCV) architecture. It focuses on coordinating batch image processing and provides APIs for setting up image sources and result receivers, configuring workflows with parameters, and controlling processes. | Mandatory |
   | `DynamsoftImageProcessing.aar` | The Dynamsoft Image Processing module facilitates digital image processing and supports operations for other modules, including the Barcode Reader, Label Recognizer, and Document Normalizer. | Mandatory |
   | `DynamsoftLicense.aar` | The Dynamsoft License module manages the licensing aspects of Dynamsoft SDKs based on the DCV (Dynamsoft Capture Vision) architecture. | Mandatory |
   | `DynamsoftCameraEnhancer.aar` | The [Dynamsoft Camera Enhancer]({{ site.dce_android_api }}){:target="_blank"} module controls the camera, transforming it into an image source for the DCV (Dynamsoft Capture Vision) architecture through ISA implementation. It also enhances image quality during acquisition and provides basic viewers for user interaction. | Mandatory |
   | `DynamsoftUtility.aar` | The Dynamsoft Utility module defines auxiliary classes, including the ImageManager, and implementations of the CRF (Captured Result Filter) and ISA (Image Source Adapter) . These are shared by all Dynamsoft SDKs based on the DCV (Dynamsoft Capture Vision) architecture. | Optional |

2. Copy the above five **aar** files to the target directory `HelloWorld\app\libs`

3. Open the file `HelloWorld\app\build.gradle` and add reference in the dependencies:

    ```groovy
    dependencies {
         implementation fileTree(dir: 'libs', include: ['*.aar'])

         def camerax_version = '1.1.0'
         implementation "androidx.camera:camera-core:$camerax_version"
         implementation "androidx.camera:camera-camera2:$camerax_version"
         implementation "androidx.camera:camera-lifecycle:$camerax_version"
         implementation "androidx.camera:camera-view:$camerax_version"
    }
    ```

    > Note:
    >
    > DCE 4.x is based on Android CameraX, so you need to add the CameraX dependency manually.

4. Click **Sync Now**. After the synchronization completes, the SDK is added to the project.

#### Add the Library via Maven

1. Open the file `HelloWorld\app\build.gradle` and add the remote repository:

    ```groovy
    repositories {
         maven {
            url "https://download2.dynamsoft.com/maven/aar"
         }
    }
    ```

2. Add reference in the dependencies:

   ```groovy
   dependencies {
      implementation 'com.dynamsoft:dynamsoftcapturevisionrouter:2.0.10'
      implementation 'com.dynamsoft:dynamsoftdocumentnormalizer:2.0.10'
      implementation 'com.dynamsoft:dynamsoftcameraenhancer:4.0.0'
      implementation 'com.dynamsoft:dynamsoftutility:1.0.10'
   }
   ```

3. Click **Sync Now**. After the synchronization completes, the SDK is added to the project.

### Initialize License

1. Import the `LicenseManager` class and initialize the license in the file `MyApplication.java`.

   ```java
   import com.dynamsoft.license.LicenseManager;

   public class MyApplication extends Application {
      private static final String TAG = "MyApplication";
      private static final String LICENSE = "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9";

      @Override
      public void onCreate() {
         super.onCreate();
         LicenseManager.initLicense(LICENSE, this, (isSuccess, error) -> {
               if (!isSuccess) {
                  Log.e(TAG, "InitLicense Error: " + error);
               }
         });
      }
   }
   ```

   >Note:  
   >  
   >- Network connection is required for the license to work.
   >- The license string here will grant you a time-limited trial license.
   >- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=ddn&utm_source=guide&package=android){:target="_blank"} link

### MainActivity for Realtime Document Normalization

#### Initialize Camera Module

1. In the Project window, open **app > res > layout > `activity_main.xml`** and create a DCE camera view section under the root node.

    ```xml
    <com.dynamsoft.dce.DCECameraView
        android:id="@+id/camera_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent">
    </com.dynamsoft.dce.DCECameraView>
    ```

2. Import the camera module, initialize the camera view and bind to the created Camera Enhancer instance in the file `MainActivity.java`.

   ```java
   ...
   
   import com.dynamsoft.dce.CameraView;
   import com.dynamsoft.dce.CameraEnhancer;
   import com.dynamsoft.dce.CameraEnhancerException;
   import com.dynamsoft.dce.utils.PermissionUtil;

   public class MainActivity extends AppCompatActivity {
      private CameraEnhancer mCamera;

      @Override
      protected void onCreate(Bundle savedInstanceState) { 

         ...

         CameraView cameraView = findViewById(R.id.camera_view);
         mCamera = new CameraEnhancer(cameraView, MainActivity.this);
 
         PermissionUtil.requestCameraPermission(MainActivity.this);
      }
   }
   ```

#### Initialize Capture Vision Router

1. Import and initialize the capture vision router, and set the created Camera Enhancer instance as the input image source.

   ```java
   ...

   import com.dynamsoft.cvr.CaptureVisionRouter;
   import com.dynamsoft.cvr.CaptureVisionException;

   public class MainActivity extends AppCompatActivity {
      
      ...

      private CaptureVisionRouter mRouter;

      @Override
      protected void onCreate(Bundle savedInstanceState) { 
         
         ...

         mRouter = new CaptureVisionRouter(MainActivity.this);
         try {
               mRouter.setInput(mCamera);
         } catch (CaptureVisionRouterException e) {
               e.printStackTrace();
         }
      }
   }
   ```

#### Add a Captured Result Receiver and Filter

1. Add a result receiver to get the normalized image results.

   ```java
   ...

   import com.dynamsoft.core.basic_structures.CapturedResultReceiver;
   import com.dynamsoft.core.basic_structures.ImageData;
   import com.dynamsoft.cvr.EnumPresetTemplate;
   import com.dynamsoft.ddn.NormalizedImagesResult;

   public class MainActivity extends AppCompatActivity {
      
      ...

      public static ImageData mNormalizedImageData;
      private boolean mJumpToOtherActivity = false;

      @Override
      protected void onCreate(Bundle savedInstanceState) { 
         
         ...
         
         mRouter.addResultReceiver(new CapturedResultReceiver() {
               @Override
               public void onNormalizedImagesReceived(NormalizedImagesResult result) {
                  if (mJumpToOtherActivity && result.getItems().length > 0) {
                     mJumpToOtherActivity = false;

                     mNormalizedImageData = result.getItems()[0].getImageData();

                     Intent intent = new Intent(MainActivity.this, ResultActivity.class);
                     startActivity(intent);
                  }
               }
         });
      }
   }
   ```

2. Add a result cross filter to validate the normalized image result across multiple frames.

   ```java
   ...

   import com.dynamsoft.utility.MultiFrameResultCrossFilter;

   public class MainActivity extends AppCompatActivity {
      
      ...

      @Override
      protected void onCreate(Bundle savedInstanceState) { 
         
         ...
         
         MultiFrameResultCrossFilter filter = new MultiFrameResultCrossFilter();
         filter.enableResultCrossVerification(CRIT_NORMALIZED_IMAGE, true);
         mRouter.addResultFilter(filter);
      }
   }
   ```

#### Start and Stop Video Document Normalization

1. Override the `MainActivity.onResume` function to open camera and start video document normalization, override the `MainActivity.onPause` function to close camera and stop video document normalization.

   ```java
   public class MainActivity extends AppCompatActivity {
      
      ...

      @Override
      public void onResume() {
         super.onResume();
         try {
               mCamera.open();
               mRouter.startCapturing(EnumPresetTemplate.PT_DETECT_AND_NORMALIZE_DOCUMENT);
         } catch (CameraEnhancerException | CaptureVisionRouterException e) {
               e.printStackTrace();
         }
      }

      @Override
      public void onPause() {
         super.onPause();
         try {
               mCamera.close();
         } catch (CameraEnhancerException e) {
               e.printStackTrace();
         }

         mRouter.stopCapturing();
      }
   }
   ```

2. Add `onCaptureBtnClick` function to start the video document normalization. After start capturing, the SDK will process the video frames from the Camera Enhancer, then send the normalized image results to the registered result receiver.

   ```java
   public class MainActivity extends AppCompatActivity {
      
      ...

      public void onCaptureBtnClick(View v) {
        mJumpToOtherActivity = true;
      }
   }
   ```

#### Additional Steps in MainActivity

1. In the Project window, open **app > res > layout > `activity_main.xml`**, create a button under the root node to capture the quads detected on the image.

   ```xml
   ...

   <Button
      android:id="@+id/btn_capture"
      android:layout_width="130dp"
      android:layout_height="50dp"
      android:layout_marginBottom="8dp"
      android:onClick="onCaptureBtnClick"
      android:text="Capture"
      app:layout_constraintBottom_toBottomOf="parent"
      app:layout_constraintEnd_toEndOf="parent"
      app:layout_constraintHorizontal_bias="0.5"
      app:layout_constraintStart_toStartOf="parent" />
   ```

### ResultActivity for Displaying the Normalized Image

#### Display the Normalized Image

1. Create a new empty activity named `ResultActivity`.

2. In the Project window, open **app > res > layout > `activity_result.xml`**, create a image view under the root node to display the result image.

   ```xml
   <ImageView
      android:id="@+id/iv_normalize"
      android:layout_width="match_parent"
      android:layout_height="match_parent"/>
   ```

3. Display the normalized image.

   ```java
   import com.dynamsoft.core.basic_structures.CoreException;

   public class ResultActivity extends AppCompatActivity {

      @Override
      protected void onCreate(@Nullable Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_result);

         ImageView ivNormalize = findViewById(R.id.iv_normalize);

         try {
               ivNormalize.setImageBitmap(MainActivity.mNormalizedImageData.toBitmap());
         } catch (CoreException e) {
               e.printStackTrace();
         }
      }
   }
   ```

### Build and Run the Project

1. Select the device that you want to run your app on from the target device drop-down menu in the toolbar.

2. Click the **Run app** button, then Android Studio installs your app on your connected device and starts it.

You can download the similar source code here:

- [Java](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/android/HelloWorld/AutoNormalize){:target="_blank"}.
- [Kotlin](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/android/HelloWorld/AutoNormalizeKt){:target="_blank"}.
