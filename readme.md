# URL Shortener

A simple URL shortener built with React and Node.js.

## Screenshots

<img width="1919" height="939" alt="Screenshot 2025-07-15 121734" src="https://github.com/user-attachments/assets/07136264-647b-4379-85f8-f913b4229004" />
<img width="1881" height="961" alt="Screenshot 2025-07-15 121742" src="https://github.com/user-attachments/assets/7ff122e8-483c-4e88-b259-dec812071184" />
<img width="1193" height="455" alt="Screenshot 2025-07-15 121724" src="https://github.com/user-attachments/assets/7419e651-0ab9-4b74-b718-3bdfc04da303" />

https://github.com/user-attachments/assets/25da0795-da1c-46f3-b898-4353565a7ffd

## What it does

- Shortens long URLs
- Custom short codes or auto-generated ones
- Click tracking and statistics
- Expiration dates for URLs
- Health monitoring

## Tech Stack

**Frontend:**
- React with TypeScript
- Material-UI for styling
- Vite for building
- Axios for API calls

**Backend:**
- Node.js with Express
- MongoDB for database
- Rate limiting for security

**Logging:**
- Custom middleware for evaluation service

## Project Structure

```
backend/
  - server.js (main server file)
  - models/url.js (database model)
  - package.json

frontend/
  - src/
    - components/ (React components)
    - api.ts (API calls)
    - logger.ts (logging)
  - package.json

logging-middleware/
  - logger.js (evaluation service logging)
```

## Setup

### Backend
1. Go to backend folder: `cd backend`
2. Install: `npm install`
3. Create `.env` file:
   ```
   MONGODB_URI=your_mongodb_connection
   PORT=3001
   ACCESS_TOKEN=your_evaluation_service_token
   ```
4. Start: `npm start`

### Frontend  
1. Go to frontend folder: `cd frontend`
2. Install: `npm install`
3. Create `.env` file:
   ```
   VITE_ACCESS_TOKEN=your_evaluation_service_token
   VITE_API_BASE_URL=http://localhost:3001
   ```
4. Start: `npm run dev`

## API Endpoints

- `POST /api/shorten` - Create short URL
- `GET /api/shorturls` - Get all URLs  
- `GET /r/:shortcode` - Redirect to original URL
- `GET /health` - Health check

## Environment Variables

**Backend:**
- `MONGODB_URI` - Database connection
- `ACCESS_TOKEN` - Evaluation service token
- `PORT` - Server port (default 3001)
- `CORS_ORIGIN` - Frontend URL

**Frontend:**
- `VITE_ACCESS_TOKEN` - Evaluation token
- `VITE_API_BASE_URL` - Backend URL
## Logging

The app sends logs to the evaluation service for tracking. It logs things like:
- API requests and responses
- Errors and warnings  
- User actions

## Development

To run both frontend and backend:
1. Start backend: `cd backend && npm start`
2. Start frontend: `cd frontend && npm run dev`
3. Open http://localhost:5173

## Deployment

You can deploy this to:
- **Backend**: Render, Heroku, Railway
- **Frontend**: Vercel, Netlify

Make sure to set all the environment variables on your hosting platform.

---

*Built for campus hiring evaluation*
