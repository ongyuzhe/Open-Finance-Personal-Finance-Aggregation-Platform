# MyDuit - Open Finance Personal Finance Aggregation Platform

<div align="center">

![MyDuit Logo](https://img.shields.io/badge/MyDuit-Personal_Finance-6366f1?style=for-the-badge)

**A modern, intelligent personal finance aggregation platform designed for young Malaysian professionals**

[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)](https://www.prisma.io/)
[![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)

[Features](#-key-features) • [Demo](#-demo) • [Architecture](#-architecture) • [Quick Start](#-quick-start) • [API](#-api-documentation) • [Team](#-team)

</div>

**Live App:** http://161.97.158.103:3000/

**Pitch Video:** https://drive.google.com/file/d/1g65NWjcp9JYqNcjbjb52eNzT6Q0e49x7/view?usp=sharing

**Product Video:** https://streamable.com/bw8rjl

<img width="1920" height="1037" alt="image" src="https://github.com/user-attachments/assets/ea3759f8-59b4-4435-9f26-45882b131c15" />


## Team

| Name       | Github                                       |
| ---------- | -------------------------------------------- |
| Leo        | [@\_leo247]()      |
| Jeet       | [@jeet\_\_](https://github.com/Jeet2216)     |
| Ong        | [@ong9255](https://github.com/ongyuzhe)      |
| Sterbweise | [@sterbweise](https://github.com/sterbweise) |

## Table of Contents

- [Overview](#-overview)
- [The Problem](#-the-problem)
- [Our Solution](#-our-solution)
- [Key Features](#-key-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Virtual Bank API Integration](#-virtual-bank-api-integration)
- [Quick Start](#-quick-start)
- [API Documentation](#-api-documentation)
- [Team](#-team)
- [Deployment](#-deployment)
- [License](#-license)

---

## Overview

**MyDuit** is an open finance personal finance aggregation platform built specifically for young Malaysian professionals (ages 18-30) who manage multiple financial accounts across traditional banks and modern e-wallets.

In Malaysia's rapidly evolving digital economy, where e-wallets like GrabPay, Touch 'n Go, and ShopeePay are as common as traditional bank accounts, **MyDuit** provides a unified dashboard to track, analyze, and optimize personal spending habits with AI-powered behavioral nudges and sustainability insights.

### Demo

- **Live Demo**: [Coming Soon]
- **Frontend**: Responsive Next.js dashboard with real-time data visualization
- **Backend API**: RESTful API with clean architecture principles

---

## The Problem

Modern Malaysians face several challenges managing their finances:

1. **Fragmented Financial Data**: Money spread across multiple banks (Maybank, RHB, CIMB) and e-wallets (GrabPay, Touch 'n Go, ShopeePay)
2. **Lack of Unified View**: No single platform to see complete financial picture
3. **Poor Spending Insights**: Difficult to track spending patterns across multiple platforms
4. **Budget Overruns**: Easy to overspend without consolidated oversight
5. **Sustainability Concerns**: No way to track environmental impact of spending
6. **Multi-Currency Confusion**: Managing MYR, USD, SGD across different accounts

## Our Solution

**MyDuit** solves these problems by providing:

### Unified Financial Dashboard

- Aggregate transactions from **multiple banks** and **e-wallets** in one place
- Real-time synchronization with financial institutions
- Support for Maybank, RHB Bank, Touch 'n Go, Grab Wallet, Shopee Wallet

### Intelligent Analytics

- **Spending Trends**: Visualize 6-month spending history with interactive charts
- **Category Breakdown**: See where your money goes (Food, Transport, Shopping, etc.)
- **Monthly Reports**: Detailed income, expenses, and savings rate analysis
- **Account Distribution**: Understand your wealth distribution across accounts

### Nudges

We analyzes your spending patterns and provides personalized insights:

- "Your food spending is up 31% this month"
- "You could save RM300/month by cooking at home 3 times per week"
- "You're using cash-back opportunities effectively!"
- "Transportation costs are high - consider e-wallet promotions"

### Multi-Currency Support

- Default currency: **Malaysian Ringgit (MYR)**
- Support for USD, SGD, EUR, GBP, JPY
- Real-time exchange rates
- Automatic currency conversion for unified reporting

## Key Features

### For Users

✅ **Unified Transaction Dashboard**

- View all transactions from multiple accounts in one place
- Filter by date, category, account, or merchant
- Search functionality for quick lookup

✅ **Smart Spending Analysis**

- Monthly/weekly spending summaries
- Category-wise breakdown with percentages
- Trend analysis with visual charts
- Comparison with previous periods

✅ **Intelligent Insights**

- Budget warnings and recommendations
- Recurring payment detection
- Savings opportunities identification

✅ **Sustainability Tracking**

- Eco-friendly transaction tagging
- Carbon footprint estimation
- Environmental impact reports
- Green spending challenges

✅ **Multi-Account Management**

- Real-time balance synchronization
- Account-wise performance metrics
- Wealth distribution visualization

## Architecture

MyDuit follows **Clean Architecture** (Hexagonal/Onion Architecture) principles, ensuring:

- **Independence**: Business logic independent of frameworks, UI, and databases
- **Testability**: Easy to test core business logic
- **Flexibility**: Easy to swap implementations
- **Maintainability**: Clear boundaries between layers

### Architecture Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                         Frontend                            │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Next.js 14 App Router + React Components           │    │
│  │  • Dashboard  • Charts  • Settings  • Transactions  │    │
│  └─────────────────────────────────────────────────────┘    │
└────────────────────────┬────────────────────────────────────┘
                         │ HTTP/REST
                         ▼
┌─────────────────────────────────────────────────────────────┐
│                    Backend API Layer                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │         Express.js REST Controllers                 │    │
│  │  /api/v1/dashboard  /api/v1/transactions  etc.      │    │
│  └─────────────────────────────────────────────────────┘    │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│                  Application Layer                          │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Use Cases / Services                                │   │
│  │  • DashboardService     • NudgesEngine               │   │
│  │  • TransactionService   • SustainabilityService      │   │
│  │  • CurrencyService      • AggregationService         │   │
│  └──────────────────────────────────────────────────────┘   │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│                      Domain Layer                           │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Business Entities & Value Objects                   │   │
│  │  • User  • Account  • Transaction  • Nudge           │   │
│  │  • Money (Value Object)  • DateRange (Value Object)  │   │
│  └──────────────────────────────────────────────────────┘   │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Repository Interfaces (Ports)                       │   │
│  │  • IUserRepository  • ITransactionRepository         │   │
│  └──────────────────────────────────────────────────────┘   │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│                 Infrastructure Layer                        │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Persistence (Adapters)                              │   │
│  │  • Prisma ORM  • SQLite/PostgreSQL                   │   │
│  └──────────────────────────────────────────────────────┘   │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  External APIs                                       │   │
│  │  • Virtual Bank API  • Exchange Rate API             │   │
│  └──────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

### Project Structure

```
myduit/
├── backend/
│   ├── src/
│   │   ├── domain/                 # Core Business Logic
│   │   │   ├── entities/           # Business entities
│   │   │   │   ├── User.ts
│   │   │   │   ├── Account.ts
│   │   │   │   ├── Transaction.ts
│   │   │   │   └── Nudge.ts
│   │   │   ├── value-objects/      # Immutable value objects
│   │   │   │   ├── Money.ts
│   │   │   │   └── DateRange.ts
│   │   │   └── repositories/       # Repository interfaces (Ports)
│   │   │
│   │   ├── application/            # Use Cases & Services
│   │   │   └── services/
│   │   │       ├── DashboardService.ts
│   │   │       ├── TransactionAggregationService.ts
│   │   │       ├── NudgesEngine.ts
│   │   │       ├── CurrencyService.ts
│   │   │       └── SustainabilityService.ts
│   │   │
│   │   ├── infrastructure/         # External Systems
│   │   │   ├── persistence/        # Database implementations
│   │   │   │   └── repositories/
│   │   │   │       └── PrismaTransactionRepository.ts
│   │   │   └── external/           # External APIs
│   │   │       └── virtual-bank-api/
│   │   │
│   │   ├── api/                    # HTTP Interface
│   │   │   ├── controllers/        # REST controllers
│   │   │   ├── routes/             # Express routes
│   │   │   └── middleware/         # Express middleware
│   │   │
│   │   └── shared/                 # Utilities
│   │       └── utils/
│   │
│   └── prisma/
│       ├── schema.prisma           # Database schema
│       ├── migrations/             # Database migrations
│       └── seed.ts                 # Sample data seeder
│
└── frontend/
    ├── src/
    │   ├── app/                    # Next.js App Router
    │   │   ├── page.tsx            # Dashboard page
    │   │   ├── accounts/           # Accounts page
    │   │   ├── transactions/       # Transactions page
    │   │   └── settings/           # Settings page
    │   │
    │   ├── components/             # React Components
    │   │   ├── DashboardOverview.tsx
    │   │   ├── SpendingChart.tsx
    │   │   ├── CategoryBreakdown.tsx
    │   │   ├── SmartNudgesWidget.tsx
    │   │   └── TransactionList.tsx
    │   │
    │   └── contexts/               # React Contexts
    │       └── SettingsContext.tsx # User preferences
    │
    └── public/                     # Static assets
```

---

## Tech Stack

### Backend

| Technology     | Purpose              | Why We Chose It                         |
| -------------- | -------------------- | --------------------------------------- |
| **Node.js**    | Runtime environment  | JavaScript everywhere, great ecosystem  |
| **TypeScript** | Programming language | Type safety, better DX, fewer bugs      |
| **Express.js** | Web framework        | Minimal, flexible, industry standard    |
| **Prisma**     | ORM                  | Type-safe database access, migrations   |
| **SQLite**     | Database (dev)       | Zero configuration, perfect for demos   |
| **PostgreSQL** | Database (prod)      | Robust, scalable, production-ready      |
| **tsyringe**   | Dependency Injection | Clean architecture, testability         |
| **Zod**        | Validation           | Type-safe schema validation             |
| **Winston**    | Logging              | Structured logging, multiple transports |
| **date-fns**   | Date utilities       | Lightweight, immutable, tree-shakeable  |

### Frontend

| Technology        | Purpose            | Why We Chose It                 |
| ----------------- | ------------------ | ------------------------------- |
| **Next.js 14**    | React framework    | App Router, SSR, excellent DX   |
| **React 18**      | UI library         | Component-based, huge ecosystem |
| **TypeScript**    | Type safety        | Same language as backend        |
| **Chart.js**      | Data visualization | Beautiful charts, easy to use   |
| **Lucide React**  | Icons              | Modern, consistent icon set     |
| **CSS Variables** | Styling            | Dynamic theming, no build step  |

### DevOps & Tools

| Tool       | Purpose            |
| ---------- | ------------------ |
| **Git**    | Version control    |
| **npm**    | Package management |
| **PM2**    | Process management |
| **Nginx**  | Reverse proxy      |
| **Docker** | Containerization   |

---

## Virtual Bank API Integration

To simulate real banking APIs and demonstrate our platform's capabilities, we integrate with the **Virtual Bank API**, a hackathon-provided banking simulation service.

### API Details

- **Base URL**: `https://161.97.158.103:8030`
- **Documentation**: [https://161.97.158.103:8030/swagger/](https://161.97.158.103:8030/swagger/)
- **Type**: RESTful API with Swagger/OpenAPI documentation

### Available Endpoints

The Virtual Bank API provides realistic banking operations:

| Endpoint                 | Method | Description             |
| ------------------------ | ------ | ----------------------- |
| `/api/auth/login`        | POST   | Authenticate user       |
| `/api/accounts`          | GET    | List user accounts      |
| `/api/accounts/{id}`     | GET    | Get account details     |
| `/api/transactions`      | GET    | List transactions       |
| `/api/transactions/{id}` | GET    | Get transaction details |
| `/api/balance`           | GET    | Get current balance     |

### Integration Implementation

We auto-generate a TypeScript client from the OpenAPI specification:

```bash
# Generate TypeScript client
npm run swagger:generate
```

This creates type-safe API client code in:

```
backend/src/infrastructure/external/virtual-bank-api/
```

### Usage Example

```typescript
import { VirtualBankApiClient } from "@/infrastructure/external/virtual-bank-api";

// Initialize client
const bankClient = new VirtualBankApiClient({
  baseURL: "https://161.97.158.103:8030",
  timeout: 10000,
});

// Authenticate
const authToken = await bankClient.login({
  username: "user@example.com",
  password: "secure_password",
});

// Fetch accounts
const accounts = await bankClient.getAccounts(authToken);

// Fetch transactions
const transactions = await bankClient.getTransactions(authToken, accountId, {
  startDate: "2024-01-01",
  endDate: "2024-12-31",
});
```

### Security Considerations

- API credentials stored in environment variables
- Tokens refreshed automatically
- HTTPS-only communication
- Rate limiting implemented
- Error handling for API failures

### Integration Benefits

1. **Realistic Demo**: Simulate real banking operations
2. **Multiple Institutions**: Support various bank types
3. **Live Data**: Real-time transaction sync
4. **Extensible**: Easy to add more providers
5. **Standardized**: OpenAPI specification ensures consistency

---

## Quick Start

### Prerequisites

Before you begin, ensure you have:

- **Node.js** 18+ (20+ recommended) - [Download](https://nodejs.org/)
- **npm** or **yarn** - Comes with Node.js
- **Git** - [Download](https://git-scm.com/)
- **Code Editor** - VS Code recommended

### Installation

#### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/myduit.git
cd myduit
```

#### 2️⃣ Setup Backend

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create environment file
cp .env.example .env

# Generate Prisma client
npx prisma generate

# Run database migrations
npx prisma migrate dev

# Seed database with sample data
npm run db:seed

# Start development server
npm run dev
```

Backend should now be running at **http://localhost:3001**

#### 3️⃣ Setup Frontend

Open a new terminal:

```bash
# Navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Create environment file (optional for development)
cp .env.example .env.local

# Start development server
npm run dev
```

Frontend should now be running at **http://localhost:3000**

### Access the Application

- **Frontend Dashboard**: [http://localhost:3000](http://localhost:3000)
- **Backend API**: [http://localhost:3001/api/v1](http://localhost:3001/api/v1)
- **Health Check**: [http://localhost:3001/health](http://localhost:3001/health)

### Sample Data

The seeded database includes:

- **1 demo user**: `demo@myduit.my`
- **5 accounts**: Maybank, RHB Bank, Touch 'n Go, Grab Wallet, Shopee Wallet
- **328 transactions** across 6 months (June - December 2024)
- **Categorized spending**: Food, Transport, Shopping, Utilities, etc.
- **Realistic Malaysian amounts** in MYR currency

---

## 📚 API Documentation

### Dashboard Endpoints

#### Get Complete Dashboard

```http
GET /api/v1/dashboard
```

**Response:**

```json
{
  "success": true,
  "data": {
    "overview": {
      "totalBalance": { "amount": 16850, "currency": "MYR" },
      "monthlyIncome": { "amount": 8700, "currency": "MYR" },
      "monthlyExpenses": { "amount": 5113.29, "currency": "MYR" },
      "savingsRate": 41.2
    },
    "accounts": [...],
    "spendingTrends": {
      "sixMonthHistory": [...]
    },
    "categories": [...],
    "recentTransactions": [...]
  }
}
```

#### Get Spending Trends

```http
GET /api/v1/dashboard/trends
```

#### Get Category Breakdown

```http
GET /api/v1/dashboard/categories
```

### Transaction Endpoints

#### List Transactions

```http
GET /api/v1/transactions?startDate=2024-01-01&endDate=2024-12-31&category=FOOD_DINING
```

#### Create Transaction

```http
POST /api/v1/transactions
Content-Type: application/json

{
  "accountId": "account-uuid",
  "amount": 45.50,
  "currency": "MYR",
  "type": "EXPENSE",
  "category": "FOOD_DINING",
  "merchantName": "Nasi Lemak Corner",
  "description": "Lunch",
  "transactionDate": "2024-12-06T12:30:00Z"
}
```

### Account Endpoints

#### List Accounts

```http
GET /api/v1/accounts
```

#### Get Account Details

```http
GET /api/v1/accounts/:id
```

For complete API documentation, see [API.md](./API.md)

---

## Deployment

### For Hackathons (Quick Deploy)

See **[HACKATHON_DEPLOY.md](./HACKATHON_DEPLOY.md)** for step-by-step deployment instructions.

**Quick Deploy:**

```bash
# Run automated deployment script
./deploy-hackathon.sh
```

### Production Deployment

**Option 1: PM2 (Process Manager)**

```bash
# Backend
cd backend
npm install
npm run build
pm2 start dist/index.js --name myduit-backend

# Frontend
cd frontend
npm install
npm run build
pm2 start npm --name myduit-frontend -- start
```

**Option 2: Docker**

```bash
# Build and run all services
docker-compose up -d --build
```

For detailed production deployment guide, see **[README_DEPLOY.md](./README_DEPLOY.md)**

---

## Testing

```bash
# Run all tests
npm test

# Run tests with coverage
npm run test:coverage

# Run tests in watch mode
npm run test:watch
```

---

## Security

- **Environment Variables**: Sensitive data in `.env` files (gitignored)
- **Input Validation**: Zod schemas for all inputs
- **SQL Injection**: Prisma ORM prevents SQL injection
- **XSS Protection**: React automatically escapes output
- **CORS**: Configured for specific origins only
- **Rate Limiting**: Implemented on API endpoints
- **JWT Authentication**: Ready for implementation

## Acknowledgments

- **Virtual Bank API** - For providing banking simulation services
- **Next.js Team** - For the amazing React framework
- **Prisma Team** - For the excellent ORM
- **Chart.js** - For beautiful data visualizations
- **Hackathon Organizers** - For the opportunity to build this

---

## 📞 Contact & Support

- **Issues**: [GitHub Issues](https://github.com/your-username/myduit/issues)
- **Discord**:
  - @\_leo247
  - @jeet\_\_
  - @ong9255
  - @sterbweise

---

<div align="center">

**Built with ❤️ in Malaysia for Cursor x Anthropic Hackaton**

Made by Leo, Jeet, Ong, and Sterbweise

⭐ Star us on GitHub if you find this project useful!

</div>





