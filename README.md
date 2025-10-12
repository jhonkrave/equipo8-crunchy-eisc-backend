# 🎬 Crunchy EISC Backend

A modern backend built with Express.js and TypeScript that integrates the Pexels API to provide access to popular videos and search functionality.

## ✨ Features

- 🎥 **Popular Videos**: Get the most popular videos from Pexels
- 🔍 **Video Search**: Search for videos by specific terms
- 🚀 **RESTful API**: Well-structured and documented endpoints
- 🛡️ **CORS Configured**: Support for multiple origins
- 📝 **TypeScript**: Typed and maintainable code
- ⚡ **Error Handling**: Consistent error responses

## 🚀 Installation

### Prerequisites

- Node.js (version 16 or higher)
- npm or yarn
- Pexels API Key

### Steps

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd crunchy-eisc-backend
   ```

2. **Switch to the development branch**
   ```bash
   git checkout dev
   ```
   
   ⚠️ **Important**: Make sure you're on the `dev` branch before starting the application.

3. **Install dependencies**
   ```bash
   npm install
   ```

4. **Configure environment variables**
   
   Create a `.env` file in the project root:
   ```env
   PORT=3000
   PEXELS_API_KEY=your_pexels_api_key
   ORIGIN=http://localhost:3000,http://localhost:3001
   ```

5. **Get your Pexels API Key**
   - Go to [Pexels API](https://www.pexels.com/api/)
   - Sign up or log in
   - Generate your free API key

6. **Run the server**
   ```bash
   npm run dev
   ```

## 📚 API Endpoints

### Health Check
```http
GET /
```
**Response:** `"Server running"`

### Popular Videos
```http
GET /videos/popular
```
**Description:** Gets the most popular videos from Pexels

**Response:**
```json
{
  "page": 1,
  "per_page": 3,
  "total_results": 1000,
  "url": "...",
  "videos": [
    {
      "id": 123456,
      "width": 1920,
      "height": 1080,
      "duration": 30,
      "url": "...",
      "image": "...",
      "user": {
        "id": 123,
        "name": "User",
        "url": "..."
      },
      "video_files": [...],
      "video_pictures": [...]
    }
  ]
}
```

### Video Search
```http
POST /videos/search
Content-Type: application/json

{
  "query": "nature"
}
```
**Description:** Search for videos by specific term

**Parameters:**
- `query` (string): Search term

**Response:** Similar to popular videos but with search results

## 🛠️ Technologies Used

- **Node.js** - JavaScript runtime
- **Express.js** - Web framework for Node.js
- **TypeScript** - Typed superset of JavaScript
- **Pexels API** - Official Pexels API
- **CORS** - Cross-Origin Resource Sharing middleware
- **dotenv** - Environment variables loader

## 📁 Project Structure

```
crunchy-eisc-backend/
├── api/
│   └── index.ts          # Main server and endpoints
├── node_modules/         # Dependencies
├── .env                  # Environment variables (create)
├── package.json          # Project configuration
├── package-lock.json     # Dependencies lock file
├── tsconfig.json         # TypeScript configuration
└── README.md            # This file
```

## 🔧 Available Scripts

```bash
# Development
npm run dev          # Run server in development mode

# Production
npm start           # Run server in production mode

# TypeScript
npm run build       # Compile TypeScript to JavaScript
```

## 🌐 CORS Configuration

The server is configured to handle multiple origins through the `ORIGIN` environment variable:

```env
ORIGIN=http://localhost:3000,http://localhost:3001,https://your-domain.com
```

## 📝 Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `PORT` | Server port | `3000` |
| `PEXELS_API_KEY` | Pexels API Key | `your_api_key_here` |
| `ORIGIN` | Allowed origins (comma-separated) | `http://localhost:3000,https://app.com` |

## 🚨 Error Handling

All endpoints handle errors consistently:

```json
{
  "error": "Error description"
}
```

**Status codes:**
- `200` - Success
- `500` - Internal server error


## 🔗 Useful Links

- [Pexels API Documentation](https://www.pexels.com/api/documentation/)
- [Express.js Documentation](https://expressjs.com/)
- [TypeScript Documentation](https://www.typescriptlang.org/)

## 👨‍💻 Authors

**John Lourido - 1124153**
