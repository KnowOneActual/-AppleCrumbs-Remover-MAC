# macOS Drive Cleaner

A simple shell script for macOS to remove hidden system files (`.DS_Store`, `._*`, etc.) from external drives.

This is perfect for cleaning a USB flash drive before plugging it into a media player, car stereo, projector, or sharing it with non-Mac users to prevent compatibility issues.

## The Problem

macOS creates hidden files and folders on external drives to manage how it displays icons, stores metadata, and handles trashed items. While useful on a Mac, these files can cause problems on other devices:

-   **Media Players & TVs:** May show these files as unplayable "ghost" tracks.
-   **Windows/Linux Users:** See cluttered folders with confusing extra files.
-   **File Sharing:** Can create unnecessary clutter when sending zipped projects.

This script offers a simple solution to clean these files off your drive.

## What It Removes

The script is designed to safely find and delete:

-   All `.DS_Store` files
-   All `._*` resource fork files (AppleDouble files)
-   Common hidden macOS system folders:
    -   `.Trashes`
    -   `.Spotlight-V100`
    -   `.fseventsd`

---

## How to Use

You can use this script in two ways. The Quick Action method is recommended for most users as it's the easiest.

### Option 1: The Easy Way (Create a Right-Click Action)

This method adds a "Clean Drive" option to your right-click menu. You only have to set this up once.

**Part 1: Create the Quick Action**

1.  Open the **Automator** app (located in your `/Applications` folder).
2.  Click **New Document**, then select **Quick Action** and click "Choose".
3.  Set the top two dropdowns to: "Workflow receives current **files or folders** in **Finder**".
4.  Search for **"Run Shell Script"** in the actions library on the left and drag it into the main workflow area.
5.  In the "Run Shell Script" box, make sure "Pass input" is set to **"as arguments"**.
6.  Delete the default text in the box and paste in the script from the `clean_drive.sh` file in this repository.
7.  Go to **File > Save** and name your Quick Action **`Clean Drive for Other Devices`**.

**Part 2: Use the Quick Action**

1.  Connect your USB drive.
2.  Right-click on the drive's icon (on your Desktop or in a Finder window).
3.  Go to **Quick Actions > Clean Drive for Other Devices**.
4.  A notification will appear when the process is complete. Your drive is now clean!

### Option 2: The Terminal Method

This method is for users who are comfortable with the command line.

1.  Download the `clean_drive.sh` script from this repository.
2.  Open the **Terminal** app.
3.  Make the script executable by running the following command (you only need to do this once):
    ```sh
    chmod +x /path/to/your/clean_drive.sh
    ```
    *(Tip: You can type `chmod +x ` and then drag the script file into the Terminal window to automatically fill in the path.)*
4.  To run the script, drag it into the Terminal window and press **Enter**.
5.  The script will ask you to drag the drive you want to clean into the Terminal window. Follow the on-screen prompts to complete the process.

## ⚠️ Important

This script permanently deletes files. Please double-check that you have selected the correct drive before running it. We are not responsible for any accidental data loss.

## License

This project is licensed under the MIT License.
