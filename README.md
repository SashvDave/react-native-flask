# AI-Developer with React Native Flask Integration

## Project Overview
This project combines a Go server utilizing the Gin framework, GORM ORM library, and Asynq for task management, along with a Next.js based GUI. It also integrates a React Native frontend with a Flask backend, creating a powerful full-stack mobile application foundation. This combination offers the flexibility and performance of React Native for the mobile interface with the robustness of Flask for the server-side logic.

## Core Components

### Go Server (AI-Developer)
- Utilizes Gin framework for HTTP routing
- Implements GORM for object-relational mapping
- Uses Asynq for task management
- Includes a Next.js based GUI

### React Native Frontend
- Based on the expo-supabase-starter template
- Utilizes Expo for easier development and deployment
- Implements NativeWind for styling
- Configured with Expo router for navigation

### Flask Backend
- Initialized with SQLite database
- Configured with SQLAlchemy for ORM
- Integrated Flask-Migrate for database migrations
- Logging configured for better debugging and monitoring

## Directory Structure
```
/
├── [Go server files and directories]
├── [Next.js GUI files]
└── react-native-flask/
    ├── app.py (Flask backend entry point)
    ├── pyproject.toml (Python dependencies)
    ├── package.json (React Native dependencies)
    └── [React Native files and directories]
```

## Prerequisites
Before you proceed, ensure that you have the following installed on your system:
- Docker and Docker Compose
- `direnv`
- Node.js (v14 or later)
- Python (v3.10 or later)
- Poetry (for Python dependency management)
- Expo CLI

### Installing Direnv
To handle environment variables more efficiently, install `direnv`:
```bash
# For macOS
brew install direnv

# For Ubuntu
sudo apt-get install direnv
```

After installation, hook direnv into your shell:

```bash
echo 'eval "$(direnv hook bash)"' >> ~/.bashrc
source ~/.bashrc
```

If you are using a shell other than bash, replace bash with your specific shell (e.g., zsh or fish).

## Setup

### 1. Environment Configuration
Create a .envrc file in the root directory of your project and populate it with the necessary environment variables:
```bash
export AI_DEVELOPER_GITNESS_TOKEN=
export AI_DEVELOPER_GITNESS_URL=https://gitness:3000
export AI_DEVELOPER_GITNESS_HOST=gitness:3000
export AI_DEVELOPER_GITNESS_USER=
export AI_DEVELOPER_OPENAI_API_KEY=
export AI_DEVELOPER_WORKSPACE_WORKING_DIR=/workspaces
export AI_DEVELOPER_WORKSPACE_TEMPLATE_DIR=/templates/python
export AI_DEVELOPER_WORKSPACE_SERVICE_ENDPOINT=http://ws:8080
export AI_DEVELOPER_APP_URL=
export AI_DEVELOPER_GITNESS_PASSWORD=admin
export AI_DEVELOPER_GITNESS_USER=admin
export AI_DEVELOPER_GITHUB_CLIENT_SECRET=
export AI_DEVELOPER_GITHUB_CLIENT_ID=

export NEW_RELIC_ENABLED=false

export WORKSPACES_GITNESS_USER=
export WORKSPACES_GITNESS_TOKEN=
```

To allow direnv to load these settings, run:

```bash
direnv allow .
```

### 2. Build and Run the Go Server, Asynq worker, and Postgres

To build and run the Go server, Asynq worker, and Postgres, execute the following command:

```bash
docker-compose up --build
```

You can now access the UI at http://localhost:3000.

### 3. Set up the React Native Flask Integration

1. Navigate to the React Native Flask directory:
   ```
   cd react-native-flask
   ```

2. Set up the Flask backend:
   ```
   cd backend
   poetry install
   poetry shell
   flask db upgrade
   ```

3. Set up the React Native frontend:
   ```
   cd ../frontend
   npm install
   ```

## Running the Application

1. Start the Go server and related services (if not already running):
   ```
   docker-compose up
   ```

2. Start the Flask backend:
   ```
   cd react-native-flask/backend
   flask run
   ```

3. In a new terminal, start the React Native frontend:
   ```
   cd react-native-flask/frontend
   expo start
   ```

4. Use the Expo Go app on your mobile device or an emulator to run the React Native application.

## Development

- Go server and related services run in Docker containers
- Flask backend runs on `http://localhost:5000`
- React Native frontend uses Expo for development
- Modify Go files for AI-Developer changes
- Modify `app.py` for Flask backend changes
- Edit React Native components in the `frontend/src` directory

Remember to keep all necessary services running during development for full functionality.

## Next Steps
1. Complete the integration of Flask backend with React Native frontend
2. Set up API endpoints in Flask to serve data to the React Native app
3. Configure environment variables for secure configuration management
4. Implement user authentication and authorization
5. Develop core features of the application
6. Set up CI/CD pipeline for automated testing and deployment

## Contributing
[Guidelines for contributing to the project will be added here]

## License
[License information will be added here]
