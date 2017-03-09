Source : [Paper](http://www.roboticsproceedings.org/rss05/p21.pdf)

# pre

## Multivariate normal distribution

N(μ, Σ) : Σ = E[(Χ - μ)(Χ - μ)^T]

N(α, Α) + T N(β, Β) = N(α + Tβ, A + TΒT^T)

f(x) = Constant * exp(-½(x - μ)Σ^(-1)(x - μ)^T)

# main

* 一般
  
  T ← argmin_T{ ∑_i { w_i*|T b_i - m_i|² } }

* Point to Plane

  T ← argmin_T{ ∑_i { w_i*|n_i (T b_i - m_i)|² }
  
* Generalized :

  Point Cloud :
  
  * {a_i} ~ N(α, C₁)
  * {b_i} ~ N(β, C₂)

  Assume :

  define : d_T(i) = b_i - T a_i
  
  ⊢ d_T*(i) ~ N
