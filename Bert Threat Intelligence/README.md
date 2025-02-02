# BERT Email Threat Classification

A sophisticated threat intelligence system using BERT (Bidirectional Encoder Representations from Transformers) for classifying and analyzing potential cyber threats in text data.

## 🌟 Features

- BERT-based text classification for threat detection
- Real-time threat analysis capabilities
- Custom dataset handling for cyber threat intelligence
- High accuracy in identifying malicious content
- Detailed performance metrics and evaluation
- Entity recognition for threat indicators

## 🛠️ Technical Requirements

- Python 3.7+
- PyTorch
- Transformers library
- CUDA-capable GPU (optional, but recommended)

## 📦 Dependencies

```bash
pip install transformers torch datasets pandas numpy tqdm scikit-learn
```

## 🚀 Quick Start

1. Clone the repository:
```bash
git clone https://github.com/yourusername/Bert-Email-Classification.git
cd Bert-Email-Classification
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Prepare your data:
- Place your TSV data file in the project directory
- Ensure it contains 'text' and 'entities' columns

4. Run the model:
```python
python main.py
```

## 📊 Model Architecture

- Base Model: BERT (bert-base-uncased)
- Classification Head: Binary classification (Malicious/Benign)
- Max Sequence Length: 256 tokens
- Batch Size: 16
- Learning Rate: 2e-5

## 🎯 Performance Metrics

The model achieves the following performance on test data:
- Accuracy: ~77%
- Precision: ~77%
- Recall: 100%
- F1 Score: ~87%

## 💡 Usage Example

```python
analyzer = ThreatAnalyzer('path_to_saved_model')

result = analyzer.analyze(
    text="A new variant of Ryuk ransomware targeting healthcare systems was detected",
    entities="[{'label': 'ransomware'}, {'label': 'sector'}]"
)

print(f"Prediction: {result['prediction']} (Confidence: {result['confidence']:.2f})")
```

## 📝 Data Format

The system expects data in TSV format with the following structure:
- `text`: The input text to analyze
- `entities`: JSON-formatted string containing entity labels

Example:
```
text    entities
"Suspicious email detected"    [{"label": "malware"}, {"label": "threat-actor"}]
```

## 🔍 Malicious Entity Labels

The system recognizes the following as potential threat indicators:
- attack-pattern
- malware
- threat-actor
- Infrastructure
- C&C
- exploit
- ransomware

## 📈 Model Training

The model implements:
- Custom dataset handling
- Progressive learning rate scheduling
- Best model checkpointing
- Comprehensive validation metrics