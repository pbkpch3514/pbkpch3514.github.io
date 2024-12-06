---
title: 랜덤변수가 뭔데?
description: 랜덤변수를 엄밀하게 기술하기
author: pbkpch3514
date: 2024-12-06 12:00:00 +0900
categories: [수학, 확률론]
tags: [수학, 랜덤변수, 위상수학]
pin: true
math: true
mermaid: true
---
미완성본 추후 내용 수정 예정

# 거리공간의 정의

어떤 집합 $V$가 주어질 때 함수 $d : V \times V \rightarrow \mathbb{R}_{\geq 0}$ 가 세 가지 성질을 만족하면
함수 $d$는 거리함수이다.

1. $\forall x, y \in V : d(x,y) = 0 \iff x = y$
2. $\forall x, y \in V : d(x, y) = d(y, x)$
3. $\forall x, y, z \in V : d(x, z) \leq d(x, y) + d(y, z)$

# 거리 공간에서의 open set의 정의

거리 공간 $(S, d)$ 가 주어질 때,

$\forall p \in S, \forall \epsilon > 0 : B_{\epsilon}(p) := \{ x \in S \ | \ d(x, p) < \epsilon \}$ 를 정의 할 수 있다.

이 때 $(S, d)$ 에서의 open set은 $B_{\epsilon}(p)$ 들의 임의의 합집합(arbitrary union) 으로 정의된다.

# 위상공간의 정의

집합 $S$ 가 주어지고  그의 power set  $P(S)$의 부분집합  $T$ 가 다음 조건을 만족하면

$T$를 위상(Topology)라 하고 $(S, T)$를 위상 공간(Topological space)라고 부른다

1. $S, \phi \in T$
2. $\forall i \in I, V_i \in T \implies \bigcup_{i \in I} V_i \in T$ (arbitrary union)
3. $V_1, V_2 \in T \implies V_1 \cap V_2 \in T$ (유한개의 교집합)

그리고 위상  $T$의 원소를 open set이라고 함

# 함수의 정의

두 집합 $A, B$ 가 주어질 때, relation $f \subseteq A \times B$ 가 다음 조건을 만족하면

$f$를 함수라고 한다.

- $\forall a \in A, \exists !b \in B : (a, b) \in f$

$A$의 부분집합 $S$와  $B$의 부분집합 $V$가 주어질 때

- $f(S) := \{ f(x) \in B \ | \ x \in S \}$ the **image of f** under $S$ (상)
- $f^{-1}(V) := \{ x \in A \ | \ f(x) \in V \}$ the **pre-image of f** under $V$ (역상)

# $\epsilon - \delta$ 기반 연속 함수의 정리

$f : \mathbb{R} \rightarrow \mathbb{R}$ 가 $x=p$ 에서 연속이다

$\iff \lim_{x \to p} f(x) = f(p)$

$\iff \forall \epsilon >0, \exists \delta > 0 \text{ such that } \forall q \in (p - \delta, p + \delta), \ f(q) \in (f(p) - \epsilon, f(p) + \epsilon)$

$\iff \forall \epsilon >0, \exists \delta > 0 \text{ such that } B_{\delta}(p) \subseteq f^{-1}(B_{\epsilon}(f(p)))$ 

$\iff \forall \epsilon > 0, f^{-1}(B_{\epsilon}(f(p)) \text{ is open set including } p$

$\iff \forall \epsilon > 0, f^{-1}(B_{\epsilon}f(p))) \text{ is open set in topological space of domain}$

$\iff \forall V \in \text{topological space of codomain}, \ f^{-1}(V) \in \text{topological space of domain}$

# 연속 함수의 정의

두 위상공간 $(A, T_1), \ (B, T_2)$에 대해 함수 $f: A \to B$ 가 다음 조건을 만족할 때

$f$를 연속함수라 부른다.

- $\forall V \in T_2, \ f^{-1}(V) \in T_1$

# 확률 공간의 정의

Sample space $S$, sigma($\sigma$)-field $F$, Probability measure $P$ 의 Triple $(S, F, P)$

# $\sigma$-field

집합 $S$가 주어질 때, $P(S)$의 부분집합 $F$가 세 가지 조건을 만족하면 $F$를 $\sigma$-field라 부른다.

1. $S \in F$
2. $\forall E \in F, E^c \in F$
3. $\forall n \in \mathbb{N}, E_n \in F \implies \bigcup_{n \in \mathbb{N}} E_n \in F$

# Borel $\sigma$-field

위상공간 $(S, T)$가 주어질 때  $T$를 포함하는 가장 작은 $\sigma$-field (유일함)

Borel $\sigma$-field의 원소를 Borel set이라고 한다

# Probability Measure

집합 $S$ 위에 $\sigma$-field  $F$가 주어져 있다고 가정하자.

$P : F \to [0, 1]$가 다음 조건들을 만족하면 $P$를 확률 측도(Probability Measure)라고 한다

1. $\forall n \in \mathbb{N}, \, E_n \in F \, \text{ and } \, \forall n, m \in \mathbb{N} \, (n \neq m \implies E_n \cap E_m = \emptyset) \implies P\left(\bigcup_{n=1}^\infty E_n\right) = \sum_{n=1}^\infty P(E_n).$
2. $P(S) = 1$

# Random Variable

확률공간 $(S, F, P)$가 주어지고 함수 $X : S \to \mathbb{R}$ 이 다음 조건을 만족하면

$X$를 Random Variable이라고 한다.

- $\mathbb{R}$의 Borel $\sigma$-field $B(\mathbb{R})$이 주어질 때,
$\forall B \in B(\mathbb{R}), X^{-1}(B) \in F$

# Distribution of Random Variable

Random Variable $X$가 주어진 시점에서 공역인 $\mathbb{R}$에 확률 측도를 주는 개념

$P_X : B(\mathbb{R}) \to [0, 1]$ 를 정의 할 수 있다.

Random Variable $X$를 활용하여 $P_X(B) := P(X^{-1}(B))$ 를 만들 수 있는데

이 때  $P_X$를 Random Variable $X$의 분포(distribution)이라고 한다.

# Cumulative Distribution Function

Random Variable $X : (S, F, P) \to (\mathbb{R}, B(\mathbb{R}))$ 가 주어지면

$X$의 **Cumulative Distribution Function(CDF) $F_X: \mathbb{R} \to [0, 1]$**는 다음과 같이 정의된다.

$F_X(x) := P(X^{-1}((-\infty, x)))$

CDF $F_X : \mathbb{R} \to [0, 1]$은 다음 세 가지를 만족한다.

1. $\forall x, y \in \mathbb{R}, \ x \leq y \implies F(x) \leq F(y)$
2. $\forall x \in \mathbb{R},\ \lim_{y \searrow x}F(y) = F(x)$
3. $\lim_{x\to -\infty}F(x) = 0 \text{ and } \lim_{x \to \infty}F(x) = 1$
