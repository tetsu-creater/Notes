# matplotlibのサンプルコード

## 1. 白抜き
通常プロット
```python
plt.plot(x, y, color='blue', lw=2.0, alpha=0.6)
plt.plot(x, y, 'o', color='none', markersize=8, markeredgewidth=1.5, markeredgecolor='blue', alpha=0.9)
```
<div align="center">
    <img width="400" alt="image" src="https://github.com/user-attachments/assets/69b65b31-5169-4dcc-b743-ae5e2e5a4c07">
</div>

サブプロット
```python
fig, axes = plt.subplots(1, 2, figsize=(15, 6))
axes[0].plot(x, y, color='blue', lw=2.0, alpha=0.6)
axes[0].plot(x, y, 'o', color='none', markersize=7, markeredgewidth=1.5, markeredgecolor='blue', alpha=0.9)

axes[1].plot(x, y, color='tomato', lw=2.0, alpha=0.6)
axes[1].plot(x, y, 'o', color='none', markersize=7, markeredgewidth=1.5, markeredgecolor='tomato', alpha=0.9)
```
<div align="center">
    <img width="700" alt="image" src="https://github.com/user-attachments/assets/27751a44-65b8-421e-a3d3-dd4c42f9f590">
</div>


## 2. カラープロット
サブプロット
```python
fig, axes = plt.subplots(1, 2, figsize=(15, 6))

mappable1 = axes[0].pcolor(x_list, y_list, C1, cmap='jet', shading="auto", vmin=0, vmax=1)
mappable2 = axes[1].pcolor(x_list, y_list, C2, cmap='jet', shading="auto", vmin=0, vmax=1)

plt.colorbar(mappable1, ax=axes[0])
plt.colorbar(mappable2, ax=axes[1])

```
<img width="800" height="337" alt="スクリーンショット 2025-08-28 15 01 15" src="https://github.com/user-attachments/assets/42aaac1c-6319-4725-af6c-5a8bac796308" />

</div>

