# AI-Powered-Behavioral-Analysis-for-Suicide-Prevention
Crisis Analysis Pipeline 🚨
A comprehensive social media analysis tool for mental health crisis detection and intervention.
Overview
The Crisis Analysis Pipeline monitors social media platforms to identify potential mental health crises. By analyzing text content from Twitter and Reddit, the system detects high-risk language patterns, performs sentiment analysis, and maps crisis hotspots to enable timely interventions.
Key Features

Multi-platform data collection: Extracts data from Twitter and Reddit with customizable keyword filtering
Advanced text preprocessing: Cleans and normalizes text data for optimal analysis
Sentiment analysis: Uses VADER and TextBlob to measure emotional tone and intensity
Risk classification: Identifies high-risk content through keyword matching and similarity scoring
Geolocation analysis: Maps crisis hotspots to visualize geographical distribution
Comprehensive visualizations: Creates intuitive charts and heatmaps for data interpretation

Technical Stack

Data Collection: Tweepy (Twitter API), PRAW (Reddit API)
Text Processing: NLTK, spaCy, RegEx
Sentiment Analysis: VADER, TextBlob
Risk Assessment: TF-IDF, Cosine Similarity
Visualization: Matplotlib, Seaborn, Folium, Plotly
Geolocation: Named Entity Recognition (NER), Geocoding
Data Management: Pandas, NumPy

System Architecture
The pipeline consists of several interconnected modules:

SocialMediaDataExtractor: Collects data from Twitter and Reddit APIs
TextPreprocessor: Cleans and normalizes text data
DataProcessor: Standardizes data from different sources
SentimentAnalyzer: Applies multiple sentiment analysis techniques
RiskClassifier: Identifies high-risk content
Geolocator: Extracts and geocodes location information
Visualizer: Creates visual representations of analysis results
CrisisAnalysisPipeline: Orchestrates the entire workflow

Installation
bashCopy# Clone the repository
git clone https://github.com/yourusername/crisis-analysis-pipeline.git
cd crisis-analysis-pipeline

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Download required NLTK data
python -c "import nltk; nltk.download('punkt'); nltk.download('stopwords'); nltk.download('wordnet'); nltk.download('averaged_perceptron_tagger')"

# Download spaCy model
python -m spacy download en_core_web_sm
Configuration
Create a config.json file with your API credentials:
jsonCopy{
  "twitter": {
    "api_key": "YOUR_TWITTER_API_KEY",
    "api_secret": "YOUR_TWITTER_API_SECRET",
    "access_token": "YOUR_TWITTER_ACCESS_TOKEN",
    "access_token_secret": "YOUR_TWITTER_ACCESS_TOKEN_SECRET"
  },
  "reddit": {
    "client_id": "YOUR_REDDIT_CLIENT_ID",
    "client_secret": "YOUR_REDDIT_CLIENT_SECRET",
    "user_agent": "YOUR_REDDIT_USER_AGENT"
  }
}
Usage
pythonCopyfrom crisis_analysis_pipeline import CrisisAnalysisPipeline

# Use sample data (for testing)
pipeline = CrisisAnalysisPipeline(use_sample_data=True)
crisis_data = pipeline.run_pipeline()

# Or use real API connections
import json
with open('config.json') as f:
    config = json.load(f)

pipeline = CrisisAnalysisPipeline(
    twitter_credentials=config['twitter'],
    reddit_credentials=config['reddit'],
    use_sample_data=False
)
crisis_data = pipeline.run_pipeline()
Output
The pipeline generates several outputs:

cleaned_crisis_data.csv: Preprocessed dataset with sentiment and risk scores
sentiment_risk_analysis.png: Visualizations of sentiment and risk distributions
crisis_heatmap.html: Interactive map of crisis hotspots
top_crisis_locations.png: Bar chart of locations with highest crisis discussions

Ethical Considerations
This tool is designed for early intervention and research purposes only. When deploying in production:

Ensure compliance with platform Terms of Service
Maintain user privacy and data protection
Implement proper security measures for sensitive information
Consult with mental health professionals for appropriate response protocols
Use the tool as part of a broader intervention strategy, not as a standalone solution

License
This project is licensed under the MIT License - see the LICENSE file for details.
Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
Acknowledgments

Mental health professionals for guidance on crisis indicators
API providers for enabling data collection
Open-source libraries that made this project possible
