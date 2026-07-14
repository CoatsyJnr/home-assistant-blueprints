# Home Assistant Blueprints

Welcome to my collection of custom Home Assistant blueprints! 

I build and test these automations on my local Home Assistant instance (running on a Raspberry Pi 5 with Zigbee2MQTT and Thread integrations) to make smart home automation more practical, accessible, and tailored to everyday life. 

## 📋 Available Blueprints

| Blueprint | Description | File |
| :--- | :--- | :--- |
| **ADHD Toothbrush Tracker** | Unpredictable, persistent routine tracker to defeat notification blindness. | [`adhd_toothbrush_system.yaml`](adhd_toothbrush_system.yaml) |

<!-- FUTURE BLUEPRINT TEMPLATE (Copy and paste the row below into the table above when ready):
| **Blueprint Name** | Short description here | `filename.yaml` |
-->

---

## 🦷 ADHD-Friendly Brushing System (Morning & Evening)

Standard time-based reminders are easily dismissed, and if they fire at the exact same time every day, "notification blindness" sets in. To solve this, I built a system that adds unpredictability to the alerts and requires actual task completion to dismiss the routine.

### ✨ Key Features
*   🎲 **Randomized Delays:** The initial reminder doesn't fire exactly on the hour. It delays by a random window to break predictability.
*   ⏳ **Randomized Snoozing:** Hitting "Snooze" waits a random duration (e.g., between 4.5 and 5.5 minutes) rather than a fixed 5 minutes.
*   🔁 **Persistent Loops:** The notification will keep coming back until the helper toggle is turned on.
*   🧹 **Auto-Clearing:** As soon as the smart toothbrush reports a "running" state for the required duration, it instantly wipes active alerts from your phone.

### ⚙️ Prerequisites

1.  **A Home Assistant 'Toggle' Helper:** You will need an `input_boolean` helper (e.g., "Toothbrush Tracker") to act as the system's memory for the day.
2.  **The Home Assistant Mobile App:** Installed on your target notification device.
3.  **A Compatible Smart Toothbrush:** This blueprint requires a toothbrush that broadcasts its live active state over Bluetooth. 

**Supported Integrations:**

| Brand | Integration Type | Link |
| :--- | :--- | :--- |
| **Oral-B** | Core Integration | [Home Assistant: Oral-B](https://www.home-assistant.io/integrations/oralb) |
| **Philips Sonicare** | Custom Component | [GitHub: philips_sonicare_ble](https://github.com/mtheli/philips_sonicare_ble) |
| **Laifen** | Custom Component | [GitHub: laifen_ble](https://github.com/UrbanTechIO/Laifen) |

*(Note: Batch-syncing brushes like Oclean are not supported as they rely on historical polling rather than live state broadcasting).*

### 📥 Import

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FCoatsyJnr%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fadhd_toothbrush_system.yaml)

---

## 🛠️ General Installation 

If you prefer to install any of these blueprints manually without using the My Home Assistant badge above:

1. Navigate to **Settings** > **Automations & Blueprints** > **Blueprints** in your Home Assistant UI.
2. Click **Import Blueprint** in the bottom right corner.
3. Paste the raw GitHub URL of the desired `.yaml` file.
4. Click **Preview** and then **Import**.

## 🤝 Feedback and Contributions

Feedback is always welcome! If you have suggestions for improving these automations, modifying the YAML logic, or find a bug, please feel free to open an issue or submit a pull request. 

---
*Created by CoatsyJnr*