# GBP/USD Real-time Analysis and Prediction System

A comprehensive system that analyzes news, live events, and market sentiment to predict GBP/USD exchange rate movements. The system monitors financial news sources, Federal Reserve and Bank of England announcements, and uses advanced machine learning to generate predictions every 5 minutes.

## 🚀 Features

### Real-time News Analysis
- **Multi-source News Monitoring**: Automatically scrapes financial news from Reuters, Bloomberg, BBC Business, Financial Times, and MarketWatch
- **Advanced Sentiment Analysis**: Uses transformer-based models (RoBERTa) for accurate sentiment scoring
- **Relevance Filtering**: Intelligent filtering to focus on news that actually impacts GBP/USD

### Live Event Monitoring
- **Central Bank Tracking**: Monitors Federal Reserve and Bank of England announcements in real-time
- **Economic Indicators**: Tracks key economic data releases (CPI, GDP, Employment, etc.)
- **Event Impact Scoring**: Calculates potential market impact of upcoming events

### AI-Powered Predictions
- **Enhanced LSTM Model**: Combines traditional price data with news sentiment for better predictions
- **Multi-timeframe Forecasts**: Generates predictions for 1-hour, 4-hour, and 24-hour horizons
- **Confidence Scoring**: Provides confidence levels based on data quality and market conditions

### Real-time Dashboard
- **Live Data Visualization**: Interactive charts showing price movements, sentiment trends, and predictions
- **News Feed**: Real-time display of relevant news with sentiment scores
- **Event Calendar**: Upcoming high-impact economic events
- **System Controls**: Start/stop monitoring and trigger manual updates

### Data Persistence
- **Historical Storage**: SQLite database storing all news, events, and predictions
- **Performance Tracking**: Monitor prediction accuracy over time
- **Comprehensive Logging**: Detailed system logs for troubleshooting

## 📋 Requirements

- Python 3.8 or higher
- Internet connection for data fetching
- ~2GB disk space for historical data

## 🛠️ Installation

### Quick Setup
```bash
# Clone or download the system files
cd gbptousd

# Run the setup script
python setup_and_run.py setup
```

### Manual Installation
```bash
# Install dependencies
pip install -r requirements.txt

# Initialize the system
python -c "from news_analyzer import NewsAnalyzer; NewsAnalyzer()"
```

## 🚀 Usage

### Start the Complete System
```bash
# Run both analysis system and web dashboard
python setup_and_run.py both
```

### Individual Components
```bash
# Run only the analysis system (terminal output)
python setup_and_run.py run

# Run only the web dashboard
python setup_and_run.py dashboard
```

### Access the Dashboard
Open your browser and go to: **http://localhost:5000**

## 📊 System Components

### 1. News Analyzer (`news_analyzer.py`)
- Fetches news from multiple RSS feeds
- Performs sentiment analysis using NLP models
- Calculates relevance scores for GBP/USD impact
- Stores processed news in database

### 2. Enhanced Predictor (`enhanced_predictor.py`)
- LSTM neural network trained on historical price data
- Integrates news sentiment for enhanced predictions
- Provides multi-timeframe forecasts with confidence levels
- Handles model training and persistence

### 3. Event Monitor (`event_monitor.py`)
- Monitors Federal Reserve announcements and speeches
- Tracks Bank of England policy decisions
- Collects economic calendar data
- Calculates event impact scores

### 4. Real-time System (`real_time_system.py`)
- Orchestrates all components
- Runs update cycles every 5 minutes
- Manages data collection and prediction generation
- Handles system metrics and error recovery

### 5. Web Dashboard (`dashboard.py`)
- Flask-based web interface
- Real-time charts and data visualization
- System control interface
- Live updates via WebSocket

## 📈 How It Works

