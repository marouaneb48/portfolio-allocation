# Dynamic Allocation Strategies

This notebook explores various **portfolio allocation strategies**—both static and dynamic—using robust control and covariance matrix filtering techniques. The goal is to optimize asset allocation under uncertainty and transaction cost constraints, and to evaluate performance using backtesting and turnover metrics.

---

## 📊 Project Structure

### 1. Data Preparation
- Load and preprocess stock data.

### 2. Stock Selection
- Clustering techniques are used to select stocks from a larger universe for focused portfolio construction.

---

## ⚙️ Methods Implemented

### 1. Robust Control Allocation

#### 1.1 Static Allocation

Optimization of the following objective:

```
w_rob = argmax(μᵀw - κ√(wᵀΩw) - (λ/2)wᵀΣw)
```

- Applied on:
  - Random Stocks
  - Selected Stocks
  - Backtesting included

#### 1.2 Dynamic Allocation

Adds a transaction penalty term:

```
w_rob = argmax(μᵀw - κ√(wᵀΩw) - (λ/2)wᵀΣw - ∑|w - w_previous|)
```

---

### 2. Covariance Matrix Filtering

#### Techniques:
- Clipping Method
- Cross Validation
- Markowitz Optimization

#### 2.1 Static Allocation

```
w_MVO = argmax(μᵀw - (λ/2)wᵀΣw)
```

- Applied on:
  - Random Stocks
  - Selected Stocks

#### 2.2 Dynamic Allocation

With turnover penalty:

```
w_MVO = argmax(μᵀw - (λ/2)wᵀΣw - c∑|w - w_previous|)
```

---

## 📈 Evaluation

- **Backtesting** of all strategies
- **Turnover analysis** to evaluate transaction costs
- **Comparative results** between static and dynamic strategies

---
