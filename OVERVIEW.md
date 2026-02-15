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
- **Vertex AI** for text embeddings (text-embedding-004)
- **Gemini API** for LLM-powered category prediction
- **Firestore** for vector storage and embeddings

### Infrastructure & Deployment
- **Google Cloud Run** for containerized deployment
- **Docker** for containerization
- **Google Cloud Build** for CI/CD
- **Terraform** for Infrastructure as Code (IaC) and state management
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
- **End-to-End Token Verification**: Frontend and backend Firebase ID token validation
- **Firebase Admin SDK**: Server-side token verification with email whitelist enforcement
- **Session Management**: 30-minute idle timeout with activity detection
- **API Security**: All backend endpoints protected with Firebase authentication middleware
- **Authorized Access**: Email-based access control

### 📊 Data Visualization
- **Interactive Charts**: Expense trends, income analysis, portfolio performance
- **Real-time Updates**: Live data synchronization
- **Responsive Design**: Mobile-optimized interface

### 🔔 Portfolio Sentinel (AI-Powered Market Monitoring)
- **Automated News Monitoring**: AI-powered analysis of market news for portfolio holdings
- **Google News RSS Integration**: Real-time news aggregation from trusted sources
- **LLM-Powered Filtering**: Gemini 2.0 Flash for intelligent relevance detection
- **Multi-Category Alerts**: Regulatory, corporate events, and risk factors
- **Discord Notifications**: Instant alerts via Discord webhooks
- **Severity Classification**: HIGH/MEDIUM/LOW priority levels
- **Freshness Guarantee**: Only articles published within the last 7 days
- **Cost-Optimized**: Fixed query templates + minimal LLM calls

### 🤖 RAG-Based Category Prediction (AI-Powered Transaction Categorization)
- **Hybrid Prediction System**: Combines keyword matching, vector search, and LLM generation
- **Vector Search**: Semantic similarity search using Vertex AI text-embedding-004
- **Firestore Vector Store**: Past transaction embeddings for similarity matching
- **BigQuery Integration**: Historical transaction data for context augmentation
- **Gemini API**: Final category prediction with confidence scoring
- **Feedback Loop**: Learns from user corrections to improve accuracy
- **Cost-Efficient**: ~$0.17 for full dataset embedding generation

### 💬 SQL Agent (Natural Language Data Analysis)
- **Two-Step Structured Output**: Reliable data retrieval via SQL Agent + `with_structured_output` for fixed JSON formatting
- **Autonomous SQL Generation**: LangChain-based agent for intelligent data extraction from BigQuery
- **Multi-Format Visualization**: Automatic selection of 'table', 'chart' (trend/comparison), or 'text' based on query context
- **Natural Language Interface**: Supports complex analytical questions in Japanese or English
- **Reliable JSON Response**: Guaranteed schema consistency for seamless frontend rendering
- **Gemini 2.0 Flash**: High-speed, high-accuracy LLM orchestration
- **Chat Interface**: Modern dark mode UI with message history

### 🔄 Self-Healing Pipeline (Agentic RAG)
- **Auto Rule Generator**: Automatically proposes new merchant categorization rules from frequent user corrections
- **Human-in-the-Loop**: Discord notifications with Approve/Reject links for rule proposals
- **Incremental Embedding Updates**: Monthly batch job to embed only new transactions (cost-optimized)
- **Cloud Run Jobs + Cloud Scheduler**: Fully automated weekly/monthly scheduled execution via Terraform
- **Feedback-Driven Learning**: Closes the loop between user corrections and system improvement

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
- **Authentication Middleware**: FastAPI dependency injection for Firebase token verification
- **Security Architecture**: All API endpoints protected with `verify_firebase_token` dependency
- **RAG Implementation**: Hybrid prediction system combining vector search, BigQuery, and LLM
- **Vector Search**: Semantic similarity using Vertex AI embeddings and Firestore
- **Feedback Loop**: User correction tracking for continuous model improvement
- **Self-Healing Pipeline**: Auto-rule generation from corrections with Discord HITL approval workflow
- **SQL Agent**: Two-step architecture with `with_structured_output` for guaranteed JSON delivery
- **Structured Data Extraction**: Reliable separation of raw data retrieval and UI-centric formatting

