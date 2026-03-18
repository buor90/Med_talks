# MedTalks - AI-Powered Medical Assistant for Students

## Project Description

**MedTalks** is an intelligent conversational system based on an LLM agent architecture, specifically designed to support medical students in their exam preparation. The system analyzes medical questions, retrieves information from reliable sources (internal dataset and external APIs), and generates structured, educational responses tailored to assessment formats.

## Objectives

- Provide a 24/7 virtual tutor for medical students
- Answer medical questions with accuracy and reliability
- Adapt responses to exam formats: MCQs, clinical cases, definitions, clinical reasoning
- Combine validated internal sources with up-to-date external APIs
- Memorize interactions to improve future responses

## Architecture

The project is built on a modular agent-based architecture with four main components:

### 1. Agent Core (Intelligent Core)
- **Planning Module**: Determines response strategy based on question type
- **LLM Engine**: Generates responses using the BLOOM model (Hugging Face)

### 2. Tool Module (Toolbox)
- **Internal Dataset**: Validated medical knowledge base
- **External APIs**: PubMed, Wikipedia, ApiMedic for up-to-date information

### 3. Memory Module (Memory)
- Stores questions, types, API results, and generated answers
- Enables reuse for frequently asked questions

### 4. Classification Module
- Zero-shot classification to identify question type (Definition, Reasoning, Stepwise, MCQ)

## Workflow

```
User Question → Preprocessing → Dataset Lookup → Classification → 
Planning → Tools/APIs → LLM Generation → Memory → Formatting → Answer
```

## Key Features

- Intelligent classification of medical questions
- Multi-source retrieval (internal dataset + APIs)
- Adaptive generation based on question type
- Persistent memory of interactions
- Educational formatting of responses (paragraphs, lists, steps)
- Exam format support: MCQs, clinical cases, definitions

## Technologies Used

- **Python**: Primary programming language
- **BLOOM**: Open-source language model (Hugging Face)
- **APIs**: PubMed, Wikipedia, ApiMedic
  
## Project Structure

```
MedTalks/
├── handler.py                    # Main orchestrator (decision-making)
├── agents/                       # External agents
│   ├── aya_naim/                 # Internal dataset + Memory Module
│   │   ├── orchestrator.py       # Dataset lookup
│   │   └── memory/                # Persistent storage
│   │       ├── question_db/
│   │       ├── type_cache/
│   │       ├── api_cache/
│   │       └── generated_answers/
│   │
│   ├── elaazaouzi_fadwa/         # Classification Module
│   │   └── orchestrateur.py      # Zero-shot classification
│   │
│   ├── noussaiba_mdaghri/        # External APIs Module
│   │   └── orchestrateur.py      # PubMed, Wikipedia, ApiMedic
│   │
│   └── aya_sindel/                # LLM Module (what i worked on)
│       ├── handler.py             # LLM orchestration
│       ├── planning.py             # Prompt construction
│       ├── llm.py                  # BLOOM interface
│       └── prompts/                 # Prompt templates
│           ├── api_prompt.txt
│           ├── dataset_only.txt
│           ├── qcm.txt
│           └── stepwise.txt 
```

## Target Audience

- Medical students preparing for exams (residency, certifications)
- Healthcare professionals seeking quick medical information
- Medical educators creating educational content

## Future Developments

- Integration of interactive clinical cases
- Adaptation to specific medical specialties
- Collaborative features for study groups
- Fine-tuning BLOOM on French medical data

## License

Academic project. All rights reserved.

---
