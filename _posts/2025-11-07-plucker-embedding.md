---
title: "Plucker Embedding 이란?"
date: 2025-11-07 17:30:00 +0900
categories: [Computer Vision]
tags: [3DOD]
math: true
---

monocular 3D Obeject Detction에서는 카메라 파라미터의 차이에 따른 성능 저하가 크게 발생한다. 따라서 카메라 높이 변화에 강건한 모델을 구축하기 위해, image transformations, data augmentations, Plcuker Embedding과 같은 방식이 활용된다. 여기서 말하는 "Plucker Embedding"에 대해 공부해보고자 한다. 

## <b>❓Plucker Embedding 이란</b>

3차원 공간에서 선을 표현하는 방법이며, 주로 카메라 위치나 자세의 변화에 불변하는 특징을 추출할 때 사용된다. 
원래 3차원 공간상의 한 직선을 표현할 때는 공간 위 두 점 P, Q를 사용하여 다음과 같이 나타낸다. 

$$
P(x_p, y_p, z_p) \quad Q(x_q, y_q, z_q)
$$
<br>
$$
\overline{PQ} = (x_q-x_p, y_q-y_p, z_q-z_p)
$$

하지만 plucker 좌표는 아래처럼 방향 벡터 $$d$$와 모멘트 벡터 $$m$$으로 표현한다.

$$
(d_x, d_y, d_z, m_x, m_y, m_z)
$$
<br>
$$
d = (x_q-x_p, y_q-y_p, z_q-z_p)
$$
<br>
$$
m = P_1 \times P_2 
$$

따라서 이 plucker 좌표는 3차원 공간의 직선을 6차원 벡터로 나타내는 것이다. 이 좌표를 쓰면 3차원 공간의 복잡한 기하 문제를, 6차원 벡터들의 단순한 연산으로 바꿀 수 있게 된다. 

<br><br>

## <b>❓모멘트 벡터란</b>


