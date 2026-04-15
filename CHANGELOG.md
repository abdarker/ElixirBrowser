# History

---

## ・Upcoming Features
<br>

-   Major refactoring of all code related to the bottom toolbar (This is going to take a lot of time & be tough)
    -   Until this is complete, I cannot accept any requests related to the bottom toolbar. Please forgive me. 💃

---

<br>

## ・Ideas Under Consideration
<br>

-   Direct installation support for .crx extension files. (Looks very difficult, so maybe if I feel like it)
-   Allow custom JavaScript execution as a gesture action.
-   Disable the automatic keyboard language switching based on the browser's language setting. (This is becoming a low-priority task)

---

<br>

## ・Implemented Features

## [1.0.20]

- Added a toggle to disable pinch-to-zoom in the main menu.
    - Also switchable via gestures.
    - When I’m lying in bed using my phone, my palm would often brush against the screen and accidentally zoom in.
    - It was incredibly frustrating, but this solves the problem.
    - I really wonder why Chromium doesn’t offer a feature to turn zoom off.
    - I thought I could probably solve this with a user script, but since it will allow for even more detailed customization in the future, I think it was worth the effort.

<br>

## [1.0.19]

- **Added support for external download managers.**
    - A toggle has been added under Settings > Downloads.
    - Based on testing with 1DM and ADM, it works properly. There should be no issues.
    - If you select “Download” from the menu that appears after a long tap, Elixir will handle the download as usual.
- Fixed an issue where a blank space appeared below the toolbar on some devices.

<br>

## [1.0.18]

- Fixed an issue where selecting “Web Search” from other apps didn't work properly.
    - This was a pretty big problem, but I hadn't noticed it at all until recently. 🐧
