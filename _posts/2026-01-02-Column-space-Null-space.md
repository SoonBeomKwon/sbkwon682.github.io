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
#### null space란?
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

#### null space 계산
- pivot: REF(row echelon form)으로 만들었을 떄, zero row가 아닌 row중에 가장 왼쪽에 있는 0이 아닌 성분
- pivot column: pivot이 있는 column
- rank: pivot의 갯수
- free column: pivot column을 제외한 나머지 column
- free variable: REF에서 pivot이 없는 열에 해당하는 변수
- free variable 갯수 = n(column의 수) - r(rank)
- free variable을 통해서 만들어진 해들의 선형결합이 바로 **null space**

#### RREF(Reduced Row Echelon Form)
- Gauss Elimination 방법으로 REF로 만듦
- Gauss-Jordan Elimination으로 pivot원소 위쪽에 있는 원소들을 소거
- pivot원소를 1로 만들기 위해서 pivot에 해당하는 row 전체를 pivot으로 나눔
- origial matrix, REF, RREF 모두 null space는 동일

## complete solution(완전해)
- complete solution이란 $Ax=b$를 만족하는 모든 $x$
- $b$에 대한 가해조건(solvability condition on $b$): $b$벡터가 행렬$A$의 column space 안에 존재할 떄
- particular solution(특수해), $x_p$: free variable을 0으로 설정하고 나머지 $x$벡터의 원소를 구함. 상수배는 하지 않음
- null space solution, $x_n$: 이전에 구한 것처럼 구함
- complete solution: $x=x_p+x_n$

## rank와 해의 조건
$r$: rank, $m$: number of rows, $n$: number of columns

| $r=m=n$ | $r=n<m$ | $r=m<n$ | $r<m, r<n$ |
| :---: | :---: | :---: | :---: |
| $RREF=I$ | $RREF=\left[ {I \atop O} \right]$ | $RREF=\left[ I \ \ F \right]$ <br> $F$: free columns | $RREF=\left[ {I \atop O} \ \ {F \atop O} \right]$ <br> $F$: free columns |
| • $Ax=b$에 대해 오직 하나의 해만 존재 | • 해가 없거나 <br> • 오직 하나의 해만 존재 | • 해가 항상 존재 <br> • 무한대의 해가 존재 | • 해가 없거나 <br> • 무한대의 해가 존재 |

> [참고 블로그1](https://twlab.tistory.com/17 "Learn Again! 러너게인")
> [참고 블로그2](https://twlab.tistory.com/21 "Learn Again! 러너게인")
> [참고 블로그3](https://twlab.tistory.com/22 "Learn Again! 러너게인")
{: .prompt-info }
