# Heads Up

A personal news briefing for Windows: top news, local news and weather, politics, social media, Claude and AI news, Counter-Strike 2 patch notes and esports, and topics you follow, in one window.

## Download

**[Download the latest Heads Up](https://github.com/lmgoffical/heads-up/releases/latest)** (`HeadsUp.zip`, Windows).

Windows may say "Windows protected your PC" because the app isn't signed. Click **More info → Run anyway**.

## Use it

1. Install **[Node.js](https://nodejs.org/en/download)** (the LTS version) if you don't have it. It's free.
2. Unzip `HeadsUp.zip` and double-click **Install Heads Up**.
3. Heads Up opens in its own window and puts a shortcut on your Desktop and in the Start menu. Make an account (or continue as a guest) and pick the news you want.

It updates itself from this repository, so you never need to download it again.

Your account (username, scrambled password, and your news settings) is stored only on your computer, in `%APPDATA%\Heads Up`.

## How it works

The installed app lives in `Documents\Heads Up`. It's a single page (`app/app.html`) served by a small Node.js helper (`app/server.js`) that fetches the news feeds, keeps accounts for the people who use it on that computer, and updates the app from this repository.

## Announcements

Every copy of Heads Up reads `announcements.json` here and shows new announcements as a banner and in the notification bell. The owner sends them from the megaphone button in the app (it only appears on the computer that has this repository at `~/heads-up`), or by editing that file on GitHub.

## How updates work

The helper checks `app/version.json` here when Heads Up opens and every 30 minutes while it's open. If its `version` is higher than the installed one, it downloads every file in `files`, swaps them in, and the app shows a reload banner.

## Releasing a new version

1. Change the files in `app/`.
2. Raise the version by one in **both** `app/version.json` (`"version"`) and `app/app.html` (`const APP_VERSION`), and describe the change in `"notes"`.
3. Commit and push to `main`. Installed copies pick it up the next time they open (GitHub can take a few minutes to serve the new files).

## Building the download

`HeadsUp.zip` is just `Install Heads Up.bat`, `install.ps1` and the `app` folder zipped together. Nothing needs compiling.
