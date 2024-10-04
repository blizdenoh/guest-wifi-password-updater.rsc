# guest-wifi-password-updater.rsc
This script ensures secure, efficient, and consistent guest network management.
# MikroTik Guest Wi-Fi Password Updater

## Description
This MikroTik RouterOS script automatically generates and updates a unique, random password for the guest Wi-Fi network at specified intervals (e.g., daily). It ensures improved security by preventing password reuse and unauthorized access.

## Features
- Generates a random Wi-Fi password for guest users.
- Automatically applies the new password to the specified wireless interface (SSID).
- Supports logging the new password for auditing purposes.
- Optional email notification of the new password.
- Automatically reschedules itself to run at the desired interval (e.g., every 24 hours).

## Usage
1. Copy the `guest-wifi-password-updater.rsc` script file to your MikroTik Router.
2. Modify the variables in the script:
   - `ssid`: Set this to the name of your guest Wi-Fi SSID (wireless interface).
   - `passwordLength`: Set the desired password length (default is 10 characters).
   - `validDuration`: Set the password's validity duration (default is 24 hours).
3. Optionally configure email notifications by uncommenting and editing the email section in the script.
4. Schedule the script to run automatically using MikroTik's scheduler.

## Scheduler Setup
You can schedule the script to run at regular intervals using the MikroTik scheduler:
1. Go to **System > Scheduler** in Winbox or use the terminal.
2. Add a new scheduler:
   - **Name**: `UpdateGuestWiFiPassword`
   - **Interval**: `24:00:00` (or any other duration you prefer)
   - **On Event**: `/system script run guest-wifi-password-updater`
3. The script will now update the guest Wi-Fi password automatically at the defined interval.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
