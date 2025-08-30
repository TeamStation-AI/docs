---
layout: page
title: Getting Started
description: Quick start guide for TeamStation-AI platforms
permalink: /docs/getting-started/
---

# Getting Started with TeamStation-AI

Welcome to the TeamStation-AI ecosystem! This guide will help you get up and running with our AI platforms quickly and efficiently.

## Overview

TeamStation-AI provides two flagship platforms:

### Axiom Cortex™ - Cognitive AI Evaluation
A comprehensive AI testing and validation framework designed for enterprise-grade cognitive computing solutions.

**Key Features:**
- Advanced AI model evaluation
- Cognitive reasoning assessment  
- Performance benchmarking
- Enterprise security compliance

### Nearshore IT Co-Pilot™ - Intelligent Operations
An AI-powered platform for nearshore development and operations management.

**Key Features:**
- Intelligent project management
- Automated code review and quality assurance
- Real-time collaboration tools
- Performance monitoring and optimization

## Prerequisites

Before getting started, ensure you have:

- [ ] Valid TeamStation-AI account
- [ ] API access credentials
- [ ] Development environment setup
- [ ] Basic understanding of AI/ML concepts

## Installation

### Option 1: Quick Setup (Recommended)

```bash
# Clone the starter repository
git clone https://github.com/TeamStation-AI/starter-kit.git
cd starter-kit

# Install dependencies
npm install

# Configure your credentials
cp .env.example .env
# Edit .env with your API keys
```

### Option 2: Manual Installation

```bash
# Install the CLI tool
npm install -g @teamstation-ai/cli

# Initialize a new project
teamstation-ai init my-project
cd my-project

# Authenticate
teamstation-ai auth login
```

## Quick Start

### 1. Authentication

```javascript
const { TeamStationAI } = require('@teamstation-ai/sdk');

const client = new TeamStationAI({
  apiKey: process.env.TEAMSTATION_API_KEY,
  environment: 'production' // or 'sandbox'
});
```

### 2. Your First Evaluation (Axiom Cortex™)

```javascript
// Create a cognitive evaluation
const evaluation = await client.cortex.createEvaluation({
  name: 'My First Evaluation',
  model: 'gpt-4',
  dataset: 'reasoning-benchmark',
  metrics: ['accuracy', 'reasoning_depth', 'coherence']
});

console.log('Evaluation created:', evaluation.id);
```

### 3. Your First Co-Pilot Task

```javascript
// Initialize a co-pilot session
const session = await client.copilot.createSession({
  project: 'my-nearshore-project',
  team: 'development',
  timezone: 'UTC-5'
});

// Request code review
const review = await session.requestCodeReview({
  repository: 'github.com/myorg/myrepo',
  branch: 'feature/new-functionality',
  reviewer_preferences: ['security', 'performance', 'maintainability']
});
```

## Next Steps

### 📖 Learn More
- [API Reference](../api/) - Complete API documentation
- [Integration Examples](../examples/) - Real-world use cases
- [Best Practices](../best-practices/) - Recommended patterns

### 🛠️ Development
- [SDK Documentation](../sdk/) - Language-specific guides
- [Webhook Setup](../webhooks/) - Real-time notifications
- [Testing Guide](../testing/) - How to test your integrations

### 🚀 Advanced Topics
- [Custom Models](../advanced/custom-models/) - Bring your own models
- [Enterprise Setup](../advanced/enterprise/) - Large-scale deployments
- [Security Guide](../advanced/security/) - Best security practices

## Support

Need help? We're here for you:

- 📧 **Email**: [support@teamstation.ai](mailto:support@teamstation.ai)
- 💬 **Community**: [GitHub Discussions](https://github.com/TeamStation-AI/docs/discussions)
- 📖 **Documentation**: You're reading it!
- 🐛 **Bug Reports**: [GitHub Issues](https://github.com/TeamStation-AI/docs/issues)

---

**Ready to build something amazing?** Let's get started! 🚀