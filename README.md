# 🇮🇩 Analisis Sentimen Jersey Erspo Timnas Indonesia

Menggunakan Model Klasifikasi dan Algoritma Naïve Bayes

## 📌 Deskripsi Proyek

Proyek ini bertujuan untuk melakukan analisis sentimen terhadap opini masyarakat mengenai jersey terbaru Timnas Indonesia yang diproduksi oleh Erspo. Analisis dilakukan menggunakan pendekatan Natural Language Processing (NLP) dengan model klasifikasi berbasis algoritma Naïve Bayes.

Data yang digunakan diperoleh melalui proses crawling dari Twitter (X), sehingga mencerminkan opini publik secara real-time.

Hasil analisis dikategorikan ke dalam beberapa label sentimen:

* Positif 😊
* Negatif 😠
* Netral 😐

---

## 🎯 Tujuan

* Mengidentifikasi sentimen publik terhadap jersey Erspo Timnas Indonesia
* Mengimplementasikan algoritma Naïve Bayes untuk klasifikasi teks
* Mengolah data hasil crawling Twitter
* Menyediakan visualisasi hasil analisis

---

## 🌐 Sumber Data

Data dikumpulkan melalui proses crawling dari Twitter (X) menggunakan API Twitter Harvest.

Contoh keyword pencarian:

* "jersey timnas erspo"
* "jersey indonesia terbaru"
* "erspo timnas review"

---

## 🧠 Metodologi

1. **Data Crawling (Twitter API)**

   * Menggunakan API Twitter Harvest untuk mengambil tweet berdasarkan keyword tertentu
   * Membutuhkan autentikasi menggunakan API Key & Token

2. **Data Preprocessing**

   * Case folding
   * Cleaning (hapus URL, mention, hashtag, emoji)
   * Tokenization
   * Stopword removal
   * Stemming (Sastrawi)

3. **Feature Extraction**

   * TF-IDF (Term Frequency - Inverse Document Frequency)

4. **Modeling**

   * Algoritma Naïve Bayes (MultinomialNB)

5. **Evaluation**

   * Accuracy
   * Precision
   * Recall
   * F1-Score

6. **Visualization**

   * Grafik distribusi sentimen
   * Word cloud

---

## 🛠️ Teknologi yang Digunakan

* Python (Google Colab)
* Pandas
* NumPy
* Scikit-learn
* NLTK / Sastrawi
* Matplotlib / Seaborn
* Tweepy / snscrape (untuk crawling Twitter)


## 🐦 Contoh Crawling Data Twitter

```python id="colab3"
query = "jersey timnas erspo -filter:retweets"
tweets = tweepy.Cursor(api.search_tweets, q=query, lang="id", tweet_mode="extended").items(100)

data = []
for tweet in tweets:
    data.append(tweet.full_text)

print(data[:5])
```

---
