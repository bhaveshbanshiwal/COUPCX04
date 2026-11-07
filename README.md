# COUP — Tabletop Digital Companion (2–6 Players)

[![GitHub Pages](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-brightgreen?style=for-the-badge&logo=github)](https://bhaveshbanshiwal.github.io/COUPCX04/)
[![WebRTC](https://img.shields.io/badge/Multiplayer-PeerJS%20WebRTC-orange?style=for-the-badge&logo=webrtc)](https://peerjs.com/)

A modern, serverless digital companion for playing **Coup** with 2 to 6 players sitting around a physical table using their phones or laptops instead of physical cards and coins.

---

## 🎯 Gameplay Rules & Mechanics

1. **0 Starting Coins for All Player Counts (2–6 Players):**
   - Every player starts with **0 Coins** and **2 Face-Down Cards**, regardless of whether there are 2, 3, 4, 5, or 6 players.
2. **Real Ordered FIFO Court Deck:**
   - The 15-card Court Deck (3× Duke, 3× Assassin, 3× Captain, 3× Ambassador, 3× Contessa) is shuffled only once at initial deal.
   - **Draw from TOP (`deck.shift()`):** New cards (Ambassador exchange, challenge replacement) always come from the top of the stack.
   - **Return to BOTTOM (`deck.push()`):** Cards returned to the deck go straight to the bottom without random reshuffling.
3. **Strict Card Privacy & Quiet Return:**
   - **Proven Claim (No Bluff):** If challenged and telling the truth, your card is revealed to the table in a verification banner, placed at the bottom of the Court Deck, and replaced from the top.
   - **Bluff Caught / Card Lost:** Your lost card is **never shown** to opponents. You quietly select which card to return to the bottom of the Court Deck face-down.
4. **Tabletop Privacy Shield:**
   - Features a **"🙈 Hide / 👁️ Peek My Cards"** toggle so players sitting next to each other at the physical table cannot see your screen.
5. **Zero Backend Required (PeerJS WebRTC Mesh):**
   - Direct phone-to-phone data channels with keep-alive pings and automatic ICE negotiation.
   - Includes **Single-Device Pass & Play** mode for playing on a single shared tablet or laptop.

---

## 🚀 How to Play

### Online / Mobile Tabletop (Multi-Device)
1. **Host:** Open [https://bhaveshbanshiwal.github.io/COUPCX04/](https://bhaveshbanshiwal.github.io/COUPCX04/), enter your name, and click **👑 Host Table**.
2. **Invite:** Share the 5-letter Table Code or click **📋 Copy Link** to send the join link.
3. **Join:** Friends open the link on their phones, enter their name, and click **Join Table**.
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
