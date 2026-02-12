# installation

This guide will help you install Superdesk on your system.

## Prerequisites

Before installing Superdesk, ensure you have the following prerequisites:

### For Docker Installation (Recommended)

* Docker (version 20.10 or higher)
* Docker Compose (version 2.0 or higher)
* At least 4GB of RAM available
* At least 10GB of disk space

### For Development Installation

* **Backend Requirements:**
  * Python 3.8 or higher
  * MongoDB 4.4 or higher
  * Elasticsearch 7.x
  * Redis 6.x
  * Node.js 16.x or higher (for some build tools)
* **Frontend Requirements:**
  * Node.js 16.x or higher
  * npm 8.x or higher

## Installation Methods

### Docker Installation (Recommended for Production)

The easiest way to get Superdesk up and running is using Docker:

{% code title="Docker - Start services" %}
```bash
# Clone the main repository
git clone https://github.com/superdesk/superdesk.git
cd superdesk

# Start all services
docker-compose -f docker-compose.yml up -d

# Initialize the database
docker-compose exec backend python manage.py app:initialize_data
docker-compose exec backend python manage.py users:create -u admin -p admin -e admin@example.com --admin
```
{% endcode %}

{% hint style="warning" %}
The `admin` / `admin` credentials shown above are for local testing only. For any non-local or production deployment, use a strong, unique password for the admin user and never keep default credentials. If you used these example credentials temporarily, change the admin password immediately after the first login.
{% endhint %}

Access Superdesk at `http://localhost:9000` with the credentials you created.

### Development Installation

For development, you'll want to run the components separately.

{% stepper %}
{% step %}
### Install Backend (superdesk-core)

{% code title="Backend - Install and run" %}
```bash
# Clone the repository
git clone https://github.com/superdesk/superdesk-core.git
cd superdesk-core

# Create and activate virtual environment
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up configuration
cp settings_sample.py settings.py
# Edit settings.py with your database and service configurations

# Initialize the database
python manage.py app:initialize_data
python manage.py users:create -u admin -p admin -e admin@example.com --admin

# Run the server
python manage.py app:run
```
{% endcode %}
{% endstep %}

{% step %}
### Install Frontend (superdesk-client-core)

{% code title="Frontend - Install and start" %}
```bash
# Clone the repository
git clone https://github.com/superdesk/superdesk-client-core.git
cd superdesk-client-core

# Install dependencies
npm install

# Start development server
npm start
```
{% endcode %}
{% endstep %}

{% step %}
### Optional: Install Planning Module

{% code title="Planning - Clone repo" %}
```bash
# Clone the planning repository
git clone https://github.com/superdesk/superdesk-planning.git
cd superdesk-planning

# Follow the installation instructions in the planning repository
```
{% endcode %}
{% endstep %}
{% endstepper %}

## Configuration

### Environment Variables

Key environment variables for configuration:

{% code title="Environment variables" %}
```bash
# Backend
MONGO_URI=mongodb://localhost/superdesk
ELASTICSEARCH_URL=http://localhost:9200
REDIS_URL=redis://localhost:6379
SECRET_KEY=your-secret-key

# Frontend
SUPERDESK_URL=http://localhost:5000/api
```
{% endcode %}

### Database Configuration

Ensure MongoDB and Elasticsearch are running and accessible:

{% code title="Check database services" %}
```bash
# Check MongoDB
mongo --eval "db.version()"

# Check Elasticsearch
curl http://localhost:9200
```
{% endcode %}

## Verification

After installation, verify that Superdesk is running correctly:

* Access the frontend at `http://localhost:9000`
* Log in with your admin credentials
* Check that all services are healthy in the system status page

## Troubleshooting

### Common Issues

**Port Already in Use**

{% code title="Find process using port" %}
```bash
# Check what's using the port
lsof -i :9000

# Kill the process or change the port in your configuration
```
{% endcode %}

**Database Connection Failed**

* Ensure MongoDB and Elasticsearch are running
* Check connection strings in your configuration
* Verify firewall settings

**Frontend Build Errors**

{% code title="Frontend troubleshooting" %}
```bash
# Clear npm cache
npm cache clean --force

# Remove node_modules and reinstall
rm -rf node_modules
npm install
```
{% endcode %}

## Next Steps

* [Quick Start Guide](/broken/pages/1886a01b2022d9329ea3e88e5cf549dc1a9e7922) - Learn the basics
* [Developer Guide](file:///docs/developer-guide/architecture) - Understand the architecture
* [Deployment Guide](file:///docs/deployment) - Deploy to production

## Additional Resources

* https://github.com/superdesk/superdesk-core
* https://github.com/superdesk/superdesk-client-core
* https://hub.docker.com/u/superdesk
