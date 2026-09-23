# Adorable-bay
You always live in the past.

![buh](https://github.com/nicolasbaez/Adorable-bay/blob/main/xp081.gif)
```javascript
setup = (_) => {
  createCanvas((w = 500), w, WEBGL);
  h = w / 2;
  k = -h;
};
draw = (_) => {
  rotateY(1);
  for (i = -h; i < k; i++) {
    push();
    translate(-h / 2, -h / 2, k);
    fill(0, 1);
    stroke(h, noise(k));
    rect(0, 0, h, h);
    r = h / 4;
    y = map(sin(map(k, -h, w * 0.3, 0, 9)), -1, 1, h, 0);
    stroke(h, h, 0);
    n = noise(y) * h;
    line(n, y, h - n, y);
    pop();
  }
  if (k == -h) saveGif("xp081.gif", 400, { delay: 0, units: "frames" });
  k++;
};
