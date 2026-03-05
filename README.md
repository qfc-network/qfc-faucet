# QFC Faucet

Testnet faucet for QFC Network. Request free test tokens for development.

**Live site**: https://faucet.testnet.qfc.network

## Development

```bash
# Install dependencies
npm install

# Start dev server (port 3001)
npm run dev

# Build for production
npm run build
```

## Configuration

Create `.env.local`:

```env
RPC_URL=http://127.0.0.1:8545
FAUCET_AMOUNT=10
COOLDOWN_HOURS=24
```

## API

**GET** `/api/faucet` — Faucet info (balance, recent requests)

**POST** `/api/faucet` — Request tokens

```bash
curl -X POST http://localhost:3001/api/faucet \
  -H "Content-Type: application/json" \
  -d '{"address": "0x..."}'
```

## Docker

```bash
docker build -t qfc-faucet .
docker run -p 3001:3000 -e RPC_URL=http://host:8545 qfc-faucet
```

## Tech Stack

- Next.js 14 (App Router)
- TypeScript
- Tailwind CSS
- ethers.js v6

## License

MIT
