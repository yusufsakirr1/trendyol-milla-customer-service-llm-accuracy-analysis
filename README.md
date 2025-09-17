# Trendyol Milla Customer Service LLM Accuracy Analysis

A comprehensive evaluation project that analyzes OpenAI GPT-5-nano performance on Turkish e-commerce customer service conversations using structured JSON schema output.

## 📊 Project Overview

This project evaluates Large Language Model performance across three critical customer service tasks:
- **Sentiment Analysis**: Positive, Negative, Neutral classification
- **Intent Classification**: Customer intent detection (15+ categories)
- **Resolution Status**: Whether customer issues were resolved

## 🎯 Key Features

- **Structured Output**: Uses Pydantic models with OpenAI's JSON Schema for reliable parsing
- **Turkish Language Support**: Optimized prompts for Turkish customer service conversations
- **Comprehensive Dataset**: 40 real customer service conversations with ground truth labels
- **Multi-format Results**: JSON and CSV export capabilities
- **Error Handling**: Robust error management with fallback mechanisms
- **Performance Metrics**: Detailed accuracy analysis with confusion matrices

## 🛠 Technical Stack

- **Python 3.8+**
- **OpenAI API** (GPT-5-nano)
- **Pydantic 2.11.7** - Schema validation
- **Pandas & NumPy** - Data processing
- **Jupyter Notebooks** - Interactive analysis
- **Matplotlib & Seaborn** - Visualization

## 📁 Project Structure

```
├── data_preprocessing.ipynb             # Data preprocessing pipeline
├── openai_analysis_updated.ipynb       # Initial analysis (sample)
├── openai_analysis_full_40.ipynb       # Full dataset analysis (MAIN ANALYSIS)
├── prepared_data.json                  # Processed conversation data
├── 20-sohbet-trendyol-mila.json        # Original conversation data
├── openai_analysis_complete_40_chats.json    # Complete analysis results
├── sentiment_analysis_results_40_chats.csv   # Sentiment analysis results
├── intent_analysis_results_40_chats.csv      # Intent classification results
├── resolution_analysis_results_40_chats.csv  # Resolution prediction results
├── complete_analysis_summary_40_chats.csv    # Consolidated summary
├── TRENDYOL_MILA_CHATBOT_SWOT_ANALIZI.txt   # SWOT Analysis Report
├── BOT_GELİŞTİRME_ÖNERİLERİ.txt       # Bot Development Recommendations
├── musteri_talepleri_analizi.ipynb     # Customer Demand Analysis Notebook
├── musteri_talepleri_ozet.csv          # Customer Demand Summary
├── requirements.txt                    # Python dependencies
├── .gitignore                         # Git ignore file
└── README.md                          # This file
```

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- OpenAI API account and API key
- Jupyter Notebook environment

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yusufsakirr1/trendyol-milla-customer-service-llm-accuracy-analysis.git
   cd trendyol-milla-customer-service-llm-accuracy-analysis
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up OpenAI API key**
   ```bash
   # Option 1: Environment variable (recommended)
   export OPENAI_API_KEY='your-api-key-here'
   
   # Option 2: Create .env file
   echo "OPENAI_API_KEY=your-api-key-here" > .env
   ```

### Running the Analysis

1. **Start Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

2. **Run the analysis notebooks in order:**
   - `data_preprocessing.ipynb` - Data preprocessing pipeline
   - `openai_analysis_full_40.ipynb` - **MAIN ANALYSIS** - Complete 40-chat analysis with structured output
   - `openai_analysis_updated.ipynb` - Initial sample analysis (optional)
   - `musteri_talepleri_analizi.ipynb` - Customer demand analysis and visualization

3. **View results in the project folder:**
   - CSV files for detailed analysis
   - JSON file for complete results
   - SWOT analysis TXT report
   - Bot development recommendations TXT file
   - Customer demand analysis and visualizations

## 📊 Dataset Details

- **Size**: 40 Turkish customer service conversations
- **Domain**: E-commerce customer support (Trendyol-style)
- **Format**: JSON with structured conversation data
- **Labels**: Manual ground truth annotations
- **Tasks**: Sentiment, Intent, Resolution status

### Sample Conversation Structure
```json
{
  "sohbet_id": 90001,
  "conversation": "Bot: Merhaba!...\nMüşteri: Siparişimde eksik ürün var...",
  "ground_truth_sentiment": "Pozitif",
  "ground_truth_intent": "Eksik ürün",
  "ground_truth_resolution": "Çözüldü"
}
```

## 🤖 Model Configuration

- **Model**: OpenAI GPT-5-nano
- **Response Format**: Structured JSON with Pydantic validation
- **Rate Limiting**: 1 second delay between API calls
- **Token Limit**: 5000 max completion tokens
- **Error Handling**: Automatic retry and fallback mechanisms

## 📈 Results Summary