### 5-Minute Update Cycle
1. **News Collection**: Fetch latest news from all sources
2. **Event Monitoring**: Check for new central bank announcements
3. **Market Data**: Get current GBP/USD price and technical indicators
4. **Sentiment Analysis**: Process news sentiment and relevance
5. **Prediction Generation**: Combine LSTM predictions with sentiment
6. **Data Storage**: Save all data for historical analysis
7. **Dashboard Update**: Push updates to connected web clients

### Prediction Algorithm
The system uses a multi-layer approach:

1. **Base LSTM Model**: Trained on historical price data with technical indicators
2. **Sentiment Integration**: Adjusts predictions based on news sentiment
3. **Event Impact**: Modifies forecasts based on upcoming high-impact events
4. **Confidence Calculation**: Determines prediction reliability

## 📊 Data Sources

### News Sources
- **Reuters**: Business news and forex updates
- **Bloomberg**: Financial market news
- **BBC Business**: UK economic news
- **Financial Times**: Global financial news
- **MarketWatch**: Real-time market news

### Central Bank Sources
- **Federal Reserve**: Press releases and speeches
- **Bank of England**: Policy announcements and minutes

### Market Data
- **Yahoo Finance**: Real-time GBP/USD price data and historical charts

## 🎯 Use Cases

### For Traders
- Get early signals on potential GBP/USD movements
- Monitor market sentiment in real-time
- Track high-impact events that could move the market
- Use predictions as part of trading strategy

### For Analysts
- Research correlation between news sentiment and price movements
- Analyze the impact of central bank communications
- Track prediction accuracy over time
- Study market reaction patterns

### For Researchers
- Access to clean, processed financial news data
- Sentiment analysis on financial texts
- Database of events and their market impact
- Machine learning model for forex prediction

## ⚙️ Configuration

### Update Frequency
By default, the system updates every 5 minutes. You can modify this in `real_time_system.py`:
```python
self.update_interval = 5  # Change to desired minutes
```

### News Sources
Add or modify news sources in `news_analyzer.py`:
```python
self.news_sources = {
    'your_source': 'https://example.com/rss',
    # ... existing sources
}
```

### Prediction Horizons
Adjust prediction timeframes in `enhanced_predictor.py`:
```python
hours_ahead = [1, 4, 24]  # Modify as needed
```

## 📝 Logging

The system creates detailed logs in:
- `gbpusd_system.log`: Main system operations
- Console output: Real-time status updates

## 🔧 Troubleshooting

### Common Issues

**"No data retrieved" Error**
- Check internet connection
- Verify RSS feeds are accessible
- Some sources may have rate limits

**Model Training Fails**
- Ensure sufficient historical data
- Check available memory (LSTM training requires ~2GB)
- Verify TensorFlow installation

**Dashboard Not Loading**
- Check if port 5000 is available
- Ensure Flask dependencies are installed
- Check firewall settings

**Prediction Accuracy Low**
- More historical data improves accuracy
- Consider adjusting feature weights
- Monitor news relevance scores

### Performance Optimization

**For Better Speed**
- Enable GPU support for TensorFlow
- Use faster RSS parsing libraries
- Implement caching for frequently accessed data

**For Lower Resource Usage**
- Reduce update frequency
- Limit news history retention
- Use smaller LSTM model

## 📈 Future Enhancements

### Planned Features
- **Additional Data Sources**: Economic calendars, social media sentiment
- **Advanced Models**: Transformer-based prediction models
- **Alert System**: Email/SMS notifications for significant events
- **API Access**: RESTful API for external integrations
- **Mobile App**: React Native mobile dashboard

### Contributing
The system is designed to be modular and extensible. Key areas for enhancement:
- Additional news sources and parsing
- Improved sentiment analysis models
- Advanced prediction algorithms
- Enhanced visualization and UI

## 📄 License

This project is provided as-is for educational and research purposes. Please ensure compliance with data source terms of service when using this system.

## ⚠️ Disclaimer

This system is for educational and research purposes only. The predictions should not be used as the sole basis for trading decisions. Always do your own research and consider the risks involved in forex trading.

---

**Built with ❤️ for the GBP/USD trading community**