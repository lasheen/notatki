---
title: Układy równań na macierzach
---

# Układy równań na macierzach

## Kontynuacja z poprzedniego wykładu

Macierz jest odwracalna wtedy i tylko wtedy, gdy jest ona iloczynem macierzy elementarnych.
{:.conc}

- Macierz $$ A \in M_{n \times n}(K) $$ jest odwracalna wtedy i tylko wtedy, gdy `rząd(A) = n`, co równoważne jest temu, że postać schodkowa nie ma zerowych wierszy.
- Macierz jest odwracalna wtedy i tylko wtedy, gdy jej wyznacznik jest różny od 0.
{:.conc}

## Układy równań liniowych

To jest układ równań liniowych (*):

$$
a_{ij} \in K \\
b_i \in K \\

\left\{\begin{array}{l}
    a_{11}x_1 + a_{12}x_2 + \ldots + a_{1n}x_n = b_1 \\
    a_{21}x_1 + a_{22}x_2 + \ldots + a_{2n}x_n = b_2 \\
    \vdots \\
    a_{m1}x_1 + a_{m2}x_2 + \ldots + a_{mn}x_n = b_m
\end{array}\right.
$$

To jest macierz układu (*):

$$ \\
A = \left[
\begin{array}{ccc}
a_{11} & \ldots & a_{1n} \\
\vdots & \ddots & \vdots \\
a_{m1} & \ldots & a_{mn}
\end{array}
\right] \\
$$

To jest macierz rozszerzona układu (*):

$$ \\
A' = \left[
\begin{array}{ccc|c}
a_{11} & \ldots & a_{1n} & b_1 \\
\vdots & \ddots & \vdots & \vdots \\
a_{m1} & \ldots & a_{mn} & b_n
\end{array}
\right] \\
$$

Układ (*) można zapisać w postaci $$ A \cdot \left[ \begin{array}{c} x_1 \\ \vdots \\ x_n \end{array} \right] = \left[ \begin{array}{c} b_1 \\ \vdots \\ b_m \end{array} \right] $$ lub $$ A \cdot \vec{x} = \vec{b} $$.

## Równoważność układów równań

Dwa układy równań są **równoważne**, gdy mają ten sam zbiór rozwiązań.
{:.def}

Jeśli macierze rozszerzone dwóch układów równań są wierszowo równoważne, to dane układy są równoważne. Innymi słowy, po zastosowaniu ciągu operacji elementarnych na równaniach układu dostajemy układ z nim równoważny.
{:.fact}

## Rozwiązywanie układów równań

<div class="theorem" markdown="1">
Niech A' - macierz rozszerzona układu (*), a A" - macierz schodkowa z nią wierszowo równoważna. Wtedy:

