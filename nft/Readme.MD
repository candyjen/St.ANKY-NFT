Polygon NFT–Gated Next.js App

A complete starter that lets newbies claim a free Polygon NFT and immediately unlock a gated “secret” page—no prior blockchain experience required!

⸻

🚀 Features
	•	Claim Page (/claim)
Visitors connect a wallet and mint one free NFT (powered by Thirdweb NFT Drop on Polygon).
	•	Secret Page (/secret)
Only holders of that NFT can view your exclusive content.
	•	Beginner-friendly wallet guide
Step-by-step MetaMask setup, Polygon network, MATIC funding, and claim flow.
	•	Next.js + wagmi + RainbowKit + Thirdweb
Modern React stack, on-chain and optional OpenSea off-chain gating.

⸻

📦 Project Structure
## 📦 Project Structure

```plaintext
polygon-nft-gated-app/
├── .env.local
├── hooks/
│   └── useNftGate.js
├── pages/
│   ├── api/
│   │   └── check-access.js      # optional OpenSea API endpoint
│   ├── _app.js
│   ├── claim.js                 # free-mint page
│   ├── index.js                 # landing page
│   └── secret.js                # gated content
├── next.config.js
└── package.json

⸻

🔧 Prerequisites
	1.	Node.js & npm (v16+ recommended)
	2.	A Thirdweb NFT Drop contract on Polygon with a free claim condition
	3.	Git (to clone the repo)
	4.	(Optional) OpenSea API Key for off-chain gating

⸻

⚙️ Environment Variables

Create a .env.local in the project root:

# Public RPC & provider
NEXT_PUBLIC_POLYGON_RPC=https://polygon-rpc.com
NEXT_PUBLIC_ALCHEMY_API_KEY=your-alchemy-api-key

# Thirdweb (for /claim)
NEXT_PUBLIC_THIRDWEB_API_KEY=your-thirdweb-api-key

# OpenSea (optional, for /api/check-access)
OPENSEA_API_KEY=your-opensea-api-key


⸻

📥 Installation

# 1. Clone the repo
git clone https://github.com/your-username/polygon-nft-gated-app.git
cd polygon-nft-gated-app

# 2. Install dependencies
npm install


⸻

🏃 Development

npm run dev

	•	Runs at http://localhost:3000
	•	/claim → test free NFT mint
	•	/secret → verify NFT gating

⸻

📦 Build & Start

npm run build
npm run start

	•	Production build
	•	Serves on http://localhost:3000

⸻

☁️ Deployment

Vercel
	1.	Install & log in:

npm install -g vercel
vercel login


	2.	From project root:

vercel

	•	Choose scope
	•	Link or create a new project
	•	Build command: npm run build
	•	Output directory: (leave blank)

	3.	In Vercel Dashboard ▶️ Settings ▶️ Environment Variables, add the keys from .env.local.
	4.	Deploy:

vercel --prod



Netlify
	1.	Push to GitHub/GitLab/Bitbucket
	2.	In Netlify Dashboard ▶️ New site from Git
	3.	Set:
	•	Build command: npm run build
	•	Publish directory: .next
	4.	Add your .env.local keys under Site settings ▶️ Environment
	5.	Deploy site

⸻

🔐 Wallet Setup (for Complete Newbies)

If you’ve never used crypto or wallets before, follow these steps:

1. Install MetaMask
	•	Desktop: https://metamask.io → Download Chrome/Firefox extension
	•	Mobile: Search “MetaMask” in App Store / Google Play

2. Create & Secure Your Wallet
	1.	Click Create a Wallet, set a strong password.
	2.	Back up your 12-word seed phrase on paper—never share it.
	3.	Confirm the phrase to finish setup.

3. Add Polygon Mainnet
	1.	Open MetaMask → Network dropdown → Add Network
	2.	Enter:

Field	Value
Network Name	Polygon Mainnet
RPC URL	https://polygon-rpc.com
Chain ID	137
Currency Symbol	MATIC
Block Explorer	https://polygonscan.com


	3.	Save. Select Polygon Mainnet from the network list.

4. Acquire MATIC for Gas

Even “free” NFT mints need a tiny gas fee (~0.002 MATIC):
	•	Buy on exchange (Coinbase, Binance) → withdraw MATIC to your MetaMask address.
	•	On-ramp in MetaMask: click Buy → pick Transak/MoonPay.
	•	Bridge ETH→MATIC: https://wallet.polygon.technology/bridge/

⸻

🎁 Claim & Access Flow
	1.	Visit https://<your-app>/claim
	2.	Connect Wallet (MetaMask) on Polygon
	3.	Click Claim Your NFT → confirm in MetaMask
	4.	Automatically redirects to /secret
	5.	/secret verifies on-chain ownership and unlocks your content

⸻

🔄 Optional: Off-Chain Gating (OpenSea API)

Use pages/api/check-access.js to ask OpenSea who owns your token instead of useNftGate. Swap the gating logic in secret.js to fetch /api/check-access?owner=<address> and gate on the JSON response.

⸻

🛠️ Customization
	•	Contract Address: Replace "0xYourDropContractHere" in /claim.js & /secret.js
	•	Styling: Swap inline styles for your CSS framework (Tailwind, Chakra, etc.)
	•	Content: Edit index.js, secret.js with your branding and secret copy

⸻

📖 References
	•	Next.js: https://nextjs.org/docs
	•	wagmi: https://wagmi.sh/
	•	RainbowKit: https://www.rainbowkit.com/docs
	•	ethers.js: https://docs.ethers.io/
	•	Thirdweb NFT Drop: https://portal.thirdweb.com/

⸻

You’re now ready to onboard complete newcomers—no wallet, no problem—straight into minting and unlocking your exclusive content. Enjoy!
