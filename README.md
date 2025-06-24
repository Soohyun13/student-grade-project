# 🎓 학생 성적에 영향을 미치는 요인 탐색 및 시각화 프로젝트

> **멋쟁이사자처럼 데이터 분석 4기 미드 프로젝트**  
> 학생들의 성적에 영향을 미치는 핵심 요인을 데이터 시각화와 추론통계를 통해 탐색하고, 교육적 인사이트를 도출한 팀 프로젝트
>
> 진행 기간: 2025.03.14 ~ 2025.03.21 (8일)

---

## 📌 프로젝트 개요

학생들 간의 학습 격차가 심화되고 있는 상황에서, 성적 부진의 원인을 단순히 ‘노력 부족’으로 해석하는 경향이 있음
그러나, 실제로는 **학생의 개인적 배경, 수업 참여도 등 다양한 요인이 학생들의 학업 성취도에 영향**을 줄 수 있음

실질적인 교육적 인사이트와 시사점을 도출하고 학생들의 학업 성취도를 효율적으로 높이기 위하여,
정량적 데이터를 기반으로 성적에 영향을 미치는 핵심 요인을 찾는 프로젝트를 기획

---

## 🎯 목표

- **학생의 성적과 관련 있는 요인들을 통계적으로 검정**
- **변수 간 관계를 시각적으로 명확하게 전달**
- 분석 결과를 통해 **교육 인사이트 도출**

---

## 📂 데이터 개요

