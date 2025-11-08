# Image Optimizer

A full-stack web application for optimizing images through compression while maintaining visual quality. Built with React (frontend) and Flask (backend), this tool helps developers and designers optimize images for better web performance.

## Features

- Interactive web interface for image optimization
- Real-time quality adjustment with preview
- Side-by-side comparison of original and optimized images
- File size reduction information
- Support for common image formats (JPEG, PNG)
- Cross-Origin Resource Sharing (CORS) enabled
- Error handling and validation

## Tech Stack

### Frontend (`/imageoptimizer.web`)
- React 18.3
- Vite
- Modern CSS with flexbox/grid
- ESLint for code quality

### Backend (`/imageoptimizer.app`)
- Flask
- OpenCV
- Pillow (Python Imaging Library)
- NumPy
- Flask-CORS

## Installation

### Prerequisites
- Python 3.8 or higher
- Node.js 16.0 or higher
- npm or yarn

### Backend Setup

1. Navigate to the backend directory:
```bash
cd imageoptimizer.app
```

2. Create and activate a virtual environment:
```bash
# Windows
python -m venv venv
.\venv\Scripts\activate

# Unix/macOS
python3 -m venv venv
source venv/bin/activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Run the Flask server:
```bash
python run.py
```
The backend will start on http://127.0.0.1:5000

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd imageoptimizer.web
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```
The frontend will start on http://localhost:5173

## Project Structure

### Frontend Structure
```
imageoptimizer.web/
├── src/
│   ├── App.jsx           # Main application component
│   ├── App.css           # Main styles
│   ├── main.jsx         # Application entry point
│   └── assets/          # Static assets
├── public/              # Public assets
├── index.html           # HTML template
└── package.json        # Project dependencies and scripts
```

### Backend Structure
```
imageoptimizer.app/
├── app/
│   ├── __init__.py     # Flask app initialization
│   ├── routes.py       # API endpoints
│   └── templates/      # HTML templates
├── requirements.txt    # Python dependencies
└── run.py             # Application entry point
```

## API Endpoints

### POST /upload
Optimizes a single image
- Request: Multipart form data
  - `image`: Image file
  - `quality`: Integer (0-100)
- Response: Optimized image file
- Error Handling: Returns JSON with error message on failure

## Development Guidelines

### Frontend Development
1. Components follow functional approach with React Hooks
2. Use ESLint for code quality (`npm run lint`)
3. CSS follows BEM naming convention
4. Image processing is handled by backend API

### Backend Development
1. Follow PEP 8 style guide
2. Error handling with proper logging
3. Input validation for all API endpoints
4. Use Flask blueprints for scalability

## Building for Production

### Frontend
```bash
cd imageoptimizer.web
npm run build
```
Production files will be in the `dist` directory

### Backend
1. Set `DEBUG=False` in production
2. Use a production WSGI server (e.g., Gunicorn)
3. Configure proper CORS settings for production

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License.

## Authors

- Maxdacoder1

## Troubleshooting

### Common Issues
1. CORS errors: Check if the backend CORS settings match your frontend URL
2. Image upload fails: Verify file size and format restrictions
3. Backend connection refused: Ensure Flask server is running
4. npm dependencies issues: Try clearing npm cache and reinstalling

### Debug Mode
- Frontend: Run with `npm run dev`
- Backend: Set `debug=True` in `run.py`
