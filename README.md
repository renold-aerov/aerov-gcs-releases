# AEROV GCS

Ground control software for ArduPilot drones, planes, VTOLs, rovers, boats and underwater ROVs, and for Betaflight quads. You can also hook up your own AI app to it, so it can look at your vehicle and help you fix problems.

**Download:** [latest release](https://github.com/renold-aerov/aerov-gcs-releases/releases/latest) (Windows 10 and 11, 64 bit)

This is a test version. If something breaks, we want to hear about it.

## Install

1. Open the [latest release](https://github.com/renold-aerov/aerov-gcs-releases/releases/latest) and download **AEROV-GCS-Setup-x.x.x.exe** from the Assets list. Ignore the "Source code" links, they only contain this page.
2. Run it. Windows will say "Windows protected your PC" because we have not signed the app yet. Click **More info**, then **Run anyway**.
3. Pick an install folder. A desktop shortcut is added.

The app updates itself when a new version is out, and it never does this while the vehicle is armed. You can also check by hand in Settings > About and updates.

## Connect your vehicle

Click the link button at the top, or press **Find and connect** and AEROV will try every port and network link for you.

- ArduPilot (Copter, Plane, VTOL, Rover, Boat, Sub): USB, telemetry radio, WiFi, TCP or UDP.
- Betaflight: USB, or WiFi over TCP (an ESP bridge at 192.168.4.1:5760, for example).

## What you get

- Guided setup and calibration: accelerometer, compass, level, radio, motor test and firmware.
- Parameters with ArduPilot's own descriptions, and the full Betaflight configuration.
- Fly view with a map (street, satellite, and an offline map you can save), flight display, takeoff, return and land.
- Missions and survey grids that upload straight to the autopilot.
- If the link drops in flight, the map keeps the last GPS position, the flight trail and home. Useful for finding the vehicle after a crash.
- Video from USB cameras, capture cards, MJPEG and WebRTC, with recording and a telemetry subtitle file.
- Logs: ArduPilot DataFlash and Betaflight Blackbox (also over WiFi), with plots, spectrum and step response.

## Using an AI with AEROV

AEROV does not come with an AI. You use your own, and AEROV lets it see what is going on with your vehicle. Either way, the AI can only suggest. Nothing gets changed until you press Apply.

### Option 1: the Assistant inside AEROV

1. Click the **Assistant** button at the top, then the settings icon in the panel.
2. Choose a service. Claude, Google Gemini, OpenAI, OpenRouter, Groq, DeepSeek, Mistral, xAI Grok, a local model with Ollama, or any OpenAI compatible one.
3. Paste your API key. It is saved encrypted on your computer. You need your own account with that service and they bill you for usage. A local Ollama model is free.
4. Type your question. You can also drop a log file into the chat.

### Option 2: the AI app you already have

AEROV runs a small MCP server on your computer. MCP is the usual way AI apps talk to other software. Claude Desktop, Claude Code, Cursor, VS Code, Antigravity and other MCP apps can use it, and you do not need an API key in AEROV for this.

1. In AEROV open **Settings > AI agents** and turn it on.
2. Connect your app:
   - **Claude Desktop:** press **Add to Claude Desktop**, then close Claude fully (right click its icon near the clock and choose Quit) and open it again.
   - **Antigravity:** press **Add to Antigravity**, then refresh its MCP servers.
   - **Claude Code:** press **Claude Code command** and paste it in a terminal.
   - **Cursor, VS Code and others:** press **JSON for Cursor and others** and paste it into that app's MCP settings.
3. Leave AEROV open with your vehicle connected and chat in your AI app as usual.

It only works on the same computer, and AEROV makes a token for it. Settings > AI agents shows which apps are connected and what they used lately.

### What the AI can do

- Look at the vehicle: status, why it won't arm, setup progress, parameters and what they mean, Betaflight settings, recent telemetry and autopilot messages.
- Read logs. That means ArduPilot .bin files and Betaflight Blackbox straight from the board. It can spot vibration, oscillation, motor and battery problems and give you a tuning summary.
- See your AEROV screen and open the right page for you.
- Ask you questions with buttons, like "Are the props off?", and show you messages step by step.
- Suggest parameter or setting changes, and a restart if needed.

### What it can't do

- Change anything on its own. Every suggestion shows up in AEROV as a card with the current value, the new value and the reason. You press **Apply** or **Reject**.
- Arm, switch flight modes or fly the vehicle.
- Restart the flight controller while it is armed.

### Things you can ask

- "My drone won't arm. Check AEROV and tell me why."
- "Walk me through compass calibration."
- "Look at the Blackbox on the board. Do my PIDs need tuning?"
- "Go through C:\Logs\00000042.BIN and tell me what caused the crash."
- "Set up a failsafe so it comes home if the radio link drops."

## Where files are saved

- Camera recordings and snapshots go to **Videos > AEROV GCS**.
- Problems and crashes are written to a log file. In Settings > About and updates, use **Copy diagnostics** and **Open log folder** when you report a bug.

## Feedback

Tell us what you did, send a screenshot and the time it happened, and attach the diagnostics from Settings > About and updates.

## Terms

Free to use for testing. Please don't share the installer around or reverse engineer it. Use it at your own risk and follow your local drone rules.

Copyright 2026 AEROV
