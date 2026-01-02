---
layout: post
title:  "Column space & Null space"
date:   2024-01-02 19:00:00 +0900       # 작성 날짜 (자동 생성됨)
categories: [Study, Linear Algebra]               # [메인 카테고리, 서브 카테고리]
tags: [linar algebra, matrix, column space, null space]    # 태그 (소문자로 작성 추천)
math: true                              # 수식(LaTeX)을 쓴다면 필수! (중요)
---

## Column space
### 목적
$A$ 시스템이 만들어 낼 수 있는 모든 가능성

> ex) 로봇 팔이 닿을 수 있는 작업공간
{: .prompt-info }

### 설명
$$
Ax=b
$$
$$
A = \begin{bmatrix}
1 & 1 & 2 \\
2 & 1 & 3 \\
3 & 1 & 4 \\
4 & 1 & 5 
\end{bmatrix}
$$

다음과 같을 때, 아래처럼 $A$의 column 선형 결과 형태로 표현이 가능

$$
x_1
\begin{bmatrix} 1 \\
2 \\
3 \\
4
\end{bmatrix} + x_2
\begin{bmatrix} 1 \\
1 \\
1 \\
1
\end{bmatrix}+ x_3
\begin{bmatrix} 2 \\
3 \\
4 \\
5
\end{bmatrix}= \begin{bmatrix} b_1 \\
b_2 \\
b_3 \\
b_4
\end{bmatrix}
$$

즉, $b$가 행렬 $A$의 column space에 존재해야만, 해를 구할 수 있음

## Null space
### 목적
$A$ 시스템에 입력을 해도 결과값이 항상 0이 됨.

즉, 아무런 변화를 주지 않는 입력값들임

- null space가 O벡터 하나라면, 해는 오직하나.
- null space에 다른 벡터가 있다면, 해가 무수히 많다는 뜻

> ex) 로봇 팔이 컵을 들고 있는 상태($Ax=b$ 유지)에서, 컵을 쏟지 않고 팔꿈지만 들어 올려 장애물을 피하려면, 움직임은 반드시 null space 안에서 계산되어야 함
{: .prompt-info }

### 설명
$Ax=O$에서 이 식을 만족시키는 $x$의 집합

O벡터는 무조건 null space에 포함

위의 예시에서는 col1과 col2를 더하고 col3에 -1을 곱하여 더해주면 그 결과가 O벡터가 됨.

즉, x = [1 1 -1]T의 상수배는 전부 null space

$$
x = c\begin{bmatrix} 1 \\
1 \\
-1
\end{bmatrix}
$$

> [참고 블로그](https://twlab.tistory.com/17 "Learn Again! 러너게인")
{: .prompt-info }
