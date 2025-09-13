# 🚀 Uptime Monitoring Service

A modern, scalable uptime monitoring service built with Next.js and Turborepo. Monitor your websites, APIs, and services with real-time alerts and beautiful status pages.

## ✨ Features
- 🔍 Multi-Protocol Monitoring - Support for HTTP/HTTPS, TCP, Ping, DNS, and more
- 📊 Real-time Dashboard - Beautiful, responsive dashboard for monitoring all your services
- 🔔 Instant Alerts - Get notified immediately when services go down via multiple channels
- 📈 Performance Metrics - Track response times, uptime percentages, and historical data
- 🎨 Customizable Status Pages - Public status pages for your users
- 🚀 High Performance - Built with Turborepo for optimized builds and development
- 🔒 Secure by Default - TypeScript for type safety and best security practices
- 📱 Mobile Responsive - Works seamlessly on all devices

## 🏗️ Architecture
This project is structured as a monorepo using Turborepo, containing:

### Apps and Packages
- **apps/web** - Main Next.js application for the monitoring dashboard
- **apps/docs** - Documentation site built with Next.js
- **packages/ui** - Shared React component library
- **packages/eslint-config** - Shared ESLint configurations
- **packages/typescript-config** - Shared TypeScript configurations

## 🚀 Quick Start

### Prerequisites
- Node.js 18.x or higher
- npm, yarn, or pnpm package manager
- Git

### Installation
Clone the repository:
```
git clone https://github.com/vidhiagg2005/uptime.git
cd uptime
```

Install dependencies:
```
npm install
# or
yarn install
# or
pnpm install
```

Set up environment variables:
```
cp .env.example .env.local
```

Edit `.env.local` with your configuration:
```env
DATABASE_URL=your_database_url
NEXT_PUBLIC_API_URL=http://localhost:3000
SECRET_KEY=your_secret_key
# Add other required environment variables
```

Run the development server:
```
npm run dev
# or
yarn dev
# or
pnpm dev
```

The application will be available at:
- Web app: http://localhost:3000
- Documentation: http://localhost:3001

## 🛠️ Development

### Available Scripts
```
# Development
npm run dev          # Start all apps in development mode
npm run dev:web      # Start only the web app
npm run dev:docs     # Start only the docs app

# Building
npm run build        # Build all apps and packages
npm run build:web    # Build only the web app
npm run build:docs   # Build only the docs app

# Testing
npm run test         # Run all tests
npm run test:watch   # Run tests in watch mode

# Linting & Formatting
npm run lint         # Lint all code
npm run format       # Format all code with Prettier
npm run type-check   # Run TypeScript type checking
```

### Using Filters
You can use Turborepo filters to work with specific packages:
```
# Build a specific package
turbo build --filter=web

# Run development for a specific app
turbo dev --filter=docs

# Test a specific package
turbo test --filter=@repo/ui
```

## 📦 Project Structure
```
uptime/
├── apps/
│   ├── web/                # Main monitoring dashboard
│   │   ├── app/            # Next.js app directory
│   │   ├── components/     # React components
│   │   ├── lib/            # Utility functions
│   │   └── public/         # Static assets
│   └── docs/               # Documentation site
├── packages/
│   ├── ui/                 # Shared component library
│   ├── eslint-config/      # ESLint configurations
│   └── typescript-config/  # TypeScript configurations
├── turbo.json              # Turborepo configuration
├── package.json            # Root package.json
└── README.md               # This file
```

## 🔧 Configuration

### Monitor Configuration
```javascript
{
  "name": "API Server",
  "url": "https://api.example.com",
  "type": "http",
  "interval": 60,
  "timeout": 30,
  "alerts": {
    "email": ["admin@example.com"],
    "webhook": "https://hooks.slack.com/services/..."
  }
}
```

### Status Page Customization
```javascript
{
  "title": "Service Status",
  "description": "Current status of our services",
  "theme": {
    "primaryColor": "#0070f3",
    "darkMode": true
  },
  "services": ["api", "website", "database"]
}
```

## 🚀 Deployment

### Deploy to Vercel
The easiest way to deploy this application is using Vercel.

### Manual Deployment
```
npm run build
export NODE_ENV=production
export DATABASE_URL=your_production_database
npm run start
```

### Docker Deployment
```dockerfile
# Build the Docker image
docker build -t uptime-monitor .

# Run the container
docker run -p 3000:3000 --env-file .env.production uptime-monitor
```

## 🏎️ Performance
Enable Turborepo remote caching for faster builds:
```
npx turbo login
npx turbo link
```

## 🧪 Testing
```
npm run test
npm run test:coverage
npm run test:watch
npm run test:e2e
```

## 📊 Monitoring Features

### Supported Monitor Types
- HTTP/HTTPS
- TCP Port
- Ping
- DNS
- Keyword
- JSON Path
- Certificate monitoring

### Alert Channels
- Email
- SMS (via Twilio)
- Slack
- Discord
- Custom webhooks
- PagerDuty

## 🤝 Contributing
Contributions are welcome! Please fork the repo and open a PR.

## 📝 API Documentation

### REST API Endpoints
```
GET    /api/monitors
POST   /api/monitors
GET    /api/monitors/:id
PUT    /api/monitors/:id
DELETE /api/monitors/:id
```

### WebSocket Events
```javascript
const ws = new WebSocket('wss://your-domain.com/ws');
ws.on('monitor:update', (data) => console.log(data));
ws.on('alert:triggered', (data) => console.log(data));
```

## 🙏 Acknowledgments
- Built with Next.js and Turborepo
- UI components from shadcn/ui
- Icons from Lucide

---

<p align="center">Made with ❤️ by <a href="https://github.com/vidhiagg2005">Vidhi Aggarwal</a></p>
<p align="center"><a href="https://github.com/vidhiagg2005/uptime/stargazers">⭐ Star us on GitHub</a></p>
