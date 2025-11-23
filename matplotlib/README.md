# matplotlibのサンプルコード

## 1. 白抜き
通常プロット
```python
plt.plot(x, y, marker='o', color='blue', markersize=8, markeredgewidth=1.5, mfc='white')
```
<div align="center">
    <img width="448" height="354" alt="スクリーンショット 2025-11-23 16 40 26" src="https://github.com/user-attachments/assets/1ac3fb79-f754-461c-ad4c-ed732e53e676" />

</div>

サブプロット
```python
fig, axes = plt.subplots(1, 2, figsize=(15, 6))
axes[0].plot(x, y, marker='o', color='blue', markersize=8, markeredgewidth=1.5, mfc='white')

axes[1].plot(x, y, marker='o', color='orange', markersize=8, markeredgewidth=1.5, mfc='white')
```
<div align="center">
    <img width="824" height="342" alt="スクリーンショット 2025-11-23 16 41 52" src="https://github.com/user-attachments/assets/0051423b-27ff-4e85-ae83-381404862804" />

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

