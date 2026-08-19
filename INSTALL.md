# Installing Zirchron

This is the detailed version of the installation instructions, including what
to do when something does not go as expected. Jump to your system:

- [**Windows**](#windows) — short version: *download the installer, click
  through the SmartScreen warning, and follow the wizard*.
- [**macOS**](#macos) — short version: *download the `.dmg`, drag Zirchron to
  Applications, and the first time you open it approve it in System Settings →
  Privacy & Security*.

---

# Windows

## 1. Check that your PC is compatible

| Requirement | Value |
|---|---|
| Windows | 10 or 11, **64-bit** |
| Processor | any 64-bit Intel or AMD |
| Disk space | about 350 MB |

To check: **Start → Settings → System → About**. Under *Device
specifications*, the line **System type** must say *64-bit operating system*.
Zirchron does not run on 32-bit Windows, nor on Windows 8.1 or earlier.

There is a single Windows download — unlike macOS, you do not have to pick a
processor.

---

## 2. Download

Go to the [Releases](../../releases) page and download
**`Zirchron-1.0-windows-setup.exe`** (about 81 MB). It will land in your
**Downloads** folder.

---

## 3. Install

1. **Double-click the downloaded installer.**

2. **Windows will block it.** A blue full-screen panel appears saying
   *"Windows protected your PC"*, with only a **Don't run** button visible.
   Click **More info** — the text expands and a **Run anyway** button appears.
   Click it. (Section 4 explains why this happens; it is expected.)

3. **Choose the install mode.** The installer asks whether to install *for all
   users* (requires an administrator password) or *for me only* (no password
   needed). Either works — pick *for me only* if you are not an administrator
   of the computer, which is the common case on shared laboratory machines.

4. **Follow the wizard:** pick a language (English or Spanish), accept the
   licence, and confirm the destination folder. You can leave every default.

5. On the last page you can tick **Launch Zirchron**. Afterwards you will find
   it in the **Start menu**, and on the desktop if you left the shortcut
   option ticked.

You can delete the installer from Downloads once it finishes.

---

## 4. First launch — the SmartScreen warning

Windows shows *"Windows protected your PC"* for any program that is not signed
with a **code-signing certificate** — a paid commercial service, renewed
yearly. Zirchron is distributed directly by its author, unsigned.

**This is not a detection of anything harmful.** SmartScreen is not saying the
file is dangerous; it is saying it does not recognise the publisher, which is
true of every new unsigned program. The wording is deliberately alarming
because it is also what you would see for genuinely unknown software.

To proceed: **More info** → **Run anyway**. You only need to do this once, for
the installer — the installed application starts normally from then on.

**If your antivirus quarantines the file** instead, that is a related
phenomenon: some scanners flag anything bundled with PyInstaller (the tool that
packages Python applications) because malware authors also use it. Restore the
file from quarantine and add an exception for the Zirchron folder if your
scanner keeps intercepting it.

---

## 5. Opening project files

Zirchron saves your work as `.zirchron` files. The installer registers the file
type, so **double-clicking a `.zirchron` file opens it in Zirchron
immediately** — no need to open the application first.

If a `.zirchron` file does not open with Zirchron, right-click it → **Open
with** → **Choose another app** → select Zirchron and tick *Always use this
app*.

---

## Troubleshooting (Windows)

**I only see "Don't run" — there is no "Run anyway" button.**
The button is hidden until you click **More info** on the left side of the
SmartScreen panel. Click that first and the panel expands.

**"This app can't run on your PC."**
Your Windows is 32-bit. Zirchron is 64-bit only (the scientific libraries it
uses are not published for 32-bit Windows). Check under Settings → System →
About → *System type*.

**The installer finishes but nothing opens.**
Look for Zirchron in the Start menu and open it from there. If it still does
not appear, reinstall and make sure you did not change the destination folder
to a location you lack permission to write to.

**The first launch takes several seconds.**
Normal. On the very first run the application builds an internal font cache.
Later launches are faster.

**Antivirus removed the program after installing.**
Add an exception for the installation folder (by default
`C:\Users\<you>\AppData\Local\Programs\Zirchron`, or
`C:\Program Files\Zirchron` if you installed for all users) and reinstall.

---

## Uninstalling (Windows)

**Settings → Apps → Installed apps → Zirchron → Uninstall.** That removes the
application and the `.zirchron` file association. Your `.zirchron` project
files are ordinary documents and are not affected — delete them yourself if you
no longer need them.

---

# macOS

## 1. Check that your Mac is compatible

| Requirement | Value |
|---|---|
| macOS | 13 (Ventura) or later |
| Processor | Apple Silicon (M1–M5) **or** Intel — one download for each |
| Disk space | about 500 MB |

To check both at once: click the **** menu in the top-left corner of the
screen → **About This Mac**.

- The **macOS** line must show **13 or higher**. Zirchron does not run on
  macOS 12 (Monterey) or earlier.
- The **Chip** / **Processor** line tells you which file to download:

| That line says | Your download |
|---|---|
| **Chip:** Apple M1, M2, M3, M4 or M5 | `Zirchron-1.0.1-arm64.dmg` |
| **Processor:** Intel Core i5 / i7 / i9, or Xeon | `Zirchron-1.0.1-intel.dmg` |

Each file holds the same application, compiled for that processor. You do not
need Rosetta, and picking the wrong one cannot damage anything — macOS just
refuses to open it, and you download the other.

---

## 2. Download

Go to the [Releases](../../releases) page of this repository and download the
file that matches your processor (step 1):

- **Apple Silicon** → `Zirchron-1.0.1-arm64.dmg` (about 97 MB)
- **Intel** → `Zirchron-1.0.1-intel.dmg` (about 107 MB)

It will land in your **Downloads** folder.

---

## 3. Install

A `.dmg` file is a *disk image*: opening it mounts a temporary virtual disk,
much like plugging in a USB drive. Installing means copying the application out
of it.

1. **Double-click the `.dmg` you downloaded.** A Finder window opens showing two
   icons: the blue **Zirchron** crystal, and a shortcut to your **Applications**
   folder.

2. **Drag the Zirchron icon onto the Applications folder** and release. macOS
   copies the application. This is the entire installation — Mac applications
   are self-contained bundles, so there is no setup wizard, and nothing is
   written elsewhere on your system.

3. **Eject the disk image.** In the Finder sidebar, find *Zirchron 1.0.1* under
   *Locations* and click the ⏏ symbol next to it. You can then delete the
   `.dmg` from Downloads.

> **Why not run it straight from the disk image?** It works, but the app would
> be running from a temporary read-only volume that disappears when you eject
> it. Copying to Applications is what makes it a permanent installation that
> appears in Launchpad and Spotlight.

---

## 4. First launch

Open Zirchron from **Launchpad**, from your **Applications** folder, or with
Spotlight (⌘ Space, then type "Zirchron").

The first time, macOS will **refuse to open it** and show a dialog saying that
it cannot verify the app is free of malware, or that the developer cannot be
identified.

**This is expected and it is not a sign that something is wrong with the file.**
Apple shows this for any application that has not been *notarized* — a paid
service that requires an Apple Developer account. Zirchron is distributed
directly by its author, unnotarized.

To allow it to run:

1. Click **Done** / **Cancel** to dismiss the warning.
2. Open the  menu → **System Settings**.
3. Go to **Privacy & Security** in the sidebar.
4. Scroll down to the **Security** section. You will see a message:
   *"Zirchron" was blocked to protect your Mac.*
5. Click **Open Anyway**.
6. Authenticate with your password or Touch ID if asked, then click **Open**
   in the confirmation dialog.

**You only need to do this once.** From then on, Zirchron opens like any other
application, and you can right-click its Dock icon → *Options* → *Keep in Dock*.

---

## 5. Opening project files

Zirchron saves your work as `.zirchron` files. After you have opened the
application at least once, macOS learns the association and **double-clicking a
`.zirchron` file opens it directly in Zirchron.**

If a `.zirchron` file does not open with Zirchron, right-click it → **Open
With** → *Zirchron*. To make it permanent, right-click → **Get Info** → under
*Open with:* choose Zirchron → **Change All…**

---

## Troubleshooting (macOS)

**"The application is damaged and can't be opened."**
This usually means the download was incomplete or the file was altered in
transit. Delete it and download the `.dmg` again from the Releases page. If it
persists, the quarantine attribute can be cleared by opening **Terminal** and
running:

```
xattr -cr /Applications/Zirchron.app
```

**The app bounces in the Dock and quits, or macOS says the application "cannot
be opened on this Mac".**
Almost always this means you downloaded the file built for the *other*
processor. Go back to step 1, check the **Chip** / **Processor** line, and
download the matching `.dmg`.

**macOS says Zirchron "requires macOS 13 or later".**
Exactly what it says: your system is too old for this build. Updating macOS is
the only route — there is no version of Zirchron for macOS 12 or earlier.

**The first launch takes several seconds.**
Normal. On the very first run the app builds an internal font cache and macOS
performs a one-time security scan of the bundle. Later launches are faster.

**I do not see "Open Anyway" in Privacy & Security.**
The entry only appears shortly after a blocked launch attempt. Try opening
Zirchron once more, then go straight back to System Settings → Privacy &
Security.

---

## Uninstalling (macOS)

Drag `Zirchron.app` from your Applications folder to the Trash. That removes
the application. Your `.zirchron` project files are ordinary documents and are
not affected — delete them yourself if you no longer need them.

---

---

# Getting help

If none of the above resolves the problem, please
[open an issue](../../issues) describing what you tried, and say which system
you are on — Windows 10 or 11, or your macOS version and Mac model.
