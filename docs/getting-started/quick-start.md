# quick start

Get up and running with Superdesk in minutes!

## Using Docker (Fastest Method)

The quickest way to try Superdesk is using Docker:

{% code title="Start with Docker" %}
```bash
# Clone and start
git clone https://github.com/superdesk/superdesk.git
cd superdesk
docker-compose up

# In another terminal, initialize data
docker-compose exec backend python manage.py app:initialize_data
docker-compose exec backend python manage.py users:create -u admin -p admin -e admin@example.com --admin
```
{% endcode %}

{% hint style="warning" %}
The `admin` / `admin` credentials shown above are for **local testing only**. For any non-local or production deployment, use a strong, unique password for the admin user and never keep default credentials. If you used these example credentials temporarily, change the admin password immediately after the first login.
{% endhint %}

Access Superdesk at `http://localhost:9000` and log in with:

* **Username:** admin
* **Password:** admin (change immediately for non-local environments)

## Basic Workflow

Once logged in, here's a quick overview of the basic workflow:

{% stepper %}
{% step %}
### Create Content

* Click on **"+ Create"** in the top navigation
* Select the content type (e.g., "Article")
* Fill in the headline and body
* Add media, tags, and metadata as needed
{% endstep %}

{% step %}
### Edit and Collaborate

* Content appears in your **Personal Space**
* Move content to different desks using drag-and-drop
* Use the commenting feature to collaborate with team members
* Track changes and versions in the history panel
{% endstep %}

{% step %}
### Publish

* Click **"Publish"** to send content live
* Choose the publishing destination
* Set embargo times if needed
* Confirm and publish
{% endstep %}
{% endstepper %}

## Key Features to Explore

### Content Management

* Create articles, photos, videos, and multimedia packages
* Rich text editing with formatting options
* Media library for managing assets
* Metadata and tagging system

### Workflow

* Desk-based organization
* Stage-based workflow (e.g., Working, Submitted, Published)
* Assignment and task management
* Publishing queues

### Search and Filtering

* Advanced search with multiple criteria
* Saved searches for quick access
* Filter by desk, stage, type, date, and more

### Planning (if installed)

* Event management
* Planning items for coverage
* Assignment workflow
* Calendar views

## Common Tasks

### Creating a New User

{% code title="Create user (Docker)" %}
```bash
# Using Docker
docker-compose exec backend python manage.py users:create \
  -u username \
  -p password \
  -e email@example.com

# Or in development
python manage.py users:create -u username -p password -e email@example.com
```
{% endcode %}

### Managing Desks

{% stepper %}
{% step %}
Navigate to **Settings** → **Desks**
{% endstep %}

{% step %}
Click **"+ Add Desk"**
{% endstep %}

{% step %}
Configure desk name, working stages, and permissions
{% endstep %}

{% step %}
Assign users to the desk
{% endstep %}
{% endstepper %}

### Configuring Publishing Destinations

{% stepper %}
{% step %}
Go to **Settings** → **Publish**
{% endstep %}

{% step %}
Add subscribers and destinations
{% endstep %}

{% step %}
Configure output formats (NINJS, NewsML, etc.)
{% endstep %}

{% step %}
Set up transmit configurations
{% endstep %}
{% endstepper %}

## Development Quick Start

For developers wanting to customize or extend Superdesk:

### Backend Development

{% code title="Backend setup" %}
```bash
# Clone and set up
git clone https://github.com/superdesk/superdesk-core.git
cd superdesk-core
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Run in development mode
python manage.py app:run --reload
```
{% endcode %}

### Frontend Development

{% code title="Frontend setup" %}
```bash
# Clone and set up
git clone https://github.com/superdesk/superdesk-client-core.git
cd superdesk-client-core
npm install

# Run development server with hot reload
npm start
```
{% endcode %}

### Creating a Plugin

{% code title="Create plugin (example)" %}
```bash
# Create a new backend plugin
cd superdesk-core/apps
mkdir my_plugin
# Create __init__.py and implement your service

# Create a new frontend extension
cd superdesk-client-core/scripts/extensions
mkdir my-extension
# Create index.tsx and implement your React component
```
{% endcode %}

## Configuration Tips

### Essential Settings

Edit your `settings.py` (backend) or environment variables:

{% code title="Backend settings.py example" %}
```python
# Backend (settings.py)
MONGO_URI = 'mongodb://localhost/superdesk'
ELASTICSEARCH_URL = 'http://localhost:9200'
SECRET_KEY = 'your-secret-key-change-this'

# Enable features
PLANNING_MODULE_ENABLED = True
PUBLISH_ASSOCIATED_ITEMS = True
```
{% endcode %}

### Frontend Configuration

Create a `superdesk.config.js`:

{% code title="superdesk.config.js" %}
```javascript
module.exports = {
    apps: ['superdesk-core'],
    defaultRoute: '/workspace/monitoring',
    langOverride: {
        'en': {
            'Dashboard': 'My Dashboard'
        }
    }
};
```
{% endcode %}

## Next Steps

Now that you have Superdesk running:

* [User Guide](file:///docs/user-guide) - Learn how to use all features
* [Developer Guide](file:///docs/developer-guide/architecture) - Understand the architecture
* [API Reference](file:///docs/api) - Explore the REST API
* [Contributing](file:///docs/contributing) - Help improve Superdesk

## Getting Help

* **Documentation:** Browse this documentation site
* **GitHub Issues:** Report bugs on the specific repository
* **Community:** Join discussions on GitHub

## Clean Up (Docker)

When you're done testing:

{% code title="Stop and remove Docker services" %}
```bash
# Stop services
docker-compose down

# Remove volumes (deletes all data)
docker-compose down -v
```
{% endcode %}
