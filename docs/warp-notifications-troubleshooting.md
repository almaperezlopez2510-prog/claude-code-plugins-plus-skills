Warp requires two distinct notification settings to work. Mac system settings found in Mac > System Preferences > Notifications & Focus and Warp app settings found in Settings > Features > Session must both be enabled for Notifications to show.

If you have Notifications enabled in the system and Warp, but you still aren't receiving desktop notifications, try the following:

Make sure that you are navigated away from Warp when you expect to receive the notification.
Make sure the Do Not Disturb mode is turned off in Mac > System Preferences > Notifications > Notifications & Focus > Focus.
Go to Mac > System Preferences > Notifications & Focus > Notifications and select Warp in the list. Make sure either banner style or alert style notifications are selected, then quit and restart Warp.
To get the MacOS notification prompt to show again for Warp, run defaults delete dev.warp.Warp-Stable Notifications, then restart Warp and toggle on the Settings > Features > Receive desktop notifications from Warp.
Once all of the above is done, please Restart MacOS to apply the changes and that should help with restoring notifications in Warp.