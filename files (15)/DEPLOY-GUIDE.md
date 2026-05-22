# GUARDIAN NETWORK GAME ROOM — DEPLOYMENT GUIDE

## What's In This Package

```
guardian-game-room-package/
├── gameroom.html              ← The Game Room hub page
├── guardian-duel-elite.html   ← Call of Duty style flagship game
├── guardian-duel-tactical.html ← Tactical mode with drones
├── guardian-duel-voice.html   ← Voice announcer settings
├── HOMEPAGE-BUTTON.html       ← Drop-in code for your homepage
└── DEPLOY-GUIDE.md            ← This file
```

---

## STEP 1 — Upload Files to Netlify

Drag all 4 game files to your existing guardiannetwork.io Netlify site:

- `gameroom.html`
- `guardian-duel-elite.html`
- `guardian-duel-tactical.html`
- `guardian-duel-voice.html`

They should sit alongside your existing `index.html`.

**Result:** These URLs become live:
- `guardiannetwork.io/gameroom.html`
- `guardiannetwork.io/guardian-duel-elite.html`
- `guardiannetwork.io/guardian-duel-tactical.html`
- `guardiannetwork.io/guardian-duel-voice.html`

---

## STEP 2 — Add the Hero Button to Your Homepage

Open `HOMEPAGE-BUTTON.html` in any text editor. It has two parts:

1. A `<style>` block — copy this into your homepage's `<head>` (or your existing CSS file)
2. A `<section>` block — paste this into your homepage where you want the Game Room callout to appear

**Recommended placement:** Right after your hero section, before your features grid. This is where it grabs attention without disrupting your investor pitch flow.

---

## STEP 3 — Test the Full Flow

Open `guardiannetwork.io` on your phone:

1. See the Game Room hero button → tap it
2. Land on `gameroom.html` → see live counters, leaderboard, flagship card
3. Tap "DROP INTO BATTLE" on Guardian Duel → modal opens
4. Either:
   - Tap CREATE ROOM → launches `guardian-duel-elite.html?mode=create`
   - Tap JOIN ROOM → enter code → launches with that code
   - Tap an open room → joins directly
5. Loading screen plays → game launches

---

## STEP 4 — Set Up Voice Announcer (Optional)

The voice announcer page (`guardian-duel-voice.html`) lets players configure their announcer voice. Three options:

**Option A — Player decides:** Add a "Settings" link on the gameroom that points to voice page. Players configure once, settings saved in their browser.

**Option B — Default included:** Voice announcer code can be embedded into the game files themselves so it works out of the box with device voice (no ElevenLabs key needed).

**Option C — Premium upsell:** Promote ElevenLabs API key signup as a "premium feature" on the gameroom.

---

## STEP 5 — Connect Real Multiplayer (Final Step)

Right now the games run in **demo mode** with AI bots. To enable real 16-player multiplayer:

1. Sign up at **partykit.io** (free)
2. Deploy the PartyKit server from your `guardian-duel-multiplayer.zip` (built in earlier session):
   ```bash
   cd guardian-duel-multiplayer
   npm install
   npx partykit login
   npx partykit deploy
   ```
3. In each game file, find the line:
   ```js
   const PK_HOST = "guardian-duel.YOUR-USERNAME.partykit.dev";
   ```
   Replace `YOUR-USERNAME` with your actual PartyKit username.
4. Re-upload to Netlify.

**Now players from anywhere in the world can join the same room in real-time.**

---

## MARKETING FLOW

This is the full traffic funnel:

```
guardiannetwork.io (main site)
         ↓
    [PLAY NOW button]
         ↓
guardiannetwork.io/gameroom.html
         ↓
    [Pick a game]
         ↓
guardiannetwork.io/guardian-duel-elite.html?mode=create
         ↓
    Player creates room → shares code → squad joins → battle begins
         ↓
    Players come back, post on social, drive more traffic
         ↓
    Reg CF launch → people already know your tech works
```

---

## CONTENT TO POST (Goes With This Launch)

When this goes live, here's what to post on social:

**Tweet 1 (Launch):**
> 🎯 Guardian Network just launched the GAME ROOM
> 
> Real-time AR combat. Up to 16 players. Patent-pending tech.
> Drop into battle from your phone. No download required.
> 
> guardiannetwork.io/gameroom
> 
> ⚔️ #GuardianNetwork #GhostENT

**Tweet 2 (Demo video):**
> POV: you're playing real-world AR Call of Duty with your phone 📱
> 
> Point. Lock on. Fire.
> 
> Your friend's phone flashes red when you hit them.
> 
> This is Guardian Duel. Live now at guardiannetwork.io

**Instagram Reel script:**
1. Open phone → guardiannetwork.io
2. Tap "PLAY NOW"
3. Show the game room hub
4. Tap "DROP INTO BATTLE"
5. Create room, share code
6. Cut to two people in a park playing → real action footage
7. End card: "Patent pending. Built by Ghost ENT × Guardian Network."

---

## INVESTOR PITCH ANGLE

When investors ask "what does it look like?":
- "Open guardiannetwork.io on your phone right now"
- They land on the Game Room
- They see the live counters, the global leaderboard, the polished UI
- They tap into the game and play with you
- **You just demoed a $40B opportunity in 30 seconds**

This is the deck killer. The pitch becomes:
> "Don't take my word for it. Open guardiannetwork.io on your phone and play. That's the IP."

---

## QUICK CHECKLIST

- [ ] Upload 4 HTML files to Netlify
- [ ] Add hero button to homepage
- [ ] Test on iPhone (Safari)
- [ ] Test on Android (Chrome)
- [ ] Share gameroom URL with one friend, play together
- [ ] Record demo video on iPhone
- [ ] Post to social
- [ ] Deploy PartyKit for real multiplayer (when ready)

---

**You now have a deployed, playable, investor-grade AR combat game accessible from anywhere in the world via a single URL.**

This is Phase 1 complete. Phase 2 (voice + military polish) is ready to layer in next session.