### DevOps & Infrastructure
- **Infrastructure as Code (IaC)**: 100% resource management with Terraform
- **Containerization**: Docker multi-stage builds for optimization
- **CI/CD**: Automated deployment with Google Cloud Build
- **Scheduled Jobs**: Cloud Run Jobs + Cloud Scheduler for automated batch processing
- **Environment Management**: Proper separation of dev/prod environments
- **Monitoring**: Health checks and logging for production readiness

## 🎯 Skills Demonstrated

- **Full-Stack Development**: End-to-end application development
- **Modern Web Technologies**: React, Next.js, TypeScript, Tailwind CSS
- **Backend Development**: Python, FastAPI, BigQuery, Google Cloud APIs
- **AI/ML Integration**: RAG systems, vector search, LLM orchestration, self-healing pipelines
- **Cloud Engineering**: Google Cloud Platform, Docker, CI/CD, Serverless Architecture
- **Infrastructure as Code**: Terraform, State Management, Resource Synchronization
- **Authentication & Security**: Firebase, OAuth, session management
- **Data Engineering**: BigQuery data modeling, cost-optimized analytics, vector embeddings
- **API Design**: RESTful API architecture and documentation
- **DevOps**: Containerization, deployment automation, monitoring

## 📊 Code Quality

- **TypeScript**: 100% type coverage for enhanced reliability
- **Component Testing**: Unit tests for critical components
- **API Testing**: Comprehensive endpoint testing
- **Code Standards**: ESLint, Prettier for consistent code style
- **Documentation**: Comprehensive inline documentation

## 🔒 Firebase Authentication Implementation

### Architecture Overview

This application implements a **complete end-to-end Firebase authentication system** protecting both frontend access and backend API endpoints.

### Frontend Authentication (`frontend/`)

**Files:**
- `src/lib/firebase.ts` - Firebase SDK initialization
- `src/contexts/AuthContext.tsx` - Authentication state management with session timeout
- `src/lib/api.ts` - API helper functions with automatic token injection
- `src/components/Login.tsx` - Google OAuth login interface

**Flow:**
1. User authenticates via Google OAuth (Firebase)
2. `AuthContext` manages authentication state and session timeout (30 min)
3. All API calls automatically include Firebase ID token via `apiCall()` helper
4. Token sent as `Authorization: Bearer <token>` header

### Backend Authentication (`backend/`)

**Files:**
- `app/config/firebase_config.py` - Firebase Admin SDK initialization
- `app/dependencies/auth.py` - Authentication middleware with email whitelist
- All endpoint files - Protected with `Depends(verify_firebase_token)`

**Implementation:**
```python
# Firebase Admin SDK initialization
def initialize_firebase_admin():
    credentials_json = os.getenv("FIREBASE_ADMIN_CREDENTIALS_JSON")
    credentials_dict = json.loads(credentials_json)
    cred = credentials.Certificate(credentials_dict)
    firebase_admin.initialize_app(cred)

# Authentication middleware
async def verify_firebase_token(
    credentials: HTTPAuthorizationCredentials = Depends(security)
) -> dict:
    auth = get_firebase_auth()
    decoded_token = auth.verify_id_token(credentials.credentials)
    email = decoded_token.get('email')
    if email not in ALLOWED_EMAILS:
        raise HTTPException(status_code=403, detail="Access denied")
    return decoded_token

# Protected endpoint example
@router.get("/api/v1/records")
async def get_records(token_data: dict = Depends(verify_firebase_token)):
    # Only accessible with valid Firebase token
    return records
```

### Security Features

1. **Email Whitelist**: Only `inthemoshpit@gmail.com` can access the system
2. **Token Verification**: Every API request verified by Firebase Admin SDK
3. **Session Management**: 30-minute idle timeout on frontend
4. **No Public Access**: All endpoints require valid authentication
5. **Environment Variables**: Secure credential management via Cloud Run secrets

### Deployment Configuration

**Cloud Run Environment Variables:**
- `FIREBASE_ADMIN_CREDENTIALS_JSON` - Service account credentials (JSON string)
- Configured via: `gcloud run services update --set-env-vars`

---

**Note**: This is a personal finance management application developed to demonstrate full-stack development capabilities, cloud deployment skills, modern web development best practices, and comprehensive security implementation with Firebase authentication.
