# BoostPilot

**BoostPilot** is a Windows app for sellers on [Eldorado.gg](https://www.eldorado.gg). It watches your boosting requests and orders, prices them from your own price lists, and sends your first reply in the Eldorado chat — so buyers hear from you within a minute, even while you're away.

This page has the installers. **[⬇ Download the latest version](https://github.com/AnmarRahman/boostpilot-releases/releases/latest)** — pick `BoostPilot-Setup-x.y.z.exe`.

---

## What it does

- **Boosting requests** — finds new requests every minute, reads the details (ranks, platform, region…), prices them and writes your opening message. You send with one click, or let **Hands-free mode** send automatically.
- **Games** — EA Sports FC (Division Rivals, FUT Champions, Clubs, Gauntlet…), plus Valorant, League of Legends and Rocket League, built from Eldorado's own request forms.
- **Your prices** — per rank step, per win/game/level, with % adjustments (Duo, region, queue, add-ons such as Stream).
- **Your messages** — several alternate messages per service (BoostPilot takes turns). An empty line splits a message into separate chat messages, sent one after another like a person typing.
- **FC Coins** — keeps your Eldorado coin offer in sync and can greet new coin buyers in the order chat.
- **Pause buttons** — pause a service in one click (also stops/starts it on Eldorado).
- **Safety first** — nothing is sent until you turn on *Allow real sending*; each buyer gets a message once, never twice; limits per minute/hour; a kill switch in the tray.

---

## Requirements

- Windows 10 or 11 (64-bit) — a normal PC or a Windows virtual machine.
- About 1 GB of free memory for BoostPilot (8 GB RAM in total is plenty).
- An Eldorado seller account. Recommended: an Eldorado **Seller API** key (free, in your Eldorado dashboard — see step 4).

---

## Install

1. Download **`BoostPilot-Setup-x.y.z.exe`** from the [latest release](https://github.com/AnmarRahman/boostpilot-releases/releases/latest).
2. Run it. Windows may show **"Windows protected your PC"** (the installer isn't code-signed yet): click **More info → Run anyway**.
3. Follow the installer. BoostPilot starts when it's done and adds a desktop and Start-menu shortcut.

**Already have BoostPilot?** Just run the new installer — it says *"Update BoostPilot x → y?"*, closes the running copy cleanly and keeps all your prices, messages, settings, Eldorado login and history. (Usually you don't even need this: BoostPilot updates itself — see *Updates* below.)

---

## First-time setup (about 10 minutes)

BoostPilot starts in a safe state: **nothing is ever sent** until you switch it on in step 7.

1. **Log in to Eldorado inside BoostPilot.**
   Go to **Connections → Open Eldorado window** and log in on Eldorado's own page (use email + password if "Sign in with Google" is refused). If Eldorado shows a *"Verify you are human"* check, complete it there. BoostPilot never sees or stores your password; you stay logged in.

2. **Turn on the Eldorado connection.**
   **Connections → Browser Integration Enabled** (and **Browser Auto Detect**). Press **Run read-only check** to confirm BoostPilot can read your requests — it never types or sends during this check.

3. **Set your prices.**
   - **Pricing → Division Rivals / FUT Champions** for EA FC (price + time per rank step).
   - **Games** for Valorant, League of Legends and Rocket League: switch the game on, open a category, fill in the price per step (or per win/game), optional % adjustments, and press **Save**. Use **Test a request** to check a price.
   - **Pricing → FC Coins** for your coin offer.

4. **Connect the Eldorado Seller API** (recommended).
   On Eldorado, open your seller dashboard → **Seller API** and create a Client ID + Client Secret. In BoostPilot, **Connections → Eldorado Seller API**, paste both and press **Connect & test**. The secret is stored encrypted on your PC (Windows protection) and is only ever sent to Eldorado.
   With the API, BoostPilot finds new requests and orders faster and can pause/resume services and your coin offer on Eldorado.

5. **Write your messages.**
   On each pricing / game page (or **Messages**), edit the opening message and add alternates. Use variables such as `{{buyer}}`, `{{current_rank}}`, `{{target_rank}}`, `{{price}}`, `{{eta}}` — the editor lists the ones available. **Leave an empty line** to send the message as several chat messages. Keep everything on Eldorado (no Discord links or outside contacts — that's against Eldorado's rules).

6. **(Optional) FC Coins orders.**
   **Coin orders**: write the welcome message for coin buyers and choose a mode — start with **Dry run** (shows exactly what it would send), then **Approve** (one click per order) or **Auto**.

7. **Go live — Hands-free mode.**
   On the **Dashboard → Hands-free mode**, go down the checklist:
   - **Allow real sending** — BoostPilot may now really click *Send*.
   - **Send opening messages automatically** — new priced requests get your message without you clicking (only requests up to 60 min old, max 3/min and 30/hour, never twice).
   - **Bot is running** — press **Start**.
   - **Start the bot when BoostPilot opens** and **Open BoostPilot with Windows** — so it keeps going after a restart.
   - **Keep the PC awake** — recommended on a PC that runs BoostPilot all the time.

   When the badge says **"ON — BoostPilot runs by itself"**, you can close the window: BoostPilot keeps working in the system tray (bottom-right, next to the clock).

**Prefer to stay in control?** Skip *Send opening messages automatically* — then you review each request under **Requests** and press **Send Opening Message**.

---

## Everyday use

- **Tray icon** (right-click): open BoostPilot or the Eldorado window, start/pause the bot, **Kill switch** (stops everything at once), start with Windows, keep the PC awake, quit.
- **Pause a service**: **Dashboard → Services** (Division Rivals, FUT Champions, FC Coins) or the pause option on each game category.
- **Notifications** pop up when something needs you (e.g. Eldorado asks you to log in again or complete a check, a message couldn't be confirmed, a coin order is waiting for approval).
- **Requests** shows every request, its price, the exact message and what was sent.

---

## Updates

BoostPilot checks this page for new versions every few hours and downloads them quietly.

- **Settings → Updates → "Ask me"** (default): a banner says *"BoostPilot x.y.z is ready"* — press **Update now** (see *What's new* first).
- **Settings → Updates → "Install automatically when idle"**: best for a PC that's always on.

An update **never interrupts a message being sent**. Before installing, BoostPilot backs up its database and closes cleanly; it restarts by itself with everything as it was. Each release lists its changes on the [releases page](https://github.com/AnmarRahman/boostpilot-releases/releases).

---

## Your data

Everything is stored on your PC in **`%APPDATA%\BoostPilot`** (tray → *Open data folder*):

| | |
|---|---|
| `fc27.json` | your prices, messages and game settings |
| `bot.db` | requests, orders, history |
| `backups\` | automatic database copies (daily and before every update) |
| `logs\` | `backend.log`, `updater.log`, `main.log` — useful when asking for help |

Uninstalling BoostPilot (Windows Settings → Apps) keeps this folder, so a reinstall picks up where you left off. Delete the folder yourself only if you want a completely fresh start.

---

## Troubleshooting

- **"Windows protected your PC"** when installing → *More info → Run anyway*.
- **"Eldorado needs you" / login or "Verify you are human"** → open the Eldorado window from the tray and complete it; BoostPilot continues by itself.
- **Nothing gets sent** → check the Dashboard checklist: *Allow real sending*, the bot running, the service not paused, prices set for that request, and the kill switch released.
- **A request shows "No price"** → that route/amount isn't priced yet on its pricing page, or the request is older than your Hands-free age limit.
- **"Another BoostPilot is already running"** → BoostPilot is already open in the tray; only one copy can run.
- **Slow PC / virtual machine** → use version 0.2.2 or newer (the hidden Eldorado window no longer uses CPU while idle).

Still stuck? Send the files from `%APPDATA%\BoostPilot\logs` along with a short description.
