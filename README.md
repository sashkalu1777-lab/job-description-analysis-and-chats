# Multi-Agent AI System for job advertisements analysis via LangGraph RAG

Built a multi-agent AI system with LangChain, LangGraph, ChromaDB, and LangFuse to demonstrate an intelligent RAG workflow. It analyzes, evaluates and improves job advertisements from Seek. Then answer questions from users such as HR or job seekers based on analyzed job advertisements and uploaded CVs to help users target the most suitable applicants or job opportunities. The workflow is in streaming style. It offers various measurement metrics such as ROUGE, Bert Score and customised RAG quality.  The average latency for each job advertisement processing is around 8 seconds, and the cost is around 0.05 AUD.

## Project Overview

This repository contains a hybrid pipeline that combines 2 Multi-Agent pipeline with RAG and conditional edges.

- Extract skills, responsibilities, and requirements in good format from job advertisements. Then evaluate and improve the original job advertisements.

- <img width="681" height="616" alt="image" src="https://github.com/user-attachments/assets/864edbb6-28e2-43cc-892c-5de913408abf" />

- Perform intelligent matching between improved job advertisements and candidate CVs.

- <img width="820" height="690" alt="image" src="https://github.com/user-attachments/assets/7fd493eb-6777-4950-966f-2b4b99c6be10" />

The system also contains following functions.

- Multi-document processing in streaming style.
- Version control and self-refreshment in Vector Store.
- Clear and human-friendly workflow outputs.
- Consistent chat history with memory and thread management.
- Measurement and evaluation using BERTScore, ROUGE metrics, and customised RAG metrics.
- Local logging system and monitoring system.
- LangFuse tracing to catch exchanged messages, erros, latencies and costs.

## Repository Structure

```
job-description-analysis/
├── 01-data-import.ipynb                       # Data import and basic exploration
├── 02-data-preprocessing.ipynb                # Data cleaning and preprocessing
├── 03-langgraph-job-description.ipynb         # LangGraph pipeline with LangFuse integration to analyse, evaluate and improve job advertisements.
├── 04-measurement.ipynb                       # Evaluation using BERTScore and ROUGE
├── 05-langgrph-agentic-rag-client-help.ipynb  # RAG assistant for HR/job-seeker to match suitable applicants or opportunites based on processed job advertisements and CVs.
├── job-description-data/                      # Dataset files
│   ├── ads-50k.csv                            # Main dataset
│   ├── ads-50k.json                           # JSON format dataset
│   └── sample_df.csv                          # Sample data for testing
├── chroma_db/                                 # ChromaDB vector database
├── client-help-logs/                          # RAG assistant logs and outputs.
├── job-description-logs/                      # Job advertisements analysis and processing outputs.
├── instructions/                              # Project documentation
├── reference/                                 # Reference implementations
└── requirements.txt                           # Python dependencies
```

## Features

### 1. Data Processing Pipeline
- **Data Import**: Load and explore job description datasets
- **Preprocessing**: Clean HTML content, extract text, and prepare data for analysis
- **Feature Engineering**: Extract structured information from unstructured text

### 2. AI-Powered Analysis
- **LangGraph Integration**: Advanced workflow orchestration with LangGraph
- **LangFuse Integration**: Comprehensive tracing and monitoring
- **RAG Capabilities**: Retrieval-augmented generation for document analysis
- **Vector Database**: ChromaDB for efficient similarity search

### 3. Evaluation and Measurement
- **BERTScore**: Semantic similarity evaluation
- **ROUGE Metrics**: Text overlap and quality assessment
- **Cosine Similarity**: Content similarity analysis
- **Performance Logging**: Detailed tracking of model performance

### 4. Intelligent Matching
- **Job-Candidate Matching**: AI-powered compatibility assessment
- **Skills Extraction**: Automated identification of required skills
- **Requirements Analysis**: Structured extraction of job requirements
- **Classification**: Job categorization and metadata extraction

## 🛠️ Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd job-description-analysis
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**:
   Create a `.env` file with your API keys:
   ```
   OPENAI_API_KEY=your_openai_api_key
   LANGFUSE_PUBLIC_KEY=your_langfuse_public_key
   LANGFUSE_SECRET_KEY=your_langfuse_secret_key
   LANGFUSE_HOST=your_langfuse_host
   ```

## 📊 Usage

### 1. Data Import and Preprocessing
```python
# Run the data import notebook
jupyter notebook 01-data-import.ipynb

# Process and clean the data
jupyter notebook 02-data-preprocessing.ipynb
```

### 2. LangGraph Pipeline
```python
# Execute the main analysis pipeline
jupyter notebook 03-langgraph-job-description.ipynb
```

### 3. Evaluation
```python
# Run performance measurements
jupyter notebook 04-measurement.ipynb
```

### 4. RAG Agent
```python
# Use the intelligent document analysis agent
jupyter notebook 05-langgrph-agentic-rag-client-help.ipynb
```

## Key Technologies

- **LangChain**: Framework for LLM applications
- **LangGraph**: Workflow orchestration
- **LangFuse**: LLM observability and tracing
- **ChromaDB**: Vector database for embeddings
- **OpenAI**: GPT models for text analysis
- **BERTScore**: Semantic similarity evaluation
- **ROUGE**: Text quality metrics
- **Pandas**: Data manipulation
- **Scikit-learn**: Machine learning utilities

## Performance Metrics

The system provides comprehensive evaluation using:
- **BERTScore**: Measures semantic similarity between generated and reference text
- **ROUGE-1, ROUGE-2, ROUGE-L**: Measures n-gram overlap and longest common subsequence
- **Cosine Similarity**: Content similarity analysis
- **Custom Metrics**: Domain-specific evaluation criteria

## Data Format

The system processes job descriptions in JSON format with the following structure:
```json
{
  "id": "unique_identifier",
  "title": "Job Title",
  "abstract": "Job Summary",
  "content": "Full Job Description",
  "metadata": {
    "classification": "Job Category",
    "location": "Job Location",
    "workType": "Employment Type"
  }
}
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For questions or support, please open an issue in the repository or contact the development team.

## Future Enhancements

- [ ] Multi-language support
- [ ] Advanced skill matching algorithms
- [ ] Real-time job recommendation system
- [ ] Integration with job boards and ATS systems
- [ ] Enhanced visualization and reporting capabilities
