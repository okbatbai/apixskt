# API XSMB Today

> API để lấy kết quả xổ số miền Bắc từ [https://apixskt-1.onrender.com/api/v1](https://apixskt-1.onrender.com/api/v1)

## 📋 Prerequisites

- Node.js v14 or higher
- npm or yarn
- Git

## 🚀 Installation

### 1. Clone the repository
```bash
git clone https://github.com/[your-username]/api-xsmb-today.git
cd api-xsmb-today
```

### 2. Install dependencies
```bash
npm install
```

### 3. Setup environment variables
```bash
# Copy the example env file
cp .env.example .env

# Edit .env and add your configuration
# Important: Set the URL variable with your target website
```

### 4. Configure `.env` file
```env
PORT=3000
URL=https://your-target-website.com
NODE_ENV=development
```

## 💻 Development

### Run in development mode (with auto-reload)
```bash
npm run dev
```

### Run in production mode
```bash
npm start
```

## 🌐 Deployment

### Deploy to Render.com

1. Push code to GitHub
2. Connect GitHub repo to Render
3. Add environment variables in Render Dashboard:
   - `URL`: Your target website URL
   - `PORT`: (Auto-provided by Render)
4. Deploy

### Deploy to other platforms

See documentation for:
- Vercel
- Railway
- Heroku
- Docker

## 📡 API Endpoints

### Get lottery results
```
GET /api/v1
```

**Response format:**
```json
{
  "countNumbers": 27,
  "time": "26/09/2025",
  "results": {
    "ĐB": ["12345"],
    "G1": ["67890"],
    "G2": ["11111", "22222"],
    "G3": ["33333", "44444", "55555", "66666", "77777", "88888"],
    "G4": ["1234", "5678", "9012", "3456"],
    "G5": ["7890", "2345", "6789", "0123", "4567", "8901"],
    "G6": ["123", "456", "789"],
    "G7": ["01", "23", "45", "67"]
  }
}
```

### Health check
```
GET /api/v1/health
```

## 📊 Response Keys

| Keys | Type         | Description |
| ---- | ------------ | ----------- |
| time | String       | Date of lottery results |
| ĐB   | Array String | Special prize |
| G1   | Array String | First prize |
| G2   | Array String | Second prize (2 numbers) |
| G3   | Array String | Third prize (6 numbers) |
| G4   | Array String | Fourth prize (4 numbers) |
| G5   | Array String | Fifth prize (6 numbers) |
| G6   | Array String | Sixth prize (3 numbers) |
| G7   | Array String | Seventh prize (4 numbers) |

## 🛠 Technologies

- **Node.js** - Runtime environment
- **Express** - Web framework
- **Cheerio** - Web scraping
- **Axios** - HTTP client
- **Cors** - CORS middleware
- **Dotenv** - Environment variables

## 📝 Environment Variables

| Variable | Description | Required |
| -------- | ----------- | -------- |
| `PORT` | Server port (default: 3000) | No |
| `URL` | Target website URL for scraping | **Yes** |
| `NODE_ENV` | Environment (development/production) | No |

## 🐛 Troubleshooting

### Error: ERR_INVALID_ARG_TYPE
- **Cause:** URL environment variable not set
- **Solution:** Add URL to your .env file or environment variables

### Error: ECONNREFUSED
- **Cause:** Cannot connect to target website
- **Solution:** Check if the target URL is correct and accessible

### Error: No data found
- **Cause:** HTML structure changed or selectors outdated
- **Solution:** Update the selectors in `controllers/mainController.js`

## 📄 License

ISC

## 👤 Author

Your Name

## 🤝 Contributing

Contributions, issues and feature requests are welcome!

## ⭐️ Show your support

Give a ⭐️ if this project helped you!