| Task | Accuracy | Correct/Total | Performance Level |
|------|----------|---------------|-------------------|
| **Sentiment Analysis** | **92.5%** | 37/40 | Excellent |
| **Intent Classification** | **95.0%** | 38/40 | Outstanding |
| **Resolution Prediction** | **100.0%** | 40/40 | Perfect |
| **Overall Average** | **95.8%** | 115/120 | Outstanding |

### Detailed Performance Metrics
- **Total API Calls**: 120 (40 chats × 3 analysis types)
- **Successful Analyses**: 120/120 (100% completion rate)
- **API Error Rate**: 0% (Perfect reliability)
- **Analysis Method**: Structured JSON Schema with Pydantic validation

### Customer Demand Analysis Results
- **Top Intent Categories**: İade (12.5%), Ödeme (10.0%), Eksik ürün (7.5%)
- **Intent Distribution**: 25 different categories identified
- **Coverage**: Top 5 categories represent 45% of all customer requests
- **Request Types**: Şikayet (45%), Sorun (32.5%), Soru (17.5%), İstek (5%)
- **Resolution Rate**: 82.5% successfully resolved, 17.5% unresolved

## 🔧 Key Components

### Pydantic Models
```python
class SentimentAnalysis(BaseModel):
    sentiment: str  # "Pozitif", "Negatif", "Nötr"
    explanation: str

class IntentAnalysis(BaseModel):
    intent: str  # Customer intent category
    detail: str  # Specific details
    category: str  # Type: Şikayet/Sorun/Soru/İstek
```

### Advanced Prompt Engineering
- **Context-aware Turkish prompts** with cultural nuances
- **Domain-specific e-commerce instructions** for customer service
- **Comprehensive rule sets** with examples and edge cases
- **Iteratively optimized** through analysis of false predictions
- **Structured JSON Schema** enforcement for reliable parsing
- **Multi-layered validation** with Pydantic models

## 📊 Output Formats

### JSON Format
Complete analysis results with metadata, confidence scores, and raw responses.

### CSV Format
- Individual task results (sentiment, intent, resolution)
- Consolidated summary for analysis
- Customer demand analysis summary
- Ready for statistical analysis and visualization

### TXT Reports
- **SWOT Analysis**: Comprehensive strengths, weaknesses, opportunities, threats analysis
- **Bot Development Recommendations**: 387 lines of detailed improvement strategies

### Interactive Notebooks
- **Customer Demand Analysis**: Visual charts, statistical analysis, and actionable insights
- **Data Preprocessing**: Complete data preparation pipeline

## 🔬 Use Cases

- **Customer Service Optimization**: Understand conversation patterns and resolution effectiveness
- **LLM Performance Evaluation**: Benchmark structured output approaches with 95.8% accuracy
- **Turkish NLP Research**: Advanced Turkish language customer service analysis
- **Conversation Analytics**: Extract actionable insights from customer interactions
- **SWOT Analysis**: Comprehensive bot performance evaluation and strategic planning
- **Customer Demand Analysis**: Identify most common support topics and intent distribution
- **Bot Development Strategy**: Evidence-based recommendations for chatbot improvements
- **Prompt Engineering**: Optimize AI prompts for better customer service outcomes

## 🛡 Security & Privacy

- API keys are not stored in the repository
- Customer data is anonymized
- No personal information in conversation logs
- Rate limiting prevents API abuse

## 📋 Requirements

See `requirements.txt` for complete dependency list:

```txt
openai>=1.106.1
pydantic>=2.11.7
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.5.0
seaborn>=0.11.0
jupyter>=1.0.0
python-dotenv>=0.19.0
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 🔗 Links

- [OpenAI API Documentation](https://platform.openai.com/docs)
- [Pydantic Documentation](https://docs.pydantic.dev/)
- [Trendyol Technology](https://trendyol.com)

## 📞 Contact

- **Author**: Yusuf Sakir
- **Email**: sakiryusuf36@gmail.com
- **LinkedIn**: www.linkedin.com/in/yusuf-sakir
- **GitHub**: [@yusufsakirr1](https://github.com/yusufsakirr1)

## 🙏 Acknowledgments

- OpenAI for providing GPT-5-nano API access
- Trendyol for inspiration on customer service excellence
- Turkish NLP community for language-specific insights

---

## 📊 Key Achievements

- ✅ **95.8% Overall Accuracy** across all analysis tasks
- ✅ **100% API Reliability** with zero failed requests
- ✅ **Perfect Resolution Analysis** (100% accuracy)
- ✅ **Comprehensive SWOT Analysis** of chatbot performance
- ✅ **Strategic Bot Development Recommendations** (387 detailed lines)
- ✅ **Customer Demand Analysis** with 25+ intent categories
- ✅ **Production-Ready Prompts** optimized through iterative testing
- ✅ **Structured JSON Output** with reliable parsing
- ✅ **Turkish Language Excellence** in customer service context
- ✅ **Interactive Data Visualizations** with Jupyter notebooks

**Note**: This project requires an OpenAI API key. Estimated cost for full analysis: ~$5-8 for 120 API calls with GPT-5-nano.