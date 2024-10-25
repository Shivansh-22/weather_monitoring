# Weather Monitoring System

A real-time weather monitoring system that collects, processes, and analyzes weather data from multiple Indian metropolitan cities using the OpenWeatherMap API.

## Features

- Real-time weather data collection from OpenWeatherMap API
- Monitoring of 6 major Indian cities (Delhi, Mumbai, Chennai, Bangalore, Kolkata, Hyderabad)
- Temperature conversion and data processing
- Daily weather summaries and aggregates
- Configurable alerting system for weather conditions
- Data visualization with temperature trends and weather condition distribution
- Persistent storage using SQLAlchemy
- Email notifications for weather alerts
- Comprehensive test suite

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Shivansh-22/weather_monitoring.git
cd weather_monitoring
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
./venv/Scripts/activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up environment variables:
Create a `.env` file in the project root with the following variables:
```
OPENWEATHER_API_KEY=your_api_key_here
DATABASE_URL=sqlite:///weather_data.db

# Email configuration (optional)
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
SMTP_USERNAME=your_email@gmail.com
SMTP_PASSWORD=your_app_password
SMTP_RECIPIENT=recipient@email.com
```

## Configuration

You can modify the following settings in `config/settings.py`:

- Polling interval for weather updates
- Temperature thresholds for alerts
- Cities to monitor
- Database configuration
- Alert settings

## Usage

1. Start the monitoring system:
```bash
python main.py
```

2. View visualizations:
The system automatically generates visualization plots in the `visualizations` directory:
- Temperature trends for each city
- Weather condition distribution

3. Access the database:
The system stores all weather data in an SQLite database (by default) at `weather_data.db`

4. Monitor alerts:
- Alerts are displayed in the console
- If email configuration is provided, alerts are also sent via email

## Running Tests

Run the test suite using pytest:
```bash
pytest tests/
```

## Project Structure

```
weather_monitoring/
├── config/                 # Configuration settings
├── core/                   # Core functionality
├── models/                # Data models
├── utils/                 # Utility functions
├── alerts/               # Alert system
├── visualization/        # Data visualization
├── storage/             # Database management
├── tests/               # Test suite
├── requirements.txt     # Dependencies
└── main.py             # Application entry point
```

## Error Handling

The system includes comprehensive error handling:
- API connection failures
- Database errors
- Invalid data handling
- Graceful shutdown on interruption

## Extending the System

To add new features:

1. Additional Weather Parameters:
- Modify `WeatherData` model in `models/weather_data.py`
- Update data processing in `core/data_processor.py`

2. New Alert Types:
- Add new alert conditions in `alerts/threshold_manager.py`

3. Custom Visualizations:
- Add new plotting functions in `visualization/plotter.py`

## Troubleshooting

Common issues and solutions:

1. API Connection Errors:
- Verify API key in environment variables
- Check internet connection
- Confirm API rate limits

2. Database Issues:
- Check database URL in configuration
- Verify write permissions
- Ensure sufficient disk space

3. Email Alert Problems:
- Verify SMTP settings
- Check email credentials
- Confirm recipient address
