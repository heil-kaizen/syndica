# HAWKINS (Wallet Gazette)

![HAWKINS](https://github.com/heil-kaizen/syndica/blob/main/hawkins.webp?raw=true)

HAWKINS is a classified investigation tool designed to uncover hidden alpha on the Solana blockchain. By analyzing overlapping holders across multiple tokens, investigators can track repeat whales, expose sybil clusters, and find the wallets that matter before the crowd does.

## Features

* **Token Gazette (Data Ingestion):** Fetch real-time market cap, price, and top holder data for any Solana token using the Solana Tracker API.
* **Overlap Ledger:** Automatically cross-reference holders across multiple scanned tokens to identify wallets that are early or heavily invested in your specific token combinations.
* **Sybil Cluster Detection:** Advanced grouping algorithm that identifies suspected sybil wallets—entities splitting funds across multiple addresses holding the exact same tokens with similar portfolio percentages (within a 20% tolerance).
* **Wallet Scoring (Beta):** A proprietary scoring system that ranks overlapping wallets based on their holding patterns and overlap frequency.
* **Insider Dossier (Profile Management):** Organize your investigations into separate profiles/workspaces. Keep your data segregated for different narratives or sectors.
* **Permanent Snapshots:** Token data is saved to your dossier, creating an immutable record of holders at the time of your scan.
* **Newspaper Aesthetic:** A unique, immersive "Gazette" UI featuring classic typography (Newsreader, Playfair Display) and a classified dossier layout.

## System Architecture

```text
+-------------------+       +-------------------+       +-------------------+
|                   |       |                   |       |                   |
| Solana Tracker API+------>+      HAWKINS      +<------+ Solana Tracker API|
|  (Top Holders)    |       |   (Core Engine)   |       | (MCAP & Price)    |
|                   |       |                   |       |                   |
+-------------------+       +---------+---------+       +-------------------+
                                      |
                                      v
                            +---------+---------+
                            |                   |
                            | Firebase Database |
                            | (Permanent Store) |
                            |                   |
                            +-------------------+
```

## Tech Stack

* **Frontend:** React 18, Vite, Tailwind CSS
* **Backend/Auth:** Firebase (Firestore, Google Authentication)
* **Data Provider:** Solana Tracker API
* **Styling:** Custom newspaper theme with carefully selected typography

## Setup & Deployment

1. Clone the repository.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Set up your environment variables (see `.env.example`):
   * `VITE_SOLANA_TRACKER_API_KEY`: Your API key from Solana Tracker.
4. Run the development server:
   ```bash
   npm run dev
   ```

## Disclaimer

The data presented in this dossier is derived from immutable ledger records. We hold no liability for market volatility. Professional discretion is advised before shadowing suspected insider activity.
