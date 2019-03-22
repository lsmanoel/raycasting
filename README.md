# Raycasting

----

**Drawing Map:**

```python
wall_map = np.zeros((30, 30), dtype=int)
wall_map[:, :2]=1
wall_map[:2, :]=1
wall_map[:, -2:]=1
wall_map[-2:, :]=1

wall_map[6:7, 6:7]=1
wall_map[8:9, 6:7]=1
wall_map[10:11, 6:7]=1
wall_map[12:13, 6:7]=1
wall_map[14:15, 6:7]=1
wall_map[16:17, 6:7]=1
wall_map[18:19, 6:7]=1
wall_map[20:21, 6:7]=1
wall_map[22:23, 6:7]=1
wall_map[24:25, 6:7]=1


wall_map[6:7, -7:-6]=1

wall_map[-7:-6, -7:-6]=1

wall_map[-7:-6, 6:7]=1
cmap = mpl.colors.ListedColormap(['black','blue','red'])
plt.figure(figsize=(9,9))
plt.imshow(wall_map, cmap=cmap)
plt.grid(False)
plt.xticks([])
plt.yticks([])
plt.show
```

![](https://raw.githubusercontent.com/lsmanoel/raycasting/master/image/map_2d.png)

---

Render Map:

```python
obs_1 = observer(wall_map, texture_mode=True)

obs_1.theta = np.pi/4
obs_1.update_raycasting()
obs_1.plot_screen()

obs_1.theta = np.pi/3
obs_1.update_raycasting()
obs_1.plot_screen()

obs_1.forward(3)
obs_1.update_raycasting()
obs_1.plot_screen()

obs_1.forward(3)
obs_1.update_raycasting()
obs_1.plot_screen()

obs_1.forward(2)
obs_1.theta = np.pi/-8
obs_1.update_raycasting()
obs_1.plot_screen()
```

![](https://raw.githubusercontent.com/lsmanoel/raycasting/master/image/render_1.png)

![](https://raw.githubusercontent.com/lsmanoel/raycasting/master/image/render_2.png)

![](https://raw.githubusercontent.com/lsmanoel/raycasting/master/image/render_3.png)

![](https://raw.githubusercontent.com/lsmanoel/raycasting/master/image/render_4.png)

![](https://raw.githubusercontent.com/lsmanoel/raycasting/master/image/render_5.png)

