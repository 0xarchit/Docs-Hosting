---
label: ApiCortex
icon: plug
description: "Autonomous API failure prediction and contract testing SaaS platform with ML-powered analytics."
order: 77
tags: [FastAPI, Go, Rust, Python, Next.js, Kafka, PostgreSQL, ML, XGBoost]
---

# ApiCortex

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white&labelColor=000000&color=000000) ![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white&labelColor=000000&color=000000) ![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white&labelColor=000000&color=000000) ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=000000&color=000000) ![Next.js](https://img.shields.io/badge/Next.js-black?style=for-the-badge&logo=nextdotjs&logoColor=white&labelColor=000000&color=000000) ![Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apache-kafka&logoColor=white&labelColor=000000&color=000000)  
![Stars](https://img.shields.io/github/stars/0xarchit/ApiCortex?style=for-the-badge&logo=github&logoColor=white&labelColor=000000&color=000000) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/ApiCortex?style=for-the-badge&logo=github&logoColor=white&labelColor=000000&color=000000) ![Forks](https://img.shields.io/github/forks/0xarchit/ApiCortex?style=for-the-badge&logo=github&logoColor=white&labelColor=000000&color=000000) ![Issues](https://img.shields.io/github/issues/0xarchit/ApiCortex?style=for-the-badge&logo=github&logoColor=white&labelColor=000000&color=000000) [![Website](https://img.shields.io/website?url=https://api-cortex.vercel.app&style=for-the-badge&logo=html5&logoColor=white&labelColor=000000&color=000000)](https://api-cortex.vercel.app){target="_blank"}

:icon-mark-github: **GitHub:** [0xarchit/ApiCortex](https://github.com/0xarchit/ApiCortex){target="_blank"}  
:icon-globe: **Live Demo:** [https://api-cortex.vercel.app](https://api-cortex.vercel.app){target="_blank"}

> [!TIP]
> Predict API Failures Before They Happen. An enterprise-grade SaaS platform using ML analytics on real production traffic.

## :icon-milestone: Overview

**ApiCortex** is an enterprise-grade SaaS platform that predicts API failures before they occur using machine learning analytics on real production traffic. The platform ensures API contract compliance and provides proactive failure detection through advanced anomaly detection algorithms.

### Key Capabilities

- :icon-hubot: **Predictive Analytics**: ML-powered failure prediction with 95%+ accuracy
- :icon-zap: **Real-time Monitoring**: Sub-second telemetry processing via Kafka streaming
- :icon-check: **Contract Validation**: OpenAPI specification enforcement and drift detection
- :icon-organization: **Multi-tenant Architecture**: Organization-based isolation with RBAC
- :icon-database: **Time-series Analytics**: Historical querying with TimescaleDB
- :icon-device-desktop: **Developer Dashboard**: Interactive Next.js UI with live metrics

## :icon-cloud: Deployment Status (MVP)

For the initial MVP launch, we have adopted a hybrid-cloud strategy utilizing high-performance managed services.

| Component | Provider | Role |
| :------- | :------- | :--- |
| **Frontend** | **Vercel** | Dashboard & Edge Proxy |
| **Backend** | **HuggingFace** | Unified Docker Orchestration |
| **Metadata** | **NeonDB** | Serverless PostgreSQL |
| **Metrics** | **TigerData** | Managed TimescaleDB |
| **Streaming** | **Aiven** | Cloud Managed Kafka |
| **Caching** | **Upstash** | Serverless Redis |

> [!NOTE]
> To maximize efficiency and minimize cross-service latency on free-tier resources, the core backend services (Ingest, Control Plane, and ML Service) are orchestrated within a unified Docker container on HuggingFace Spaces.

## :icon-stack: Architecture

### System Flow Diagram

```mermaid
graph TB
    subgraph "Presentation Layer"
        A[Next.js Dashboard]
        B[REST API Clients]
    end
    
    subgraph "Control Plane"
        C[FastAPI Server]
        D[Auth Service]
        E[API Management]
        F[Contract Validator]
    end
    
    subgraph "Data Plane"
        G[Go Ingest Service]
        H[Kafka Producer]
        I[Rate Limiter]
    end
    
    subgraph "ML Plane"
        J[Python ML Service]
        K[Feature Engineering]
        L[XGBoost Predictor]
        M[Anomaly Detector]
    end
    
    subgraph "Execution Plane"
        Q[Rust Testing Engine]
        R[SSRF Shield]
        S[External APIs]
    end

    subgraph "Storage"
        N[(PostgreSQL)]
        O[(TimescaleDB)]
        P[Kafka Topics]
    end
    
    A --> C
    B --> C
    C --> D
    C --> E
    C --> F
    C <--> Q
    Q --> R
    R --> S
    G --> H
    H --> P
    J --> P
    J --> K
    K --> L
    L --> M
    C --> N
    G --> O
    J --> O
```

## :icon-tools: Features

### Core Features

| Feature | Description | Status |
|---------|-------------|--------|
| :icon-zap: **Real-time Telemetry** | Collect API metrics with <10ms latency | ✔ Active |
| :icon-hubot: **ML Failure Prediction** | XGBoost-based anomaly detection | ✔ Active |
| :icon-check: **Contract Validation** | OpenAPI 3.0 specification enforcement | ✔ Active |
| :icon-lock: **Multi-tenant RBAC** | Organization-based access control | ✔ Active |
| :icon-graph: **Time-series Analytics** | Historical data querying | ✔ Active |
| :icon-bell: **Alerting System** | Webhook-based notifications | ✔ Active |
| :icon-device-desktop: **Developer Dashboard** | Interactive UI with live metrics | ✔ Active |
| :icon-gear: **API Testing** | High-performance Rust execution engine | ✔ Active |

### Technical Specifications

- **Throughput**: 10,000+ events/second
- **Latency**: <50ms p99 for telemetry ingestion
- **Accuracy**: 95%+ failure prediction accuracy
- **Retention**: Configurable (default 30 days)
- **Scalability**: Horizontal scaling with Kafka partitions

## :icon-server: System Components

### 1. Data Plane (Go)

**Location**: `ingest-service/`

Responsible for high-throughput telemetry collection and streaming.

**Key Files**:
- `cmd/server/main.go` - Application entry point
- `internal/api/handler.go` - HTTP request handlers
- `internal/kafka/producer.go` - Kafka producer
- `internal/buffer/batcher.go` - Event batching

### 2. Control Plane (FastAPI)

**Location**: `control-plane/`

Handles authentication, API metadata, and contract management.

**Key Files**:
- `app/main.py` - FastAPI application
- `app/routers/auth.py` - Authentication endpoints
- `app/routers/apis.py` - API management
- `app/services/contract_service.py` - Contract validation

### 3. ML Plane (Python)

**Location**: `ml-service/`

Processes telemetry streams and generates failure predictions.

**Key Files**:
- `app/main.py` - ML worker entry
- `workers/inference_worker.py` - Inference pipeline
- `app/features/feature_engineering.py` - Feature extraction
- `app/inference/predictor.py` - Model prediction

### 4. Presentation Plane (Next.js)

**Location**: `frontend/`

Developer dashboard for monitoring and management.

### 5. Execution Engine (Rust)

**Location**: `api-testing/`

High-performance, secure engine optimized for executing REST, GraphQL, and WebSocket tests.

**Key Files**:
- `src/main.rs` - Axum server entry
- `src/executor.rs` - Core execution & security logic
- `src/protocols/` - WebSocket & HTTP handlers
- `src/models.rs` - Result & Snapshot schemas

## :icon-sync: Data Flow

### Telemetry Data Flow

```mermaid
sequenceDiagram
    participant Client as API Client
    participant Ingest as Ingest Service
    participant Kafka as Apache Kafka
    participant ML as ML Service
    participant DB as TimescaleDB
    participant UI as Dashboard
    
    Client->>Ingest: POST /v1/telemetry
    Ingest->>Ingest: Validate & Buffer
    Ingest->>Kafka: Publish telemetry.raw
    Ingest->>DB: Store telemetry
    Ingest-->>Client: 200 OK
    
    ML->>Kafka: Consume telemetry.raw
    ML->>ML: Feature Engineering
    ML->>ML: XGBoost Prediction
    ML->>DB: Store prediction
    ML->>Kafka: Publish alerts
    
    UI->>DB: Query metrics
    UI->>UI: Display charts
```

### Prediction Flow

```mermaid
flowchart TD
    A[Telemetry Event] --> B{Kafka Consumer}
    B --> C[Feature Extraction]
    C --> D[1m Window Stats]
    C --> E[5m Window Stats]
    C --> F[15m Window Stats]
    D --> G[Feature Vector]
    E --> G
    F --> G
    G --> H{XGBoost Model}
    H --> I[Risk Score]
    I --> J{Threshold Check}
    J -->|Score > 0.8| K[Generate Alert]
    J -->|Score < 0.8| L[Store Prediction]
    K --> M[Kafka Alerts Topic]
    L --> N[TimescaleDB]
```

## :icon-gear: Getting Started

### Prerequisites

- **Go**: 1.26 or later
- **Python**: 3.11 or later
- **Node.js**: 22 or later
- **PostgreSQL**: 16+ or NeonDB
- **TimescaleDB**: Latest version
- **Apache Kafka**: 3.0 or later

### Installation

```bash
# Clone repository
git clone https://github.com/0xarchit/apicortex.git
cd apicortex

# Set up environment variables
cp .env.example .env
# Edit .env with your credentials

# Start infrastructure (Docker)
docker-compose up -d
```

### Running Services

```bash
# Ingest Service
cd ingest-service && go run cmd/server/main.go

# Control Plane
cd control-plane && uvicorn app.main:app --reload

# ML Service
cd ml-service && python app/main.py

# API Testing Engine (Rust)
cd api-testing && cargo run

# Frontend
cd frontend && npm run dev
```

## :icon-file-directory: Configuration

### Environment Variables

| Variable | Service | Description | Default |
|----------|---------|-------------|---------|
| `DATABASE` | Control Plane | PostgreSQL connection string | - |
| `TIMESCALE_DATABASE` | All | TimescaleDB connection string | - |
| `KAFKA_SERVICE_URI` | Ingest, ML | Kafka broker URI | - |
| `ACTIVE_POLLING_ENABLED` | Ingest | Enable active polling | `true` |
| `BATCH_SIZE` | Ingest | Kafka batch size | `500` |
| `MODEL_PATH` | ML | Path to XGBoost model | `model/xgboost.pkl` |
| `ALERT_THRESHOLD` | ML | Alert threshold (0-1) | `0.8` |

### Service Configuration

**Ingest Service** (`ingest-service/.env`):
```env
PORT=8080
KAFKA_SERVICE_URI=kafka:9092
BATCH_SIZE=500
FLUSH_INTERVAL_SECONDS=2
ACTIVE_POLLING_ENABLED=true
```

**Control Plane** (`control-plane/.env`):
```env
DATABASE=postgresql://user:pass@host:5432/db
JWT_SECRET_KEY=your-secret-key
OAUTH_GITHUB_CLIENT_ID=your-client-id
```

**ML Service** (`ml-service/.env`):
```env
KAFKA_TOPIC_RAW=telemetry.raw
MODEL_PATH=model/xgboost_failure_prediction.pkl
ALERT_THRESHOLD=0.8
ENABLE_SHAP=true
```

## :icon-play: Usage

### Dashboard Access

1. Open browser: `http://localhost:3000`
2. Sign in with OAuth (Google/GitHub)
3. Navigate to Dashboard

### API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/auth/login` | POST | User authentication |
| `/apis` | GET | List APIs |
| `/apis/{id}/endpoints` | GET | Get API endpoints |
| `/telemetry` | POST | Submit telemetry |
| `/predictions` | GET | Get predictions |
| `/dashboard/metrics` | GET | Dashboard metrics |
| `/testing/execute` | POST | Execute API test |

## :icon-graph: Monitoring

### Health Checks

| Service | Endpoint | Port |
|---------|----------|------|
| Ingest | `/health` | 8080 |
| API Testing | `/health` | 9090 |
| Control Plane | `/health` | 8000 |
| Frontend | `/` | 3000 |

### Logging

All services use structured logging in JSON format:
- **Ingest**: Zerolog
- **Control Plane**: Python logging
- **ML Service**: Python logging

## :icon-bug: Troubleshooting

### Common Issues

#### Services Won't Start

**Solution**:
```bash
# Check environment variables
printenv | grep APICORTEX

# Verify database connectivity
psql $DATABASE -c "SELECT 1"

# Check Kafka connection
kafka-consumer-groups --bootstrap-server $KAFKA_URI --list
```

#### High Memory Usage

**Solution**:
```bash
# Reduce batch size
BATCH_SIZE=100

# Limit buffer capacity
MAX_BUFFER_CAPACITY=10000
```

#### Kafka Consumer Lag

**Solution**:
- Increase consumer parallelism
- Add more ML worker instances
- Check network connectivity

### Debug Mode

```env
DEBUG=true
LOG_LEVEL=debug
```

## :icon-shield: Security

### Authentication Flow

```mermaid
sequenceDiagram
    participant User
    participant Frontend
    participant ControlPlane
    participant OAuth
    participant DB
    
    User->>Frontend: Click "Login"
    Frontend->>ControlPlane: Initiate OAuth
    ControlPlane->>OAuth: Redirect
    User->>OAuth: Authenticate
    OAuth->>ControlPlane: OAuth Callback
    ControlPlane->>DB: Create/Update User
    ControlPlane->>Frontend: JWT Token
    Frontend->>User: Dashboard Access
```

### API Key Management

- Keys are hashed with pepper before storage
- Keys are rotated every 90 days
- Audit logging for all key operations

## :icon-pencil: Contributing

1. Fork the repository
2. Create feature branch
3. Submit pull request
4. Pass CI/CD pipeline

### Development Setup

```bash
# Install dependencies
go mod download
pip install -r requirements.txt
npm install

# Run tests
go test ./...
pytest
npm test
```

## :icon-heart: Support

- **Email:** mail@0xarchit.is-a.dev
- **Discussions:** [GitHub Discussions](https://github.com/0xarchit/ApiCortex/discussions){target="_blank"}
- **Issues:** [GitHub Issues](https://github.com/0xarchit/ApiCortex/issues){target="_blank"}
