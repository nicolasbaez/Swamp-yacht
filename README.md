# Swamp-yacht
control is an illusion

![buh](https://github.com/nicolasbaez/Swamp-yacht/blob/main/xp032.gif)
```javascript
d = 50;
setup = (_) => createCanvas((w = 500), w);
g = (x, y, w, l, m, k) => {
  fill(225);
  rect(x, y, w, w);
  for (a = x; a < x + w; a += 0.25) {
    b = map(a, x, x + w, 0, d);
    point(a, map(sin(b / l + k) + sin(b / m + k), -2, 2, y + w, y));
  }
};
draw = (_) => {
  for (j = 0; j < w; j += d)
    for (i = 0; i <= w; i += d) {
      g(i, j, d, noise(i, j) * 9, noise(j, i) * 9, w);
    }
  w -= 0.1;
};

keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp032.gif", 500, { delay: 0, units: "frames" });
  }
};
