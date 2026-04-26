# CityTrack

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white&labelColor=000000&color=000000) ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=000000&color=000000) ![Next.js](https://img.shields.io/badge/Next.js-black?style=for-the-badge&logo=nextdotjs&logoColor=white&labelColor=000000&color=000000) ![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=white&labelColor=000000&color=000000) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white&labelColor=000000&color=000000) ![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white&labelColor=000000&color=000000)  
![Stars](https://img.shields.io/github/stars/0xarchit/CityTrack?style=for-the-badge&logo=github&logoColor=white&labelColor=000000&color=000000) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/CityTrack?style=for-the-badge&logo=github&logoColor=white&labelColor=000000&color=000000) ![Forks](https://img.shields.io/github/forks/0xarchit/CityTrack?style=for-the-badge&logo=github&logoColor=white&labelColor=000000&color=000000) ![Issues](https://img.shields.io/github/issues/0xarchit/CityTrack?style=for-the-badge&logo=github&logoColor=white&labelColor=000000&color=000000) [![Website](https://img.shields.io/website?url=https://city-track-seven.vercel.app&style=for-the-badge&logo=html5&logoColor=white&labelColor=000000&color=000000)](https://city-track-seven.vercel.app){target="_blank"}

:icon-mark-github: **GitHub:** [0xarchit/CityTrack](https://github.com/0xarchit/CityTrack){target="_blank"}  
:icon-globe: **Live Demo:** [https://city-track-seven.vercel.app](https://city-track-seven.vercel.app){target="_blank"}

> [!TIP]
> Governance at the Speed of Software. An autonomous AI-powered system transforming civil infrastructure maintenance from reactive to proactive.

## :icon-milestone: Problem Statement

Traditional urban governance is plagued by:

- :icon-clock: **Manual Bottlenecks**: Every report sits in a queue waiting for human categorization
- :icon-duplicate: **Redundancy**: Multiple citizens report the same issue, creating duplicate tickets
- :icon-database: **Data Black Holes**: Citizens rarely receive feedback on their reports
- :icon-question: **Subjective Prioritization**: Urgent issues treated the same as minor ones

## :icon-tools: Features

- :icon-device-camera: **Anti-Fraud Reporting**: Mandatory live camera and high-precision GPS lock
- :icon-hubot: **AI-Powered Validation**: Automatic classification using YOLOv8
- :icon-search: **Smart Deduplication**: Geospatial clustering to merge similar reports
- :icon-zap: **Dynamic Priority Assignment**: Context-aware urgency levels with SLA enforcement
- :icon-sync: **Intelligent Routing**: Automatic department and worker assignment
- :icon-eye: **Real-Time Tracking**: Live progress updates for citizens
- :icon-check: **Proof of Resolution**: Workers must upload "After" photos to close tickets

## :icon-stack: System Architecture

CityTrack is an autonomous, event-driven operating system for smart cities that transforms civil infrastructure maintenance. The system leverages AI agents to instantly detect, validate, and route urban issues without human fatigue or bias.

### The "Issue Packet"

Every interaction starts with an **Issue Packet** - an immutable, atomic unit of civic data:

- **Evidence**: Primary visual proof captured via mandatory live camera
- **Context**: High-precision GPS (< 10m accuracy), Compass Heading, Device Metadata
- **Intent**: User-provided description, enhanced by NLP

### Anti-Fraud Enforcement

1. **Live Camera Only**: Users MUST capture photos live, preventing repurposing of old images
2. **GPS Precision Lock**: Submission blocked unless GPS accuracy < 10 meters
3. **Identity Binding**: Reports cryptographically linked to verified Google Identity (Supabase Auth)

### System Flow Diagram

```mermaid
graph TD
    A[Citizen Mobile App] -->|Issue Packet| B[FastAPI Backend]
    B --> C[Event Bus]
    
    subgraph "Autonomous Agent Pipeline"
        C --> D[Vision Agent]
        D -->|Annotated Data| E[Geo-Deduplicate Agent]
        E -->|Clustered Info| F[Priority Agent]
        F -->|Urgency Level| G[Routing Agent]
        G -->|Assignment| H[Notification Agent]
    end
    
    H --> I[Worker Dashboard]
    H --> J[Admin Portal]
    H --> K[Citizen Updates]
    
    subgraph "Data Layer"
        L[(PostgreSQL)]
        M[(Supabase Storage)]
    end
    
    D -.-> M
    E -.-> L
```

## :icon-desktop-download: Client Ecosystem

### 1. Citizen Mobile App (The Sensors)
*Built with React Native + Expo (TypeScript)*

- **Offline-First**: Caches reports locally and syncs when connection returns
- **Real-Time Tracking**: Server-driven events update processing screen live
- **Gamification**: Civic points for verified reports (Planned)

### 2. Admin Command Center (The Control)
*Built with Next.js 16 (App Router) + Tailwind CSS*

- **Role-Based Access Control (RBAC)**: Super Admin, Department Admin, Worker Dashboard
- **Visual Intelligence**: Heatmaps and density plots for infrastructure zones

### 3. Worker Interface (The Hands)
*Mobile-First Web View*

- **Task List**: Priority-sorted list of jobs
- **Navigation**: One-tap deep link to Google Maps
- **Proof of Resolution**: Vision Agent verifies fix photos against originals

## :icon-hubot: The Autonomous Pipeline

### Stage 1: The Senses (Input & Validation)

**Vision Agent: The "Eyes"**
- Uses fine-tuned YOLOv8s model to scan incoming images
- Automatically discards irrelevant images (selfies, blurry photos)
- Identifies defects (Pothole, Debris, Graffiti) with confidence scores

**Geo-Temporal Deduplication Agent: The "Memory"**
- Uses bounding box queries and haversine distance calculation
- Merges reports into clusters, increasing urgency score

### Stage 2: The Brain (Decision Making)

**Priority Agent: The "Judge"**
- Combines Vision Confidence + Location Context + Repeat Count
- Assigns dynamic SLA deadlines (e.g., 4 hours for Critical)

**Routing Agent: The "Dispatcher"**
- Matches issue category to Department and assigns workers by geolocation and load

### Stage 3: The Enforcers (Execution)

**SLA Watchdog Agent: The "Timekeeper"**
- Analyzes context of delayed issues, not just the timer
- Triggers warnings at 50% and 20% remaining time

**Notification Agent: The "Messenger"**
- Pushes updates to Citizen, Worker, and Admin simultaneously
- Email notifications to stakeholders

## :icon-file-directory: Project Structure

```
/
├── Backend/              # Core Logic (FastAPI + Async SQLAlchemy)
│   ├── agents/           # 7 Autonomous Agents
│   │   ├── vision/       # Vision Agent (YOLOv8)
│   │   ├── geoDeduplicate/ # Geo-Temporal Deduplication
│   │   ├── priority/     # Priority Assignment
│   │   ├── routing/      # Department & Worker Routing
│   │   ├── sla/          # SLA Monitoring & Watchdog
│   │   ├── escalation/   # Escalation Management
│   │   └── notification/ # Omnichannel Notifications
│   ├── api/              # Stateless REST Endpoints
│   ├── core/             # Shared Infrastructure
│   ├── database/         # Database Layer
│   ├── orchestration/    # Agent Base Classes
│   └── services/         # External Services
├── User/                 # Citizen Mobile App (Expo/React Native)
│   ├── src/
│   └── android/
├── Frontend/             # Admin & Worker Portals (Next.js 16)
│   ├── app/
│   └── components/
└── static/               # Static page for pipeline preview
```

## :icon-gear: Tech Stack

| Category | Technologies |
|----------|-------------|
| **Backend** | FastAPI, Python 3.11+, SQLAlchemy 2.0 (Async) |
| **Database** | PostgreSQL 18, Haversine distance calculation |
| **AI/ML** | YOLOv8s (Fine-tuned), 2000+ labeled images |
| **Frontend** | Next.js 16 (App Router), Tailwind CSS |
| **Mobile** | React Native, Expo SDK 54, TypeScript |
| **Auth** | Supabase Auth (Google OAuth) |
| **Storage** | Supabase Storage |
| **Deployment** | Docker, Docker Compose, GitHub Actions |

## :icon-play: Getting Started

### Prerequisites

- Node.js 20+
- Python 3.11+
- Docker & Docker Compose
- PostgreSQL 15+
- Android SDK (for mobile development)

### Installation

```bash
# Clone the repository
git clone https://github.com/0xarchit/CityTrack.git
cd CityTrack

# Backend Setup
cd Backend
pip install -r requirements.txt

# Frontend Setup
cd ../Frontend
npm install

# Mobile App Setup
cd ../User
npm install
```

### Environment Configuration

**Backend/.env**
```env
DATABASE_URL=postgresql://user:password@localhost:5432/citytrack
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_service_role_key
SUPABASE_BUCKET=your_bucket_name
SUPABASE_JWT_SECRET=your_jwt_secret
GOOGLE_CLIENT_ID=your_google_client_id
GEMINI_API_KEY=your_gemini_api_key
SENDER_EMAIL=noreply@yourdomain.com
RESEND_API_KEY=your_resend_api_key
```

**Frontend/.env.local**
```env
NEXT_PUBLIC_API_URL=http://localhost:8000
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
```

**User/.env**
```env
EXPO_PUBLIC_API_BASE_URL=http://localhost:8000
EXPO_PUBLIC_SUPABASE_URL=your_supabase_url
EXPO_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
EXPO_PUBLIC_GOOGLE_CLIENT_ID=your_google_client_id
```

### Running the Project

**Using Docker (Recommended):**
```bash
docker compose up
```

**Manual Setup:**
```bash
# Terminal 1 - Backend
cd Backend
uvicorn api.app:app --host 0.0.0.0 --port 8000 --reload

# Terminal 2 - Frontend
cd Frontend
npm run dev

# Terminal 3 - Mobile App
cd User
npm start
```

## :icon-diff: Components

- **agents/**: 7 Autonomous Agents (Vision, GeoDeduplicate, Priority, Routing, SLA, Escalation, Notification)
- **api/**: Stateless REST Endpoints for Admin, Worker, and Issue routes
- **core/**: Configuration, Event Bus, Flow Tracker, Pydantic Models
- **database/**: SQLAlchemy Models, Connection Pool, SQL Migrations
- **services/**: Email, Geocoding, and Vision Processing services

## :icon-database: Key Features

### Admin Features
- :icon-graph: **Geospatial Heatmaps**: Visual density plots for problem areas
- :icon-organization: **Department Management**: Create and manage city departments
- :icon-people: **Worker Administration**: Onboard and assign workers
- :icon-checklist: **Manual Review Queue**: Review AI decisions
- :icon-graph: **Analytics Dashboard**: Real-time metrics and trends

### Worker Features
- :icon-list-ordered: **Priority Task List**: Auto-sorted by urgency and proximity
- :icon-location: **One-Tap Navigation**: Google Maps integration
- :icon-device-camera: **Evidence Upload**: Mandatory before-and-after photos
- :icon-history: **Task History**: Complete audit trail

## :icon-rocket: Deployment

### Docker Deployment

```bash
# Build and run with Docker Compose
docker compose up -d

# View logs
docker compose logs -f

# Stop services
docker compose down
```

### GitHub Actions CI/CD

Automated workflows for Docker image building, pushing to GHCR, and deployment.

## :icon-light-bulb: Roadmap

### Phase 1: Foundation (Completed)
- Autonomous Agent Pipeline
- Cross-Platform Ecosystem
- Real-time notifications and tracking
- Anti-fraud mechanisms

### Phase 2: Intelligence Enhancement (In Progress)
- Predictive Maintenance using historical data
- Automated Testing suite
- Multi-City Support with tenant architecture
- Civic Reputation System

### Phase 3: Scale & Gamification (Planned)
- Advanced Analytics with ML models
- Incentive Programs (tax credits, transit passes)
- Public API for third-party integrations
- Mobile SDK for white-label solutions
- IoT Integration (smart bins, streetlights, sensors)

## :icon-pencil: Contributing

We welcome contributions!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines

- Follow PEP 8 for Python code
- Use TypeScript for all new frontend code
- Write descriptive commit messages
- Add tests for new features
- Update documentation as needed

## :icon-people: Team

Built by **BitBots** at IIIT Una, HackTheThrone 2026

| Role | Name | GitHub |
|------|------|--------|
| Lead Developer | Archit Jain | [@0xarchit](https://github.com/0xarchit) |
| Developer | Rachit Verma | [@vxrachit](https://github.com/vxrachit) |
| Developer | Pushpendra Sharma | [@synapticpush](https://github.com/synapticpush) |
| Developer | Deepti Yadav | [@DeeptiYadav10648](https://github.com/DeeptiYadav10648) |

## :icon-book: License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## :icon-heart: Acknowledgments

- YOLOv8 by Ultralytics for object detection
- Supabase for authentication and storage
- FastAPI for the robust backend framework
- Next.js and React Native teams for excellent frameworks
