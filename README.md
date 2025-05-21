# Steam Review Analysis

간단한 파이프라인으로 Steam 리뷰와 설명문 데이터를 수집·분석·시각화합니다.

1. **리뷰 수집**  
   - `requests`, `BeautifulSoup`로 Top Rated 리뷰 스크래핑  
   - CSV(`steam_reviews.csv`)에 날짜, 텍스트, 추천 여부, 게임 제목 저장

2. **감성 분류 모델**  
   - 텍스트 정제(소문자, 숫자/URL/이모지 제거) 및 spaCy 토큰화  
   - 단어 빈도 기반 BOW 벡터화, SGD 분류기로 긍정/부정 예측  
   - 교차검증, 테스트 정확도·F1, 긍정 단어 Top 20 도출

3. **연도별 감성 트렌드**  
   - `pandas`로 연도별 긍정률 계산  
   - 80% 이상 긍정 게임 수 막대그래프, 개별 히트맵 생성

4. **설명문 토픽 분석**  
   - 2021–2023 게임 설명문 스니펫 수집  
   - LDA로 키워드 추출 후 연도별 빈도 집계  
   - 증가/감소 토픽 클러스터형 막대그래프 시각화

![Image](https://github.com/user-attachments/assets/69f51142-a33c-4bf6-a0e1-e460f7ea882a)
![Image](https://github.com/user-attachments/assets/1fc5c342-8f61-41a6-a40f-1374b1c5ccc7)
![Image](https://github.com/user-attachments/assets/b1cb7c3a-cf03-432b-be9e-2b16714280fa)
![Image](https://github.com/user-attachments/assets/cf6908be-1914-4ff3-8e84-7c656c827209)
