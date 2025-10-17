# CISO Executive Dashboard

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)
![Docker](https://img.shields.io/badge/docker-ready-blue.svg)
![Security](https://img.shields.io/badge/security-A-green.svg)

> **Open-source CISO Executive Dashboard for comprehensive cybersecurity visibility, risk management, and compliance tracking**

A modern, real-time cybersecurity dashboard designed for Chief Information Security Officers (CISOs) and security executives to monitor, analyze, and report on their organization's security posture. **Fully mobile-responsive** with a mobile-first design approach.

## 🌟 Features

- **Real-time Security Metrics Visualization** - Monitor key security indicators in real-time
- **Multi-Framework Compliance Tracking** - Support for ISO 27001, SOC 2, NIST CSF, PCI DSS, and more
- **Vulnerability Management** - Track and manage vulnerabilities across your infrastructure
- **Incident Response Dashboard** - Monitor and respond to security incidents efficiently
- **Threat Intelligence Integration** - Integrate with open-source threat feeds (MISP, OpenCTI, NVD)
- **Executive Reporting** - Generate professional PDF reports for board meetings
- **Role-Based Access Control** - Secure access with customizable permissions
- **API-First Design** - RESTful API for easy integration with existing tools
- **Docker Containerization** - Easy deployment and scalability
- **Mobile-First Responsive Design** - Optimized for smartphones, tablets, and desktops

## 📊 Dashboard Sections

1. **Executive Overview** - High-level security posture and KPIs
2. **Risk & Threat Exposure** - Active threats and risk metrics
3. **Compliance & Governance** - Multi-framework compliance status
4. **Incident Response** - Active incidents and response metrics
5. **Vulnerability Management** - CVE tracking and patch management
6. **Security Operations** - SOC performance and alert management
7. **Human Risk & Awareness** - Security training and phishing simulations
8. **Third-Party Risk** - Vendor risk assessments

## 📱 Mobile-First Design

The dashboard is built with a **mobile-first approach**, ensuring excellent user experience on all devices:

- **Smartphone** - Optimized single-column layout with hamburger menu
- **Tablet** - Adaptive two-column layout with side drawer
- **Desktop** - Full multi-column layout with fixed sidebar

### Mobile Features
- Touch-friendly interface (44x44px minimum touch targets)
- Hamburger menu navigation
- Pull-to-refresh functionality
- Swipeable sections
- Expandable cards with tap interactions
- Responsive charts optimized for small screens
- Fast loading with lazy-loaded sections

## 🛠️ Tech Stack

**Frontend:**
- React 18+ with TypeScript
- TailwindCSS for styling
- Recharts for data visualization
- React Router for navigation

**Backend:**
- FastAPI (Python 3.10+)
- PostgreSQL for data storage
- Redis for caching
- OAuth2/JWT authentication

**Infrastructure:**
- Docker & Docker Compose
- Nginx reverse proxy
- GitHub Actions CI/CD

## 🚀 Quick Start

### Prerequisites

- Docker 20.10+
- Docker Compose 2.0+
- Git

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/SiteQ8/ciso-executive-dashboard.git
cd ciso-executive-dashboard
```

2. **Configure environment variables**
```bash
cp config/config.example.yml config/config.yml
# Edit config.yml with your settings
```

3. **Start the application**
```bash
docker-compose up -d
```

4. **Access the dashboard**
- Frontend: http://localhost:3000
- API Documentation: http://localhost:8000/docs
- Default credentials: admin / changeme

## 📖 Configuration

### API Integrations

Configure external data sources in `config/config.yml`:

**National Vulnerability Database (NVD)**
```yaml
nvd:
  api_key: your_nvd_api_key
  update_interval: 3600
```

**MISP Threat Intelligence**
```yaml
misp:
  url: https://your-misp-instance.com
  api_key: your_misp_api_key
```

**AbuseIPDB**
```yaml
abuseipdb:
  api_key: your_abuseipdb_key
```

See [Configuration Guide](docs/configuration.md) for detailed setup instructions.

## 📡 API Endpoints

The dashboard exposes a RESTful API for data integration:

- `GET /api/v1/metrics` - Retrieve security metrics
- `GET /api/v1/vulnerabilities` - List vulnerabilities
- `POST /api/v1/incidents` - Report security incident
- `GET /api/v1/compliance` - Compliance status
- `GET /api/v1/reports/executive` - Generate executive report

Full API documentation: http://localhost:8000/docs

## 🔌 Integrations

### Supported Threat Intelligence Feeds

- MISP (Malware Information Sharing Platform)
- OpenCTI (Open Cyber Threat Intelligence)
- AlienVault OTX
- AbuseIPDB
- PhishTank
- URLhaus

### Supported SIEM/Log Sources

- Elasticsearch
- Splunk
- Azure Sentinel
- AWS CloudWatch
- Custom syslog sources

## 🏗️ Architecture

```
┌─────────────────┐
│   React Frontend │
│   (Port 3000)    │
└────────┬────────┘
         │
    ┌────▼────────────────┐
    │  Nginx Reverse Proxy │
    └────┬────────────────┘
         │
┌────────▼──────────┐
│  FastAPI Backend   │
│   (Port 8000)      │
└────────┬───────────┘
         │
    ┌────▼────────┐
    │ PostgreSQL   │
    │ Database     │
    └──────────────┘
```

## 🧪 Development

### Local Development Setup

```bash
# Backend
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload

# Frontend
cd frontend
npm install
npm run dev
```

### Running Tests

```bash
# Backend tests
pytest tests/

# Frontend tests
npm test
```

### Mobile Development Testing

Test the mobile-responsive design:

```bash
# Use Chrome DevTools Device Mode
# Or test on actual devices
# Recommended test devices:
# - iPhone 12/13/14 (390x844)
# - Samsung Galaxy S21 (360x800)
# - iPad Pro (1024x1366)
```

## 📚 Documentation

- [Installation Guide](docs/installation.md)
- [Configuration Guide](docs/configuration.md)
- [User Guide](docs/user-guide.md)
- [API Documentation](docs/api-documentation.md)
- [Deployment Guide](docs/deployment.md)
- [Integration Guide](docs/integrations.md)
- [Mobile Development Guide](docs/mobile-guide.md)

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 🔒 Security

For security issues, please see [SECURITY.md](SECURITY.md) for our security policy and how to report vulnerabilities.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with open-source threat intelligence feeds
- Inspired by industry-standard security frameworks (NIST, ISO, CIS)
- Community-driven development

## 📧 Contact

- Project Link: https://github.com/SiteQ8/ciso-executive-dashboard
- Issues: https://github.com/SiteQ8/ciso-executive-dashboard/issues
- Discussions: https://github.com/SiteQ8/ciso-executive-dashboard/discussions

## ⭐ Star History

If you find this project useful, please consider giving it a star!

---

**Made with ❤️ for the cybersecurity community**
