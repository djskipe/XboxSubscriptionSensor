# 🎮 Home Assistant - Xbox Abbonamento Sensor / Xbox Subscription Sensor

## Italiano 🇮🇹

Monitorare la **scadenza dell'abbonamento Xbox** direttamente in Home Assistant, con **notifiche automatiche** alla scadenza!
Facile, veloce e completamente personalizzabile.

### 📄 Cosa include

- **Sensore di scadenza** (`sensor.scadenza_xbox`) che mostra se l'abbonamento è scaduto o la data prevista di scadenza.
- **Sensore di stato** (`sensor.stato_abbonamento_xbox`) che mostra "Attivo" o "Scaduto".
- **Automazione** che invia una **notifica** alla scadenza.

### 🚀 Come si installa

1. Scarica i file dal pacchetto ZIP.
2. Copia i file:
   - `sensors/scadenza_xbox.yaml` nella tua cartella dei sensori (`/config/sensors/`).
   - `automations/notifica_scadenza_xbox.yaml` nella tua cartella delle automazioni (`/config/automations/`).
3. Aggiungi i file al tuo `configuration.yaml` usando `!include`.
4. Riavvia Home Assistant.

### 📢 Suggerimento

Per un'integrazione completa, aggiungi anche l'integrazione ufficiale di Xbox su Home Assistant:

➡️ [Configura Xbox Integration](https://my.home-assistant.io/redirect/config_flow_start?domain=xbox)

### 📌 Requisiti

- Home Assistant aggiornato
- Servizio di notifica configurato (`notify`)
- (Facoltativo) Integrazione Xbox Live di Home Assistant

---

## English 🇬🇧

Monitor your **Xbox subscription expiration date** directly inside Home Assistant, with **automatic notifications** when it expires!
Easy to use, fast, and fully customizable.

### 📄 What's Included

- **Expiration sensor** (`sensor.scadenza_xbox`) showing whether the subscription is expired or the expiration date.
- **Status sensor** (`sensor.stato_abbonamento_xbox`) showing "Active" or "Expired".
- **Automation** to send you a **notification** when the subscription expires.

### 🚀 How to Install

1. Download the files from the ZIP package.
2. Copy the files:
   - `sensors/scadenza_xbox.yaml` into your sensor folder (`/config/sensors/`).
   - `automations/notifica_scadenza_xbox.yaml` into your automations folder (`/config/automations/`).
3. Add the files into your `configuration.yaml` using `!include`.
4. Restart Home Assistant.

### 📢 Tip

For a complete experience, integrate your Xbox account into Home Assistant with the official Xbox integration:

➡️ [Set up Xbox Integration](https://my.home-assistant.io/redirect/config_flow_start?domain=xbox)

### 📌 Requirements

- Updated Home Assistant
- Configured notification service (`notify`)
- (Optional) Home Assistant Xbox Live Integration

