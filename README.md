# metismex for windows
If the only necessity is to use metismex with matlab,
the directory ``compiled metismex`` already has a compiled version ready to use. <br>

---

## metis compilation
### To retrieve the original metis archive either:
1. Clone this repo https://github.com/KarypisLab/METIS
2. If you're following the Numerical Computing course at USI ask the professor for the code
3. Use the zipped archive in this repo

**Note:** If you are using the original version of metis, apply to your version the changes made to the files in this commit 
before compiling it on windows. <br>

---

### Compilation



To compile it you will need `cmake`. <br>
In the `metis-5.1.0` directory execute: <br>
```
mkdir build
cd build
cmake -A x64 ..
cmake --build . --config Release 
```

Once this is done, in the `metis-5.1.0` directory clone the metismex repo (https://github.com/dgleich/metismex.git) <br>
Then open MATLAB with the `metis-5.1.0\metismex` path and in the Command Window run `make`. <br>
<br>
To double-check that everything works run: 
```
A = blkdiag(ones(5),ones(5)); A(1,10) = 1; A(10,1) = 1; A(5,6) = 1; A(6,5) = 1;
[p1,p2] = metispart(sparse(A))
```
The results should be:

```
p1 =

     6     7     8     9    10


p2 =

     1     2     3     4     5
```

sources: [gninr](https://github.com/gninr/metis-5.0.2)