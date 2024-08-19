# React Native Flask Integration

## Project Overview
This project integrates a React Native frontend with a Flask backend, creating a powerful full-stack mobile application foundation. It combines the flexibility and performance of React Native for the mobile interface with the robustness and simplicity of Flask for the server-side logic.

## Integration Details

### Flask Backend
- Initialized with SQLite database
- Configured with SQLAlchemy for ORM
- Integrated Flask-Migrate for database migrations
- Logging configured for better debugging and monitoring

### React Native Frontend
- Based on the expo-supabase-starter template
- Utilizes Expo for easier development and deployment
- Implements NativeWind for styling
- Configured with Expo router for navigation

## Directory Structure
```
/react-native-flask
├── app.py (Flask backend entry point)
├── pyproject.toml (Python dependencies)
├── package.json (React Native dependencies)
├── [React Native files and directories]
```

## Key Changes Made
1. Updated `pyproject.toml`:
   - Set Python version to "^3.10"
   - Added Flask and related dependencies

2. Modified `package.json`:
   - Integrated expo-supabase-starter template
   - Added React Native and Expo dependencies

3. Created `app.py`:
   - Set up Flask application structure
   - Configured SQLAlchemy and Flask-Migrate

## Next Steps
1. Complete the integration of Flask backend with React Native frontend
2. Set up API endpoints in Flask to serve data to the React Native app
3. Configure environment variables for secure configuration management
4. Implement user authentication and authorization
5. Develop core features of the application
6. Set up CI/CD pipeline for automated testing and deployment

## Getting Started

### Prerequisites
- Node.js (v14 or later)
- Python (v3.10 or later)
- Poetry (for Python dependency management)
- Expo CLI

### Setup

1. Clone the repository:
   ```
   git clone <repository-url>
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

### Running the Application

1. Start the Flask backend:
   ```
   cd backend
   flask run
   ```

2. In a new terminal, start the React Native frontend:
   ```
   cd frontend
   expo start
   ```

3. Use the Expo Go app on your mobile device or an emulator to run the application.

### Development

- Flask backend runs on `http://localhost:5000`
- React Native frontend uses Expo for development
- Modify `app.py` for backend changes
- Edit React Native components in the `frontend/src` directory

Remember to keep both the backend and frontend running during development for full functionality.

## Contributing
[Guidelines for contributing to the project will be added here]

## License
[License information will be added here]