- **출처**: [Kaggle - Students’ Academic Performance Dataset](https://www.kaggle.com/datasets/aljarah/xAPI-Edu-Data/data)
- **특징**
  - Kalboard 360 학습 관리 시스템(LMS)에서 수집된 480명의 학생 데이터
  - 학습 활동 추적 도구 xAPI (Experience API)를 통해 수집되었으며, 학생의 인구통계 정보, 학업 배경, 행동 특성을 포함
#### 📑 주요 변수 목록

| 속성명                   | 설명                           |
|------------------------|--------------------------------|
| `gender`              | 학생의 성별                     |
| `Nationality`         | 학생의 국적                     |
| `PlaceofBirth`        | 학생의 출생 국가                |
| `StageID`             | 학생의 교육 단계                |
| `GradeID`             | 학생의 학년                     |
| `SectionID`           | 학생의 반 ID                       |
| `Topic`               | 수업 과목                       |
| `Semester`            | 학기 정보                       |
| `Relation`            | 학생을 책임지는 부모            |
| `raisedhands`         | 수업 중 손을 든 횟수            |
| `VisITedResources`    | 학습 리소스 방문 횟수           |
| `AnnouncementsView`   | 공지사항 확인 횟수              |
| `Discussion`          | 토론 그룹 참여 횟수             |
| `ParentAnsweringSurvey` | 부모 설문조사 응답 여부       |
| `ParentschoolSatisfaction` | 부모의 학교 만족도         |
| `StudentAbsentDays`   | 학생의 결석 일수                |
| `Class`               | 학생의 성적 (L/M/H 분류)        |


---

## 🛠 사용 기술

- **언어/환경**: Python, Jupyter Notebook  
- **데이터 처리**: pandas, numpy  
- **시각화**: seaborn, matplotlib  
- **통계 분석**: scipy.stats (카이제곱 검정, T-test 등)
- **문서화 및 협업**: GitHub, Notion, PowerPoint

---

## 🔍 분석 및 탐색 과정

### 1. EDA 및 전처리
- 성적(Class) 변수를 L=1, M=2, H=3으로 변환 -> 상관계수, 성적 평균 계산 등의 편의를 위함
- 이상치/결측치 없음 확인
- 변수별 분포 및 상관 관계 시각화

### 2. 통계 검정 및 인사이트 도출
- **부모의 성별/부모의 만족도/결석 일수/수업 참여도/학생의 성별** 등 다양한 요인에 대해 성적과의 유의미한 관계 검정
  - 부모의 성별과 성적: **어머니가 관리**할수록 성적 우수
  - 부모 만족도와 성적: **만족도가 높을수록** 성적 우수 (p-value < 0.05)
  - 결석 일수와 성적: **결석이 적을수록** 성적 우수 (p-value < 0.05)
  - 수업 참여도(손들기/자료 이용)와 성적: **양의 상관관계**
  - 학생의 성적과 성별: **인문계열, 자연/공학계열 과목 모두 여학생**이 성적 우수 (p-value < 0.05)

### 3. 시각화
바 차트, 파이 차트 등을 통해 변수 간 관계를 직관적으로 표현

**(1) 어머니가 관리하는 경우 Class 1(우수한 성적)의 비율이 더 높음**
![image](https://github.com/user-attachments/assets/19f293c1-f312-4a17-8c41-0d26d2eaeaa1)

**(2) 학교에 대한 부모의 만족도가 높을 수록 Class 1(우수한 성적)의 비율이 더 높음**
![image](https://github.com/user-attachments/assets/328181f1-51ca-4cea-bfe6-2bcc42049bd8)

**(3) 결석일수가 적을 수록(7일 미만 vs 7일 이상) Class 1(우수한 성적)의 비율이 더 높음**
![image](https://github.com/user-attachments/assets/c650d3ae-8989-433c-9c18-b310ce22349a)

**(4) 성적이 우수한 학생들은(Class 1) 수업 참여도(손들기/자료 이용)가 높은 쪽에 더 많이 분포되어 있음**
![image](https://github.com/user-attachments/assets/cb47d38c-6228-476b-bea4-2397131bc324) ![image](https://github.com/user-attachments/assets/d9549c49-17fb-46e4-ac79-76e4c97c1134)

**(5) 인문계열, 자연/공학계열 과목 모두 남학생보다 여학생의 Class 1(우수한 성적) 비율이 더 높음**
![image](https://github.com/user-attachments/assets/93388733-2d8a-47df-86bb-778b6500f275) ![image](https://github.com/user-attachments/assets/f09d8ca2-e3f3-4ab3-9609-e1b6c4ae9533)

---

## 📈 성과

- **부모의 관심도, 수업 참여도 요인이 성적에 유의한 영향을 준다는 통계적 근거 확보**  
- **각 가설별 통계 검정을 통한 분석 타당성 확보**  
- 교육업계 종사자를 대상으로 하는 실질적 교육 인사이트 제공 가능 → **가정과 학교 간의 상호작용 강화 필요, 수업 중 손들기를 유도할 수 있는 교실 분위기 조성 및 온라인 학습 자료에 대한 접근성 확대 필요**

---

## 🙌 팀원

- **김수현**: 조장 / 시각화, 인사이트 도출 / PPT 작성 / 발표
- **문병두**: 시각화, 인사이트 도출 / 회의록 작성
- **이정태**: 시각화, 인사이트 도출 
- **장선희**: 시각화, 인사이트 도출 / PPT 작성 / 팀 노션 구축
- **최지영**: 시각화, 인사이트 도출 / PPT 작성 / 최종 코드 정리

---

## 🗂 브랜치 & 파일 구조

| 브랜치       | 파일명                                                                                                                                                                                                                                                                               | 설명                    |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |
| `main`    | [README.md](https://github.com/Soohyun13/student-grade-project)                                                                                                                                                                                                                   | 메인 프로젝트 설명 문서         |
| `soohyun` | [README.md](https://github.com/Soohyun13/student-grade-project/tree/soohyun)                                                                                                                                                                                                      | 동일한 설명 문서 (개인 작업 브랜치) |
| `soohyun` | [\[멋사\]DAB4\_6팀\_미드프로젝트\_코드취합.ipynb](https://github.com/Soohyun13/student-grade-project/blob/soohyun/%5B%EB%A9%8B%EC%82%AC%5DDAB4_6%ED%8C%80_%EB%AF%B8%EB%93%9C%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8_%EC%BD%94%EB%93%9C%EC%B7%A8%ED%95%A9.ipynb)                                   | 팀 통합 분석 코드            |
| `soohyun` | [학생\_성적\_분석\_데이터\_전처리\_및\_시각화\_250317.ipynb](https://github.com/Soohyun13/student-grade-project/blob/soohyun/%ED%95%99%EC%83%9D_%EC%84%B1%EC%A0%81_%EB%B6%84%EC%84%9D_%EB%8D%B0%EC%9D%B4%ED%84%B0_%EC%A0%84%EC%B2%98%EB%A6%AC_%EB%B0%8F_%EC%8B%9C%EA%B0%81%ED%99%94_250317.ipynb) | 개인 분석 및 시각화 작업 파일     |

---
