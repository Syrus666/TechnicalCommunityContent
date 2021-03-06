# Demo 3.4: DevOps

This demo should take about 6 minutes.

## Objectives

Show how DevOps can be used to improve the development, build and test deployment of an application.

## Requirements\

Hyper-V enabled PC. Required for the Visual Studio UWP and Visual Studio Android emulators.

Internet connection is required in order to setup and run the demos.

You will need Visual Studio 2015 or Community edition with Update 3

To download Visual Studio 2015 Community edition, [https://www.visualstudio.com/vs/mobile-app-development/](https://www.visualstudio.com/vs/mobile-app-development/%20)

Visual Studio Android emulator: <https://www.visualstudio.com/vs/msft-android-emulator/>

If you encounter issues with connecting Visual Studio debugger with the Visual Studio I would recommend following the steps from this blog article: <http://dotnetbyexample.blogspot.ca/2016/02/fix-for-could-not-connect-to-debugger.html>

This demo uses Xamarin Test Cloud. Using test cloud is optional. If you want to use it go to this url: <https://testcloud.xamarin.com/register> . You will need a work email account.

## Setup

### Android emulator

Get the Android emulator running ahead of the demo. Use the link above to install the Visual Studio Android emulator if you don’t have it already.

1.  In Visual Studio, under the Tools menu options (1). Select the Visual Studio Emulator for Android option (2).

> <img src="./media/image1.png" width="239" height="371" />

1.  Select the Android device profile 5”KitKat (4.4) XXHDPI Phone (1). Click the Run green button (2). Click the Close button (3).

> <img src="./media/image2.png" width="355" height="334" />

### Setup of VSTS and Android Build

1.  Register for a free Visual Studio Online (VSTS) account at <https://www.visualstudio.com/vso/>.

2.  Click on the ‘Get started for free’ button (1).

> <img src="./media/image3.png" width="530" height="370" />

1.  Login into your VSTS account.

2.  At the home screen located the New project hyperlink button

> <img src="./media/image4.png" width="230" height="251" />

1.  Enter the Project name GPSImageTag (1). Click on the ‘Create project’ button to finish (2).

> <img src="./media/image5.png" width="246" height="293" />

1.  Wait until VSTS creates the project. Once it’s done, click on the ‘Navigate to project’ button (1).

> <img src="./media/image6.png" width="317" height="167" />

1.  Click on the ‘Add code’ button to continue (1).

> <img src="./media/image7.png" width="541" height="309" />

1.  For this step we need to setup the Git repo on the demo workstation. Click on the ‘Clone in Visual Studio’ button (1).

> <img src="./media/image8.png" width="555" height="309" />

1.  Allow the VSTS web operation to open Visual Studio by clicking on the ‘Yes’ button (1).

> <img src="./media/image9.png" width="536" height="151" />

1.  This will load up Visual Studio on the demo workstation. We need to setup the local location for the project Git repo. For this example I’ve used ‘C:\\Users\\DevUser\\Documents\\Session 3\\Demo 3.5\\src\\Start’ (1). Once you’ve satisfied with the repo location click the ‘Clone’ button (1).

> <img src="./media/image10.png" width="777" height="276" />

1.  Locate the Demo3.4.zip file in the Solutions folder with this content, extract it to a new folder under your Documents folder.

2.  We need to copy the completed 3.4 demo solution to the cloned repo folder. We need to copy the GPSImageTag folder found in the Demo3.4\\Complete folder. In this example I would copy the GPSImageTag into C:\\Users\\DevUser\\Documents\\Session 3\\Demo 3.5\\src\\Start

3.  Next we need to open the new copy of the solution in Visual Studio using File-&gt;Open-&gt;Project/Solution.

4.  Open the properties for the Xamarin.Forms GSPImageTag.DroidNative project. Select the Android Options (1). In the Packaging properties make sure that ‘Use Shared Runtime’ and ‘Use Fast Deployment’ are disabled (2).

> <img src="./media/image11.png" width="456" height="192" />

1.  We need to create a temporary Android certificate for the Xamarin.Forms Android head. In the Solution panel select the GPSImageTag.Droid project. Bring up the dialog menu and select the Archive option (1).

> <img src="./media/image12.png" width="297" height="194" />

1.  The Archive step will build Android apk file. Next we to need to click the ‘Distribute’ button.

> <img src="./media/image13.png" width="429" height="270" />

1.  Next, we to click on the ‘Ad Hoc’ button.

> <img src="./media/image14.png" width="486" height="278" />

1.  Next we need to create the temporary Android Keystore file. Click on the plus button to continue.

> <img src="./media/image15.png" width="467" height="267" />

1.  Next we need to enter the Alias, Password and Full Name as the minimal information for the Android KeyStore file (1). Next, click the ‘Create’ button (2). You need to remember this password for later setup steps.

> <img src="./media/image16.png" width="256" height="318" />

1.  Once the Android KeyStore file is created we need to add it to the Xamarin.Forms Android Project. Double click on the KeyStore line (1).

> <img src="./media/image17.png" width="538" height="307" />

1.  The KeyStore path can be found on the first line (1) – We need this for an upcoming step. Click on the Cancel button.

> <img src="./media/image18.png" width="270" height="336" />

1.  Select the GPSImageTag.Droid project (1). Bring up the popup menu and select Add (2). Then click Existing Item (3).

> <img src="./media/image19.png" width="343" height="403" />

1.  Use the path for the KeyStore from just a moment about - add to the GPSImageTag.Droid project.

> <img src="./media/image20.png" width="284" height="318" />

1.  In Visual Studio we need to open the Team Explorer panel (1). Then click on the ‘Changes’ button (2).

> <img src="./media/image21.png" width="286" height="332" />

1.  Before we can commit the project code we need to enter our Git User information. Enter both your name and email address (1). Finally click the ‘Save’ button (2).

> <img src="./media/image22.png" width="256" height="116" />

1.  Next, we need to enter a comment for the code commit (1). Then press the ‘Commit All’ button to continue.

> <img src="./media/image23.png" width="284" height="329" />

1.  After we have committed the code to the local Git repo we need to update the VSTS project repo. To do this we just need to click on the Sync url link (1).

> <img src="./media/image24.png" width="360" height="96" />

1.  Now we need to Push up our committed changes from the local repo to the VSTS project repo. We can do this by clicking the ‘Push’ url link.

> <img src="./media/image25.png" width="261" height="210" />

1.  To check to see if the GPSImageTag has been published to the VSTS project click on ‘Code’ (1). Next, verify that the code is present in the repo (2).

> <img src="./media/image26.png" width="513" height="336" />

1.  Now we are ready to setup the Build Definition for the GPSImageTag repo. First, click on the ‘Build & Release’ url (1). Then click on the ‘New definition’ button (2).

> <img src="./media/image27.png" width="376" height="268" />

1.  Next, select the Xamarin.Android build template (1). Click on the ‘Next’ button (2).

> <img src="./media/image28.png" width="285" height="316" />

1.  Next enable the option ‘Continuous Integration’ (1). Then click on the ‘Create’ button (2).

> <img src="./media/image29.png" width="332" height="370" />

1.  If you want to demonstrate Xamarin Test Cloud. We will need to enter in our Xamarin account credentials. Click on the Variables url option (1). Enter two new variables ‘XamarinPassword’ and ‘XamarinEmail’ (2). Fill in the appropriate password and email address (3). To hide the values, click on the lock icon next to the fields. Click on the ‘Save’ button (4).

> <img src="./media/image30.png" width="750" height="208" />

1.  The save dialog will appear. Enter the name ‘GPSImageTag Android Build’ and click ‘OK’ button (2).

> <img src="./media/image31.png" width="263" height="197" />

1.  Next, we need to update the Build Xamarin.Android Project build step. Select this step to continue (1).

> <img src="./media/image32.png" width="472" height="232" />

1.  In the settings for the Build Xamarin.Android Project step, we need to set the MSBuild Version to MSBuild 15.0 (preview) (1). Next we need to update the JDK version to JDK 8 (2).

> <img src="./media/image33.png" width="561" height="380" />

1.  We need to create another Variable for the next build step. Click on the Variables (1). Next enter the Variable ‘KeyStorePassword’ (2). Next enter the password you used during the KeyStore creation as the value and click on the lock icon next to the field (3). Last step is to click the Save (4).

> <img src="./media/image34.png" width="783" height="287" />

1.  On the Build Solution step for the test project (1). We need make sure to set the Project to point to the \*.csproj file for our test project (2). Make sure to enable this step for the initial setup Build run (3).

> <img src="./media/image35.png" width="651" height="380" />

1.  Do not do the Xamarin Test Cloud steps if you didn’t setup a Xamarin Test Cloud account.

2.  **(Xamarin Test Cloud step)** We need to go and log into the Xamarin Test Cloud <https://testcloud.xamarin.com>. Within the Account Settings click on the Teams & Apps (1). Next click on the show API key (2). We will need to copy the Team API Key for the Xamarin Test Cloud Build step (3).

> <img src="./media/image36.png" width="645" height="277" />

1.  **(Xamarin Test Cloud step)** Next we need to get the Devices setting for the Xamarin Test Cloud Build step. In Xamarin Test Cloud click on the New Test Run button (1).

> <img src="./media/image37.png" width="576" height="92" />

1.  **(Xamarin Test Cloud step)** Select the GPSImageTag.Droid Team project (1) and click on the Next button (2).

> <img src="./media/image38.png" width="590" height="360" />

1.  **(Xamarin Test Cloud step)** Click on the Availability option (1) this will show the devices currently available. Select Phone as the Form Factor (2). Select up to 5 devices (3). Finally click on the Select 7 devices button (4).

> <img src="./media/image39.png" width="675" height="389" />

1.  **(Xamarin Test Cloud step)** Click on the Next button (1).

> <img src="./media/image40.png" width="758" height="438" />

1.  **(Xamarin Test Cloud step)** The Devices setting can be found after the parameter –devices (1). This is the value we need for the Xamarin Test Cloud build step. We done need to run the tests so we can close the panel (2).

> <img src="./media/image41.png" width="657" height="379" />

1.  **(Xamarin Test Cloud step)** For the Xamarin Test Cloud step (1). We need to set a few settings here (2). We need to set the App File to the **(\$(build.binariesdirectory)/\$(BuildConfiguration)\\\*.apk**) \*.apk that will be built by the build steps. Team API Key is pulled from the Xamarin Test Cloud Account profile section. The User Email setting is the email address of the registered Xamarin Test Cloud user. Devices is copied from the Xamarin Test Cloud prompt from setting up a Test run in the previous step. The Test Assembly Directory needs to set as shown below **(\$(build.binariesdirectory)/\$(BuildConfiguration)/test-assembly**), to the build folder from the Build Solution step for the Test project. Finally, we need to enable this step for the initial setup Build run (3).

> <img src="./media/image42.png" width="855" height="616" />

1.  Select the Signing and aligning APK build step (1).

> <img src="./media/image43.png" width="525" height="193" />

1.  Enable the Sign the APK option (1). Enter the credentials used to define the KeyStore file creation (2). Note we are using the KeyStore variable.

> <img src="./media/image44.png" width="654" height="466" />

1.  Go to HockeyApp to register for a new account. <https://hockeyapp.net/>

2.  Click on the ‘Get Started For Free’ (1).

> <img src="./media/image45.png" width="690" height="382" />

1.  Click on the ‘New App’ button (1).

> <img src="./media/image46.png" width="334" height="250" />

1.  Click on the manually url (1)

> <img src="./media/image47.png" width="390" height="252" />

1.  Set the Platform to Android (1). Enter GPSImageTag for the Title (2). Enter GPsImageTag.Droid for Package Name (3). Click Save button (4).

> <img src="./media/image48.png" width="510" height="360" />

1.  We need to go back to the VSTS portal. Click on the VSTS MarketPlace icon (1)&gt;

> <img src="./media/image49.png" width="467" height="159" />

1.  Enter the search term ‘HockeyApp’ and press enter (1). In the results, click on the HockeyApp (2).

> <img src="./media/image50.png" width="522" height="317" />

1.  Click on the Install button (1).

> <img src="./media/image51.png" width="543" height="247" />

1.  Click on Confirm to continue (1).

> <img src="./media/image52.png" width="333" height="303" />

1.  Click on the Close button (1).

> <img src="./media/image53.png" width="359" height="244" />

1.  Click on Releases (1).

> <img src="./media/image54.png" width="362" height="100" />

1.  Click on the ‘New definition’ button (1).

> <img src="./media/image55.png" width="503" height="196" />

1.  Click on the Empty template (1). Click on the Next button (2).

> <img src="./media/image56.png" width="361" height="400" />

1.  Enable the option Continuous deployment (1). Click on the Create button (2).

> <img src="./media/image57.png" width="333" height="370" />

1.  Click on the Add tasks option (1).

> <img src="./media/image58.png" width="539" height="291" />

1.  Click on the Deploy group (1). Locate the HockeyApp task and click the Add button (2). Finally click the close button (3).

> <img src="./media/image59.png" width="331" height="337" />

1.  Click on the Add option (1).

> <img src="./media/image60.png" width="681" height="212" />

1.  Log into your HockeyApp account in a different browser tab. Under the profile menu option click on the Account Settings (1).

> <img src="./media/image61.png" width="216" height="227" />

1.  In Account Settings, click on the API Tokens (1). Copy the HockeyApp API Token (2).

> <img src="./media/image62.png" width="369" height="415" />

1.  Back in the VSTS portal, copy the API Token copied from HockeyApp (1). Click the OK button to continue (2)&gt;

> <img src="./media/image63.png" width="392" height="219" />

1.  Log back into HockeyApp, click on the GPSImageTag Android App definition (1).

> <img src="./media/image64.png" width="274" height="289" />

1.  Copy the App ID we will need to complete the HockeyApp publish task in the release definition.

> <img src="./media/image65.png" width="365" height="299" />

1.  Back in the release definition we need to complete the HockeyApp publish task. Set the HocekyApp Connection to HockeyApp (1). Paste in the HockeyApp AppID (2). Click on the ellipse button and set the path to the \*.apk file found in the drop folder, as shown below (3).

> <img src="./media/image66.png" width="759" height="452" />

1.  Next we need to use the same HockeyApp ID to register the Hockey SDK within our Android application. In the GSPImageTag.Droid project in the MainActivity.cs file (2). Set the HockeyAppId to the one from the HockeyApp portal (2).

> <img src="./media/image67.png" width="819" height="320" />

1.  If you did setup Xamarin Test Cloud account, run a build prior to the demo to get the test cloud results.

2.  In VSTS portal, select Build & Release (1), then click on the Queued tab. Next, click on the Queue build (3)

> <img src="./media/image68.png" width="556" height="372" />

1.  In the pop up dialog window, click on the OK button (1).

> <img src="./media/image69.png" width="496" height="380" />

1.  Disable Build Unit Test and the Xamarin Test Cloud steps in build definition. This means unchecking the enabled checkbox in these build steps and clicking save.

## Demo Steps

1.  Go to VSTS and show that the code is in a Git repository. Click on the Code menu option in VSTS (1).

> <img src="./media/image70.png" width="629" height="444" />

1.  Point out Work tab, under which you can do all kinds of agile project management work item tracking methodologies.

2.  Go to Build & Release

3.  On the GPSImageTag Android Build definition select the ellipse button (1). Next, click on the Queue new build option (2). Explain we are running a new build and will come back to it in the final demo.

> <img src="./media/image71.png" width="730" height="222" />

1.  It will display a monitoring page. This will continue on while the session continues. We'll come back to it in demo 3.6

> <img src="./media/image72.png" width="536" height="362" />

1.  Back to Build & Release

2.  Show start of Add New Build sequence and what initial out-of-box steps look like. Click on the New button (1).

> <img src="./media/image73.png" width="307" height="133" />

1.  Cancel out of that and select edit for the one we built by clicking on the ellipse button (1) and then click on Edit option (2).

> <img src="./media/image74.png" width="685" height="250" />

1.  This is to build for the Xamarin Forms Android head'

> <img src="./media/image75.png" width="476" height="386" />

1.  Show Repository tab to see where code is coming from for the build definition. Click on the Repository link (1). We can see that the Repository is mapped to the GPSImageTag master branch.

> <img src="./media/image76.png" width="377" height="171" />

1.  Back to Build tab and Explain steps.

2.  Click on the Variables link (1). Point out password protection. These are the variables we defined to be used for the Xamarin Test Cloud step (2).

> <img src="./media/image77.png" width="847" height="309" />

1.  Explain that for the NuGet restore step (1), we need to make sure to set the NuGet Version to 3.5 build (rc2) (2).

> <img src="./media/image78.png" width="908" height="366" />

1.  For the Build Xamarin.Android step we need to make sure to set the MSBuild to MSBuild 15 (preview) (2). Plus, the JDK needs to be set to JDK 8 (3).

> <img src="./media/image79.png" width="764" height="393" />

1.  Point out disabled Test Cloud. This is where the build process would publish the tests to Xamarin Test Cloud to be run.

2.  On the Signing and aligning step (1) we set it up to sign the \*.apk with the KeyStore certification (2). This is necessary for publishing to HockeyApp.

> <img src="./media/image80.png" width="918" height="352" />

1.  The next step is the Publish Artifact:drop (1). This step copies the built \*.apk file to the drop folder on the VSTS server (2)

> <img src="./media/image81.png" width="796" height="337" />

1.  Go into Triggers (1). Explain how Continuous Integration can be configured to build every time code is checked in (2).

> <img src="./media/image82.png" width="378" height="276" />

1.  Go to Releases (1). A Release is like a versioned publication of the software into which we can publish one or more builds (2).

> <img src="./media/image83.png" width="505" height="210" />

1.  Show how New Release is created without completing the whole thing. Click on the Plus button and select ‘Create release definition’ option (1).

> <img src="./media/image84.png" width="304" height="236" />

1.  Select the Empty template (1) and click on the ‘Next’ button (2).

> <img src="./media/image85.png" width="258" height="286" />

1.  In the next step click on the Cancel button (1).

> <img src="./media/image86.png" width="325" height="361" />

1.  We can have multiple environments for example QA. Dev, Staging, Production. We can add these by clicking on the Add environment button (1) to add in the required deployments.

> <img src="./media/image87.png" width="520" height="268" />

1.  On the Triggers tab (1). We can setup continuous deployment option. Here we have defined that after each Build run we want to run this Release (2).

> <img src="./media/image88.png" width="710" height="280" />

1.  Open existing Release definition. The one release step we have is that after a successful Build we want to deploy the \*.apk to HockeyApp (1).

> <img src="./media/image89.png" width="777" height="347" />

1.  Here we have the HockeyApp registration to allow for the Release to publish the Android \*.apk file to our HockeyApp portal

> <img src="./media/image90.png" width="564" height="332" />

1.  Hockey app allows us to publish apps to testers, track crashes in production apps, and monitor app usage'

2.  Go to the HockeyApp portal. We use the AppID in the Release HockeyApp step to identify the correct app (1). Here we have the list of Android app versions published (2). We can also see Crash and registered Events from the app (3).

> <img src="./media/image91.png" width="927" height="402" />

1.  Custom Events are events we register in our code to capture when a button or feature is used within our application.

2.  Under the Code tab, click Files and expand down to MainActivity.cs under GPSImageTag.Droid. We can see that we are using the HockeyApp Id (1). We next need to register the app with HockeyApp (2). This allows for the Crashes to be captured and sent to HockeyApp portal when we next run the application. We can also register custom events to capture the use of features within our application (3).

> <img src="./media/image92.png" width="823" height="595" />

1.  Click on Build/Releases tab then Releases and edit the release definition.

2.  Another feature we can enable on the HockeyApp step is to enable the option to Notify Users (1). When a new version of the app is published to HockeyApp. This steps uses the list of registered team members to the HockeyApp project and sends each one an email update.

> <img src="./media/image93.png" width="805" height="354" />

1.  We covered a lot of DevOps features. We will return back to see the results of the Build process in Demo 3.6.
