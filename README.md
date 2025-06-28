<h1 align="center"> Retrieval-Augmented Generation with Gradio and Groq API Key</h1>
<p align="center"> Natural Language Processing Project</p>

<div align="center">

<img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54">

</div>

### Name : Arifian Saputra
### Tech Stack : Python, Gradio, LangChain, HuggingFace Embedding, FAISS vector store

---

### 1. Analysis about how the project works
- Proyek ini menggunakan Retrieval Augmented Generation (RAG) yaitu sebuah pendekatan inovatif dalam Natural Language Processing (NLP) untuk mengambil informasi (retrieval) dari dokumen dan pembuatan teks (generation). RAG bekerja dengan cara mengambil dokumen-dokumen yang relevan dari basis data atau sumber eksternal berdasarkan pertanyaan atau konteks yang diberikan, lalu menggunakan model bahasa (seperti LLM) untuk menghasilkan jawaban atau teks baru yang didasarkan pada informasi yang diambil tersebut. 

### 2. Analysis about how different every model works on Retrieval-Augmented Generation

```python
def get_llm():
    return ChatGroq(
        groq_api_key=GROQ_API_KEY,
        model_name="deepseek-r1-distill-llama-70b", # Change the model in the code
        temperature=0.2
    )
```
- Model used : ```[llama-3.3-70b-versatile, deepseek-r1-distill-llama-70b, gemma2-9b-it]```

- Question : Mengapa Layanan Kesehatan, Kesejahteraan Seksual, dan Reproduksi di Kampus itu penting?

2.1 Analysis on ```llama-3.3-70b-versatile``` : 

<img src="model 1 RAG.jpeg" alt="llama-3.3-70b-versatile" width="200"/>

- Model 1 (llama-3.3-70b-versatile) memberikan jawaban dalam bahasa Indonesia dengan struktur yang cukup runtut. Jawaban terdiri dari poin-poin bernomor yang menjelaskan pentingnya KKSR dari sudut kesehatan, pendekatan positif dan hormat, hingga cakupan aspek edukasi seksual seperti PMS, persetujuan, dan seks aman. Bahasa yang digunakan formal namun tetap mudah dipahami, serta diakhiri dengan kesimpulan yang mengaitkan manfaat layanan KKSR dengan kemampuan mahasiswa mengambil keputusan sehat. Model ini ringkas, jelas, dan sangat relevan dengan konteks kampus.

2.2 Analysis on ```deepseek-r1-distill-llama-70b``` : 

<img src="model 2 RAG gambar 1.jpeg" alt="deepseek-r1-distill-llama-70b" width="200"/>
<img src="model 2 RAG gambar 2.jpeg" alt="deepseek-r1-distill-llama-70b" width="200"/>

- Model 2 (deepseek-r1-distill-llama-70b) tampil lebih panjang dan analitis. Pada gambar kedua, model “berpikir keras” dulu (metacognitive reasoning), memecah konteks menjadi poin-poin: hambatan akses, pentingnya layanan, pendekatan positif, dan edukasi. Pada gambar kedua, ia menyusun jawaban terstruktur dengan subjudul tebal (bold), merangkum poin-poin utama. Jawaban sangat informatif, logis, dan mencakup konteks yang luas, meski terasa sedikit teknis. Model ini unggul dalam kejelasan alur pikir dan detail, cocok untuk audiens akademik atau laporan analisis.

2.3 Analysis on ```gemma2-9b-it``` :

<img src="model 3 RAG.jpeg" alt="gemma2-9b-it" width="200"/>

- Model 3 (gemma2-9b-it) memilih bahasa Inggris dan gaya yang lebih langsung. Model ini menyebut alasan pentingnya layanan KKSR secara poin-poin berbintang, menekankan hambatan akses, pentingnya kesehatan seksual, pendekatan positif tanpa paksaan, dan topik edukasi seperti PMS dan seks aman. Jawabannya ringkas dan efisien, namun cenderung lebih deskriptif daripada argumentatif. Model ini efektif untuk merangkum esensi konten dengan cepat, tetapi terasa kurang narasi atau kesimpulan integratif yang mengaitkan keseluruhan gagasan secara mendalam.

### 3. Analysis about how temperature works

```python
def get_llm():
    return ChatGroq(
        groq_api_key=GROQ_API_KEY,
        model_name="llama-3.3-70b-versatile",
        temperature=0.2 # Change the temperature value here and analzye
    )
```

3.1 Analysis on higher temperature 

<img src="model 1 RAG.jpeg" alt="llama-3.3-70b-versatile" width="200"/>

- Pada temperature 0.2, jawaban model sangat terstruktur, ringkas, dan ditulis dalam bahasa Indonesia. Model memberikan tiga poin alasan pentingnya layanan KKSR secara jelas: merawat kesehatan seksual, pentingnya pendekatan positif, serta mencakup edukasi spesifik seperti PMS, persetujuan, dan seks aman. Bahasanya formal, informatif, dan langsung menuju inti, serta diakhiri kesimpulan yang mengaitkan layanan KKSR dengan kemampuan mahasiswa membuat keputusan sehat. Temperatur rendah ini menghasilkan respons yang lebih “aman,” konsisten, dan cenderung mengikuti gaya faktual tanpa variasi gaya bahasa.

3.2 Analysis on lower temperature

<img src="model 1 RAG temp 0.8.jpeg" alt="llama-3.3-70b-versatile" width="200"/>

- Sebaliknya, pada temperature 0.8, model menjawab dalam bahasa Inggris dengan gaya lebih naratif dan deskriptif. Model memecah jawaban ke dalam poin-poin berbintang, menekankan berbagai aspek layanan KKSR, termasuk hambatan akses, pendekatan positif, dan edukasi. Kalimatnya lebih panjang, penjelasan lebih luas, dan terasa lebih “bebas” dalam menyusun ungkapan. Temperatur tinggi ini tampak memicu model untuk menghasilkan jawaban dengan gaya ekspresi yang lebih variatif, lebih kreatif, dan detail, meski sedikit kurang ringkas dibanding temperature rendah.

### 4. How to run the project

- Clone this repository with : 

```git
git clone https://github.com/arifian853/RAG_with_GroqAPI.git
```

- Copy the ```.env.example``` file and rename it to ```.env```

```
GROQ_API_KEY=your-groq-api-key
```

- Fill the ```GROQ_API_KEY``` with your Groq API Key, find it here : https://console.groq.com/keys

- Create and activate a virtual environment:

```
python -m venv venv
source venv/Scripts/activate       # Untuk Git Bash
venv\Scripts\activate              # Untuk Command Prompt (CMD)
```

- Install all dependencies listed in requirements.txt:

```
pip install -r requirements.txt
```

- Run the project using the following command:

```
python app.py
```

- Open your browser and go to the following address:

```
http://.....
```

- Upload a PDF file and ask a question to test the Retrieval-Augmented Generation system.
