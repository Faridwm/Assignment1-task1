### Farid Wujdi Mubarok
### 1313617006
### Sistem Pakar Semester 112
### Assigment 1
### Task 1: 2D Transformation

# Translasi

Tranlasi adalah pergeseran suatu objek, baik itu titik, garis, maupun bidang dengan jarak dan arah tertentu. Translasi ditanyakan dengan vector (tx, ty), dimana tx merupakan pergesaran pada sumbu x, sedangkan ty merupakan pegeseran pada sumbu y.
Jika sebuah titik A = (x, y) di transalsikan oleh (tx, ty), maka akan diperoleh koordinat titik baru A' = (x' + y') dengan x' = x + tx dan y' = y + ty.

Didalam buku Computer Vision: Algorithms and Applications notasi tranlasi ditulis dengan 
```python
x' = [I, t] x
```

Dengan I merupakan matriks identitas (2 x 2). Karena kita menggunakan *homogeneous coordinates* maka koordinat titik A dinyatakan dengan A = (x, y, 1). Maka notasinya menjadi 

```python
x' = [I & t]
     [0^T & 1] x
```

Dengan notasi matriks diatas, didapat matriks pengali translasi pada *homogeneous coordinates* sebagai berikut
```python
[x', y', 1]= [
               [1, 0, tx],
               [0, 1, ty],
               [0, 0, 1]
             ]  [x, y, 1]

```

Atau dapat di tulis
```python
A' = [
       [1, 0, tx],
       [0, 1, ty],
       [0, 0, 1]
     ]  A

```

# Rotasi
Rotasi merupakan transformasi yang memindahkan suatu objek dengan cara memutar titik-titik objek tersebut sebesar *theta* dalam derajat atau radian (dalam source code saya menggunakan derajat) dan berputar berlawanan arah jarum jam dengan pusat rotasi (0, 0).

Notasi matriks dari rotasi adalah sebagai berikut
```code
R = [
      [cos(theta), -sin(theta)],
      [sin(theta), cos(theta)]
    ]
```

Pada *homogeneus coordinates* notasi matriks rotasi dapat ditulis
```code
R = [
      [cos(theta), -sin(theta), 0],
      [sin(theta), cos(theta),  0],
      [0, 0, 1]
    ]
```

Jika sebuah titik diputar sebesar *theta* maka akan diperoleh koordinat titik baru sebagai berikut
```code
x' = x . cos(theta) - y . sin(theta)
y' = x . sin(theta) + y . cos(theta)
```

## Rotasi + Translasi
Rotasi + translasi disebut juga dengan *2D Euclidean transformation*. Notasi dari rotasi + translasi dapat ditulis dengan  A' = RA + t atau
```code
A' = [R t] A
```
dan dapat dijabarkan sebagai berikut
```code
A' = [
      [cos(theta), -sin(theta), tx],
      [sin(theta), cos(theta),  ty]
    ] A
```
Dimana A merupakan sebuah titik (x, y)

Jika sebuah titik di Rotasi + translasi kan maka di dapat koordinat titik baru sebagai berikut
```code
x' = x . cos(theta) - y . sin(theta) + tx
y' = x . sin(theta) + y . cos(theta) + ty
```

Dengan *homogeneus coordinates* notasi matriks rotasi + translasi dapat ditulis sebagai berikut
```code
[x', y', 1] = [
      [cos(theta), -sin(theta), tx],
      [sin(theta), cos(theta),  0ty,
      [0, 0, 1]
    ] [x, y, 1]
```
atau
```code
A' = [
      [cos(theta), -sin(theta), tx],
      [sin(theta), cos(theta),  0ty,
      [0, 0, 1]
    ] A
```

Dari eksperimen yang dilakukan rotasi + translasi dapat diartikan transformasi objek dengan cara di rotasi-kan sebesar *theta* kemudian di translasikan pada sumu x sebsar tx dan pada sumbu y sebesar ty.

# Dilatasi
Dilatasi merupakan trasnformasi untuk memperbesar atau memperkecil ukuran sebuah objek tanpa merubah bentuk dari objek tersebut.
Jika sebuah titik A = (x, y) di dilatasikan dengan skala s, maka akan diperoleh koordinat titik yang baru sebagai berikut
```code
x' = sx
y' = sy
```

Notasi matriks dilatasi adalaah sebagai berikut
```code
     A' = [
            [s, 0],
            [0, s]
          ] A
```

atau dalam *homogeneus coordinates* dapat ditulis
```code
     [x', y', 1] = [
            [s, 0, 0],
            [0, s, 0],
            [0, 0, 1]
          ] [x, y, 1]
```
atau
```code
A' = [
      [s, 0, 0],
      [0, s, 0],
      [0, 0, 1]
     ] A
```

