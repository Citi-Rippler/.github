# 🌊 Rippler - Microservices Impact Analysis Tool

Rippler is a comprehensive PR impact analysis tool for microservice-based systems. It performs automated impact analysis on code changes and notifies stakeholders of potential downstream effects.

## 🏗️ Architecture

```bash
rippler/
├── services/                    # All microservices (as submodules)
│   ├── api-gateway/            # Main API gateway with WebSocket
│   ├── embedding-server/       # Vector embeddings service
│   ├── llm-service/           # LLM-based analysis
│   ├── impact-analyzer/       # Core impact analysis engine
│   ├── notification-service/  # Email & GitHub notifications
│   └── webhook-handler/       # GitHub webhook processor
├── rippler-ui/                 # Flutter web/desktop UI (submodule)
├── shared/                     # Shared utilities and models
├── config/                     # Shared configuration
├── docs/                       # Documentation
└── docker-compose.yml         # Orchestration
```

## 🚀 Quick Start

### Prerequisites
- Git
- Docker & Docker Compose
- Make (optional, but recommended)

### Initial Setup

1. **Clone the repository with all submodules:**
```bash
git clone --recurse-submodules https://github.com/Citi-Rippler/rippler.git
cd rippler

# Or if you already cloned without submodules:
make init
```

2. **Configure environment:**
```bash
cp .env.example .env
# Edit .env with your API keys and tokens
```

3. **Build and start services:**
```bash
make build
make up
```

4. **View logs:**
```bash
make logs
```

## 🛠️ Development Workflow

### Working on a Specific Service

```bash
# Navigate to the service
cd services/impact-analyzer

# Work on the service independently
git checkout -b feature/new-analysis
# Make changes...
git add .
git commit -m "feat: add new analysis feature"
git push origin feature/new-analysis

# Go back to main repo
cd ../..

# Update the submodule reference
git add services/impact-analyzer
git commit -m "chore: update impact-analyzer submodule"
git push
```

### Pulling Latest Changes

```bash
# Pull main repo and all submodules
make pull-main

# Or manually:
git pull
git submodule update --remote --merge
```

### Running Individual Services

```bash
# Run only API gateway with dependencies
make dev-api-gateway

# Run impact analyzer with dependencies
make dev-analyzer

# View logs for specific service
make logs-impact-analyzer
```

## 📦 Service Management

### Check Submodule Status
```bash
make submodule-status
```

### Update Specific Submodule
```bash
make update-submodule-api-gateway
```

### Restart Specific Service
```bash
make restart-impact-analyzer
```

## 🧪 Testing

```bash
# Run all tests
make test

# Test specific service
cd services/impact-analyzer
pytest
```

## 🎯 Key Features

- ✅ Real-time PR impact analysis
- ✅ Automated dependency detection
- ✅ LLM-powered insights
- ✅ Stakeholder notifications
- ✅ Visual impact tracking
- ✅ GitHub integration

## 👥 Team Collaboration

### For Team Members

1. **First time setup:**
```bash
git clone --recurse-submodules https://github.com/hanisntsolo/rippler.git
cd rippler
make init
```

2. **Daily workflow:**
```bash
# Update everything
make pull-main

# Work on your service
cd services/your-service
git checkout -b feature/your-feature
# ... make changes ...
git push origin feature/your-feature

# Create PR in the service repo
```

3. **After your service PR is merged:**
```bash
# Update main repo to reference new commit
cd rippler
git submodule update --remote services/your-service
git add services/your-service
git commit -m "chore: update your-service to v1.2.3"
git push
```

## 📚 Documentation

- [Architecture](docs/architecture.md)
- [API Documentation](docs/api.md)
- [Development Guide](docs/development.md)
- [Deployment Guide](docs/deployment.md)

## 🤝 Contributing

1. Fork the service repository you want to work on
2. Create a feature branch
3. Make your changes
4. Submit a PR to the service repo
5. After merge, update the main rippler repo

## 📧 Contacts

**Dhirendra Pratap Singh** 
**Devyani Kumrawat** 
**Yogesh Dixit** 
**Vaishnavi Mishra** 

Project Link: [https://github.com/Citi-Rippler/rippler](https://github.com/Citi-Rippler/rippler)
