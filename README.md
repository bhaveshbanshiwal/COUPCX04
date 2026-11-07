# COUP — Tabletop Digital Companion (2–6 Players)

[![GitHub Pages](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-brightgreen?style=for-the-badge&logo=github)](https://bhaveshbanshiwal.github.io/COUPCX04/)
[![Real-Time](https://img.shields.io/badge/Multiplayer-Instant%20WebSocket%20P2P-blue?style=for-the-badge&logo=websocket)](https://bhaveshbanshiwal.github.io/COUPCX04/)

A modern, serverless digital companion for playing **Coup** with 2 to 6 players sitting around a physical table using their phones or laptops instead of physical cards and coins.

---

## 🎯 Gameplay Rules & Mechanics

1. **4-Digit Quick-Join Codes (e.g. 1234):**
   - Clean 4-digit numeric codes with native mobile number pad keyboard support (`inputmode="numeric"`).
   - Zero NAT/firewall delays — connects in under 250ms across cellular 4G/5G, Wi-Fi, and hotspots.
2. **0 Starting Coins for All Player Counts (2–6 Players):**
   - Every player starts with **0 Coins** and **2 Face-Down Cards**, regardless of whether there are 2, 3, 4, 5, or 6 players.
3. **Real Ordered FIFO Court Deck:**
   - The 15-card Court Deck (3× Duke, 3× Assassin, 3× Captain, 3× Ambassador, 3× Contessa) is shuffled only once at initial deal.
   - **Draw from TOP (`deck.shift()`):** New cards (Ambassador exchange, challenge replacement) always come from the top of the stack.
   - **Return to BOTTOM (`deck.push()`):** Cards returned to the deck go straight to the bottom without random reshuffling.
4. **Strict Card Privacy & Quiet Return:**
   - **Proven Claim (No Bluff):** If challenged and telling the truth, your card is revealed to the table in a verification banner, placed at the bottom of the Court Deck, and replaced from the top.
   - **Bluff Caught / Card Lost:** Your lost card is **never shown** to opponents. You quietly select which card to return to the bottom of the Court Deck face-down.
5. **Tabletop Privacy Shield:**
   - Features a **"🙈 Hide / 👁️ Peek My Cards"** toggle so players sitting next to each other at the physical table cannot see your screen.
6. **Zero Backend Required:**
   - Instant multi-broker failover (HiveMQ + EMQX) with encrypted per-client topic segregation.
   - Includes **Single-Device Pass & Play** mode for playing on a single shared tablet or laptop.

---

## 🚀 How to Play

### Online / Mobile Tabletop (Multi-Device)
1. **Host:** Open [https://bhaveshbanshiwal.github.io/COUPCX04/](https://bhaveshbanshiwal.github.io/COUPCX04/), enter your name, and click **👑 Host Table**.
2. **Invite:** A clean **4-digit Table Code (e.g. 1234)** is generated. Click **📋 Copy Link** to share a direct-join link.
3. **Join:** Friends open the link or enter the 4-digit code on their phones, enter their name, and click **Join Table**.
4. **Deal:** Once everyone is seated (2 to 6 players), the host taps **🎴 Deal Cards & Start (0 Coins)**.

### Single-Device Pass & Play
1. Switch to the **🛋️ Single-Device Pass & Play** tab in the lobby.
2. Add player names or click **⚡ Demo 4 Players**.
3. Tap **Deal Cards & Start**. Use the top header perspective dropdown to switch whose turn/hand is visible.

---

## 📜 Character Abilities & Action Reference

| Character | Action / Counteraction | Effect |
| :--- | :--- | :--- |
| **General** | **Income** | Take +1 Coin from Treasury. Cannot be blocked or challenged. |
| **General** | **Foreign Aid** | Take +2 Coins. Blocked by any player claiming **Duke**. |
| **General** | **Coup** | Pay 7 Coins. Target loses 1 card. Unblockable. Mandatory at 10+ coins. |
| **Duke** | **Tax** | Take +3 Coins from Treasury. Blocks **Foreign Aid**. |
| **Assassin** | **Assassinate** | Pay 3 Coins. Target loses 1 card. Blocked by target claiming **Contessa**. |
| **Captain** | **Steal** | Steal up to 2 Coins from a target player. Blocked by **Captain** or **Ambassador**. |
| **Ambassador** | **Exchange** | Draw 2 from Top of Court Deck, keep live count, quietly return unchosen to Bottom. Blocks **Steal**. |
| **Contessa** | **Block Assassination** | Blocks an incoming assassination attempt. |

---

## 📂 Repository Structure

```
COUPCX04/
├── index.html           # Full self-contained SPA, game engine, and WebRTC logic
├── images/
│   ├── box.jpg          # Coup box cover art
│   ├── duke.jpg         # Duke card portrait
│   ├── assassin.jpg     # Assassin card portrait
│   ├── captain.jpg      # Captain card portrait
│   ├── ambassador.jpg   # Ambassador card portrait
│   ├── contessa.jpg     # Contessa card portrait
│   └── back.jpg         # Card back
└── README.md
```

