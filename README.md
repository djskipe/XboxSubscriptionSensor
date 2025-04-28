
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
2. Copia il contenuto di `sensors/scadenza_xbox.yaml` **dentro il tuo** `configuration.yaml` sotto la sezione `sensor:`.  
   Esempio:

   ```yaml
   sensor:
     - platform: template
       sensors:
         scadenza_xbox:
           friendly_name: "Scadenza abbonamento Xbox"
           value_template: >-
             {% set data_scadenza = as_timestamp(strptime('2026-12-31', '%Y-%m-%d')) %}
             {% set ora_attuale = as_timestamp(now()) %}
             {% if ora_attuale >= data_scadenza %}
               L'abbonamento Xbox è scaduto
             {% else %}
               L'abbonamento Xbox scade il 31-12-2026
             {% endif %}

         stato_abbonamento_xbox:
           friendly_name: "Stato abbonamento Xbox"
           value_template: >-
             {% set data_scadenza = as_timestamp(strptime('2026-12-31', '%Y-%m-%d')) %}
             {% if now().timestamp() >= data_scadenza %}
               Scaduto
             {% else %}
               Attivo
             {% endif %}
   ```

3. Copia il contenuto di `automations/notifica_scadenza_xbox.yaml` **dentro il tuo** `configuration.yaml` sotto la sezione `automation:`.  
   Esempio:

   ```yaml
   automation:
     - alias: Notifica scadenza abbonamento Xbox
       description: Invia una notifica quando l'abbonamento Xbox scade
       trigger:
         - platform: state
           entity_id: sensor.stato_abbonamento_xbox
           to: "Scaduto"
       action:
         - service: notify.NOTIFICA_TUA
           data:
             message: "⚠️ L'abbonamento Xbox è scaduto!"
       mode: single
   ```

   > 🔵 **IMPORTANTE:** Sostituisci `notify.NOTIFICA_TUA` con il tuo servizio di notifica, ad esempio `notify.mobile_app_mio_telefono`.

4. Salva tutto e riavvia Home Assistant.

---

### 📢 Suggerimento

Per avere un controllo completo, aggiungi anche l'integrazione ufficiale di Xbox su Home Assistant:

➡️ [Configura Xbox Integration](https://my.home-assistant.io/redirect/config_flow_start?domain=xbox)

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
2. Copy the content of `sensors/scadenza_xbox.yaml` **inside your** `configuration.yaml` under the `sensor:` section.  
   Example:

   ```yaml
   sensor:
     - platform: template
       sensors:
         scadenza_xbox:
           friendly_name: "Scadenza abbonamento Xbox"
           value_template: >-
             {% set data_scadenza = as_timestamp(strptime('2026-12-31', '%Y-%m-%d')) %}
             {% set ora_attuale = as_timestamp(now()) %}
             {% if ora_attuale >= data_scadenza %}
               L'abbonamento Xbox è scaduto
             {% else %}
               L'abbonamento Xbox scade il 31-12-2026
             {% endif %}

         stato_abbonamento_xbox:
           friendly_name: "Stato abbonamento Xbox"
           value_template: >-
             {% set data_scadenza = as_timestamp(strptime('2026-12-31', '%Y-%m-%d')) %}
             {% if now().timestamp() >= data_scadenza %}
               Scaduto
             {% else %}
               Attivo
             {% endif %}
   ```

3. Copy the content of `automations/notifica_scadenza_xbox.yaml` **inside your** `configuration.yaml` under the `automation:` section.  
   Example:

   ```yaml
   automation:
     - alias: Xbox Subscription Expiration Notification
       description: Sends a notification when the Xbox subscription expires
       trigger:
         - platform: state
           entity_id: sensor.stato_abbonamento_xbox
           to: "Scaduto"
       action:
         - service: notify.YOUR_NOTIFICATION_SERVICE
           data:
             message: "⚠️ Your Xbox subscription has expired!"
       mode: single
   ```

   > 🔵 **IMPORTANT:** Replace `notify.YOUR_NOTIFICATION_SERVICE` with your actual notification service, like `notify.mobile_app_my_phone`.

4. Save and restart Home Assistant.
