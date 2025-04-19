# DeepSeek-R1 on Ollama using Open-WebUI Docker Deployment
Deploying Open-WebUI with Ollama using Docker Compose CPU-only setup.
Here's an implementation guide:

## 📋 Prerequisites
- Docker Engine v20.10.10+
- Docker Compose v2.20.0+
- 4 vCPU minimum (12 vCPU recommended for larger models)
- 16GB RAM minimum (32GB recommended for larger models)
- 30GB+ free disk space
- Linux/macOS/WSL2 (Windows)

## 🚀 Quick Start
1. **Starting Services**
```bash
git clone https://github.com/mrkimoz/deepseek.git
cd deepseek
docker-compose up -d
```

2. **Verify Installation**
```bash
docker-compose ps
```
Expected Output:
   Name                Command                      State                              Ports
----------------------------------------------------------------------------------------------------------------
ollama       /usr/bin/bash /entrypoint.sh   Up                      0.0.0.0:11434->11434/tcp,:::11434->11434/tcp
open-webui   bash start.sh                  Up (health: starting)   0.0.0.0:3000->8080/tcp,:::3000->8080/tcp


4. **Check Logs**
```bash
docker-compose logs -f ollama
docker-compose logs -f open-webui
```

5. **Stoping Services**
```bash
docker-compose down
```

## 🌐 Access the Web UI
1. Open browser to `http://localhost:3000`
2. Create admin account
3. Start chatting!

❗ **Note**: CPU inference will be significantly slower than GPU-accelerated setups. For production use, consider GPU-enabled hardware.
