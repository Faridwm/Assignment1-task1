### Farid Wujdi Mubarok
### 1313617006
### Sistem Pakar Semester 112
### Assigment 1
### Task 1: 2D Transformation

# Translasi

Tranlasi adalah pergeseran suatu objek, baik itu titik, garis, maupun bidang dengan jarak dan arah tertentu. Translasi ditanyakan dengan vector (tx, ty), dimana tx merupakan pergesaran pada sumbu x, sedangkan ty merupakan pegeseran pada sumbu y.
Jika sebuah titik A = (x, y) di transalsikan oleh (tx, ty), maka akan diperoleh koordinat titik baru A' = (x' + y') dengan x' = x + tx dan y' = y + ty.

Didalam buku Computer Vision: Algorithms and Applications notasi tranlasi ditulis dengan 
$$x' = 
\begin{bmatrix} 
I & t 
\end{bmatrix} 
\overline{x}$$ 

Dengan $I$ merupakan matriks identitas (2 x 2). Karena kita menggunakan *homogeneous coordinates* maka koordinat titik $A$ dinyatakan dengan $A = (x, y, 1)$. Maka notasinya menjadi 

```python
x' = [I & t]
     [0^T & 1] @ x
```

Dengan notasi matriks diatas, didapat matriks pengali translasi pada *homogeneous coordinates* sebagai berikut
```python
[x', y', 1]= [
               [1, 0, tx],
               [0, 1, ty],
               [0, 0, 1]
             ] @ [x, y, 1]

```

Atau dapat di tulis $$
```python
A '= [
       [1, 0, tx],
       [0, 1, ty],
       [0, 0, 1]
     ] @ A

```

# Rotasi


```python

```
