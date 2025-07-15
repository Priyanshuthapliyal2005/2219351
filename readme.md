# URL Shortener - Assessment Project

A full-stack URL shortener application built with React, Node.js, Express, and MongoDB.

## 🚀 Features

- **URL Shortening**: Convert long URLs into short, manageable links
- **Custom Short Codes**: Option to create custom short codes or auto-generate them
- **Click Tracking**: Track clicks with detailed analytics including IP, user agent, and referrer
- **Expiration Management**: Set custom expiration times for URLs
- **Statistics Dashboard**: View comprehensive statistics for all shortened URLs
- **Health Monitoring**: Built-in health check endpoint
- **Rate Limiting**: Protection against abuse with configurable rate limiting
- **Security**: Helmet.js for security headers, CORS protection, and input validation

## 🏗️ Architecture

### Frontend
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite
- **Styling**: Tailwind CSS + Material-UI
- **HTTP Client**: Axios
- **Icons**: Lucide React + Material-UI Icons

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js 4.x
- **Database**: MongoDB with Mongoose ODM
- **Security**: Helmet.js, CORS, Express Rate Limit
- **Logging**: Morgan
- **Environment**: dotenv for configuration

## 📁 Project Structure

```
├── backend/
│   ├── models/
│   │   └── url.js           # MongoDB URL schema
│   ├── server.js            # Express server with all routes
│   ├── package.json         # Backend dependencies
│   └── .env                 # Environment variables
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── HealthStatus.tsx      # Health check component
│   │   │   ├── StatisticsTable.tsx   # Statistics display
│   │   │   └── UrlShortenerForm.tsx  # Main form component
│   │   ├── api.ts           # API client functions
│   │   ├── types.ts         # TypeScript type definitions
│   │   ├── App.tsx          # Main application component
│   │   └── main.tsx         # Application entry point
│   ├── package.json         # Frontend dependencies
│   └── vite.config.ts       # Vite configuration
│
└── README.md               # This file
```

## 🛠️ Installation & Setup

### Prerequisites
- Node.js (v18 or higher)
- MongoDB (local or cloud instance)
- npm or yarn package manager

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file with the following variables:
   ```env
   MONGODB_URI=mongodb://localhost:27017/urlshortener
   PORT=3001
   NODE_ENV=development
   CORS_ORIGIN=http://localhost:5173
   RATE_LIMIT_WINDOW_MS=900000
   RATE_LIMIT_MAX_REQUESTS=100
   DEFAULT_VALIDITY_MINUTES=30
   MAX_URLS_PER_REQUEST=5
   SHORTCODE_LENGTH=6
   MAX_SHORTCODE_LENGTH=10
   MIN_SHORTCODE_LENGTH=3
   ```

4. Start the backend server:
   ```bash
   npm start
   ```

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

## 🔧 Configuration

### Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `MONGODB_URI` | MongoDB connection string | Required |
| `PORT` | Backend server port | 3001 |
| `NODE_ENV` | Environment mode | development |
| `CORS_ORIGIN` | Allowed CORS origin | http://localhost:5173 |
| `RATE_LIMIT_WINDOW_MS` | Rate limit window in ms | 900000 (15 min) |
| `RATE_LIMIT_MAX_REQUESTS` | Max requests per window | 100 |
| `DEFAULT_VALIDITY_MINUTES` | Default URL expiration | 30 |
| `MAX_URLS_PER_REQUEST` | Max URLs per batch | 5 |
| `SHORTCODE_LENGTH` | Generated shortcode length | 6 |

## 📡 API Endpoints

### Health Check
- `GET /health` - Server health status

### URL Management
- `POST /api/shorturls` - Create short URLs
- `GET /api/shorturls` - Get all URLs with statistics
- `GET /api/shorturls/:shortcode` - Get specific URL statistics
- `DELETE /api/shorturls/:shortcode` - Delete a short URL

### URL Redirection
- `GET /r/:shortcode` - Redirect to original URL (with click tracking)

### API Request Examples

#### Create Short URL
```bash
POST /api/shorturls
Content-Type: application/json

{
  "urls": ["https://example.com"],
  "validity": 60,
  "shortcode": "custom123"
}
```

#### Get Statistics
```bash
GET /api/shorturls/abc123
```

## 🎨 Frontend Components

- **UrlShortenerForm**: Main form for creating short URLs
- **StatisticsTable**: Displays URL statistics in a table format
- **HealthStatus**: Shows backend server health status

## 🔐 Security Features

- **Helmet.js**: Security headers protection
- **CORS**: Cross-origin request protection
- **Rate Limiting**: Prevents abuse and DoS attacks
- **Input Validation**: URL and shortcode validation
- **Error Handling**: Comprehensive error responses

## 📊 Analytics & Tracking

The application tracks the following metrics for each short URL:
- Total click count
- Click timestamps
- User IP addresses
- User agents
- Referrer information
- Clicks by hour distribution
- Recent click history

## 🚀 Development

### Running in Development Mode

1. Start the backend:
   ```bash
   cd backend && npm start
   ```

2. Start the frontend:
   ```bash
   cd frontend && npm run dev
   ```

3. Access the application at `http://localhost:5173`

### Building for Production

1. Build the frontend:
   ```bash
   cd frontend && npm run build
   ```

2. The backend can be deployed as-is with proper environment variables

## 🧪 Testing

Currently, the project uses basic validation and error handling. Future improvements could include:
- Unit tests for components and API endpoints
- Integration tests for the full application flow
- E2E tests using tools like Cypress or Playwright

## 📝 Future Enhancements

- User authentication and authorization
- Custom domains for short URLs
- QR code generation
- Bulk URL operations
- Enhanced analytics dashboard
- API rate limiting per user
- URL preview functionality
- Export statistics to CSV/PDF

## 📄 License

This project is created for assessment purposes.

## 👤 Author

Assessment Project - URL Shortener Application

---

**Note**: This is an assessment project demonstrating full-stack web development skills with modern technologies including React, TypeScript, Node.js, Express, and MongoDB.
