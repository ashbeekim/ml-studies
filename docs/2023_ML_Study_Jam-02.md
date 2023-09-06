# Introduction to Large Language Models

## Contexts
* [Course](#course)
* [TIL](#til)

## Course
* [x] VIDEO: Introduction to Large Language Models
* [x] DOCUMENT: Introduction to Large Language Models: Reading
* [x] QUIZ: Introduction to Large Language Models: Quiz

## TIL
강의의 내용은 다음의 과정으로 전개됨.
* Define Large Language Models(LLMs)
* Describe LLM Use Cases
* Explain Prompt Tuning
* Describe Gen AI development tools

**LLMs**?
* 크고 보편적인 데이터셋을 사용하여 학습된 모델
* 이러한 모델은 특수한 목적을 위해 사전 훈련, Fine-tuning 할 수 있음
* 분명한 목적을 가지고 있지 않은 경우, LLM은 다양한 작업에 사용할 수 있음
* common language task:
    * Text Classification
    * Question Answering
    * Document Summarization
    * Text Generation
* specific problem in a domain: 관련된 적은 양의 데이터를 사용하여 특정 문제를 해결하는 데 사용할 수 있음
    * Legal
    * Retail
    * Medical
    * Finance
    * Entertainment
    * etc.
* model
    * size: 100M ~ 1T parameters
    * Pathways Language Model(PaLM)
        * 540 billion parameters
        * leverages the new Pathway systems
        * Orchestrates distributed computation for accelerators
* 도메인 지식(by task)
    * QA
        * Big Tech
        * Consumer
        * Education
        * Media
        * Pharma and Healthcare
        * Retail
        * Supply Chain

**Prompt**
* Design: 목표한 결과를 향상시키기 위해 모델에 제공하는 텍스트(instructions, context)
* Engineering: 다양한 활용을 휘한 언어 모델을 효율적으로 사용하기 위한 실습 코드를 개발하거나 최적화하는 것
* Case:
    * Generic(or Raw) Language Models: 학습된 데이터셋의 언어 기반 다음 다음 단어(토큰)를 예측하는 모델
    * Instruction Tuned: 제공된 지침을 따른 응답(Summarization, Writing, Keyword extraction)을 예측하는 모델
    * Dialog Tuned: 다음 응답을 예측함으로써 대화를 생성하는 모델
* efficient methods of tuning
    * Parameter-Efficient Tuning Methods(PETM)

**Notes of the wrong answers**
-
