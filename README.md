\# VIDEO\_AGENT



A Python-based video processing tool that takes a video or YouTube URL, converts the audio into text, summarizes the content, and stores the processed information for later retrieval.



The project is mainly built around \*\*Whisper, LangChain, ChromaDB, and Streamlit\*\*.



\## What it does



The basic workflow is:



```text

Video / YouTube URL

&#x20;       ↓

&#x20;   Audio Extraction

&#x20;       ↓

&#x20;  Audio Chunking

&#x20;       ↓

&#x20;    Transcription

&#x20;       ↓

&#x20;  Transcript Processing

&#x20;       ↓

&#x20;     Summary

&#x20;       ↓

&#x20;  Vector Storage

&#x20;       ↓

&#x20;   Search / Retrieval

```



The idea is to make long videos easier to process and search without manually going through the entire video.



\## Features



\* Download audio from YouTube videos

\* Process local video/audio input

\* Split long audio into smaller chunks

\* Speech-to-text using Whisper

\* Support for Hinglish transcription using Sarvam AI

\* Generate a short meeting/video title

\* Generate a summary from the transcript

\* Store processed text using ChromaDB

\* Retrieve relevant information from stored transcripts

\* Simple Streamlit interface



\## Tech Stack



\* \*\*Python\*\*

\* \*\*Whisper\*\* — speech-to-text

\* \*\*LangChain\*\* — LLM and RAG pipeline

\* \*\*ChromaDB\*\* — vector database

\* \*\*Streamlit\*\* — web interface

\* \*\*yt-dlp\*\* — YouTube audio extraction

\* \*\*Pydub\*\* — audio processing

\* \*\*Mistral / Groq\*\* — LLM-based processing

\* \*\*Sarvam AI\*\* — Hinglish speech-to-text translation



\## Project Structure



```text

VIDEO\_AGENT/

│

├── core/

│   ├── extractor.py

│   ├── rag\_engine.py

│   ├── summarizer.py

│   ├── transcriber.py

│   └── vector\_store.py

│

├── utils/

│   └── audio\_processor.py

│

├── vector\_db/

│   └── ChromaDB files

│

├── app.py

├── main.py

├── test.py

├── requirements.txt

├── .gitignore

└── README.md

```



\## Setup



Clone the repository:



```bash

git clone https://github.com/Shrinetsingh9648/VIDEO\_AGENT.git

cd VIDEO\_AGENT

```



Create a virtual environment:



\### Windows



```bash

python -m venv .venv

.venv\\Scripts\\activate

```



Install the dependencies:



```bash

pip install -r requirements.txt

```



\## Environment Variables



Create a `.env` file in the project root.



Example:



```env

MISTRAL\_API\_KEY=your\_key\_here

GROQ\_API\_KEY=your\_key\_here

SARVAM\_API\_KEY=your\_key\_here

```



Do not upload `.env` to GitHub.



\## Run



For the main Python pipeline:



```bash

python main.py

```



For the Streamlit application:



```bash

streamlit run app.py

```



\## Current Pipeline



The project currently processes a video in multiple stages.



\### 1. Audio Extraction



`yt-dlp` is used to obtain audio from a YouTube URL.



\### 2. Audio Processing



The audio is divided into smaller chunks so that it can be processed without loading the complete file at once.



\### 3. Transcription



For English input, the project uses local Whisper transcription.



For Hinglish input, the transcription pipeline can use Sarvam's speech-to-text translation API.



\### 4. Summarization



The transcript is split into manageable sections and passed through an LLM-based summarization pipeline.



\### 5. Vector Storage



Processed transcript chunks can be stored in ChromaDB so that relevant sections can be retrieved later.



\## Why I built this



Watching an entire long video just to find one specific piece of information can be time-consuming.



The goal of this project is to experiment with a pipeline that can:



\* convert video into text

\* understand the transcript

\* summarize the important parts

\* store the information

\* retrieve relevant content when needed



\## Project Status



This project is still under development.



The core pipeline is working, but there are still areas that I am improving, especially transcription quality, retrieval, and the overall Streamlit experience.



\## Future Improvements



\* Better transcription accuracy

\* Timestamp-based transcript search

\* Question answering over videos

\* Better chunking and retrieval

\* Support for more languages

\* Faster processing for CPU-based systems

\* Improved Streamlit UI

\* Video-specific RAG

\* Deployment



\## Author



\*\*Shrinet Singh\*\*



GitHub: \[Shrinetsingh9648](https://github.com/Shrinetsingh9648)