1. jeśli A" ma wiersz postaci (0, ..., 0, b), gdzie b≠0, to układ (*) jest **sprzeczny** (nie ma żadnego rozwiązania)
2. jeśli A" nie ma takiego wiersza, to układ (*) jest niesprzeczny i
    1. jeśli ilość niezerowych wierszy macierzy A" jest równa liczbie niewiadomych (tzn. n), to układ ma dokładnie 1 rozwiązanie`
    2. jeśli ilość niezerowych wierszy macierzy A" jest mniejsza od n, to układ ma nieskończenie wiele rozwiązań (przy założeniu, że K jest nieskończone) i można je dokładnie opisać używając A" (a jeszcze szybciej, używając A" w postaci zredukowanej)
</div>

<div class="example" markdown="1">
$$
\left\{\begin{array}{l}
    x_1 - x_2 + 2x_3 - x_4 = 1 \\
    2x_1 - 3x_2 - x_3 + x_4 = -1 \\
    x_1 + 7x_3 - 4x_4 = 4
\end{array}\right.\ (*)
$$

**Rozwiązanie**

$$ \\
A' = \left[
\begin{array}{cccc|c}
1 & -1 & 2 & 1 & 1 \\
2 & -3 & -1 & 1 & -1 \\
1 & 0 & -7 & 4 & 4
\end{array}
\right]
\longrightarrow^{III - I}_{II - 2I}
    \left[
    \begin{array}{cccc|c}
    1 & -1 & 2 & -1 & 1 \\
    0 & -1 & -5 & 3 & -3 \\
    0 & 1 & 5 & -3 & 3
    \end{array}
    \right]
\longrightarrow^{III + II} \\
    \left[
    \begin{array}{cccc|c}
    1 & -1 & 2 & -1 & 1 \\
    0 & -1 & -5 & 3 & -3 \\
    0 & 0 & 0 & 0 & 0
    \end{array}
    \right]^{\ \normalsize{\textbf{A''}}}
\longrightarrow^{(-1) II}
    \left[
    \begin{array}{cccc|c}
    1 & -1 & 2 & -1 & 1 \\
    0 & 1 & 5 & -3 & 3 \\
    0 & 0 & 0 & 0 & 0
    \end{array}
    \right]
\longrightarrow^{I + II} \\
    \left[
    \begin{array}{cccc|c}
    1 & 0 & 7 & -4 & 4 \\
    0 & 1 & 5 & -3 & 3 \\
    0 & 0 & 0 & 0 & 0
    \end{array}
    \right]^{\ \normalsize{\textbf{A'''}}}
\textbf{- postać zredukowana} \\
$$

Teraz wystarczy analogicznie przerobić macierze na układy równań i zrobić redukcję. Z macierzy A''' wynik wychodzi bezpośrednio, podczas gdy z A'' trzeba zrobić jeszcze kilka przejść.

Zatem zbiór rozwiązań (*) to:

$$
\left\{
    \left[ \begin{array}{l}
        -7\alpha + 4\beta + 4 \\
        -5\alpha + 3\beta + 3 \\
        \alpha \\
        \beta
    \end{array} \right] : \alpha, \beta \in K
\right\}
=
\left\{
    \alpha \cdot \left[ \begin{array}{c}
        7 \\
        -5 \\
        1 \\
        0
    \end{array} \right]
    + \beta \cdot \left[ \begin{array}{c}
        4 \\
        3 \\
        0 \\
        1
    \end{array} \right]
    + \left[ \begin{array}{c}
        4 \\
        3 \\
        0 \\
        0
    \end{array} \right] : \alpha, \beta \in K
\right\}
$$

</div>

<div class="conc" markdown="1">
**Twierdzenie Kroneckera-Capelliego**

Układ równań liniowych jest niesprzeczny wtedy i tylko wtedy, gdy `rząd(A) = rząd(A')`.
</div>

Układ ma dokładnie jedno rozwiązanie wtedy i tylko wtedy, gdy `rząd(A) = rząd(A') = liczba niewiadomych`.
{:.conc}

## Układy jednorodne

<div class="def" markdown="1">
**Układ jednorodny** to układ postaci:

$$
\left\{\begin{array}{l}
    a_{11}x_1 + a_{12}x_2 + \ldots + a_{1n}x_n = 0 \\
    \vdots \\
    a_{m1}x_1 + a_{m2}x_2 + \ldots + a_{mn}x_n = 0
\end{array}\right.\ (**)
$$

</div>

Niech S - zbiór rozwiązań układu jednorodnego (\*\*). Wtedy S jest podprzestrzenią $$K^n$$ oraz $$\dim(S) = n - rząd(a)$$. W szczególności $$\vec{0} = \left[\begin{array}{c} 0 \\ \vdots \\ 0 \end{array}\right]$$ jest rozwiązaniem (\*\*).
{:.theorem}

<div class="example" markdown="1">
Układ jednorodny powstały z (*) ma zbiór rozwiązań:

$$
S = \left\{
    \alpha \cdot \left[ \begin{array}{c}
        7 \\
        -5 \\
        1 \\
        0
    \end{array} \right]
    + \beta \cdot \left[ \begin{array}{c}
        4 \\
        3 \\
        0 \\
        1
    \end{array} \right] : \alpha, \beta \in K
\right\}
$$

Baza S to:

$$
\left\{
    \left[ \begin{array}{c}
        7 \\
        -5 \\
        1 \\
        0
    \end{array} \right]\ \ 
    \left[ \begin{array}{c}
        4 \\
        3 \\
        0 \\
        1
    \end{array} \right]
\right\}
$$

</div>

Niech $$\vec{c}$$ będzie dowolnym rozwiązaniem układu $$A\vec{x} = \vec{b}$$. Wystarczy znaleźć jedno jego rozwiązanie $$\vec{c}$$ i dodać je do wszystkich rozwiązań układu jednorodnego $$A\vec{x} = \vec{0}$$.
{:.theorem}

## Układy Cramera

Układ $$ \left\{\begin{array}{l} a_{11}x_1 + a_{12}x_2 + \ldots + a_{1n}x_n = b_1 \\ \vdots \\ a_{m1}x_1 + a_{m2}x_2 + \ldots + a_{mn}x_n = b_m \end{array}\right. $$ nazywamy **układem Cramera**, gdy $$ m=n $$ i $$ \det(A) \neq 0 $$, gdzie A jest zmienną tego układu.
{:.def}

<div class="theorem" markdown="1">
Układ Cramera ma dokładnie 1 rozwiązanie i jest ono zadane **wzorami Cramera**:

$$
\left\{
    \begin{array}{l}
        x_1 = \frac{\det(A_1)}{\det(A)} \\
        \vdots \\
        x_n = \frac{\det(A_n)}{\det(A)}
    \end{array}
\right.
$$

gdzie $$A_j$$ jest macierzą powstałą z A przez zastąpienie j-tej kolumny kolumną $$ \left[\begin{array}{c} b_1 \\ \vdots \\ b_n \end{array}\right] $$.

</div>

## Macierze podobne

Macierze $$ A, B \in M_{n \times m}(K) $$ są **podobne**, gdy istnieje macierz odwracalna $$ P \in M_{n \times n}(K) $$ taka, że $$ B = P^{-1}AP^{1} $$.
{:.def}

Relacja podobieństwa macierzy jest relacją równoważności.
{:.fact}

Niech V - przestrzenie liniowe wymiaru n nad K, a $$ B, C \in M_{n \times n}(K) $$. Wówczas B i C są podobne wtedy i tylko wtedy, gdy $$ (\exists L : V \rightarrow V) (\exists \mathfrak{B}, \mathfrak{C} - bazy\ V) (B = m_{\mathfrak{BB}}(L) \times C = m_{\mathfrak{CC}}(L)) $$.
{:.theorem}