- Changed the extension management page to always open in a new tab.
- Fixed an issue where the floating keyboard became unresponsive when gesture features were enabled. (Still won't work on Android 11 and earlier due to API incompatibility)

<br>

## [1.0.17]

- **Fixed an issue where certain non-popup extensions caused the browser to crash immediately after execution.**
    - This allows several extensions that previously caused crashes to now function correctly.
    - However, it still does not guarantee the operation of all extensions.

<br>

- Fixed an issue where the extension list would disappear unexpectedly while the page was loading.
    - There are still times when it becomes unresponsive, so you may need to reopen the list.
    - At least it no longer causes your eyes to flicker, so that's a win. 🤩
- Added a toggle to always display the Quick Actions at the top of the main menu, even on tablet-sized device screens.

<br>

## [1.0.16]

- Implemented data deletion functionality. Added a “Destruct Data” option to the main menu.
    - Also added “Destruction Settings” to the settings screen. This allows specifying detailed behavior. You can also configure it to run automatically at startup without pressing a button.
    - Internally, it just calls the existing “Delete browsing data” function, so it should be very safe. 🤔
    - However, enabling auto-execution at startup required careful timing to avoid crashes, so the code ended up complex after all. Looks like it'll be tough to maintain. 😭
    - The button is hidden by default, so you need to enable it in Settings > Appearance.

<br>

## [1.0.15]

- Fixed an issue where the top 5 buttons in the main menu weren't displayed in Incognito Tab mode.

- Finally fixed the icon position in the URL bar being shifted downward.
    - This had been bothering me for a while, but I couldn't figure out how to fix it until now. The cause was that while the tablet toolbar was always being called, the dimensions and other specifications used were still set for smartphones.

- Added a toggle to accessibility settings to open new tabs via long-pressing the tab switcher button.
    - Implemented this due to high demand, but it was surprisingly tricky. Tab-related operations are prone to crashes, so I was hesitant to touch them.

<br>

- Modified history page to display the time the page was opened.
    - Sometimes when I wake up, I wonder how many hours I slept. I never remember what time I went to bed. 🤔
    - In those moments, I'd always check my browser history to confirm my sleep duration. But on Android, it just wouldn't show up. Terrible.
    - Internally, the page open time was already saved in the history data, so implementation was straightforward. But seriously, if it exists, couldn't they have just shown it from the start? 👿

<br>

## [1.0.14]

-   Revised descriptions for some options.
-   Fixed an issue where https or http was automatically added when registering Speed Dial shortcuts.
-   Added support for EdgeToEdge mode. (gesture navigation bar becomes transparent)
    -   However, it is forcibly disabled in bottom toolbar mode.
    -   May not work on some Android versions. The exact behavior in such cases is currently unknown.
-   Fixed an issue where the status bar would forcibly turn black when switching to landscape mode while gesture feature was enabled.
    -   This was a major headache. It took me three days to even realize the gesture feature was the cause. 😡

<br>

## [1.0.13]

-   **Fixed an issue where the tab reload prevention feature was not working since v1.0.11.**
-   Fixed an issue where the progress bar animation was simplified.
-   **Fixed an issue where the progress bar background occasionally remained visible.**

<br>

## [1.0.12]

- Fixed an issue where PWA functionality had failed to work.
    - The cause was undoubtedly disabling fieldtrial_testing_config. Successfully restored functionality by manually enabling several flags within it.
    - Since I never use this feature myself, I hadn't noticed at all. Thanks to the reporter.
 
<br>

## [1.0.11]

- Added option to keep the toolbar visible while scrolling.
- Added option to automatically focus the URL bar when opening a new tab.
- Added an option to always open links in Elixir instead of external apps.
    - GooglePlay is the only exception; it will still redirect to the app after opening.

- Disabled fieldtrial_testing_config.
    - This “may” resolve several issues occurring on some devices. However, it may also introduce multiple other issues.

<br>

## [1.0.10]

-   Improved extension pop-ups
    -   Previously, extensions like AdGuard weren't displayed, but they now function correctly.
    -   This also resolves issues such as AdGuard crashes and slow updates after restarting (displaying the pop-up ensures it starts working reliably).
    - However, this fix uses a less-than-ideal approach: it forces the popup to be at least a certain minimum size. This means extensions like DarkReader, which previously worked fine, now have larger popups.
    - Consequently, the popup UI might break on some devices or with certain extensions. Still, it's better than the previous state where popups didn't appear at all.

-   Implemented Speed Dial reordering functionality
    -   It probably doesn't behave as expected, but at least reordering is now possible.
    -   Please forgive me—achieving a modern, smooth sliding animation is technically very difficult. 🙇‍♀️

<br>

## [1.0.9]

-   Added a toggle to hide extension icons that are forced to appear in the toolbar on tablets.
-   Fixed severe toolbar corruption when using incognito tabs.
-   Changed the default behavior from incognito windows to incognito tabs.
-   Modified to display a “Private Tab ←→ Normal Tab” toggle button on the tab bar when one or more incognito tabs are open.

<br>

## [1.0.8]

-   **Added a toggle to prevent background tabs from reloading. (Default: OFF)**
    -   This feature is marked as **Experimental** because its long-term stability and the exact memory impact of keeping tab contents resident are still being evaluated.
    -   It should be perfectly fine on modern smartphones, so I'm personally using it with the feature turned on for now.

<br>

-   **Implemented Bookmark Import/Export functionality (Experimental)**
    -   Dedicated buttons have been added to the top-right menu of the bookmarks page.

<br>

-   Restored the Home Page feature.
-   Added toggles in Settings > Appearance to customize visible toolbar buttons.
-   Relaxed the row limit for the Speed Dial in portrait mode.

<br>

## [1.0.7]

-   Fixed an issue where the main menu contents were cut off.
-   Added toggles to customize main menu items in Settings > Appearance.
-   Added a toggle for "Pull-to-Refresh" in Accessibility settings.
-   Added a toggle in Accessibility settings to reverse the vertical swipe gesture on the toolbar that displays the tab switcher.

<br>

## [1.0.6]

-   **Fixed an issue where multi-step gestures were blocked if their prefix paths were set to "None".**

<br>

## [1.0.5]

- **Complete overhaul of gesture recognition logic.**
    - Switched from my totally custom coordinate/angle monitoring (which checked every single frame) to a **Normalized Shape-Matching system** (based on the $1 Unistroke Recognizer combined with my own additional logic).
    - Turns out relying on famous, proven logic is way better. Don't reinvent the wheel. (Self-reflection).

<br>

- Added a "Gesture Strictness" setting. Default is 85%. Lower values mean more lenient detection, making gestures easier to trigger.
- Fixed the behavior when closing tabs via gestures.
- Fixed the behavior when restoring tabs via gestures.

<br>

- **Removed "Notifications" from the Settings UI.** I hated accidentally tapping it and being warped away—it was such a waste of time.

<br>

- **Modified Chromium's default behavior so that video and music keep playing even when switching tabs or minimizing the app.**
    - Note: Sites like YouTube, which use JavaScript to actively monitor page visibility, will still pause.
    - Bypassing this would require either keeping JS running for all background tabs or "sniping" specific domains—both of which carry performance hits, memory load, and legal risks, so I have no plans to change this, and it will likely remain in its current state.

## [1.0.4]

-   **Resolved the scroll jitter issue when gestures are enabled.** It turns out that **"unavoidable structural limitation"** wasn't as permanent as I thought; a quick rethink was all it took.
    -   That said, please note that this remains an experimental feature, and stable operation is not yet guaranteed.✌🤪
-   Added a toggle in Accessibility settings to change the behavior when closing the last remaining tab (Minimize app or Open new tab).


<br>

## [1.0.3]

-   **Gesture functionality implementation complete.** However, this remains an experimental feature with no guarantee of functionality.
    -   Known issue: When gestures are enabled, slight jitter occurs during scrolling. This is an unavoidable structural limitation, and resolving it would likely require significant time.
-   Added Settings > Gesture Settings. Allows action assignment and sensitivity adjustment.
-   Set Back/Forward Transition to disabled by default.
-   Changed behavior when closing the last tab from “Return to Home” to “Open New Tab” (A toggle option for either behavior will be added in a future update).

<br>

## [1.0.2]

-   Locked background tab behavior to "Freeze" only (instead of "Discard"). This prevents page reloads when switching tabs, even after extended inactivity.
-   Removed some unnecessary code.

<br>

## [1.0.1]

-   **Updated Chromium base to version 144.0.7559.76.**
-   Added custom wallpaper support for the New Tab Page (accessible via the Speed Dial menu).
-   Added an "Open in Background" option to the Speed Dial menu.
-   Removed "Downloads" from the Settings menu.

<br>

## [1.0.0]

-   **Implementation of Extensions**
-   Implemented extension settings popups (some seem to appear in weird positions and can't be operated, but the ones I use were fine, so I'll deal with this later).
    -   I wanted to make MV2 extensions (like uBlock Origin) work too, but I couldn't get it done even after spending a whole day, so I gave up.
<br><br/>
-   **Changed back gesture behavior: When there is no more history to go back to (returned to the start of the tab), the tab now closes and moves to the adjacent tab instead of returning Home. (Every browser should have this spec by default).**
    -   Note: If the closed tab was the last remaining one, it now immediately opens a new tab and *then* returns to Home. (By default, closing the last tab would show the tab switcher).
    -   Rarely, it returns Home even when other tabs are open. Cause unknown. It doesn't crash, but it's annoying. It fixes itself if you manually switch to another tab once. Occurs more often than expected, needs investigation.
        -    Mystery solved: When a back gesture was performed on an "abnormal" tab (incomplete initialization, already closing, etc.), the default logic judged it should return Home.
        -    By forcing the tab to close no matter how abnormal it is, it now works reliably.
        -    It feels like very "bad manners" in terms of coding, but it doesn't seem to crash, so I'll see how it goes.
<br><br/>
-   **Forced Tablet UI (Tab Bar) implementation** (Toggleable in Accessibility settings. Default is ON).
-   Force the tab bar to always show when Tablet UI is ON. (By default, it disappears quite often for some reason).
<br><br/>  
-   Left-aligned the tab favicon starting position.
-   Made the tab title font size slightly smaller than default. (Note to self: Adjustable in TitleBitmapFactory. dimens.xml is either ignored or overwritten).
<br><br/>
-   **Implemented Bottom Toolbar mode. Toggleable in Accessibility settings.**
-   In Bottom Toolbar mode, moved the progress bar to the hairline position.
-   Strictly controlled Hairline visibility to ensure no gaps appear between the bottom toolbar and the bottom of the screen during tab transitions.
-   When Bottom Toolbar mode is active and the Tab Bar is ON, the tab bar moves to the bottom. (This was so incredibly tedious, it almost drove me crazy).
<br><br/>
-   Removed unnecessary toolbar icons. (visibility=gone often didn't work, so I'm removing them by setting their size to 0).
-   Only the Tab Switcher button is displayed when ForceTabletUI is off. (I thought it was essential, but since you can swipe up on the URL bar to show the tab switcher, maybe I don't need it).
<br><br/>
-   Adjusted the color tones of the status bar, toolbar, URL bar, and tab bar.
<br><br/>
-   Removed all elements from the New Tab Page and implemented a Speed Dial feature.
-   Favicon retrieval for shortcut icons was unstable with Google, so I changed it to also use DuckDuckGo.
-   Shortcut icon favicons can now be manually changed by the user via URL. (Since sometimes incredibly low-res ones appear).
-   Configured the number of shortcut icons per row to change dynamically based on screen size. (Took 2 days to implement. I never want to touch this again).
-   Resolved the issue where the New Tab Page would scroll on its own. (Unbelievably annoying to fix).
-   Removed the extremely irritating "Hints" feature on the New Tab Page.
<br><br/>
-   Disabled Google Sign-in (since it didn't seem to work anyway).
-   Forced Autofill to always rely on the Android system settings.
-   Removed Autofill-related items from the settings menu.
<br><br/>
-   Modified the browser to "lie" to itself, claiming it is *not* Google even if the search engine is Google. (This hides unnecessary icons and features. This is only internal and does not affect the website side).

-   **Added Translate button to the menu.** (Why isn't this there by default?)

-   When searching from the URL bar, the search history felt weirdly stuck too close to the toolbar, so I lowered it.

-   Supported tab reordering in the tab bar. Can be dragged with a long-press. Originally this was for split-screen logic, but since I probably won't use that, I prioritized reordering. Original split-screen is still possible via OS features if you open it in a separate window.

-   Removed "Customize New Tab" from the menu.

-   Removed the help (question mark) button in the top right of various settings screens. (Just points to Google Help, so not needed).
-   Removed the 3-dot menu in the top right of various settings screens. (Just points to Google Help, so not needed).
<br><br/>
-   Settings > Google Services > Removed "Show Google Sign-in".

-   Settings > Privacy and Security > Defaulted "Always use secure connections" to OFF. (When ON, HTTP sites just show a blank page. At least give me a warning!)

-   Settings > Removed "Safety Check" from the UI.

-   Settings > Forced Homepage to OFF and removed it from the UI.

-   Settings > Appearance > Forced Toolbar Shortcut to OFF and removed it from the UI.

-   Settings > Privacy and Security > Removed "Privacy Guide" from the UI.

-   Settings > Privacy and Security > Removed "Ad Privacy" from the UI (everything inside is OFF by default).

-   Settings > Appearance > Removed "Bookmark Bar" from the UI. (The UI breaks in Bottom Toolbar mode. Might reimplement if I feel like it).

-   Settings > Removed "DeveloperOptions" from the UI.

-   Settings > Privacy and Security > Fixed a bug where the description in "Send a Do Not Track request" was cut off by default.

-   Removed the first-run screen. Now starts directly on the New Tab Page.

-   Fixed the misalignment of the History search input. (Forced mobile UI here).

-   Removed the Custom Tabs feature. (Automatically redirects to a regular tab).

-   Fixed the wasteful process of fetching the favicon over the net every single time.

-   Initial setting to always go to the desktop site when entering the Chrome Web Store (changeable).

-   When in Tablet UI, removed the pencil icon in the bottom right of the New Tab Page. (This was the hardest of all modifications. I couldn't find its true identity in the end, so I'm dynamically searching and deleting it every time).

-   When in Tablet UI, removed the account icon from the toolbar.

-   Changed the toolbar back button to sync with the visibility of the forward button.

-   When focusing the URL bar, the content is no longer cleared (starts in Select All state). Toggleable in Accessibility settings.
<br><br/>
-   Translation work complete.
-   Replaced Chrome → Elixir and Google Chrome → Elixir Browser in all languages.
-   Improved some Japanese text that was overflowing the drawing area by default. Is it not terrible that this is left unaddressed in the official version?
    -   Editing the body of the original .grd file breaks the translation links.
    -   Because of this, I couldn't replace Chrome with Elixir in the original files only. When English users other than en-GB use it, it automatically falls back to the original grd, so Chrome is displayed in en-US or en-CA environments, for example.
    -   I didn't know how to fix this, so for now, I copied en-GB as en-US and shoved it in, and for some reason en-CA and others started loading en-US (formerly GB). I don't really get why, but it works!
    -   So, the wording will be British for all English-speaking users. "Centre," "Colour," etc. However, this only affects a very small part like the settings screen and doesn't affect websites, so it shouldn't be a problem.
<br><br/>
-   Modified and published my custom UserScript for gestures (Bonus).

-   Fixed the gap that appeared when Bottom Toolbar mode and Tab Bar were both ON. (I cheated by placing a plate of about 100dp downwards to hide it).
-   There seems to be a lag in the bottom tab bar's tracking. No matter how hard I tried, I couldn't figure out how to fix it, so I decided to ignore it.
<br><br/>
-   Fixed the progress bar position being weird when in Landscape and Bottom Toolbar mode is ON. (I didn't notice it sooner because it was fine in Portrait).

-   Removed the incredibly annoying restore button and toast when closing a tab.

-   Removed the incredibly annoying toast when opening a tab.

-   Fixed a huge bug where the Tab Bar's touch detection remained active even after the tab bar was hidden by scrolling when Bottom Toolbar and Tab Bar were both ON. (Surprising how you don't notice these things).

-   Fixed a bug where the toolbar wouldn't hide in fullscreen mode when Bottom Toolbar was ON. (I didn't know where the hiding process was, so I implemented it myself).

-   Fixed a bug where the Bottom Toolbar would ignore the bottom area for gesture navigation and go to the absolute bottom. (Almost got stuck there, but managed to deal with it).

-   Fixed the UI corruption on the URL bar search screen when Bottom Toolbar is ON and the gesture navigation bar is shown.

-   Removed the annoying "Suggested Notifications."

-   Icon production complete. I thought it was a masterpiece, but a collaborator called it creepy, so I might change it.

-   Added functionality to export and save the Speed Dial in JSON format. Naturally, implemented the import function too.

-   Disabled the "Return to Chrome" feature that forced a new tab after 4 hours of inactivity.

-   Resolved an intermittent issue where pressing Enter in the URL bar would fail to initiate navigation.

-   Added an option to toggle Back/Forward transition animations in Accessibility settings (Default: Enabled).

-   Disabled ThrottleMainFrameTo60Hz by default.  

-   Fixed an upstream Chromium bug involving iframes where scroll predictor conflicts caused rendering issues (How is such a massive bug still unfixed?).

-   Fixed an upstream Chromium bug where inertial scrolling stops abruptly when zooming in on pages with horizontal content (How is such a massive bug still...)

-   Implemented automatic update notifications (configurable in Accessibility settings; enabled by default).

-   Added a "Check for updates" button to the main menu.

---

