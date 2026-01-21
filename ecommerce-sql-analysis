# 📊 PM Data Analysis Case Study
> SQL 기반 데이터 분석을 통해 **제품/비즈니스 의사결정 인사이트**를 도출한 PM 사이드 프로젝트

---

## 1. Project Overview

### 🎯 Goal
이 프로젝트의 목적은 공개 데이터를 활용해  
**PM 관점에서 의미 있는 질문을 정의하고,  
SQL 분석을 통해 실행 가능한 인사이트를 도출하는 것**입니다.

### 👤 Role
- Product Manager (개인 프로젝트)
- 문제 정의 → 분석 설계 → 인사이트 도출 → 액션 제안 전 과정 수행

---

## 2. Problem Statement

데이터는 존재하지만,  
다음과 같은 질문에는 명확한 답이 없는 상황을 가정했습니다.

- 매출 성장은 **신규 고객** 때문인가, **기존 고객** 때문인가?
- 고객의 재구매는 **언제** 가장 많이 발생하는가?
- 현재 지표 구조는 **장기 성장에 적합한가?**

👉 본 분석은 **“그래서 PM은 무엇을 해야 하는가?”**에 답하는 데 초점을 맞췄습니다.

---

## 3. Dataset

- Source: Kaggle – *(Dataset name)*
- Period: YYYY.MM ~ YYYY.MM
- Records: 약 N rows

### Main Columns
| Column | Description |
|------|------------|
| order_id | 주문 ID |
| customer_id | 고객 ID |
| order_date | 주문 일자 |
| product | 상품 |
| quantity | 수량 |
| price | 단가 |

---

## 4. Tools & Environment

- SQL (SQLite / DuckDB)
- VS Code
- Python (pandas, matplotlib, seaborn) – 결과 검증 및 시각화

---

## 5. Analysis Approach

분석은 아래 흐름으로 진행했습니다.

1. PM 관점 핵심 질문 정의
2. SQL을 활용한 데이터 집계
3. 패턴 및 이상치 확인
4. 비즈니스 관점 해석
5. 실행 가능한 액션 도출

---

## 6. Key Analysis & Insights

### 6.1 Revenue Structure (New vs Returning)

**Question**  
> 전체 매출에서 신규 고객과 기존 고객의 기여도는?

**SQL Example**
```sql
SELECT
  CASE
    WHEN first_order_date = order_date THEN 'New'
    ELSE 'Returning'
  END AS customer_type,
  SUM(amount) AS revenue
FROM orders
GROUP BY 1;
