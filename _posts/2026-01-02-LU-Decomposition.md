---
layout: post
title:  "LU Decomposition"
date:   2024-01-02 18:55:00 +0900       # 작성 날짜 (자동 생성됨)
categories: [Study, Linear Algebra]               # [메인 카테고리, 서브 카테고리]
tags: [linar algebra, matrix, LU]    # 태그 (소문자로 작성 추천)
math: true                              # 수식(LaTeX)을 쓴다면 필수! (중요)
---

## 목적
### 1. A가 고정되고 b가 계속 바뀔 때의 효율성
> 가장 큰 이유
{: .prompt-tip }

$Ax=b$ 에서 $b$를 구하는 복잡도는 $O(n^3)$

LU분해를 한번 해두면 $b$가 바뀌어도 단순 대입으로 해를 구할 수 있음

이때 복잡도는 $O(n^2)$

> 과정
> 1. $Ax=b$ -> $LUx=b$
> 2. $Ux=y$라고 두면, $Ly=b$가 됨
> 3. 전방대입: $Ly=b$ 풀어 $y$ 구함
> 4. 후방대입: $Ux=y$ 풀어 최종 $x$를 구함

### 2. 역행렬 계산 효율
LU분해를 한번 해두면 $O(n^2)$ 과정을 n번 반복만 하면 됨

### 3. Determinant 계산 용이
$L$와 $U$는 삼각행렬이므로, 대각선 성분들의 곱이 곧 그 행렬의 determinant가 됨

$det(L)=1$로 만들고 $U$의 대각선분만 곱하면 $A$의 determinant를 구할 수 있음

### 4. 수치적 안정화
컴퓨터로 계산시 대각 성분이 0에 가까우면 오차가 크게 발생함

PLU분해($PA=LU$)를 사용하면, 수치적으로 훨씬 안정적인 해를 얻을 수 있음

> 참고 블로그: https://twlab.tistory.com/12
{: .prompt-info }
