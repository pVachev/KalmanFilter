# KalmanFilter – Schwartz & Smith Two-Factor Model (WTI Crude Oil)

<div align="center">
  <img src="futures_kf_fit.png" width="650"><br>
  <em>Log WTI futures (1 M) vs. Kalman-filter estimate</em>
</div>

## ✨ Project Overview
This repo implements the **Schwartz & Smith (2000) two-factor commodity model**:

\\[
\\ln F(t,T)=\\chi_t+\\xi_t+A(T-t)
\\]

* `\\chi_t` – short-term, mean-reverting (Ornstein–Uhlenbeck)  
* `\\xi_t` – long-term, Brownian motion with drift  
* `A(T-t)=\\alpha+\\beta\\,(T-t)` – deterministic maturity term  

Our 4-person quant-finance team at **emlyon business school** used a **Kalman filter** in Python to estimate these latent states for WTI crude-oil futures (1990–1995, 5 maturities).  
My contribution: **Kalman-filter implementation, state-space matrices, and likelihood optimisation.**

## 🔑 Results
| Model                | Log-Likelihood |
|----------------------|----------------|
| Two-Factor (S&S)     | **3585.8** |
| OU-only (short-run)  | 3206.3 |
| GBM-only (long-run)  | 2835.4 |

*Two-factor spec ↑ > 20 % vs. best one-factor benchmark.*

## 📂 Repository Structure
