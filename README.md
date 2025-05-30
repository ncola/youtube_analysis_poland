# 📺 Analiza treści o Polsce na YouTube

Projekt miał na celu pobrać i przenaalizować filmy dostępne na YouTube, dotyczące Polski, w języku angielskim. Badanie obejmuje eksplorację danych, grupowanie tematyczne oraz analizę sentymentu w odniesieniu do treści i kanałów publikujących filmy.

---

## 🎯 Hipotezy badawcze

- 📌 Najpopularniejsze są filmy o charakterze podróżniczym (EDA)  
- 📌 Filmy można pogrupować tematycznie na podstawie transkrypcji (Clustering)  
- 📌 Ogólny wskaźnik sentymentu dla kategorii wiadomości, polityki i podróży jest pozytywny (Sentiment analysis)  
- 📌 Kanały amerykańskiej telewizji pozytywnie wypowiadają się o Polsce *(hipoteza dodana na podstawie EDA)*  

---

## 📦 Dane

Dane zostały pobrane z YouTube API przy użyciu następujących parametrów:

- `q: "poland"` – filmy związane z Polską  
- `type: "video"` – tylko treści wideo  
- `videoCaption: "closedCaption"` – tylko filmy z napisami  
- `relevanceLanguage: "en"` – tylko filmy w języku angielskim  

Do pobrania transkrypcji wykorzystano bibliotekę `YouTubeTranscriptApi` i metodę `get_transcript(video_id)`.

Dodatkowo, pobrano informacje o kanałach publikujących filmy, aby przeanalizować kontekst źródła.

Kod użyty do pobrania danych znajduje się w pliku youtube_data_fetcher.ipynb. Dane zapisywane są w folderze data/

---

## 🧪 Metody

Projekt opiera się na trzech głównych filarach:

### 🔍 Eksploracyjna analiza danych (EDA)

  - Analiza częstości, długości, zliczanie kategorii
  - Wizualizacje (matplotlib, seaborn, plotly)
Pomaga zrozumieć ogólną charakterystykę treści i potwierdzić pierwsze hipotezy dotyczące dominujących tematów (np. podróże, wiadomości).

### 📝 NLP i przetwarzanie tekstu

  - Czyszczenie i lematyzacja (nltk, spacy)
  - Tokenizacja, usuwanie stopwords
  - WordCloud, CountVectorizer, TF-IDF

### 🧩 Grupowanie tematyczne

- Metoda k-średnich (K-Means)
- LDA (Latent Dirichlet Allocation)  
- Redukcja wymiarów: PCA, TruncatedSVD, t-SNE
Wykorzystano transkrypcje do identyfikacji głównych tematów poruszanych w filmach.

### 💬 Analiza sentymentu

- Ogólny ton wypowiedzi w poszczególnych tematach
- Ocena sentymentu w treściach kanałów telewizyjnych  
- NLTK, TextBlob

---

## 🧭 Etapy projektu

1. **Pobranie danych z API**  
2. **Eksploracyjna analiza danych (EDA)**  
3. **Przygotowanie transkrypcji i tekstów**  
4. **Grupowanie tematyczne**
   - KMeans (z PCA/t-SNE do wizualizacji)
   - LDA (tematy ukryte)
5. **Analiza sentymentu**
   - Globalna
   - Per kategoria
   - Per kanał (np. media amerykańskie)



