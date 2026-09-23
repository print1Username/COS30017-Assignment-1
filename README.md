# COS30017 Assignment 1: Lost and Found App

Welcome to the Lost and Found App. This is a pure UI (User Interface) project designed to demonstrate modern Android layout techniques. It includes screens for Login, Home, Search/Filter, Item Details, and User Profile.

The project features a responsive design, meaning it automatically adapts to different screen sizes (Mobile Phones and Tablets) using different layout resources.

No backend or complex logic is required. It is perfect for beginners to learn XML layouts, Material Design, and responsive UI.

## Prerequisites (Configuration)

Before you begin, ensure you have the following installed on your computer:
* Java Development Kit (JDK): Version 17 or higher (usually bundled with Android Studio).
* Android Studio: Latest stable version.
* IntelliJ IDEA: Ultimate or Community Edition (if you prefer using IntelliJ for Android development).
* Android SDK: API Level 24 (Android 7.0) or higher.

## Step 1: Get the Code (Git Clone)

You can download the source code using Git. Open your terminal or command prompt and run the following command:

```bash
git clone https://github.com/print1Username/COS30017-Assignment-1.git
```

Alternatively, if you do not have Git installed, you can download the project as a ZIP file from the repository page and extract it to a folder on your computer.

## Step 2: Folder Structure

Here is a quick guide to where everything is located in this project:

```text
app/src/main/
|
+-- java/com/example/lostandfound/    # Kotlin source code (MainActivity.kt)
|
+-- res/                              # All UI resources
    +-- drawable/                     # Images, custom shapes (e.g., bg.png, button shapes)
    +-- layout/                       # Mobile phone layouts (Portrait)
    |   +-- activity_main.xml
    |   +-- activity_login.xml
    |   +-- activity_details.xml
    |   +-- activity_profile.xml
    |   +-- item_lost_found.xml
    +-- layout-sw600dp/               # Tablet layouts (Screens wider than 600dp)
    |   +-- activity_main.xml
    |   +-- activity_login.xml
    |   +-- activity_details.xml
    |   +-- activity_profile.xml
    |   +-- item_lost_found_tablet.xml
    +-- values/                       # Colors and Text
        +-- colors.xml                # All theme colors (Pink, Red, Grey, etc.)
        +-- strings.xml               # All hardcoded text (Labels, Buttons, Hints)
```

## Step 3: How to Run the App (Deployment)

You can run this project using either Android Studio or IntelliJ IDEA. Follow the instructions for your chosen software.

### Method 1: Using Android Studio

1. Open the Project: Launch Android Studio. On the welcome screen, click Open (or go to File -> Open). Select the root folder of this project that you cloned in Step 1.
2. Gradle Sync: Wait for the bottom progress bar to finish. Android Studio will automatically download necessary Gradle dependencies. If it asks to update anything, click Update.
3. Set up an Emulator (AVD):
    - In the top-right toolbar, click the Device Manager icon (a small phone with an Android logo).
    - Click Create Device. Select a phone (e.g., Pixel 6) and click Next.
    - Download a system image (e.g., API 34) and click Finish.
4. Run: Select your newly created emulator in the top toolbar dropdown menu. Click the green Run (Play) button. The app will build and launch on the emulator.

### Method 2: Using IntelliJ IDEA

1. Install Android Plugin: Open IntelliJ IDEA. Go to Settings -> Plugins. Search for "Android" and install it (if not already installed). Restart the IDE.
2. Open the Project: Go to File -> Open and select the root folder of this project.
3. Configure Android SDK: If prompted, point IntelliJ to your Android SDK location (usually `C:\Users\YourName\AppData\Local\Android\Sdk` on Windows or `~/Library/Android/sdk` on Mac).
4. Gradle Sync: Wait for the Gradle sync to complete.
5. Run: Go to Run -> Edit Configurations. Click the plus (+) button, select Android App, and name it "app". Select module `app`. Click OK.
6. Emulator/Device: Select your device or emulator from the top toolbar. Click the green Run button. The app will build and launch.

## Step 4: Program Logic and UI Explanation

Since this is a pure UI project, there is no complex backend logic (no databases, no network calls, no actual login functionality).

* MainActivity.kt: The only Kotlin code simply sets the content view (`setContentView(R.layout.activity_main)`). Everything you see is rendered purely from XML.
* RecyclerViews without Adapters: You will notice `RecyclerView` tags in the main list pages. We did not create adapters or data models. Instead, we use `tools:itemCount="3"` and `tools:listitem="@layout/item_lost_found"`. This is a design-time trick that allows Android Studio's preview window to show multiple list items without needing actual code to populate them.
* Component Reusability: Instead of copy-pasting the search bar and navigation bars on every page, we extracted them into separate layout files (e.g., `component_search_bar.xml`, `component_bottom_nav.xml`). We use the `<include layout="@layout/..." />` tag to reuse them. This is a best practice for maintaining large apps.
* Responsive Layouts (Tablet Support): Android automatically picks the layout based on the screen width. If it is a phone, it uses `res/layout/`. If the screen width is greater than 600dp (like a tablet), it uses `res/layout-sw600dp/`. In the tablet layouts, you will see we changed from vertical `LinearLayout` to horizontal layouts with `layout_weight` to create a split-screen (Master-Detail) view.
* Material Design: We used `MaterialCardView` for rounded corners and borders, and `FloatingActionButton` for the add button, adhering to Google's Material Design guidelines.

## Customization Tips for Beginners

* To change the color of the buttons: Open `res/values/colors.xml` and change the hex values.
* To change the text: Open `res/values/strings.xml`. Never hardcode text directly in the XML files.
* To adjust the layout on a tablet: Edit files inside `res/layout-sw600dp/`. You can preview how it looks by opening any XML file, clicking "Design" mode, and selecting "Pixel Tablet" in the preview device dropdown.