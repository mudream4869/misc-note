Source : [Paper](http://www.roboticsproceedings.org/rss05/p21.pdf)

# pre

## Multivariate normal distribution

N(μ, Σ) : Σ = E[(Χ - μ)(Χ - μ)^T]

N(α, Α) + T N(β, Β) = N(α + Tβ, A + TΒT^T)

f(x) = Constant * exp(-½(x - μ)Σ^(-1)(x - μ)^T)

# main

* 一般
  
  T ← argmin_T{ ∑ { w_i|T b_i - m_i|² } }

* Point to Plane

  T ← argmin_T{ ∑ { w_i|n_i (T b_i - m_i)|² }
  
* Generalized :

  Point Cloud :
  
  * {a_i} ~ N(α, C₁)
  * {b_i} ~ N(β, C₂)

  Assume : {a_i} ~ T {b_i}, want to find *T*

  define : d_A(i) = b_i - A a_i
  
  ⊢ d_T(i) ~ N(0, C₁ + TC₂T^T)
  
  use MLE : 最佳化機率
  
  T ← argmax_A{ ∏ p(d_A(i)) }
  
  = argmax_A{ ∑ ㏑ p(d_A(i)) } 
  
  > write d = d_A(i)

  = argmax_A{ ∑ -½d{C₁ + AC₂A^T}^(-1)d^T }
  
  = argmin_A{ ∑ d{C₁ + AC₂A^T}^(-1)d^T }
