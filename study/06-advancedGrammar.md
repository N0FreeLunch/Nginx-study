
```
rewrite ^/(.*)\.(png|jpg|gif)$ /image.php?file=$1&format=$2 last;
```
