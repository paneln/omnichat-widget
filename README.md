# PanelN OmniChat Widget 🚀

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Performance: Ultra-Fast](https://img.shields.io/badge/Performance-Ultra--Fast-success.svg)](#)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-brightgreen.svg)](#)

A lightning-fast, ultra-lightweight, and fully customizable Multi-Channel Chat Widget for your website. Designed for high performance and seamless user experience. 100% Free and Open Source.

Out-of-the-box support for **WhatsApp** (Chat, Group, Channel) and **Telegram** (User, Group, Channel).

## 🌟 Why OmniChat? (For Developers)

* **Zero Performance Hit:** Uses `requestIdleCallback` to load only when the browser is idle. It won't affect your PageSpeed Insights or Lighthouse scores.
* **Shadow DOM Isolation:** Renders inside a Shadow Root. Your website's CSS won't break the widget, and the widget's CSS won't bleed into your site.
* **A11y Compliant:** Fully accessible with keyboard focus trapping, ARIA attributes, and Escape key support.
* **Event Tracking:** Auto-detects Google Analytics (`gtag` or `ga`) and logs `chat_widget_click` events automatically.
* **No Dependencies:** Pure Vanilla JavaScript. No jQuery, no React, no external stylesheets.

---

## 🚀 Quick Start & Use Cases

Installation is incredibly simple. Just paste the `<script>` tag right before your closing `</body>` tag. The widget automatically adapts based on the attributes you provide.

### Use Case 1: Simple Single WhatsApp Button
If you only provide a single contact attribute, it acts as a classic, pulsating floating button.

```html
<!-- Single WhatsApp Button -->
<script 
  src="https://cdn.paneln.com/widgets/chat/v1/launcher.min.js"
  data-wa-number="971504170626"
  data-wa-message="Hello, I need help!"
  data-position="right"
  defer>
</script>
```

### Use Case 2: Multi-Channel Support (WhatsApp + Telegram)
Provide multiple attributes, and it seamlessly transforms into a sleek pop-up menu with a backdrop blur effect.

```html
<!-- Multi-Channel Menu -->
<script 
  src="https://cdn.paneln.com/widgets/chat/v1/launcher.min.js"
  data-position="right"
  data-color="#2B2A33"
  data-welcome="Hi! How can we help?"
  
  data-wa-number="971504170626"
  data-wa-label="Chat with Support"
  
  data-tg-user="ShafiqSawand"
  data-tg-label="Message on Telegram"
  defer>
</script>
```

### Use Case 3: Communities & Channels Only
Perfect for creators or brands who want to drive traffic to their groups or channels instead of direct DMs.

```html
<!-- Community & Channels Menu -->
<script 
  src="https://cdn.paneln.com/widgets/chat/v1/launcher.min.js"
  data-position="left"
  data-welcome="Join our communities!"
  
  data-wa-group="YourWaGroupID"
  data-wa-group-label="Join WhatsApp Group"
  
  data-tg-channel="YourTgChannelName"
  data-tg-channel-label="Join Telegram Channel"
  defer>
</script>
```

### Use Case 4: Advanced Dynamic Variables
Auto-inject the user's current context (Page Title or URL) directly into the WhatsApp message.

```html
<!-- Dynamic WhatsApp Message -->
<script 
  src="https://cdn.paneln.com/widgets/chat/v1/launcher.min.js"
  data-wa-number="971504170626"
  data-wa-message="Hi, I am looking at {page_title} and I have a question. Link: {page_url}"
  defer>
</script>
```

---

## ⚙️ Configuration Attributes

| Attribute | Description | Default Value |
| :--- | :--- | :--- |
| `data-position` | Position of the widget (`left` or `right`) | `right` |
| `data-color` | Custom HEX color for the main button | `#2B2A33` (Multi) / `#25D366` (Single) |
| `data-welcome` | Text for the auto-open welcome pop-up | `Hi, how can we help you today?` |
| `data-auto-open` | Delay (in ms) before welcome message shows | `3000` |
| `data-wa-number` | WhatsApp Number (with country code, no `+`) | *-* |
| `data-wa-message` | Pre-filled WhatsApp message | `Hello!` |
| `data-wa-group` | WhatsApp Group Invite ID | *-* |
| `data-wa-channel` | WhatsApp Channel ID | *-* |
| `data-tg-user` | Telegram Username (without `@`) | *-* |
| `data-tg-group` | Telegram Group Username | *-* |
| `data-tg-channel` | Telegram Channel Username | *-* |
| `data-*-label` | Custom text for tooltips (e.g., `data-wa-label`) | *Varies by network* |

---

## 💡 Dynamic Variables
You can use these special placeholders inside your `data-wa-message`:
* `{page_title}` : Dynamically inserts the current webpage's title.
* `{page_url}` : Dynamically inserts the current webpage's full URL.

---

## 📊 Analytics & Event Tracking
The widget automatically detects if Google Analytics (GA4) is installed on your site. When a user clicks any chat link, it fires a standard event:
* **Event Name:** `chat_widget_click`
* **Event Category:** `Engagement`
* **Event Label:** e.g., `whatsapp_chat`, `telegram_channel`, etc.

> *No setup required. It silently fails if GA is not detected, ensuring zero console errors.*

---

## 📄 License
Released under the [MIT License](https://opensource.org/licenses/MIT). Free for personal and commercial use.

Crafted with ❤️ by **Shafiq Sawand** & [PanelN](https://paneln.com).
