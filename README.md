# AEROV GCS

A ground control station for drones, planes, VTOLs, rovers, boats and underwater ROVs running ArduPilot, and for Betaflight quads. It connects to the AI you already use (Claude, Gemini, OpenAI and others) so that AI can see your vehicle and help you set up, tune and troubleshoot.

**Download:** [latest release](https://github.com/renold-aerov/aerov-gcs-releases/releases/latest) (Windows 10 and 11, 64 bit)

## Install

1. Open the [latest release](https://github.com/renold-aerov/aerov-gcs-releases/releases/latest) and download **AEROV-GCS-Setup-x.x.x.exe** under Assets. (The "Source code" links there only hold this page.)
2. Run it. Windows will show "Windows protected your PC" because the app is not code signed yet: click **More info**, then **Run anyway**.
3. Choose where to install. AEROV GCS adds a desktop shortcut.

AEROV GCS updates itself when a new version comes out, and never while the vehicle is armed. You can check by hand in Settings > About and updates.

## Connect

Click the link button in the top bar, or **Find and connect** to let AEROV try every port and network link for you.

- **ArduPilot** (Copter, Plane, VTOL, Rover, Boat, Sub): USB, telemetry radio, WiFi, TCP and UDP.
- **Betaflight**: USB, or WiFi over TCP (for example an ESP bridge at 192.168.4.1:5760).

## What it does

- Setup with guided calibration: accelerometer, compass, level, radio, motor test, firmware.
- Parameters with ArduPilot's own descriptions, and Betaflight's full configuration.
- Fly view with map (street, satellite and a saveable offline map), flight display, takeoff, return and land.
- Missions and survey grids, uploaded straight to the autopilot.
- Lost link: the map keeps the last GPS position, the flight track and home, so you can find the vehicle after a crash.
- Video from USB cameras, capture cards, MJPEG and WebRTC, with recording and a telemetry subtitle file.
- Logs: ArduPilot DataFlash and Betaflight Blackbox (also downloaded over WiFi), with plots, spectrum and step response.

## AI: how to use it

AEROV does not include an AI model of its own. You bring the AI, and AEROV gives it eyes on your vehicle. There are two ways. Both can see what AEROV sees, and **neither can change anything on its own**.

### 1. The Assistant inside AEROV

1. Click the **Assistant** button in the top bar, then the settings icon in its panel.
2. Pick a service: Claude, Google Gemini, OpenAI, OpenRouter, Groq, DeepSeek, Mistral, xAI Grok, a local model through Ollama, or any compatible service.
3. Paste your API key from that service. It is stored encrypted on this computer. You need your own account with that service, and its usage costs are billed by them (a local model through Ollama is free).
4. Ask in plain words. You can also drop a log file into the chat.

### 2. The AI app you already use (no API key in AEROV)

AEROV runs an MCP server, the standard way AI apps connect to tools. Claude Desktop, Claude Code, Cursor, VS Code, Antigravity and other MCP apps can connect to it.

1. Open AEROV, go to **Settings > AI agents** and switch it on.
2. Connect your app:
   - **Claude Desktop**: click **Add to Claude Desktop**, then quit Claude completely (right click its icon near the clock, Quit) and open it again.
   - **Antigravity**: click **Add to Antigravity**, then refresh its MCP servers.
   - **Claude Code**: click **Claude Code command** and paste it into a terminal.
   - **Cursor, VS Code and others**: click **JSON for Cursor and others** and paste it into that app's MCP settings.
3. Keep AEROV open with the vehicle connected, and chat in your AI app.

The connection only works on this computer and needs a token that AEROV creates. Settings > AI agents shows which apps are connected and the tools they used recently.

### What the AI can do

- Read the vehicle: status, why it will not arm, setup progress, parameters and their documentation, Betaflight settings, recent telemetry and autopilot messages.
- Read logs: ArduPilot .bin files, and Betaflight Blackbox straight off the board without downloading. It finds vibration, oscillation, motor and battery problems, and gives a tuning overview with step response.
- See your screen in AEROV and open the right page for you.
- Ask you questions with buttons ("Are the propellers off?") and show you step by step messages.
- Suggest parameter or setting changes and restarts.

### What it cannot do

- Write anything by itself. Every suggested change appears in AEROV as a card with the current value, the new value and the reason. You press **Apply** or **Reject**.
- Arm, change flight modes or fly the vehicle.
- Restart the flight controller while armed.

### Things to ask

- "My drone won't arm. Check AEROV and tell me why."
- "Walk me through calibrating the compass."
- "Look at the Blackbox on the board and tell me if the PIDs need tuning."
- "Analyse the log at C:\Logs\00000042.BIN and explain the crash."
- "Set up a failsafe so it returns home if the radio link is lost."

## Files AEROV saves

- Camera recordings and snapshots: **Videos > AEROV GCS**.
- Problems and crashes go to a log file. Settings > About and updates has **Copy diagnostics** and **Open log folder** for bug reports.

## Feedback

This is a test release. If something does not work, tell us what you did, send a screenshot and the time it happened, and attach the diagnostics from Settings > About and updates.

## Terms

AEROV GCS is free to use for testing. Please do not redistribute it or reverse engineer it. Use it at your own risk and always follow local drone rules.

Copyright 2026 AEROV
