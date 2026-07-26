<div align="center">

# Run Appium Tests with Python on pCloudy

[![pCloudy](https://img.shields.io/badge/Made%20by-pCloudy-1a73e8?style=for-the-badge)](https://www.pcloudy.com)
[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Appium Python Client](https://img.shields.io/badge/Appium%20Python%20Client-2.x-00A4E4?style=for-the-badge)](https://pypi.org/project/Appium-Python-Client/)

</div>

## Getting Started

[pCloudy](https://www.pcloudy.com) is a mobile testing platform that gives you access to real Android and iOS devices from the cloud. This project provides Python Appium samples that run on pCloudy with minimal changes to standard Appium scripts.

pCloudy is fully integrated with Appium, allowing you to run your existing automation scripts against real devices on the pCloudy cloud.

This project is a Python-based Appium sample showing how to run Android and iOS tests on the pCloudy Real Device Cloud.

## Prerequisites

- Python 3.8 or higher
- pip
- Appium Python client and Selenium
- A [pCloudy account](https://www.pcloudy.com) with your registered email ID and API key
- Your app (`.apk`/`.ipa`) uploaded to your pCloudy Cloud Drive when needed

## Getting Started

Clone the project and install the dependencies:

```bash
git clone <your-repository-url>
cd PC-appium-python
pip install -r requirements.txt
```

### Configure your credentials and app

The sample scripts read your pCloudy credentials from environment variables:

**macOS / Linux:**

```bash
export PCLOUDY_USERNAME="YOUR_EMAIL_ID"
export PCLOUDY_APIKEY="YOUR_API_KEY"
```

**Windows:**

```bat
set PCLOUDY_USERNAME=YOUR_EMAIL_ID
set PCLOUDY_APIKEY=YOUR_API_KEY
```

You can also update the device name, app name, and app identifiers in the Python scripts to match your pCloudy account and app bundle.

## Running the Sample

Each platform has its own sample script:

### Run tests

```bash
python Androidapp.python
python IOSapp.python
python AndroidWeb.python
python IOSWeb.python
```

Alternatively, open the Python scripts and hardcode the values directly if you prefer.

The `pCloudy_ApplicationName` capability must match the name of the app already uploaded to your pCloudy Cloud Drive. For iOS, make sure the app name and bundle ID in the script match your uploaded app.

### Capabilities used in this sample

| Capability | Description |
|---|---|
| `pCloudy_Username` | Your pCloudy account email ID |
| `pCloudy_ApiKey` | Your pCloudy API key |
| `pCloudy_DeviceFullName` | Book a specific device by its full name, for example `SAMSUNG_GalaxyA10s_Android_11.0.0_99cde` |
| `pCloudy_ApplicationName` | Name of the app already uploaded to your pCloudy Cloud Drive |
| `automationName` | Appium automation engine — `UiAutomator2` (Android) or `XCUITest` (iOS) |
| `appium:appPackage` / `appium:appActivity` | (Android) Package and launch activity of the app under test |
| `bundleId` | (iOS) Bundle identifier of the app under test |

> **Note:** `pCloudy_DeviceFullName` alone is enough to book a specific device. When it is set, you can leave the manufacturer/version fields unset if you want to target a specific device directly.

The driver connects to the pCloudy Appium hub at:

```text
https://device.pcloudy.com/appiumcloud/wd/hub
```

Test results are visible on your [pCloudy dashboard](https://www.pcloudy.com) once the session starts.

### Screenshots

Each script saves screenshots to the local `screenshots/` folder during execution so you can review the test flow.

## Project Structure

```text
PC-appium-python/
├── requirements.txt          # Python dependencies
├── Androidapp.python         # Android native app sample
├── IOSapp.python             # iOS native app sample
├── AndroidWeb.python         # Android web sample
├── IOSWeb.python             # iOS web sample
├── screenshots/              # Captured screenshots
└── README.md                 # Project documentation
```

## API Documentation

For the full pCloudy REST API reference (device booking, app upload, reports, and more), see:

- [pCloudy API Documentation](https://content.pcloudy.com/apidocs/index.html)

## Learn More

- [pCloudy Website](https://www.pcloudy.com)
- [Appium Integration on pCloudy](https://www.pcloudy.com)

## Contributions

Contributions are welcome. Please open an issue to discuss your idea before submitting a pull request.