# Suimming Frontend

A location-based NFT collection game built on Sui blockchain. Players collect letters at physical locations and mint Sentence NFTs using an interactive 3D map interface.

## Features

- **Interactive 3D Map**: Google Maps with Three.js WebGL overlays
- **Geolocation Gaming**: Collect letters at real-world checkpoints
- **NFT Marketplace**: Trade Sentence NFTs with other players
- **Progressive Web App**: Mobile-optimized with offline capabilities
- **Sui Blockchain Integration**: Secure wallet connection and transactions
- **Real-time 3D Models**: GLTF models for user avatars and checkpoint markers

## Tech Stack

- **Framework**: Next.js 15 with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS v4
- **3D Graphics**: Three.js with Google Maps integration
- **Blockchain**: Sui SDK (@mysten/dapp-kit)
- **Maps**: Google Maps API with ThreeJSOverlayView
- **Package Manager**: pnpm

## Prerequisites

- Node.js 18+ and pnpm
- Google Maps API key with Maps JavaScript API enabled
- Sui wallet (Sui Wallet, Martian, or use zkLogin with Google)

## Environment Setup

Create a `.env.local` file:

```env
NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=your_google_maps_api_key
NEXT_PUBLIC_ENOKI_API_KEY=your_enoki_api_key
NEXT_PUBLIC_GOOGLE_CLIENT_ID=your_google_oauth_client_id
NEXT_PUBLIC_SUIMMING_PACKAGE_ID=0xYOUR_DEPLOYED_CONTRACT_ID
NEXT_PUBLIC_MARKETPLACE_ID=0xYOUR_MARKETPLACE_CONTRACT_ID
```

## Installation

```bash
# Install dependencies
pnpm install

# Start development server
pnpm dev

# Open http://localhost:3000
```

## Development Commands

```bash
pnpm dev      # Start development server
pnpm build    # Build for production
pnpm start    # Start production server
pnpm lint     # Run ESLint
```

## Project Structure

```
src/
├── app/                    # Next.js App Router
│   ├── components/        # React components
│   │   ├── WebGLMapOverlay.tsx    # Main 3D map component
│   │   ├── ConnectWallet.tsx      # Wallet connection
│   │   └── Toaster.tsx           # Notification system
│   ├── map/              # Interactive map page
│   ├── market/           # NFT marketplace
│   ├── my/               # User profile and inventory
│   └── signup/           # User registration
├── web3/                 # Blockchain integration
│   ├── kioskClient.ts    # NFT marketplace client
│   ├── walrusClient.ts   # Decentralized storage
│   └── sealClient.ts     # Secrets management
├── hooks/                # React hooks
├── utils/                # Utility functions
└── types/                # TypeScript definitions
```

## Key Features

### 3D Map Interface
- Real-time user location tracking with GPS
- Interactive checkpoint markers using GLTF models
- Navigation mode with automatic camera following
- Geofencing for proximity-based interactions

### Blockchain Integration
- Sui wallet connection with multiple wallet support
- zkLogin integration for Google OAuth authentication
- Smart contract interactions for letter collection
- NFT minting and marketplace transactions

### Game Mechanics
- **Letter Collection**: Visit physical locations to collect random letters
- **Sentence NFTs**: Combine collected letters to create and mint NFTs
- **Marketplace**: Trade NFTs with other players
- **Geofencing**: Automatic detection when entering checkpoint areas

### Mobile Optimization
- Progressive Web App (PWA) with installable manifest
- Touch-friendly map controls and UI
- Optimized WebGL performance for mobile devices
- Geolocation permissions and background tracking

## API Integration

### Google Maps
- Maps JavaScript API for base map rendering
- Places API for location services
- Geolocation API for user positioning

### Sui Blockchain
- Transaction building and execution
- Object querying and state management
- Event listening for real-time updates

## Development Guidelines

### Code Conventions
- Use absolute imports: `@/app/components/` not `./components/`
- Follow existing component patterns and naming
- TypeScript strict mode - all files must have proper types
- Tailwind CSS for all styling with dinosaur theme colors

### Theme Colors
- Background: `#F5F5DC` (beige)
- Primary: `#DEB887` (tan)
- Secondary: `#8B4513` (brown)
- Accent: `#20B2AA` (teal)

### Common Issues

**WebGL Models**: GLTF files must be in `/public/` directory with proper transformations
**Location Permissions**: HTTPS required for geolocation in production
**Wallet Connection**: Clear browser storage if connection issues occur

## Deployment

### Vercel (Recommended)
```bash
# Build and deploy
pnpm build
# Deploy to Vercel
```

### Environment Variables for Production
- Add all `.env.local` variables to Vercel dashboard
- Ensure Google Maps API key is restricted to your domain
- Configure HTTPS for PWA features and geolocation

## Contributing

1. Check existing patterns in similar components
2. Verify required dependencies in package.json
3. Test wallet connections and blockchain interactions
4. Verify mobile responsiveness and PWA functionality
5. Run `pnpm lint` and `pnpm build` before commits

## License

MIT License - see LICENSE file for details
