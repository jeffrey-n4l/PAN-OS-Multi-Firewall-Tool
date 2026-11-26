# PAN-OS Runner

A desktop app to run PAN-OS CLI commands across many Palo Alto firewalls at once over SSH.
Runs the same command (e.g. `show system info`) on every firewall in your list, in parallel,
and saves the results as CSV and JSON.

## Download

Go to the [**Releases**](../../releases/latest) page and download the file for your system:

- **Mac** — `PAN-OS-Runner-mac.zip`
- **Windows** — `PAN-OS-Runner-windows.zip`

You don't need Python or anything else installed — the app includes everything.

## Run it

**Mac**
1. Double-click the downloaded `.zip` to unzip it.
2. Double-click **PAN-OS Runner**.
3. First time only: macOS may say it's from an unidentified developer.
   Right-click the app → **Open** → **Open**.

**Windows**
1. Unzip the downloaded file.
2. Open the folder and run **PAN-OS Runner.exe**.
3. First time only: if SmartScreen warns, click **More info** → **Run anyway**.

## Using the app

1. Make a plain text file with one firewall IP (or hostname) per line.
2. In the app, click **Browse…** and pick that file.
3. Type the command(s) to run — one per line. Defaults to `show system info`.
4. Enter your firewall username and password (used for every firewall; never saved to disk).
5. Click **Run**. The table fills in as each firewall responds.
   Double-click a row to see that firewall's full output.

Results are saved to a **PAN-OS Runner** folder in your home directory, as CSV and JSON,
in a subfolder named by the date and time of the run.

### Notes
- Connect to the VPN first if your firewalls are only reachable through it.
- Config commands (`set …`, `delete …`) are validated automatically; nothing is committed
  unless you turn that on.
- Your password is only held in memory for the run and is never written to any file.
