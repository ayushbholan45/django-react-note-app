# React Django App

A full-stack note-taking application built with Django REST Framework backend and React with Vite frontend. Features user authentication with JWT tokens and CORS support for cross-origin requests.

## Project Structure

```
react-django-app/
├── backend/                 # Django REST API
│   ├── api/                # Main API app
│   │   ├── models.py       # Database models (Note model)
│   │   ├── views.py        # API views
│   │   ├── serializers.py  # DRF serializers
│   │   ├── urls.py         # API routes
│   │   └── migrations/     # Database migrations
│   ├── backend/            # Django project settings
│   │   ├── settings.py     # Configuration
│   │   ├── urls.py         # Root URL routing
│   │   └── wsgi.py         # WSGI config for deployment
│   ├── manage.py           # Django management
│   ├── requirements.txt    # Python dependencies
│   └── Procfile            # Deployment configuration
├── frontend/               # React + Vite application
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── pages/          # Page components
│   │   ├── styles/         # CSS files
│   │   ├── api.js          # Axios API client
│   │   ├── App.jsx         # Main app component
│   │   └── main.jsx        # Entry point
│   ├── package.json        # Node dependencies
│   └── vite.config.js      # Vite configuration
└── env/                    # Python virtual environment
```

## Tech Stack

### Backend
- **Django 6.0.3** - Web framework
- **Django REST Framework 3.17.1** - REST API toolkit
- **djangorestframework_simplejwt 5.5.1** - JWT authentication
- **django-cors-headers 4.9.0** - CORS support
- **PostgreSQL** - Database (via psycopg2)
- **Gunicorn** - WSGI application server
- **python-dotenv** - Environment variable management

### Frontend
- **React 19.2.4** - UI library
- **Vite 8.0.1** - Build tool and dev server
- **React Router 7.13.2** - Client-side routing
- **Axios 1.14.0** - HTTP client
- **jwt-decode 4.0.0** - JWT token decoding

## Getting Started

### Prerequisites
- Python 3.13+
- Node.js 16+
- pip and npm package managers

### Backend Setup

1. **Navigate to backend directory:**
   ```bash
   cd backend
   ```

2. **Create and activate virtual environment:**
   ```bash
   python -m venv ../env
   source ../env/bin/activate  # On Windows: ..\env\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Apply migrations:**
   ```bash
   python manage.py migrate
   ```

5. **Create superuser (optional):**
   ```bash
   python manage.py createsuperuser
   ```

6. **Run development server:**
   ```bash
   python manage.py runserver
   ```
   Server runs on: `http://localhost:8000`

### Frontend Setup

1. **Navigate to frontend directory:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start development server:**
   ```bash
   npm run dev
   ```
   Application runs on: `http://localhost:5173`

## Running the Application

### Development Mode

**Terminal 1 - Backend:**
```bash
cd backend
source ../env/bin/activate
python manage.py runserver
```

**Terminal 2 - Frontend:**
```bash
cd frontend
npm run dev
```

### Building for Production

**Backend:**
```bash
gunicorn backend.wsgi
```

**Frontend:**
```bash
npm run build
npm run preview
```

## API Endpoints

The backend provides REST API endpoints for:
- User authentication (login, register)
- Notes CRUD operations
- Protected endpoints with JWT authentication

## Features

- User authentication with JWT tokens
- CORS-enabled for frontend integration
- Note creation, reading, updating, and deletion
- Protected routes requiring authentication
- Responsive React components
- Modern build tooling with Vite

## Environment Variables

Create a `.env` file in the backend directory if needed for:
- Database configuration
- Secret key management
- CORS allowed origins
- Other sensitive configuration

## Troubleshooting

### Backend issues
- Ensure Python version is 3.13+
- Verify virtual environment is activated
- Check database migrations: `python manage.py migrate`

### Frontend issues
- Clear node_modules and reinstall: `rm -rf node_modules && npm install`
- Clear Vite cache: `rm -rf .vite`


