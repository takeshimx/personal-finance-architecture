# Personal Finance Management App

A comprehensive full-stack financial management application built with modern web technologies. This personal finance tracker includes expense management, investment tracking, asset management, and advanced authentication with real-time data visualization.

## 🚀 Tech Stack

### Frontend
- **Next.js 15.5.2** with TypeScript
- **React 19** with Context API for state management
- **Tailwind CSS** for responsive UI design
- **Firebase Authentication** with Google OAuth
- **Recharts** for data visualization and analytics

### Backend
- **FastAPI** (Python) for REST API
- **Google BigQuery** for data warehouse and analytics
- **BigQuery Client Libraries** for database operations
- **Uvicorn** ASGI server

### Infrastructure & Deployment
- **Google Cloud Run** for containerized deployment
- **Docker** for containerization
- **Google Cloud Build** for CI/CD
- **Firebase** for authentication services

## 🎯 Key Features

### 💰 Financial Management
- **Expense Tracking**: Record daily expenses with categories, tags, and notes
- **Income Recording**: Track various income sources
- **Multi-Currency Support**: Handle JPY, USD transactions with exchange rates
- **Negative Amounts**: Support for refunds and adjustments

### 📈 Investment Portfolio
- **Stock Transaction Management**: Buy/sell/vest stock transactions
- **Commission Tracking**: Record trading fees and commissions
- **Currency Exchange**: Multi-currency investment tracking
- **Portfolio Analytics**: Real-time portfolio valuation

### 🏦 Asset Management
- **Current Assets**: Track bank accounts, savings, crypto holdings
- **Service Provider Management**: Organize assets by financial institutions
- **Bulk Entry System**: Efficient data entry for multiple assets

### 🔐 Security & Authentication
- **Firebase Google OAuth**: Secure authentication with email whitelisting
- **Session Management**: 30-minute idle timeout with activity detection
- **Authorized Access**: Email-based access control

### 📊 Data Visualization
- **Interactive Charts**: Expense trends, income analysis, portfolio performance
- **Real-time Updates**: Live data synchronization
- **Responsive Design**: Mobile-optimized interface

## 🏗️ Architecture

```
Frontend (Next.js)     Backend (FastAPI)     Database (BigQuery)
┌─────────────────┐   ┌──────────────────┐   ┌─────────────────────┐
│ - React/TypeScript│   │ - REST API       │   │ - Expense Records   │
│ - Firebase Auth │   │ - BigQuery Client│   │ - Investment Data   │
│ - Tailwind CSS  │   │ - Data Validation│   │ - Asset Information │
│ - State Management│  │ - Business Logic │   │ - Analytics Tables  │
└─────────────────┘   └──────────────────┘   └─────────────────────┘
        │                       │                       │
        └───────────────────────┼───────────────────────┘
                                │
                    ┌──────────────────┐
                    │  Google Cloud    │
                    │  Infrastructure  │
                    │ - Cloud Run      │
                    │ - Cloud Build    │
                    │ - BigQuery       │
                    └──────────────────┘
```

## 💡 Architecture Decision: BigQuery vs Traditional Database

**Cost-Optimized Choice**: This application uses **Google BigQuery** instead of traditional PostgreSQL for several strategic reasons:

- **💰 Cost Efficiency**: No 24/7 VM costs - pay only for queries executed
- **🚀 Serverless**: Zero infrastructure maintenance overhead
- **📊 Analytics-Ready**: Built-in data warehouse capabilities for financial analytics
- **🔧 Scalability**: Automatic scaling without capacity planning
- **⚡ Performance**: Columnar storage optimized for analytical queries

For a personal finance app with moderate transaction volume, BigQuery's pay-per-query model is significantly more cost-effective than maintaining a persistent database instance.

## 📱 Key Functionality

- **Authentication**: Firebase Google OAuth with email whitelisting
- **Expense Tracking**: Daily expenses with categories and multi-currency support
- **Investment Management**: Stock transactions with real-time portfolio valuation
- **Asset Overview**: Current assets across multiple financial institutions
- **Analytics**: Spending patterns and portfolio performance visualization

## 🔧 Technical Highlights

### Frontend Engineering
- **Type Safety**: Full TypeScript implementation with strict typing
- **State Management**: React Context with custom hooks
- **Component Architecture**: Reusable, modular component design
- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Performance**: Optimized builds with Next.js

### Backend Engineering
- **RESTful API**: Well-structured endpoints with proper HTTP methods
- **Data Validation**: Pydantic models for request/response validation
- **BigQuery Integration**: Optimized SQL queries and data modeling for analytics
- **Cost-Aware Design**: Serverless architecture minimizing operational costs
- **Error Handling**: Comprehensive error handling and logging
- **Authentication**: Secure session management

### DevOps & Infrastructure
- **Containerization**: Docker multi-stage builds for optimization
- **CI/CD**: Automated deployment with Google Cloud Build
- **Environment Management**: Proper separation of dev/prod environments
- **Monitoring**: Health checks and logging for production readiness

## 🎯 Skills Demonstrated

- **Full-Stack Development**: End-to-end application development
- **Modern Web Technologies**: React, Next.js, TypeScript, Tailwind CSS
- **Backend Development**: Python, FastAPI, BigQuery, Google Cloud APIs
- **Cloud Engineering**: Google Cloud Platform, Docker, CI/CD, Serverless Architecture
- **Authentication & Security**: Firebase, OAuth, session management
- **Data Engineering**: BigQuery data modeling, cost-optimized analytics
- **API Design**: RESTful API architecture and documentation
- **DevOps**: Containerization, deployment automation, monitoring

## 📊 Code Quality

- **TypeScript**: 100% type coverage for enhanced reliability
- **Component Testing**: Unit tests for critical components
- **API Testing**: Comprehensive endpoint testing
- **Code Standards**: ESLint, Prettier for consistent code style
- **Documentation**: Comprehensive inline documentation

---

**Note**: This is a personal finance management application developed to demonstrate full-stack development capabilities, cloud deployment skills, and modern web development best practices.
