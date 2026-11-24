# FAQ Chatbot

An NLP-based FAQ chatbot with a Streamlit chat interface. It understands a user's question, finds the most similar FAQ, and replies with the matching answer.

**Live demo:** https://your-app-name.streamlit.app

## Features
- Chat interface with message history and suggested questions
- Understands everyday wording (for example, "where is my package" finds the order tracking FAQ)
- Shows the matched FAQ and a similarity score with every answer
- Polite fallback reply when a question is not covered
- Easy to customize: edit the `FAQS` list in `app.py` to use your own topic

## How it works
1. **Preprocessing (NLTK):** lowercase, remove punctuation, tokenize, remove stopwords, lemmatize.
2. **Vectorization (scikit-learn):** TF-IDF with unigrams and bigrams over the FAQ questions and answers.
3. **Matching:** cosine similarity between the user's question and every FAQ; the best match is returned.
4. **Fallback:** if the best similarity is below a threshold (0.2), the bot asks the user to contact support.

## Tech stack
Python, NLTK, scikit-learn, Streamlit

## Run locally
```bash
git clone https://github.com/gunwanti13/faq-chatbot.git
cd faq-chatbot
pip install -r requirements.txt
streamlit run app.py
```

## Project structure
```
faq-chatbot/
├── app.py             # FAQ data, NLP logic and Streamlit UI
├── requirements.txt   # dependencies
└── README.md
```

## Future improvements
- Sentence embeddings for better handling of different wording
- Load FAQs from a CSV or JSON file
- Multi-language support

## Author
Gunwanti Malviya - [GitHub](https://github.com/gunwanti13)
