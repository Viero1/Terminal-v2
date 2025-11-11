# MRKT AI Terminal - Real-Time Trading Platform

Advanced AI-powered trading terminal dengan real-time candlestick charts, technical analysis, dan market intelligence. Berjalan di browser (desktop, tablet, mobile) dan bisa ditambahkan ke home screen iOS sebagai PWA.

## 🚀 Fitur

- **Real-Time Chart**: Candlestick yang bergerak setiap detik tanpa repainting
- **Multi-Timeframe**: 1m, 5m, 15m, 1h, 4h, Daily
- **Technical Indicators**: RSI, MACD, Moving Averages, ADX
- **AI Setup Analysis**: Trend, Volatility, Volume trends
- **Entry Zones**: Dengan confidence level dan risk/reward ratio
- **TP/SL Levels**: Automatic calculation dengan multiple targets
- **PWA Support**: Add to home screen di iOS/Android sebagai aplikasi native

## 📱 Akses dari iPad/iPhone

### Langsung di Browser
1. Buka URL di Safari/Chrome
2. Terminal langsung bisa digunakan
3. Share → Add to Home Screen untuk seperti aplikasi

### Karakteristik iOS
- Optimized untuk semua ukuran layar (iPhone, iPad)
- Notch-safe dan gesture navigation compatible
- Offline support dengan cached data
- Battery-efficient WebSocket heartbeat

## 🛠️ Deploy ke Vercel (Frontend Hosting)

### Step 1: Buat Repository di GitHub
- Buka github.com → New repository → "mrkt-terminal-frontend"
- Upload file: index.html, manifest.json, package.json, .gitignore

### Step 2: Deploy ke Vercel
- Buka vercel.com → New Project
- Import Git Repository → pilih "mrkt-terminal-frontend"
- Deploy (tunggu ~2-5 menit)
- Vercel memberikan domain publik

### Step 3: Add to Home Screen (iOS)
- Buka domain Vercel di Safari
- Share → Add to Home Screen
- Aplikasi siap di home screen seperti native app

## 🔄 Integrasi Backend (Optional)

Saat siap menghubungkan backend API:

1. Deploy backend Node.js ke Railway/Render dengan WebSocket support
2. Di Vercel Settings, tambahkan Environment Variables:
   - `REACT_APP_API_URL` = `https://your-api.railway.app/v1`
   - `REACT_APP_WS_URL` = `wss://your-api.railway.app/v1/stream`
3. Redeploy Vercel

## 📊 Data Realtime (Sekarang)

Terminal menggunakan simulated real-time data:
- Tick generator di browser (1 detik interval)
- OHLC aggregation otomatis per timeframe
- Indicator calculation client-side
- Entry zone dan TP/SL calculation otomatis

Saat backend terhubung, data akan replace dengan live feeds dari:
- Broker WebSocket (Interactive Brokers, Alpaca, Binance)
- Market data providers (EODHD, Finnhub, dll)
- Economic calendar dan news feeds

## 🔧 Teknologi

- **Frontend**: HTML5 + CSS3 + Vanilla JavaScript
- **Chart**: Canvas 2D rendering dengan smooth animations
- **PWA**: Service Worker untuk offline + install to home screen
- **Responsive**: Grid layout untuk desktop, tablet, mobile
- **Dark Theme**: OLED-friendly dark mode untuk iOS

## 📈 Candlestick Chart Details

- Tick-by-tick price updates (1 detik per tick)
- OHLCV aggregation dengan volume bars
- Support/Resistance levels dengan price bands
- Multi-timeframe candle stacking
- Smooth wick dan body rendering
- Grid lines untuk readability
- Current price crosshair line

## 🔔 Real-Time Updates

- **Live Ticks**: Bid/Ask update setiap detik
- **Candle Forming**: Current candle updates in real-time
- **Indicators**: RSI, MACD, MA recalculate per tick
- **Entry Zones**: Update confidence seiring price bergerak
- **Setup Analysis**: Trend strength dan volatility refresh
- **No Repainting**: Signals bertimestamp fixed, hanya status yang berubah

## 📱 iOS Compatibility

- **Minimum**: iOS 13.4+ (PWA support)
- **Recommended**: iOS 15+
- **Browser**: Safari, Chrome (mobile)
- **Screen**: Iphone 6s+ dan iPad mini 4+
- **Notch**: Safe area inset support untuk notched devices

## 🎨 Customization

Edit `index.html` untuk mengubah:
- Warna tema (CSS variables dalam `:root`)
- Chart styling (canvas rendering parameters)
- Panel layout (grid layout di `.panels-wrap`)
- Font dan typography

## 🚫 Limitations iOS PWA

- WebSocket di background akan pause (reconnect otomatis saat foreground)
- Storage PWA terbatas (~50MB)
- Background fetch/sync minimal
- Gunakan server untuk storage histori, bukan device storage

## 🔐 Security Notes

- Untuk production, gunakan HTTPS (Vercel/Netlify default)
- JWT tokens disimpan di memory, bukan localStorage saat ada backend
- CORS properly configured untuk cross-origin requests

## 📚 Dokumentasi Lengkap

Lihat folder `docs/` untuk:
- API Specification
- Backend Implementation Guide
- Database Setup Instructions
- Troubleshooting Guide

## 🤝 Support

- GitHub Issues: https://github.com/yourusername/mrkt-terminal-frontend/issues
- Email: support@mrktedge.ai

## 📄 License

MIT License

---

**Last Updated**: November 11, 2025  
**Version**: 1.0.0 (Mobile-First Release)
