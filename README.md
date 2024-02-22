# Korea-University-Intelligent-Information-SW-Academy-
고려대학교 지능정보 SW 아카데미에서 수행한 프로젝트입니다.

# 특허 검색 시스템



## 데이터 전처리 & EDA (Crawling_1_상세.ipynb, Crawling_result_정리.ipynb)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/d1b64a9c-a45b-4203-9051-2f0971b01c2b)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/62a28eaa-ad06-42ef-838b-ee12b5e72ecf)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/a1b56566-2c85-4dd6-86d9-a557ee0d9560)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/974ab05d-fa9a-42a2-8e4b-fdff6433e0c2)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/cef56800-ba71-4d4b-a87c-52dec5896453)



## 모델 (BERT_training_2.ipynb)
### 기존 모델
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/9a4e34a5-2194-4ca8-84f5-9c1366927506)
### 제안하는 모델 & 학습 과정
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/94a719cf-5c36-4a2c-b3e9-a1f7f4ae80b3)

## 시스템
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/83a51ed0-b828-42c3-a034-5323d9ae5a60)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/ca46a272-ee87-49de-9dbd-cd136df253dc)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/bd9d873d-cbf4-4d2d-8d3e-6adc0c4f8e06)

<br/>
# 특허 특화 Chatbot

## 기본 모델
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/06bca891-f248-4913-b72f-89353936ec20)

## 전체 시스템 
### 검색 증강 생성(RAG)을 활용하였습니다
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/5d77dcc8-6653-49b0-bda0-7d55488b0cb6)

## sLLM 학습 & Prompt 시도 (llama~~~.ipynb)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/99ca1e91-18f5-45db-98b9-7b89ae7b650d)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/198541f5-85ea-4d74-9c31-59a2924c5555)
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/a47a2b5d-fa8c-483f-ad62-7381137b8b07)
전체 학습을 시키다가 시간이 너무 많이 걸려서 (30000개 특허 데이터를 기반으로 학습 시 1epoch 당 17시간), 500개를 기반으로 10 epoch까지 학습시켰습니다.

## 외부 데이터베이스 생성(Chroma DB), 결과 인터페이스 (Streamlit)
### 1218_VectorDB_Streamlit_3.ipynb 코드 참조

## 결과
![image](https://github.com/PrayPrey/Korea-University-Intelligent-Information-SW-Academy-/assets/73458088/aa35e526-52bf-4436-b328-7caf6c1eb274)

# Conclusion

## 특허 검색 시스템
전체 기간 (9월 1일 ~ 12월 21일) 중 11월까지 특허 검색 시스템은 완료하였습니다. 실제로 Fine-tunning 모델을 Embedding 층으로 사용하여 단어 기반이 아닌, 청구항 문장/ 요약 문장 을 기반으로 (문장 단위로) 검색할 수 있다는 점에서 경쟁력이 있다고 보았습니다. 왜냐하면 실제 특허 등록 시 똑같은 내용의 특허라도 청구항의 순서가 바뀌면 해당 특허가 보호하는 범위가 다르기 때문입니다. 그러므로 해당 특허 시스템은 청구항의 순서까지 고려한 검색 시스템이라고 볼 수 있습니다.

## 특허 특화 Chatbot 
RAG에서 사용자/외부 데이터베이스/ sLLM을 이어주는 Embedding 함수를 ChatGPT에서 제공하는 것이 아닌 실제 ChatGPT Embedding Class를 Overidding 시켜보았습니다. 그리고, sLLM 학습 시 제한된 자원을(구글 Colab에서 지원하는 A6000 48GB 1EA) 기반으로 QLoRA 및 LoRA 방식을 활용하여 학습시켜 보았습니다. 각 vector에서 자료형을 바꿈으로서 정확도 손실이 일어나지만, 양자화를 통해서 정확도 손실을 최소화 시키면서 전체 모델 및 데이터 크기를 줄일 수 있었습니다. 이러한 방식을 통해서 획기적으로 학습 시간을 줄여보았습니다. 최종 모델 결과는 좋지 않게 나왔지만, 의미있는 시도였고 앞으로 더 나은 컴퓨팅 자원이 있다면 더 빠르게 학습 시도를 해볼 수 있을 것 같습니다.






