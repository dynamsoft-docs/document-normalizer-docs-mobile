---
layout: default-layout
title: Detect and Normalize Document - Android User Guide
description: This page introduce how to detect and normalize document with Dynamsoft Capture Vision Android SDK.
keywords: user guide, android, document scanner
needAutoGenerateSidebar: true
needGenerateH4Content: true
noTitleIndex: true
permalink: /programming/android/user-guide.html
---

# Android User Guide for Document Scanner Integration

In this guide, you will learn step by step on how to build a document scanner application with Dynamsoft Capture Vision Android SDK.

- [Android User Guide for Document Scanner Integration](#android-user-guide-for-document-scanner-integration)
	- [Requirements](#requirements)
	- [Add the SDK](#add-the-sdk)
	- [Build Your First Application](#build-your-first-application)
		- [Create a New Project](#create-a-new-project)
		- [Include the Library](#include-the-library)
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

## Add the SDK

1. Open the file `[App Project Root Path]\app\build.gradle` and add the Maven repository:

    ```groovy
    allprojects {
        repositories {
            maven {
                url "https://download2.dynamsoft.com/maven/aar"
            }
        }
    }
    ```

2. Add the references in the dependencies:

    ```groovy
    dependencies {
        implementation 'com.dynamsoft:dynamsoftcapturevisionbundle:2.6.1001'
    }
    ```

    > Read more about the modules of [dynamsoftcapturevisionbundle]({{site.dcv_android_api}}index.html)

## Build Your First Application

In this section, let's see how to create a HelloWorld app for detecting and normalizing documents from camera video input.

>Note:
>
> - Android Studio 2022.2.1 is used here in this guide.
> - You can get the similar source code of the HelloWorld app from the following link
>   - [Java](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/android/DocumentScanner/AutoNormalize){:target="_blank"}.
>   - [Kotlin](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/android/DocumentScanner/AutoNormalizeKt){:target="_blank"}.

### Create a New Project

1. Open Android Studio, select **File > New > New Project**.

2. Choose the correct template for your project. In this sample, we use **Empty Activity**.

3. When prompted, choose your app name 'HelloWorld' and set the **Save** location, **Language**, and **Minimum SDK** (we use 21 here).
    > Note:
    >
    > - With **minSdkVersion** set to 21, your app is compatible with more than 94.1% of devices on the Google Play Store (last update: March 2021).

### Include the Library

Add the SDK to your new project. Please read [Add the SDK](#add-the-sdk) section for more details.

### Initialize License

1. Import the `LicenseManager` class and initialize the license in the file `MyApplication.java`.

   ```java
   import com.dynamsoft.license.LicenseManager;

   public class MyApplication extends Application {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", this, (isSuccess, error) -> {
            if (!isSuccess) {
                Log.e("License", "InitLicense Error: " + error);
            }
        });
   }
   ```

   >Note:  
   >  
   >- The license string here grants a time-limited free trial which requires network connection to work.
   >- You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=ddn&utm_source=guide&package=android){:target="_blank"} link

### MainActivity for Realtime Document Normalization

#### Initialize Camera Module

1. In the Project window, open **app > res > layout > `activity_main.xml`** and create a DCE camera view section under the root node.

    ```xml
    <com.dynamsoft.dce.CameraView
        android:id="@+id/camera_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent">
    </com.dynamsoft.dce.CameraView>
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
   import com.dynamsoft.cvr.CaptureVisionRouterException;

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
                  if (result.getItems().length > 0) {
                     NormalizedImageResultItem normalizedImageResultItem = result.getItems()[0];
                     if (normalizedImageResultItem.getCrossVerificationStatus() == EnumCrossVerificationStatus.CVS_PASSED || mJumpToOtherActivity)
                     {
                        mJumpToOtherActivity = false;
                        mNormalizedImageData = result.getItems()[0].getImageData();

                        Intent intent = new Intent(MainActivity.this, ResultActivity.class);
                        startActivity(intent);
                     }
               }
            }
         });
      }
   }
   ```

2. Add a result cross filter to validate the normalized image result across multiple frames.

   ```java
   ...
   import com.dynamsoft.core.basic_structures.EnumCapturedResultItemType;
   import com.dynamsoft.utility.MultiFrameResultCrossFilter;

   public class MainActivity extends AppCompatActivity {
      
      ...

      @Override
      protected void onCreate(Bundle savedInstanceState) { 
         
         ...
         MultiFrameResultCrossFilter filter = new MultiFrameResultCrossFilter();
         filter.enableResultCrossVerification(EnumCapturedResultItemType.CRIT_NORMALIZED_IMAGE, true);
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
            mRouter.startCapturing(EnumPresetTemplate.PT_DETECT_AND_NORMALIZE_DOCUMENT, new CompletionListener() {
               @Override
               public void onSuccess() {
                    
               }
               @Override
               public void onFailure(int i, String s) {
                  Log.e(TAG, "onFailure: "+s);
               }
            });
         } catch (CameraEnhancerException e) {
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

2. In the AndroidManifest.xml file, declare the `ResultActivity`.

   ```xml

   ...

        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".ResultActivity"
            android:label="Result Activity">
        </activity>
   
   ...

   ```

3. In the Project window, open **app > res > layout > `activity_result.xml`**, create a image view under the root node to display the result image.

   ```xml
   <ImageView
      android:id="@+id/iv_normalize"
      android:layout_width="match_parent"
      android:layout_height="match_parent"/>
   ```

4. Display the normalized image.

   ```java
   import android.os.Bundle;
   import android.widget.ImageView;

   import androidx.annotation.Nullable;
   import androidx.appcompat.app.AppCompatActivity;
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

- [Java](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/android/DocumentScanner/AutoNormalize){:target="_blank"}.
- [Kotlin](https://github.com/Dynamsoft/capture-vision-mobile-samples/tree/main/android/DocumentScanner/AutoNormalizeKt){:target="_blank"}.
