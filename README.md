# 📰 News Article Classification with Machine Learning

본 프로젝트는 뉴스 기사 데이터를 활용하여 **카테고리 분류 모델**을 개발한 결과물을 담고 있습니다.  
텍스트 데이터(제목+본문)와 발행사 정보를 다양한 인코딩 기법으로 전처리하여, 여러 ML 모델의 성능을 비교·평가했습니다.  

- **개발 시기**: 2024.02

---

## 📂 프로젝트 구조

### 🔹 Machine Learning 관련 파일
- **Include_PressCompany.ipynb**
  - 입력 데이터: 제목+본문(Document), 발행사
  - 타겟 데이터: 카테고리
  - 모델: Logistic Regression, Naive Bayes, XGB, SVM  
  - ✅ Best Score: **0.88 (SVM / Word2Vec(본문) + One-Hot(발행사) + Label(카테고리))**

- **Drop_PressCompany.ipynb**
  - 입력 데이터: 제목+본문(Document)
  - 타겟 데이터: 카테고리
  - 모델: Logistic Regression, Naive Bayes, XGB, SVM  
  - ✅ Best Score: **0.86 (Logistic Regression / TF-IDF(본문) + Label(카테고리))**

- **Pre-processing+.ipynb**
  - 추가 전처리: 불용어 제거, 무의미 문자열 제거, 명사·영어·한자 추출, 본문 내 발행사 제거
  - 모델: Logistic Regression, XGB, SVM  
  - ✅ Best Score: **0.87 (Logistic Regression & SVM)**

- **Test_Input.ipynb**
  - 새로운 입력 데이터에 대해 카테고리 예측  
  - 1번 파일의 **SVM(Word2Vec + One-Hot + Label, Score: 0.88)** 모델 적용

---

### 🔹 크롤링 관련 파일
- **네이버 뉴스 크롤 _ 문제점 발견.ipynb**
  - BeautifulSoup만으로는 크롤링 불가 문제 확인

- **네이버 뉴스 카테고리 크롤링 _ 최종.ipynb**
  - Selenium + BeautifulSoup 병행 사용으로 문제 해결

---

## 📊 실험 요약
- **발행사(Press Company) Feature 포함 여부 실험**
  - 포함 시: Score 약간 상승 (최대 +0.02)
  - 발행사가 카테고리 분류에 **유의미한 feature인지 판단은 제한적**

---

## ⚙️ 사용 기법
- **인코딩**
  - 텍스트: TF-IDF, Word2Vec
  - 발행사: One-Hot Encoding, Label Encoding
  - 카테고리: Label Encoding

- **모델**
  - Logistic Regression
  - Naive Bayes
  - XGBoost
  - SVM

---

## 🚀 성과
- 최고 성능 모델: **SVM (Score 0.88)**  
- 발행사 정보를 feature로 포함할 경우 약간의 성능 향상 확인  
- 뉴스 기사 자동 분류 파이프라인 구축 및 적용 테스트 완료
