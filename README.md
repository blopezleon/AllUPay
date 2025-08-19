# AlluPay Landing Page with MongoDB

A modern landing page for AlluPay with user signup functionality and MongoDB database integration.

## Features

- Responsive landing page with interactive elements
- User signup form with modal popup
- MongoDB database integration
- RESTful API endpoints
- Real-time data storage

## Setup Instructions

### Prerequisites

1. **Node.js** (v14 or higher)
2. **MongoDB** (local or cloud)

### Installation

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Set up MongoDB:**
   
   **Option A: Local MongoDB**
   - Install MongoDB locally
   - Start MongoDB service
   - The app will connect to `mongodb://localhost:27017/allupay`

   **Option B: MongoDB Atlas (Cloud)**
   - Create a free account at [MongoDB Atlas](https://www.mongodb.com/atlas)
   - Create a cluster and get your connection string
   - Update `config.env` with your MongoDB Atlas URI

3. **Configure environment variables:**
   ```bash
   # Copy the example config
   cp config.env .env
   
   # Edit .env with your MongoDB connection string
   MONGODB_URI=your_mongodb_connection_string
   ```

4. **Start the server:**
   ```bash
   # Development mode (with auto-restart)
   npm run dev
   
   # Production mode
   npm start
   ```

5. **Access the application:**
   - Open your browser and go to `http://localhost:3000`

## API Endpoints

- `GET /` - Serve the landing page
- `POST /api/signup` - Save user signup data
- `GET /api/users` - Get all users (for admin)
- `GET /api/health` - Health check

## Database Schema

```javascript
{
  name: String (required),
  email: String (required, unique),
  company: String (optional),
  timestamp: Date (auto-generated)
}
```

## Testing the Signup Form

1. Open the landing page
2. Click any "Get Started" button
3. Fill out the form with test data
4. Submit and check the console for confirmation
5. Verify data is saved in MongoDB

## Viewing Stored Data

You can view all signups by visiting:
- `http://localhost:3000/api/users` (JSON format)
- Or use MongoDB Compass to view the database directly

## Deployment

For production deployment:
1. Set up a production MongoDB instance
2. Configure environment variables
3. Deploy to your preferred hosting platform (Heroku, Vercel, etc.)
4. Update the frontend API calls to use your production URL

## Technologies Used

- **Frontend:** HTML, CSS (Tailwind), JavaScript
- **Backend:** Node.js, Express.js
- **Database:** MongoDB with Mongoose
- **Charts:** Chart.js
