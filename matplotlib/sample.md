# matplotlibのサンプルコード

## 1. 白抜き
通常プロット
```python
```

サブプロット
```python
fig, axes = plt.subplots(1, 2, figsize=(15, 6))
axes[0].plot(x, y,'k-', color='blue', lw=2.0, alpha=0.6)
axes[0].plot(x, y, 'o', color='none', markersize=7, markeredgewidth=1.5, markeredgecolor='blue', alpha=0.9)

axes[1].plot(x, y,'k-', color='tomato', lw=2.0, alpha=0.6)
axes[1].plot(x, y, 'o', color='none', markersize=7, markeredgewidth=1.5, markeredgecolor='tomato', alpha=0.9)
```

<div align="center">
    <img width="700" alt="image" src="https://github.com/user-attachments/assets/27751a44-65b8-421e-a3d3-dd4c42f9f590">
</div>



