# Menggambar Plot 3D dengan EMT
Ini adalah pengantar untuk grafik 3D di Euler. Kita memerlukan grafik
3D untuk memvisualisasikan fungsi dari dua variabel.


Euler menggambar fungsi-fungsi tersebut menggunakan algoritma
pengurutan (*sorting algorithm*) untuk menyembunyikan bagian yang
berada di latar belakang. Secara umum, Euler menggunakan proyeksi
sentral. Tampilan bawaan (*default*) adalah dari kuadran positif
$x$-$y$ menuju titik pusat $x=y=z=0$, namun sudut `angle=0°` akan
melihat tepat searah dengan sumbu $y$. Sudut pandang (*view angle*)
dan ketinggian (*height*) dapat diubah-ubah.


Euler dapat menggambar:


* 
Permukaan (*surfaces*) dengan bayangan (*shading*) dan garis kontur
* (*level lines*) atau rentang kontur (*level ranges*),

* 
Awan titik (*clouds of points*),

* 
Kurva parametrik (*parametric curves*),

* 
Permukaan implisit (*implicit surfaces*).


Grafik 3D dari suatu fungsi menggunakan `plot3d`. Cara termudah adalah
dengan menggambar ekspresi dalam variabel $x$ dan $y$. Parameter `r`
menentukan rentang (*range*) grafik di sekitar titik $(0,0)$.


\>aspect(1.5); plot3d("x^2+sin(y)",-5,5,0,6\*pi):


![images/TugasAplikom5Adi25030630001-001.png](images/TugasAplikom5Adi25030630001-001.png)

\>plot3d("x^2+x\*sin(y)",-5,5,0,6\*pi):


![images/TugasAplikom5Adi25030630001-002.png](images/TugasAplikom5Adi25030630001-002.png)

Silakan lakukan modifikasi agar gambar "talang bergelombang" tersebut
tidak lurus melainkan melengkung/melingkar, baik melingkar secara
mendatar maupun melingkar turun/naik (seperti papan peluncur pada
kolam renang. Temukan rumusnya.


Berikut:


1. Talang Melingkar Turun/Naik (Spiral/Helix)


\> plot3d("(10+x)\*cos(y)","(10+x)\*sin(y)","2\*y+x^2+x\*sin(y)",-5,5,0,6\*pi,n=100):


![images/TugasAplikom5Adi25030630001-003.png](images/TugasAplikom5Adi25030630001-003.png)

2. Talang Melingkar Mendatar (Donut/Torus)


\> plot3d("(10+x)\*cos(y)","(10+x)\*sin(y)","x^2+x\*sin(y)",-5,5,0,2\*pi,n=100):


![images/TugasAplikom5Adi25030630001-004.png](images/TugasAplikom5Adi25030630001-004.png)

# Functions of two Variables

Untuk grafik suatu fungsi, gunakan:


* 
ekspresi sederhana dalam $x$ dan $y$,

* 
nama fungsi dari dua variabel,

* 
atau matriks data.


Tampilan bawaan (*default*) adalah kisi kawat berisi (*filled wire
grid*) dengan warna berbeda di kedua sisinya. Perhatikan bahwa jumlah
default interval grid adalah 10, tetapi plot menggunakan jumlah
default $40 \times 40$ persegi panjang untuk mengonstruksi permukaan.
Hal ini dapat diubah.


* 
`n=40`, `n=[40,40]`: jumlah garis grid di setiap arah

* 
`grid=10`, `grid=[10,10]`: jumlah garis grid di setiap arah.


Kita menggunakan nilai bawaan `n=40` dan `grid=10`.


\>plot3d("x^2+y^2"):


![images/TugasAplikom5Adi25030630001-005.png](images/TugasAplikom5Adi25030630001-005.png)

Interaksi pengguna (*user interaction*) dimungkinkan dengan
menggunakan parameter `&gt;user`. Pengguna dapat menekan tombol-tombol
berikut:


* 
**kiri, kanan, atas, bawah** (*left, right, up, down*): memutar
* sudut pandang (*viewing angle*)

* 
**+,-**: memperbesar (*zoom in*) atau memperkecil (*zoom out*)

* 
**a**: menghasilkan anaglif (*anaglyph*) (lihat di bawah)

* 
**l**: beralih memutar sumber cahaya (*toggle turning the light
* source*) (lihat di bawah)

* 
**spasi** (*space*): mengembalikan ke pengaturan bawaan (*reset to
* default*)

* 
**Enter** (*return*): mengakhiri interaksi


\>plot3d("exp(-x^2+y^2)",\>user, ...  
\>     title="Turn with the vector keys (press return to finish)"):


![images/TugasAplikom5Adi25030630001-006.png](images/TugasAplikom5Adi25030630001-006.png)

Rentang plot (*plot range*) untuk fungsi dapat ditentukan dengan:


* 
`a,b`: rentang sumbu $x$

* 
`c,d`: rentang sumbu $y$

* 
`r`: persegi simetris di sekitar titik $(0,0)$

* 
`n`: jumlah subinterval untuk plot


Terdapat beberapa parameter untuk merubah skala fungsi atau mengubah
tampilan grafik:


* 
`fscale`: menyeimbangkan skala nilai fungsi (bawaannya adalah
* `&lt;fscale`)

* 
`scale`: angka atau vektor $1 \times 2$ untuk mengubah skala ke arah
* sumbu $x$ dan $y$

* 
`frame`: jenis bingkai (*frame*) (bawaannya adalah 1)


\>plot3d("exp(-(x^2+y^2)/5)",r=10,n=80,fscale=4,scale=1.2,frame=3,\>user):


![images/TugasAplikom5Adi25030630001-007.png](images/TugasAplikom5Adi25030630001-007.png)

Tampilan (*view*) dapat diubah dengan berbagai cara:


* 
`distance`: jarak pandang ke plot.

* 
`zoom`: nilai pembesaran (*zoom value*).

* 
`angle`: sudut terhadap sumbu $y$ negatif dalam satuan radian.

* 
`height`: ketinggian sudut pandang dalam satuan radian.


Nilai bawaan (*default*) dapat diperiksa atau diubah menggunakan
fungsi `view()`. Fungsi ini mengembalikan nilai parameter dengan
urutan di atas.


\>view


    [5,  2.6,  2,  0.4]

Jarak yang lebih dekat memerlukan pembesaran (*zoom*) yang lebih
kecil. Efek yang dihasilkan lebih mirip dengan lensa sudut lebar
(*wide angle lens*).


Pada contoh berikut, `angle=0` dan `height=0` membuat tampilan dilihat
dari sumbu $y$ negatif. Label sumbu untuk $y$ disembunyikan dalam
kondisi ini.


\>plot3d("x^2+y",distance=3,zoom=1,angle=pi/2,height=0):


![images/TugasAplikom5Adi25030630001-008.png](images/TugasAplikom5Adi25030630001-008.png)

Plot akan selalu mengarah ke titik pusat kubus plot (*plot cube*).
Anda dapat memindahkan titik pusat tersebut menggunakan parameter
`center`.


\>plot3d("x^4+y^2",a=0,b=1,c=-1,d=1,angle=-20°,height=20°, ...  
\>     center=[0.4,0,0],zoom=5):


![images/TugasAplikom5Adi25030630001-009.png](images/TugasAplikom5Adi25030630001-009.png)

Plot secara otomatis disesuaikan skalanya (*scaled*) agar muat ke
dalam kubus unit untuk ditampilkan. Jadi, Anda tidak perlu mengubah
parameter `distance` atau `zoom` tergantung pada ukuran plot. Meskipun
demikian, label sumbu tetap mengacu pada ukuran yang sebenarnya.


Jika Anda mematikan fitur ini dengan `scale=false`, Anda perlu
memastikan sendiri agar plot tetap muat di dalam jendela tampilan
(*plotting window*), yaitu dengan cara mengubah jarak pandang
(`distance`) atau pembesaran (`zoom`), serta memindahkan titik
pusatnya (`center`).


\>plot3d("5\*exp(-x^2-y^2)",r=2,<fscale,<scale,distance=13,height=50°, ...  
\>     center=[0,0,-2],frame=3):


![images/TugasAplikom5Adi25030630001-010.png](images/TugasAplikom5Adi25030630001-010.png)

Plot polar (*polar plot*) juga tersedia. Parameter `polar=true` akan
menggambar plot polar. Fungsi yang digunakan harus tetap berupa fungsi
dari variabel $x$ dan $y$. Parameter `fscale` akan menyesuaikan skala
fungsi dengan skalanya sendiri. Jika tidak, fungsi akan disesuaikan
skalanya agar muat ke dalam kubus (*cube*).


\>plot3d("1/(x^2+y^2+1)",r=5,\>polar, ...  
\>   fscale=2,\>hue,n=100,zoom=4,\>contour,color=blue):


![images/TugasAplikom5Adi25030630001-011.png](images/TugasAplikom5Adi25030630001-011.png)

\>function f(r) := exp(-r/2)\*cos(r); ...  
\>   plot3d("f(x^2+y^2)",\>polar,scale=[1,1,0.4],r=pi,frame=3,zoom=4):


![images/TugasAplikom5Adi25030630001-012.png](images/TugasAplikom5Adi25030630001-012.png)

Parameter `rotate` memutar suatu fungsi terhadap sumbu tertentu.


* 
`rotate=1`: Menggunakan sumbu $x$

* 
`rotate=2`: Menggunakan sumbu $z$


\>plot3d("x^2+1",a=-1,b=1,rotate=true,grid=5):


![images/TugasAplikom5Adi25030630001-013.png](images/TugasAplikom5Adi25030630001-013.png)

\>plot3d("x^2+1",a=-1,b=1,rotate=2,grid=5):


![images/TugasAplikom5Adi25030630001-014.png](images/TugasAplikom5Adi25030630001-014.png)

\>plot3d("sqrt(25-x^2)",a=0,b=5,rotate=1):


![images/TugasAplikom5Adi25030630001-015.png](images/TugasAplikom5Adi25030630001-015.png)

\>plot3d("x\*sin(x)",a=0,b=6pi,rotate=2):


![images/TugasAplikom5Adi25030630001-016.png](images/TugasAplikom5Adi25030630001-016.png)

Berikut adalah plot dengan tiga fungsi.


\>plot3d("x","x^2+y^2","y",r=2,zoom=3.5,frame=3):


![images/TugasAplikom5Adi25030630001-017.png](images/TugasAplikom5Adi25030630001-017.png)

# Contour Plots

Untuk grafik, Euler menambahkan garis grid. Sebagai gantinya,
dimungkinkan untuk menggunakan garis kontur (*level lines*) dan
bayangan satu warna (*one-color hue*) atau bayangan warna spektral
(*spectral colored hue*). Euler dapat menggambar ketinggian fungsi
pada grafik dengan pencahayaan/bayangan (*shading*). Dalam semua
grafik 3D, Euler dapat menghasilkan anaglif merah/sian (*red/cyan
anaglyphs*).


* 
`&gt;hue`: Memaktifkan bayangan cahaya (*light shading*) alih-alih
* garis kawat (*wires*).

* 
`&gt;contour`: Menggambar garis kontur otomatis pada grafik.

* 
`level=...` (atau `levels`): Vektor nilai untuk garis kontur.


Pengaturan bawaan (*default*) adalah `level="auto"`, yang menghitung
beberapa garis kontur secara otomatis. Seperti yang Anda lihat pada
grafik, nilai *level* sebenarnya merupakan rentang dari kontur
(*ranges of levels*).


Gaya bawaan dapat diubah. Untuk grafik kontur berikut, kita
menggunakan grid yang lebih halus sebesar 100x100 titik, menyesuaikan
skala fungsi dan grafik, serta menggunakan sudut pandang (*angle of
view*) yang berbeda.


\>plot3d("exp(-x^2-y^2)",r=2,n=100,level="thin", ...  
\>    \>contour,\>spectral,fscale=1,scale=1.1,angle=45°,height=20°):


![images/TugasAplikom5Adi25030630001-018.png](images/TugasAplikom5Adi25030630001-018.png)

\>plot3d("exp(x\*y)",angle=100°,\>contour,color=green):


![images/TugasAplikom5Adi25030630001-019.png](images/TugasAplikom5Adi25030630001-019.png)

Pewarnaan bayangan bawaan (*default shading*) menggunakan warna
abu-abu. Namun, rentang warna spektral (*spectral range of colors*)
juga tersedia.


* 
`&gt;spectral`: Menggunakan skema spektral bawaan

* 
`color=...`: Menggunakan warna khusus atau skema spektral


Untuk plot berikut, kita menggunakan skema spektral bawaan dan
meningkatkan jumlah titik untuk mendapatkan tampilan yang sangat
halus.


\>plot3d("x^2+y^2",\>spectral,\>contour,n=100):


![images/TugasAplikom5Adi25030630001-020.png](images/TugasAplikom5Adi25030630001-020.png)

Sebagai ganti dari garis kontur otomatis (*automatic level lines*),
kita juga dapat menentukan sendiri nilai dari garis kontur tersebut.
Hal ini akan menghasilkan garis kontur yang tipis, alih-alih berupa
rentang nilai kontur (*ranges of levels*).


\>plot3d("x^2-y^2",0,5,0,5,level=-1:0.1:1,color=redgreen):


![images/TugasAplikom5Adi25030630001-021.png](images/TugasAplikom5Adi25030630001-021.png)

Pada plot berikut, kita menggunakan dua pita kontur (*level bands*)
yang sangat lebar, yaitu dari -0.1 ke 1, dan dari 0.9 ke 1. Nilai ini
dimasukkan sebagai matriks dengan batas kontur sebagai kolomnya.


Selain itu, kita menimpa (*overlay*) tampilan dengan grid yang
memiliki 10 interval di setiap arahnya.


\>plot3d("x^2+y^3",level=[-0.1,0.9;0,1], ...  
\>     \>spectral,angle=30°,grid=10,contourcolor=gray):


![images/TugasAplikom5Adi25030630001-022.png](images/TugasAplikom5Adi25030630001-022.png)

Pada contoh berikut, kita membuat plot untuk himpunan penyelesaian
dari persamaan:


$$f(x,y) = x^y-y^x = 0$$Kita menggunakan satu garis tipis (*single thin line*) untuk garis
konturnya (*level line*).


\>plot3d("x^y-y^x",level=0,a=0,b=6,c=0,d=6,contourcolor=red,n=100):


![images/TugasAplikom5Adi25030630001-024.png](images/TugasAplikom5Adi25030630001-024.png)

Dimungkinkan juga untuk menampilkan bidang kontur (*contour plane*) di
bawah plot. Warna serta jarak bidang kontur terhadap plot dapat
ditentukan sesuai kebutuhan.


\>plot3d("x^2+y^4",\>cp,cpcolor=green,cpdelta=0.2):


![images/TugasAplikom5Adi25030630001-025.png](images/TugasAplikom5Adi25030630001-025.png)

Berikut adalah beberapa gaya (*styles*) tambahan. Kita selalu
mematikan bingkai (`frame=false`), serta menggunakan berbagai skema
warna untuk grafik dan garis grid-nya.


\>figure(2,2); ...  
\>   expr="y^3-x^2"; ...  
\>   figure(1);  ...  
\>     plot3d(expr,<frame,\>cp,cpcolor=spectral); ...  
\>   figure(2);  ...  
\>     plot3d(expr,<frame,\>spectral,grid=10,cp=2); ...  
\>   figure(3);  ...  
\>     plot3d(expr,<frame,\>contour,color=gray,nc=5,cp=3,cpcolor=greenred); ...  
\>   figure(4);  ...  
\>     plot3d(expr,<frame,\>hue,grid=10,\>transparent,\>cp,cpcolor=gray); ...  
\>   figure(0):


![images/TugasAplikom5Adi25030630001-026.png](images/TugasAplikom5Adi25030630001-026.png)

Terdapat beberapa skema warna spektral lainnya yang diberi nomor dari
1 hingga 9. Namun, Anda juga dapat menggunakan sintaks `color=nilai`,
dengan pilihan nilai sebagai berikut:


* 
`spectral`: untuk rentang warna dari biru ke merah.

* 
`white`: untuk rentang warna yang lebih samar/muda.

* 
`yellowblue`, `purplegreen`, `blueyellow`, `greenred`

* 
`blueyellow`, `greenpurple`, `yellowblue`, `redgreen`


\>figure(3,3); ...  
\>   for i=1:9;  ...  
\>     figure(i); plot3d("x^2+y^2",spectral=i,\>contour,\>cp,<frame,zoom=4);  ...  
\>   end; ...  
\>   figure(0):


![images/TugasAplikom5Adi25030630001-027.png](images/TugasAplikom5Adi25030630001-027.png)

Sumber cahaya dapat diubah menggunakan tombol `l` dan tombol arah
(*cursor keys*) saat berada dalam mode interaksi pengguna (*user
interaction*). Selain itu, posisi cahaya juga dapat diatur melalui
parameter.


* 
`light`: arah datangnya cahaya

* 
`amb`: cahaya sekitar (*ambient light*) dengan rentang nilai antara
* 0 dan 1


Harap dicatat bahwa program tidak membedakan sisi depan dan belakang
dari plot. Tidak ada efek bayangan (*shadows*). Untuk mendapatkan efek
bayangan, Anda perlu menggunakan Povray.


\>plot3d("-x^2-y^2", ...  
\>     hue=true,light=[0,1,1],amb=0,user=true, ...  
\>     title="Press l and cursor keys (return to exit)"):


![images/TugasAplikom5Adi25030630001-028.png](images/TugasAplikom5Adi25030630001-028.png)

Parameter `color` mengubah warna dari permukaan (*surface*). Warna
dari garis kontur (*level lines*) juga dapat diubah.


\>plot3d("-x^2-y^2",color=rgb(0.2,0.2,0),hue=true,frame=false, ...  
\>     zoom=3,contourcolor=red,level=-2:0.1:1,dl=0.01):


![images/TugasAplikom5Adi25030630001-029.png](images/TugasAplikom5Adi25030630001-029.png)

Nilai `color=0` memberikan efek pelangi khusus (*special rainbow
effect*).


\>plot3d("x^2/(x^2+y^2+1)",color=0,hue=true,grid=10):


![images/TugasAplikom5Adi25030630001-030.png](images/TugasAplikom5Adi25030630001-030.png)

Permukaan (*surface*) juga dapat dibuat transparan.


\>plot3d("x^2+y^2",\>transparent,grid=10,wirecolor=red):


![images/TugasAplikom5Adi25030630001-031.png](images/TugasAplikom5Adi25030630001-031.png)

# Implicit Plots

Terdapat juga plot implisit dalam tiga dimensi. Euler menghasilkan
irisan (*cuts*) yang memotong objek tersebut. Fitur `plot3d` mencakup
pembuatan plot implisit untuk menampilkan himpunan pembuat nol dari
suatu fungsi dengan tiga variabel.


Solusi dari persamaan:


$$f(x,y,z) = 0$$


dapat divisualisasikan melalui irisan yang sejajar dengan bidang
$x-y$, $x-z$, dan $y-z$.


* 
`implicit=1`: irisan sejajar dengan bidang $y-z$

* 
`implicit=2`: irisan sejajar dengan bidang $x-z$

* 
`implicit=4`: irisan sejajar dengan bidang $x-y$


Anda dapat menjumlahkan nilai-nilai tersebut jika ingin menggabungkan
beberapa irisan. Pada contoh berikut, kita membuat plot untuk:


$$M = \{ (x,y,z) : x^2+y^3+zy=1 \}$$\>plot3d("x^2+y^3+z\*y-1",r=5,implicit=3):


![images/TugasAplikom5Adi25030630001-033.png](images/TugasAplikom5Adi25030630001-033.png)

\>c=1; d=1;

\>plot3d("((x^2+y^2-c^2)^2+(z^2-1)^2)\*((y^2+z^2-c^2)^2+(x^2-1)^2)\*((z^2+x^2-c^2)^2+(y^2-1)^2)-d",r=2,<frame,\>implicit,\>user): 


![images/TugasAplikom5Adi25030630001-034.png](images/TugasAplikom5Adi25030630001-034.png)

\>plot3d("x^2+y^2+4\*x\*z+z^3",\>implicit,r=2,zoom=2.5):


![images/TugasAplikom5Adi25030630001-035.png](images/TugasAplikom5Adi25030630001-035.png)

# Plotting 3D Data

Sama seperti `plot2d`, `plot3d` juga menerima data. Untuk objek 3D,
Anda perlu menyediakan matriks dari nilai-nilai $x$, $y$, dan $z$,
atau tiga fungsi/ekspresi $f_x(x,y)$, $f_y(x,y)$, $f_z(x,y)$.


$$\gamma(t,s) = (x(t,s),y(t,s),z(t,s))$$Karena $x$, $y$, dan $z$ berbentuk matriks, kita menganggap bahwa
$(t,s)$ berjalan melewati grid berbentuk persegi. Hasilnya, Anda dapat
membuat plot dari citra persegi panjang di dalam ruang 3D.


Anda dapat memanfaatkan bahasa matriks di Euler untuk menghasilkan
koordinat-koordinat tersebut secara efektif.


Pada contoh berikut, kita menggunakan vektor baris untuk nilai $t$ dan
vektor kolom untuk nilai $s$ guna memparameterisasi permukaan bola.
Dalam gambar tersebut, kita dapat menandai wilayah tertentu, yang pada
contoh kita adalah wilayah kutub.


\>t=linspace(0,2pi,180); s=linspace(-pi/2,pi/2,90)'; ...  
\>   x=cos(s)\*cos(t); y=cos(s)\*sin(t); z=sin(s); ...  
\>   plot3d(x,y,z,\>hue, ...  
\>   color=blue,<frame,grid=[10,20], ...  
\>   values=s,contourcolor=red,level=[90°-24°;90°-22°], ...  
\>   scale=1.4,height=50°):


![images/TugasAplikom5Adi25030630001-037.png](images/TugasAplikom5Adi25030630001-037.png)

Berikut adalah contohnya, yang merupakan grafik dari suatu fungsi.


\>t=-1:0.1:1; s=(-1:0.1:1)'; plot3d(t,s,t\*s,grid=10):


![images/TugasAplikom5Adi25030630001-038.png](images/TugasAplikom5Adi25030630001-038.png)

Namun, kita dapat membuat berbagai jenis permukaan. Berikut adalah
permukaan yang sama tetapi didefinisikan sebagai suatu fungsi.


$$x = y \, z$$\>plot3d(t\*s,t,s,angle=180°,grid=10):


![images/TugasAplikom5Adi25030630001-040.png](images/TugasAplikom5Adi25030630001-040.png)

Dengan sedikit usaha lebih, kita dapat menghasilkan berbagai jenis
bentuk permukaan.


Pada contoh berikut, kita membuat tampilan berbayang (*shaded view*)
dari sebuah bola yang terdistorsi. Koordinat umum untuk bola adalah:


$$\gamma(t,s) = (\cos(t)\cos(s),\sin(t)\sin(s),\cos(s))$$dengan


$$0 \le t \le 2\pi, \quad \frac{-\pi}{2} \le s \le \frac{\pi}{2}.$$Kita mengukur/distorsi bentuk ini dengan faktor pengali:


$$d(t,s) = \frac{\cos(4t)+\cos(8s)}{4}. $$\>t=linspace(0,2pi,320); s=linspace(-pi/2,pi/2,160)'; ...  
\>   d=1+0.2\*(cos(4\*t)+cos(8\*s)); ...  
\>   plot3d(cos(t)\*cos(s)\*d,sin(t)\*cos(s)\*d,sin(s)\*d,hue=1, ...  
\>     light=[1,0,1],frame=0,zoom=5):


![images/TugasAplikom5Adi25030630001-044.png](images/TugasAplikom5Adi25030630001-044.png)

Tentu saja, *point cloud* (kumpulan titik) juga dapat dibuat. Untuk
memetakan data titik di dalam ruang 3D, kita memerlukan tiga vektor
yang masing-masing berisi koordinat titik-titik tersebut.


Gaya tampilannya (*styles*) sama persis seperti pada `plot2d` dengan
opsi `points=true`.


\>n=500;  ...  
\>     plot3d(normal(1,n),normal(1,n),normal(1,n),points=true,style="."):


![images/TugasAplikom5Adi25030630001-045.png](images/TugasAplikom5Adi25030630001-045.png)

Memungkinkan juga untuk membuat plot kurva dalam ruang 3D. Dalam hal
ini, akan lebih mudah jika kita menghitung terlebih dahulu titik-titik
pada kurva tersebut (*precompute*). Untuk kurva pada bidang 3D, kita
menggunakan sekumpulan urutan koordinat serta menambahkan parameter
`wire=true`.


\>t=linspace(0,8pi,500); ...  
\>   plot3d(sin(t),cos(t),t/10,\>wire,zoom=3):


![images/TugasAplikom5Adi25030630001-046.png](images/TugasAplikom5Adi25030630001-046.png)

\>t=linspace(0,4pi,1000); plot3d(cos(t),sin(t),t/2pi,\>wire, ...  
\>   linewidth=3,wirecolor=blue):


![images/TugasAplikom5Adi25030630001-047.png](images/TugasAplikom5Adi25030630001-047.png)

\>X=cumsum(normal(3,100)); ...  
\>    plot3d(X[1],X[2],X[3],\>anaglyph,\>wire):


![images/TugasAplikom5Adi25030630001-048.png](images/TugasAplikom5Adi25030630001-048.png)

EMT juga dapat membuat plot dalam mode anaglif (*anaglyph mode*).
Untuk melihat plot jenis ini, Anda memerlukan kacamata merah/sian
(*red/cyan glasses*).


\> plot3d("x^2+y^3",\>anaglyph,\>contour,angle=30°):


![images/TugasAplikom5Adi25030630001-049.png](images/TugasAplikom5Adi25030630001-049.png)

Sering kali, skema warna spektral (*spectral color scheme*) digunakan
pada plot 3D. Opsi ini memberikan penekanan yang jelas pada variasi
ketinggian nilai fungsi.


\>plot3d("x^2\*y^3-y",\>spectral,\>contour,zoom=3.2):


![images/TugasAplikom5Adi25030630001-050.png](images/TugasAplikom5Adi25030630001-050.png)

Euler juga dapat membuat plot permukaan terparameterisasi
(*parameterized surfaces*), yaitu ketika parameternya merupakan
nilai-nilai $x$, $y$, dan $z$ dari citra sebuah grid persegi panjang
di dalam ruang 3D.


Untuk demonstrasi berikut, kita menyiapkan parameter $u$ dan $v$, lalu
menghasilkan koordinat ruang 3D dari parameter-parameter tersebut.


\>u=linspace(-1,1,10); v=linspace(0,2\*pi,50)'; ...  
\>   X=(3+u\*cos(v/2))\*cos(v); Y=(3+u\*cos(v/2))\*sin(v); Z=u\*sin(v/2); ...  
\>   plot3d(X,Y,Z,\>anaglyph,<frame,\>wire,scale=2.3):


![images/TugasAplikom5Adi25030630001-051.png](images/TugasAplikom5Adi25030630001-051.png)

Berikut adalah contoh yang lebih rumit, yang terlihat sangat
mengagumkan jika dilihat menggunakan kacamata merah/sian (*red/cyan
glasses*).


\>u:=linspace(-pi,pi,160); v:=linspace(-pi,pi,400)';  ...  
\>   x:=(4\*(1+.25\*sin(3\*v))+cos(u))\*cos(2\*v); ...  
\>   y:=(4\*(1+.25\*sin(3\*v))+cos(u))\*sin(2\*v); ...  
\>    z=sin(u)+2\*cos(3\*v); ...  
\>   plot3d(x,y,z,frame=0,scale=1.5,hue=1,light=[1,0,-1],zoom=2.8,\>anaglyph):


![images/TugasAplikom5Adi25030630001-052.png](images/TugasAplikom5Adi25030630001-052.png)

# Statistical Plots

Plot batang (*bar plots*) juga dapat dibuat dalam 3D. Untuk ini, kita
harus menyediakan:


* 
`x`: vektor baris (*row vector*) dengan $n+1$ elemen

* 
`y`: vektor kolom (*column vector*) dengan $n+1$ elemen

* 
`z`: matriks berukuran $n \times n$ yang berisi nilai-nilai data


Ukuran `z` bisa saja lebih besar, tetapi hanya nilai berukuran $n
\times n$ yang akan digunakan.


Pada contoh ini, pertama-tama kita menghitung nilai-nilainya terlebih
dahulu. Kemudian kita menyesuaikan `x` dan `y` agar posisi vektor
berada tepat di tengah (*center*) dari nilai-nilai yang digunakan.


\>x=-1:0.1:1; y=x'; z=x^2+y^2; ...  
\>   xa=(x|1.1)-0.05; ya=(y\_1.1)-0.05; ...  
\>   plot3d(xa,ya,z,bar=true):


![images/TugasAplikom5Adi25030630001-053.png](images/TugasAplikom5Adi25030630001-053.png)

Memungkinkan juga untuk membagi plot permukaan (*surface plot*)
menjadi dua bagian atau lebih.


\>x=-1:0.1:1; y=x'; z=x+y; d=zeros(size(x)); ...  
\>   plot3d(x,y,z,disconnect=2:2:20):


![images/TugasAplikom5Adi25030630001-054.png](images/TugasAplikom5Adi25030630001-054.png)

Jika Anda memuat atau menghasilkan matriks data `M` dari sebuah berkas
dan perlu memplotnya dalam 3D, Anda dapat menykalakan matriks tersebut
ke rentang `[-1,1]` menggunakan `scale(M)`, atau menykalakannya
menggunakan opsi `&gt;zscale`. Opsi ini juga dapat digabungkan dengan
faktor skala individual (*individual scaling factors*) yang diterapkan
secara terpisah.


\>i=1:20; j=i'; ...  
\>   plot3d(i\*j^2+100\*normal(20,20),\>zscale,scale=[1,1,1.5],angle=-40°,zoom=1.8):


![images/TugasAplikom5Adi25030630001-055.png](images/TugasAplikom5Adi25030630001-055.png)

\>Z=intrandom(5,100,6); v=zeros(5,6); ...  
\>   loop 1 to 5; v[#]=getmultiplicities(1:6,Z[#]); end; ...  
\>   columnsplot3d(v',scols=1:5,ccols=[1:5]):


![images/TugasAplikom5Adi25030630001-056.png](images/TugasAplikom5Adi25030630001-056.png)

# Permukaan Benda Putar

\>plot2d("(x^2+y^2-1)^3-x^2\*y^3",r=1.3, ...  
\>   style="#",color=red,<outline, ...  
\>   level=[-2;0],n=100):


![images/TugasAplikom5Adi25030630001-057.png](images/TugasAplikom5Adi25030630001-057.png)

\>ekspresi &= (x^2+y^2-1)^3-x^2\*y^3; $ekspresi


$$\left(y^2+x^2-1\right)^3-x^2\,y^3$$Kita ingin memutar kurva hati (heart curve) mengelilingi sumbu-$y$.
Berikut adalah ekspresi yang mendefinisikan bentuk hati tersebut:


$$f(x,y)=(x^2+y^2-1)^3-x^2.y^3.$$Selanjutnya, kita menetapkan hubungan koordinat polar:


$$x=r.cos(a),\quad y=r.sin(a).$$\>function fr(r,a) &= ekspresi with [x=r\*cos(a),y=r\*sin(a)] | trigreduce; $fr(r,a)


$$\left(r^2-1\right)^3+\frac{\left(\sin \left(5\,a\right)-\sin \left(  3\,a\right)-2\,\sin a\right)\,r^5}{16}$$Hal ini memungkinkan kita untuk mendefinisikan sebuah fungsi numerik
yang menyelesaikan nilai $r$ jika nilai $a$ diberikan. Dengan fungsi
tersebut, kita dapat membuat plot permukaan terputar (*turned heart*)
sebagai permukaan terparameterisasi (*parametric surface*).


\>function map f(a) := bisect("fr",0,2;a); ...  
\>   t=linspace(-pi/2,pi/2,100); r=f(t);  ...  
\>   s=linspace(pi,2pi,100)'; ...  
\>   plot3d(r\*cos(t)\*sin(s),r\*cos(t)\*cos(s),r\*sin(t), ...  
\>   \>hue,<frame,color=red,zoom=4,amb=0,max=0.7,grid=12,height=50°):


![images/TugasAplikom5Adi25030630001-062.png](images/TugasAplikom5Adi25030630001-062.png)

Berikut adalah plot 3D dari figur di atas yang diputar mengelilingi
sumbu-$z$. Kita mendefinisikan fungsi yang mendeskripsikan objek
tersebut.


\>function f(x,y,z) ...


    r=x^2+y^2;
    return (r+z^2-1)^3-r*z^3;
     endfunction
</pre>
\>plot3d("f(x,y,z)", ...  
\>   xmin=0,xmax=1.2,ymin=-1.2,ymax=1.2,zmin=-1.2,zmax=1.4, ...  
\>   implicit=1,angle=-30°,zoom=2.5,n=[10,100,60],\>anaglyph):


![images/TugasAplikom5Adi25030630001-063.png](images/TugasAplikom5Adi25030630001-063.png)

# Special 3D Plots

Fungsi `plot3d` memang sangat berguna, tetapi tidak selalu memenuhi
semua kebutuhan. Selain rutinitas yang lebih mendasar, Anda juga dapat
membuat plot berbingkai (*framed plot*) untuk objek apa pun yang Anda
inginkan.


Meskipun Euler bukan program khusus 3D, perangkat lunak ini dapat
menggabungkan beberapa objek dasar. Kita coba memvisualisasikan sebuah
paraboloid beserta bidang singgungnya (*tangent*).


\>function myplot ...


      y=-1:0.01:1; x=(-1:0.01:1)';
      plot3d(x,y,0.2*(x-0.1)/2,<scale,<frame,>hue, ..
        hues=0.5,>contour,color=orange);
      h=holding(1);
      plot3d(x,y,(x^2+y^2)/2,<scale,<frame,>contour,>hue);
      holding(h);
    endfunction
</pre>
Fungsi `framedplot()` menyediakan bingkai (*frames*) dan mengatur
sudut pandang (*views*) untuk tampilan plot tersebut.


\>framedplot("myplot",[-1,1,-1,1,0,1],height=0,angle=-30°, ...  
\>     center=[0,0,-0.7],zoom=3):


![images/TugasAplikom5Adi25030630001-064.png](images/TugasAplikom5Adi25030630001-064.png)

Dengan cara yang sama, Anda dapat membuat plot bidang kontur (*contour
plane*) secara manual. Perhatikan bahwa `plot3d()` secara bawaan
(*default*) mengatur jendela ke `fullwindow()`, tetapi
`plotcontourplane()` mengasumsikan pengaturan tersebut telah
diterapkan.


\>x=-1:0.02:1.1; y=x'; z=x^2-y^4;

\>function myplot (x,y,z) ...  
\>  
<pre class="udf">      zoom(2);
      wi=fullwindow();
      plotcontourplane(x,y,z,level="auto",<scale);
      plot3d(x,y,z,>hue,<scale,>add,color=white,level="thin");
      window(wi);
      reset();
    endfunction
</pre>
\>myplot(x,y,z):


![images/TugasAplikom5Adi25030630001-065.png](images/TugasAplikom5Adi25030630001-065.png)

# Animation

Euler dapat menggunakan bingkai (*frames*) untuk menghitung terlebih
dahulu (*pre-compute*) animasi.


Salah satu fungsi yang memanfaatkan teknik ini adalah `rotate`. Fungsi
ini dapat mengubah sudut pandang (*angle of view*) dan menggambar
ulang plot 3D secara berulang. Fungsi ini memanggil `addpage()` untuk
setiap plot baru yang dibuat. Pada akhirnya, fungsi tersebut akan
menampilkan animasi dari kumpulan plot yang telah disimpan.


Silakan pelajari kode sumber (*source code*) dari fungsi `rotate`
untuk melihat detail dan implementasinya secara lebih lengkap.


\>function testplot () := plot3d("x^2+y^3"); ...  
\>   rotate("testplot"); testplot():


![images/TugasAplikom5Adi25030630001-066.png](images/TugasAplikom5Adi25030630001-066.png)

# Menggambar Povray

Dengan bantuan berkas Euler `povray.e`, Euler dapat menghasilkan
berkas Povray. Hasil rendernya sangat bagus dan menarik untuk dilihat.


Anda perlu menginstal Povray (32-bit atau 64-bit) dari
[http://www.povray.org/](http://www.povray.org/), lalu memasukkan
sub-direktori `bin` dari Povray ke dalam *environment path*, atau
mengatur variabel `defaultpovray` dengan jalur lengkap yang mengarah
ke `pvengine.exe`.


Antarmuka Povray di Euler menghasilkan berkas Povray di direktori
utama (*home directory*) pengguna, lalu memanggil Povray untuk
memproses (*parse*) berkas-berkas tersebut. Nama berkas bawaannya
adalah `current.pov`, dan direktori bawaannya adalah `eulerhome()`,
biasanya di `c:\Users\Username\Euler`. Povray akan menghasilkan berkas
PNG yang kemudian dapat dimuat oleh Euler ke dalam *notebook*. Untuk
membersihkan berkas-berkas ini, gunakan fungsi `povclear()`.


Fungsi `pov3d` memiliki konsep yang sama dengan `plot3d`. Fungsi ini
dapat menghasilkan grafik dari sebuah fungsi $f(x,y)$, atau permukaan
dengan koordinat matriks $X, Y, Z$, termasuk garis tingkat (*level
lines*) opsional. Fungsi ini akan menjalankan *raytracer* secara
otomatis dan memuat adegan (*scene*) tersebut ke dalam *notebook*
Euler.


Selain `pov3d()`, terdapat banyak fungsi lain yang dapat menghasilkan
objek Povray. Fungsi-fungsi ini mengembalikan nilai berupa *string*
yang berisi kode Povray untuk objek tersebut. Untuk menggunakannya:


* 
Mulai berkas Povray dengan memanggil `povstart()`.

* 
Gunakan `writeln(...)` untuk menuliskan objek ke dalam berkas
* adegan.

* 
Akhiri berkas dengan `povend()`.


Secara bawaan (*default*), *raytracer* akan berjalan dan berkas PNG
hasil render akan langsung dimasukkan ke dalam *notebook* Euler.


Fungsi-fungsi objek memiliki parameter bernama `look`, yang
membutuhkan *string* berisi kode Povray untuk tekstur dan pemolesan
(*finish*) dari objek tersebut. Fungsi `povlook()` dapat digunakan
untuk menghasilkan *string* ini. Parameter di dalamnya mencakup
pengaturan warna, transparansi, *Phong Shading*, dan lainnya.


Perhatikan bahwa ruang 3D Povray menggunakan sistem koordinat yang
berbeda. Namun, antarmuka ini secara otomatis memetakan seluruh
koordinat ke sistem Povray. Jadi, Anda tetap bisa berpikir menggunakan
sistem koordinat Euler—dengan sumbu-$z$ mengarah vertikal ke atas,
serta sumbu-$x, y, z$ yang mengikuti kaidah tangan kanan (*right hand
sense*).


Jangan lupa, Anda perlu memuat berkas `povray` terlebih dahulu sebelum
menggunakannya.


\>load povray;


Pastikan direktori bin dari Povray sudah terdaftar di dalam path
sistem Anda. Jika belum, edit variabel berikut agar berisi jalur
lengkap (full path) yang mengarah ke berkas eksekutabel Povray:


\>defaultpovray="C:\\Program Files\\POV-Ray\\v3.7\\bin\\pvengine.exe"


    C:\Program Files\POV-Ray\v3.7\bin\pvengine.exe

Untuk memberikan kesan pertama, kita akan membuat plot dari sebuah
fungsi sederhana. Perintah berikut akan menghasilkan berkas Povray di
direktori pengguna Anda, lalu menjalankan Povray untuk melakukan
proses *ray tracing* pada berkas tersebut.


Jika Anda menjalankan perintah berikut, antarmuka (*GUI*) Povray akan
terbuka, memproses berkas, lalu menutup secara otomatis. Demi alasan
keamanan, Anda mungkin akan dimintai konfirmasi apakah ingin
mengizinkan berkas `.exe` tersebut berjalan. Anda dapat menekan
*Cancel* untuk menghentikan pertanyaan lebih lanjut. Selain itu, Anda
mungkin perlu menekan tombol *OK* pada jendela Povray untuk
mengonfirmasi dialog awal (*start-up dialog*) dari Povray.


\>plot3d("x^2+y^2",zoom=2):


![images/TugasAplikom5Adi25030630001-067.png](images/TugasAplikom5Adi25030630001-067.png)

\>pov3d("x^2+y^2",zoom=3);


![images/TugasAplikom5Adi25030630001-068.png](images/TugasAplikom5Adi25030630001-068.png)

Kita dapat membuat fungsi tersebut menjadi transparan dan menambahkan
*finish* (pemolesan) lain. Kita juga dapat menambahkan garis tingkat
(*level lines*) pada plot fungsi tersebut.


\>pov3d("x^2+y^3",axiscolor=red,angle=-45°,\>anaglyph, ...  
\>     look=povlook(cyan,0.2),level=-1:0.5:1,zoom=3.8);


![images/TugasAplikom5Adi25030630001-069.png](images/TugasAplikom5Adi25030630001-069.png)

Terkadang, kita perlu mencegah penskalaan (*scaling*) otomatis dari
fungsi dan melakukan penskalaan secara manual.


Kita akan membuat plot dari himpunan titik pada bidang kompleks di
mana hasil kali jarak ke 1 dan -1 sama dengan 1.


\>pov3d("((x-1)^2+y^2)\*((x+1)^2+y^2)/40",r=2, ...  
\>     angle=-120°,level=1/40,dlevel=0.005,light=[-1,1,1],height=10°,n=50, ...  
\>     <fscale,zoom=3.8);


![images/TugasAplikom5Adi25030630001-070.png](images/TugasAplikom5Adi25030630001-070.png)

# Plotting with Coordinates

Sebagai ganti dari penggunaan fungsi secara langsung, kita dapat
membuat plot menggunakan titik koordinat. Sama seperti pada `plot3d`,
kita memerlukan tiga matriks ($X, Y, Z$) untuk mendefinisikan bentuk
objek tersebut.


Dalam contoh ini, kita memutar sebuah fungsi mengelilingi sumbu-$z$.


\>function f(x) := x^3-x+1; ...  
\>   x=-1:0.01:1; t=linspace(0,2pi,50)'; ...  
\>   Z=x; X=cos(t)\*f(x); Y=sin(t)\*f(x); ...  
\>   pov3d(X,Y,Z,angle=40°,look=povlook(red,0.1),height=50°,axis=0,zoom=4,light=[10,5,15]);


![images/TugasAplikom5Adi25030630001-071.png](images/TugasAplikom5Adi25030630001-071.png)

Dalam contoh berikut, kita membuat plot dari gelombang yang teredam
(*damped wave*). Kita menghasilkan gelombang tersebut menggunakan
bahasa matriks (*matrix language*) bawaan Euler.


Kami juga menunjukkan bagaimana objek tambahan dapat ditambahkan ke
dalam adegan `pov3d`. Untuk pembuatan objek-objek tersebut, silakan
lihat contoh-contoh berikut. Perhatikan bahwa `plot3d` secara otomatis
mengukur skala plot sehingga pas ke dalam kubus satuan (*unit cube*).


\>or=linspace(0,1,80); phi=linspace(0,2pi,80)'; ...  
\>   x=r\*cos(phi); y=r\*sin(phi); z=exp(-5\*r)\*cos(8\*pi\*r)/3;  ...  
\>   pov3d(x,y,z,zoom=6,axis=0,height=30°,add=povsphere([0.5,0,0.25],0.15,povlook(red)), ...  
\>     w=500,h=300);


![images/TugasAplikom5Adi25030630001-072.png](images/TugasAplikom5Adi25030630001-072.png)

Dengan metode pencahayaan (*shading*) tingkat lanjut dari Povray,
jumlah titik yang sangat sedikit pun dapat menghasilkan permukaan yang
sangat halus. Efek trik ini biasanya hanya terlihat jelas pada area
batas/tepi (*boundaries*) atau di wilayah bayangan.


Untuk mencapai hasil ini, kita perlu menambahkan vektor normal
(*normal vectors*) pada setiap titik matriks.


\>Z &= x^2\*y^3


    
                                     2  3
                                    x  y
    

Persamaan dari permukaan tersebut adalah $[x, y, Z]$. Kita menghitung
dua turunan parsial terhadap $x$ dan $y$ dari persamaan ini, lalu
mengambil hasil kali silang (*cross product*) keduanya sebagai vektor
normalnya.


\>dx &= diff([x,y,Z],x); dy &= diff([x,y,Z],y);


Kita mendefinisikan vektor normal sebagai hasil kali silang (*cross
product*) dari turunan-turunan parsial tersebut, lalu mendefinisikan
fungsi-fungsi koordinatnya.


\>N &= crossproduct(dx,dy); NX &= N[1]; NY &= N[2]; NZ &= N[3]; N,


    
                                   3       2  2
                           [- 2 x y , - 3 x  y , 1]
    

Kita hanya menggunakan 25 titik.


\>x=-1:0.5:1; y=x';

\>pov3d(x,y,Z(x,y),angle=10°, ...  
\>     xv=NX(x,y),yv=NY(x,y),zv=NZ(x,y),<shadow);


![images/TugasAplikom5Adi25030630001-073.png](images/TugasAplikom5Adi25030630001-073.png)

Berikut adalah simpul Trefoil (*Trefoil knot*) yang dibuat oleh A.
Busser di Povray. Terdapat versi yang telah ditingkatkan dari contoh
ini di dalam folder contoh.


  <a href="Examples\Trefoil Knot.html">Trefoil Knot</a>  

Untuk mendapatkan tampilan yang bagus tanpa menggunakan terlalu banyak
titik, kita menambahkan vektor normal di sini. Kita menggunakan Maxima
untuk menghitung vektor-vektor normal tersebut secara otomatis.
Pertama, kita tentukan tiga fungsi untuk koordinatnya sebagai ekspresi
simbolik.


\>X &= ((4+sin(3\*y))+cos(x))\*cos(2\*y); ...  
\>   Y &= ((4+sin(3\*y))+cos(x))\*sin(2\*y); ...  
\>   Z &= sin(x)+2\*cos(3\*y);


Kemudian, dua vektor turunan parsial terhadap $x$ dan $y$.


\>dx &= diff([X,Y,Z],x); dy &= diff([X,Y,Z],y);


Sekarang, kita tentukan vektor normalnya, yaitu hasil kali silang
(*cross product*) dari kedua vektor turunan parsial tersebut.


\>dn &= crossproduct(dx,dy);


Sekarang kita mengevaluasi seluruh persamaannya secara numerik.


\>x:=linspace(-%pi,%pi,40); y:=linspace(-%pi,%pi,100)';


Vektor-vektor normal tersebut merupakan hasil evaluasi dari ekspresi
simbolik `dn[i]` untuk $i=1,2,3$. Sintaks untuk melakukan hal ini
adalah `&amp;"expression"(parameters)`. Ini merupakan cara alternatif dari
metode pada contoh sebelumnya, di mana kita mendefinisikan ekspresi
simbolik `NX`, `NY`, `NZ` terlebih dahulu.


\>pov3d(X(x,y),Y(x,y),Z(x,y),\>anaglyph,axis=0,zoom=5,w=450,h=350, ...  
\>     <shadow,look=povlook(blue), ...  
\>     xv=&"dn[1]"(x,y), yv=&"dn[2]"(x,y), zv=&"dn[3]"(x,y));


![images/TugasAplikom5Adi25030630001-074.png](images/TugasAplikom5Adi25030630001-074.png)

Kita juga dapat membuat kisi-kisi (*grid*) dalam ruang 3D.


\>povstart(zoom=4); ...  
\>   x=-1:0.5:1; r=1-(x+1)^2/6; ...  
\>   t=(0°:30°:360°)'; y=r\*cos(t); z=r\*sin(t); ...  
\>   writeln(povgrid(x,y,z,d=0.02,dballs=0.05)); ...  
\>   povend();


![images/TugasAplikom5Adi25030630001-075.png](images/TugasAplikom5Adi25030630001-075.png)

Dengan `povgrid()`, kita juga dapat membuat kurva (lengkungan).


\>povstart(center=[0,0,1],zoom=3.6); ...  
\>   t=linspace(0,2,1000); r=exp(-t); ...  
\>   x=cos(2\*pi\*10\*t)\*r; y=sin(2\*pi\*10\*t)\*r; z=t; ...  
\>   writeln(povgrid(x,y,z,povlook(red))); ...  
\>   writeAxis(0,2,axis=3); ...  
\>   povend();


![images/TugasAplikom5Adi25030630001-076.png](images/TugasAplikom5Adi25030630001-076.png)

# Povray Objects

Di atas, kita menggunakan `pov3d` untuk membuat plot permukaan.
Antarmuka Povray di Euler juga dapat menghasilkan objek-objek Povray.
Objek-objek ini disimpan sebagai *string* di Euler dan perlu ditulis
ke dalam berkas Povray.


Kita memulai *output*-nya dengan `povstart()`.


\>povstart(zoom=4);


Pertama, kita mendefinisikan tiga silinder tersebut dan menyimpannya
sebagai *string* di Euler.


Fungsi-fungsi seperti `povx()` dan sejenisnya hanya mengembalikan
vektor `[1,0,0]`, yang juga dapat digunakan sebagai alternatif.


\>c1=povcylinder(-povx,povx,1,povlook(red)); ...  
\>   c2=povcylinder(-povy,povy,1,povlook(yellow)); ...  
\>   c3=povcylinder(-povz,povz,1,povlook(blue)); ...  
\>  
*String* tersebut berisi kode Povray, yang tidak perlu kita pahami
pada tahap ini.


\>c2


    cylinder { &lt;0,0,-1&gt;, &lt;0,0,1&gt;, 1
     texture { pigment { color rgb &lt;0.941176,0.941176,0.392157&gt; }  } 
     finish { ambient 0.2 } 
     }

Seperti yang Anda lihat, kita menambahkan tekstur pada objek dengan
tiga warna yang berbeda.


Hal ini dilakukan dengan menggunakan fungsi `povlook()`, yang
mengembalikan *string* berisi kode Povray yang relevan. Kita dapat
menggunakan warna bawaan (*default*) dari Euler, atau mendefinisikan
warna kita sendiri. Kita juga dapat menambahkan transparansi, atau
mengubah pencahayaan sekitar (*ambient light*).


\>povlook(rgb(0.1,0.2,0.3),0.1,0.5)


     texture { pigment { color rgbf &lt;0.101961,0.2,0.301961,0.1&gt; }  } 
     finish { ambient 0.5 } 
    

Sekarang kita mendefinisikan sebuah objek irisan (*intersection
object*), lalu menuliskan hasilnya ke dalam berkas.


\>writeln(povintersection([c1,c2,c3]));


Irisan dari tiga buah silinder memang sangat sulit untuk dibayangkan
jika Anda belum pernah melihatnya secara langsung.


\>povend;


![images/TugasAplikom5Adi25030630001-077.png](images/TugasAplikom5Adi25030630001-077.png)

Fungsi-fungsi berikut menghasilkan rekursi fraktal (*recursive
fractal*).


Fungsi pertama menunjukkan bagaimana Euler menangani objek-objek
Povray sederhana. Fungsi `povbox()` mengembalikan sebuah *string* yang
berisi koordinat kotak (*box*), tekstur, serta pengaturan
*finish*-nya.


\>function onebox(x,y,z,d) := povbox([x,y,z],[x+d,y+d,z+d],povlook());

\>function fractal (x,y,z,h,n) ...  
\>  
<pre class="udf">     if n==1 then writeln(onebox(x,y,z,h));
     else
       h=h/3;
       fractal(x,y,z,h,n-1);
       fractal(x+2*h,y,z,h,n-1);
       fractal(x,y+2*h,z,h,n-1);
       fractal(x,y,z+2*h,h,n-1);
       fractal(x+2*h,y+2*h,z,h,n-1);
       fractal(x+2*h,y,z+2*h,h,n-1);
       fractal(x,y+2*h,z+2*h,h,n-1);
       fractal(x+2*h,y+2*h,z+2*h,h,n-1);
       fractal(x+h,y+h,z+h,h,n-1);
     endif;
    endfunction
</pre>
\>povstart(fade=10,<shadow);

\>fractal(-1,-1,-1,2,4);

\>povend();


![images/TugasAplikom5Adi25030630001-078.png](images/TugasAplikom5Adi25030630001-078.png)

*Difference* (pengurangan) memungkinkan kita untuk memotong suatu
objek menggunakan objek lainnya. Sama seperti *intersection* (irisan),
fitur ini merupakan bagian dari objek CSG (*Constructive Solid
Geometry*) pada Povray.


\>povstart(light=[5,-5,5],fade=10);


Untuk demonstrasi ini, kita mendefinisikan sebuah objek langsung di
Povray, bukan menggunakan *string* di Euler. Definisi tersebut akan
langsung dituliskan ke dalam berkas secara instan.


Koordinat kotak (*box coordinate*) sebesar `-1` hanya merupakan bentuk
singkat untuk `[-1,-1,-1]`.


\>povdefine("mycube",povbox(-1,1));


Kita dapat menggunakan objek ini di dalam `povobject()`, yang akan
mengembalikan sebuah *string* seperti biasanya.


\>c1=povobject("mycube",povlook(red));


Kita membuat kubus kedua, lalu memutar (*rotate*) dan mengubah
ukurannya (*scale*) sedikit.


\>c2=povobject("mycube",povlook(yellow),translate=[1,1,1], ...  
\>     rotate=xrotate(10°)+yrotate(10°), scale=1.2);


Kemudian, kita mengambil selisih (*difference*) dari kedua objek
tersebut.


\>writeln(povdifference(c1,c2));


Kemudian, kita menambahkan tiga sumbu (*axes*).


\>writeAxis(-1.2,1.2,axis=1); ...  
\>   writeAxis(-1.2,1.2,axis=2); ...  
\>   writeAxis(-1.2,1.2,axis=4); ...  
\>   povend();


![images/TugasAplikom5Adi25030630001-079.png](images/TugasAplikom5Adi25030630001-079.png)

# Implicit Functions

Povray dapat memplot himpunan nilai di mana $f(x,y,z)=0$, mirip
seperti parameter implisit pada `plot3d`. Namun, hasil tampilan visual
dari Povray jauh lebih bagus dan halus.


Sintaks untuk penulisan fungsinya memang sedikit berbeda. Anda tidak
dapat langsung menggunakan *output* dari ekspresi Maxima atau Euler
secara mentah.


$$((x^2+y^2-c^2)^2+(z^2-1)^2)*((y^2+z^2-c^2)^2+(x^2-1)^2)*((z^2+x^2-c^2)^2+(y^2-1)^2)=d$$\>povstart(angle=70°,height=50°,zoom=4);

\>writeln(povsurface("(pow(pow(x,2)+pow(y,2)-pow(0.1,2),2)+pow(pow(z,2)-1,2))\*(pow(pow(y,2)+pow(z,2)-pow(0.1,2),2)+pow(pow(x,2)-1,2))\*(pow(pow(z,2)+pow(x,2)-pow(0.1,2),2)+pow(pow(y,2)-1,2))-0.1",povlook(red))); ...  
\>   povend();


![images/TugasAplikom5Adi25030630001-081.png](images/TugasAplikom5Adi25030630001-081.png)

\>povstart(angle=25°,height=10°); 

\>writeln(povsurface("pow(x,2)+pow(y,2)\*pow(z,2)-1",povlook(blue),povbox(-2,2,"")));

\>povend();


![images/TugasAplikom5Adi25030630001-082.png](images/TugasAplikom5Adi25030630001-082.png)

\>povstart(angle=70°,height=50°,zoom=4);


Buatlah permukaan implisit (*implicit surface*) tersebut. Perhatikan
perbedaan sintaks pada ekspresi yang digunakan.


\>writeln(povsurface("pow(x,2)\*y-pow(y,3)-pow(z,2)",povlook(green))); ...  
\>   writeAxes(); ...  
\>   povend();


![images/TugasAplikom5Adi25030630001-083.png](images/TugasAplikom5Adi25030630001-083.png)

# Mesh Object

Dalam contoh ini, kita menunjukkan cara membuat objek *mesh* (jaring)
dan menggambarnya dengan informasi tambahan.


Kita ingin memaksimalkan $xy$ dengan syarat $x+y=1$, serta
mendemonstrasikan bagaimana garis-garis level (*level lines*)
bersinggungan secara tangensial.


\>povstart(angle=-10°,center=[0.5,0.5,0.5],zoom=7);


Kita tidak dapat menyimpan objek tersebut di dalam sebuah *string*
seperti sebelumnya karena ukurannya yang terlalu besar. Oleh karena
itu, kita mendefinisikan objek tersebut secara langsung di dalam
berkas Povray menggunakan perintah `#declare`. Fungsi `povtriangle()`
melakukan proses ini secara otomatis dan dapat menerima vektor normal
(*normal vectors*) persis seperti pada `pov3d()`.


Kode berikut mendefinisikan objek *mesh* tersebut dan langsung
menuliskannya ke dalam berkas secara instan.


\>x=0:0.02:1; y=x'; z=x\*y; vx=-y; vy=-x; vz=1;

\>mesh=povtriangles(x,y,z,"",vx,vy,vz);


Sekarang kita mendefinisikan dua buah cakram (*discs*), yang nantinya
akan diiriskan dengan permukaan tersebut.


\>cl=povdisc([0.5,0.5,0],[1,1,0],2); ...  
\>   ll=povdisc([0,0,1/4],[0,0,1],2);


Tuliskan permukaan tersebut dikurangi dengan kedua cakram (*minus the
two discs*).


\>writeln(povdifference(mesh,povunion([cl,ll]),povlook(green)));


Tuliskan kedua irisan (*intersections*) tersebut.


\>writeln(povintersection([mesh,cl],povlook(red))); ...  
\>   writeln(povintersection([mesh,ll],povlook(gray)));


Tuliskan sebuah titik pada posisi nilai maksimum tersebut.


\>writeln(povpoint([1/2,1/2,1/4],povlook(gray),size=2\*defaultpointsize));


Tambahkan sumbu-sumbu (*axes*) serta atur tampilan akhir
(*finish*)-nya.


\>writeAxes(0,1,0,1,0,1,d=0.015); ...  
\>   povend();


![images/TugasAplikom5Adi25030630001-084.png](images/TugasAplikom5Adi25030630001-084.png)

# Anaglyphs in Povray

Untuk membuat gambar anaglif (*anaglyph*) yang dapat dilihat
menggunakan kacamata merah/sian (red/cyan), Povray harus dijalankan
dua kali dari posisi kamera yang berbeda. Proses ini akan menghasilkan
dua berkas Povray dan dua berkas PNG, yang kemudian dimuat menggunakan
fungsi `loadanaglyph()`.


Tentu saja, Anda memerlukan kacamata merah/sian untuk dapat melihat
contoh-contoh berikut dengan benar.


Fungsi `pov3d()` menyediakan sebuah *switch* sederhana untuk
menghasilkan gambar anaglif secara otomatis.


\>pov3d("-exp(-x^2-y^2)/2",r=2,height=45°,\>anaglyph, ...  
\>     center=[0,0,0.5],zoom=3.5);


![images/TugasAplikom5Adi25030630001-085.png](images/TugasAplikom5Adi25030630001-085.png)

Jika Anda membuat *scene* (adegan) yang berisi berbagai objek, Anda
perlu memasukkan proses pembuatan adegan tersebut ke dalam sebuah
fungsi, lalu menjalankannya dua kali dengan nilai parameter anaglif
(*anaglyph parameter*) yang berbeda.


\>function myscene ...


      s=povsphere(povc,1);
      cl=povcylinder(-povz,povz,0.5);
      clx=povobject(cl,rotate=xrotate(90°));
      cly=povobject(cl,rotate=yrotate(90°));
      c=povbox([-1,-1,0],1);
      un=povunion([cl,clx,cly,c]);
      obj=povdifference(s,un,povlook(red));
      writeln(obj);
      writeAxes();
    endfunction
</pre>
Fungsi `povanaglyph()` menangani seluruh proses tersebut secara
otomatis. Parameter-parameter yang digunakan mirip dengan gabungan
dari parameter pada `povstart()` dan `povend()`.


\>povanaglyph("myscene",zoom=4.5);


![images/TugasAplikom5Adi25030630001-086.png](images/TugasAplikom5Adi25030630001-086.png)

# Defining own Objects

Antarmuka Povray di Euler memang sudah menyediakan banyak objek
bawaan. Namun, Anda tidak terbatas hanya pada objek-objek tersebut
saja. Anda dapat membuat objek sendiri, baik dengan memadukan beberapa
objek lain maupun membuat objek yang benar-benar baru.


Sebagai demonstrasi, kita akan membuat sebuah torus (bentuk donat).
Perintah Povray untuk objek ini adalah `"torus"`. Jadi, kita cukup
mengembalikan sebuah *string* yang berisi perintah tersebut beserta
parameter-parameternya. Perlu diingat bahwa torus selalu berpusat di
titik asal (*origin*).


\>function povdonat (r1,r2,look="") ...


      return "torus {"+r1+","+r2+look+"}";
    endfunction
</pre>
Berikut adalah torus pertama kita.


\>t1=povdonat(0.8,0.2)


    torus {0.8,0.2}

Mari kita gunakan objek ini untuk membuat torus kedua, yang digeser
(*translated*) dan diputar (*rotated*).


\>t2=povobject(t1,rotate=xrotate(90°),translate=[0.8,0,0])


    object { torus {0.8,0.2}
     rotate 90 *x 
     translate &lt;0.8,0,0&gt;
     }

Sekarang kita tempatkan objek-objek tersebut ke dalam sebuah adegan
(*scene*). Untuk tampilannya (*look*), kita menggunakan *Phong
Shading*.


\>povstart(center=[0.4,0,0],angle=0°,zoom=3.8,aspect=1.5); ...  
\>   writeln(povobject(t1,povlook(green,phong=1))); ...  
\>   writeln(povobject(t2,povlook(green,phong=1))); ...  
\>  
 &gt;povend();  

calls the Povray program. However, in case of errors, it does not
display the error. You should therefore use


 &gt;povend(&lt;exit);  

if anything did not work. This will leave the Povray window open.


\>povend(h=320,w=480);


![images/TugasAplikom5Adi25030630001-087.png](images/TugasAplikom5Adi25030630001-087.png)

Berikut adalah contoh yang lebih kompleks. Kita akan menyelesaikan
sistem pertidaksamaan:


$$Ax \le b, \quad x \ge 0, \quad c.x \to \text{Max.}$$serta menampilkan titik-titik yang memenuhi syarat (*feasible points*)
dan titik optimumnya dalam plot 3D.


\>A=[10,8,4;5,6,8;6,3,2;9,5,6];

\>b=[10,10,10,10]';

\>c=[1,1,1];


Pertama-tama, mari kita periksa apakah contoh ini memiliki solusi atau
tidak.


\>x=simplex(A,b,c,\>max,\>check)'


    [0,  1,  0.5]

Ya, contoh ini memang memiliki solusi.


Selanjutnya, kita mendefinisikan dua buah objek. Objek yang pertama
adalah bidang (*plane*):


$$a \cdot x \le b$$\>function oneplane (a,b,look="") ...


      return povplane(a,b,look)
    endfunction
</pre>
Kemudian, kita mendefinisikan irisan dari seluruh ruang-separuh (*half
spaces*) tersebut dengan sebuah kubus.


\>function adm (A, b, r, look="") ...


      ol=[];
      loop 1 to rows(A); ol=ol|oneplane(A[#],b[#]); end;
      ol=ol|povbox([0,0,0],[r,r,r]);
      return povintersection(ol,look);
    endfunction
</pre>
Sekarang kita dapat membuat plot untuk adegan (*scene*) tersebut.


\>povstart(angle=120°,center=[0.5,0.5,0.5],zoom=3.5); ...  
\>   writeln(adm(A,b,2,povlook(green,0.4))); ...  
\>   writeAxes(0,1.3,0,1.6,0,1.5); ...  
\>  
Berikut adalah lingkaran di sekeliling titik optimum tersebut.


\>writeln(povintersection([povsphere(x,0.5),povplane(c,c.x')], ...  
\>     povlook(red,0.9)));


Dan sebuah panah (vektor) kesalahan ke arah titik optimum tersebut.


\>writeln(povarrow(x,c\*0.5,povlook(red)));


Kita menambahkan teks ke layar. Teks di sini hanyalah sebuah objek 3D.
Kita perlu menempatkan dan memutarnya sesuai dengan sudut pandang
(*view*) kita.


\>writeln(povtext("Linear Problem",[0,0.2,1.3],size=0.05,rotate=5°)); ...  
\>   povend();


![images/TugasAplikom5Adi25030630001-090.png](images/TugasAplikom5Adi25030630001-090.png)

# More Examples

Anda dapat menemukan beberapa contoh penggunaan Povray lainnya di
dalam berkas-berkas berikut di Euler.


  <a href="Examples/Dandelin Spheres.html">Examples/Dandelin Spheres</a>  

  <a href="Examples/Donat Math.html">Examples/Donat Math</a>  

  <a href="Examples/Trefoil Knot.html">Examples/Trefoil Knot</a>  

  <a href="Examples/Optimization by Affine Scaling.html">Examples/Optimization by Affine Scaling</a>  

\>0 


    0

1. Dandelin Spheres (Bola Dandelin)


enggambar irisan kerucut (elips) beserta bola Dandelin yang
menyinggung permukaan kerucut dan bidang iris:


\>load povray;

\>defaultpovray="C:\\Program Files\\POV-Ray\\v3.7\\bin\\pvengine.exe";

\>povstart(angle=30, height=20, zoom=3.8);

\>writeln(povcone([0,0,-1], 1.5, [0,0,1.5], 0, povlook(gray, 0.4)));

\>writeln(povsphere([0,0.2,0.3], 0.5, povlook(red, phong=1)));

\>writeln(povsphere([0,-0.4,-0.5], 0.8, povlook(blue, phong=1)));

\>writeln(povplane([0,1,1], 0.2, povlook(green, 0.5)));

\>writeAxes(-1.5,1.5,-1.5,1.5,-1.5,1.5);

\>povend();


![images/TugasAplikom5Adi25030630001-091.png](images/TugasAplikom5Adi25030630001-091.png)

2. Donat Math (Torus dan Irisan Torus)


enggabungkan objek Torus (donat) dengan bidang iris atau menggabungkan
dua torus yang saling berkaitan:


\>povstart(angle=40, height=30, zoom=4);

\>t1 = povdonat(0.8, 0.2, povlook(red, phong=1));

\>t2 = povobject(t1, rotate=xrotate(90°), translate=[0.8,0,0], look=povlook(yellow, phong=1));

\>writeln(povobject(t1));

\>writeln(povobject(t2));

\>writeAxes();

\>povend();


![images/TugasAplikom5Adi25030630001-092.png](images/TugasAplikom5Adi25030630001-092.png)

3. Trefoil Knot (Simpul Trefoil 3D)


embuat kurva simpul Trefoil berparameter dalam bentuk wireframe atau
permukaan berpilin:


\>u = linspace(-pi, pi, 300);

\>x = sin(u) + 2\*sin(2\*u);

\>y = cos(u) - 2\*cos(2\*u);

\>z = -sin(3\*u);

\>plot3d(x, y, z, \>wire, linewidth=3, wirecolor=blue, zoom=3.5):


![images/TugasAplikom5Adi25030630001-093.png](images/TugasAplikom5Adi25030630001-093.png)

4. Optimization by Affine Scaling (Optimasi dan Bidang Kendala)


enggambar bidang kendala linier (daerah layak/feasible region) dan
titik optimum dalam ruang 3D:


\>A = [2, 1, 1; 1, 2, 1; 1, 1, 2];

\>b = [4, 4, 4]';

\>c = [1, 1, 1];

\>x = simplex(A, b, c, \>max, \>check)';


\>function plane1(a, b, look="") return povplane(a, b, look) endfunction


\>povstart(angle=120, height=35, zoom=3.5);

\>writeln(plane1(A[1], b[1], povlook(green, 0.5)));

\>writeln(povsphere(x, 0.1, povlook(red)));

\>writeAxes(0,2,0,2,0,2);

\>povend();


![images/TugasAplikom5Adi25030630001-094.png](images/TugasAplikom5Adi25030630001-094.png)

\>    


# Contoh Penyelesaian Masalah Menggambar Kurva/Plot 3D

## 1. Materi Aljabar / Geometri Analitik Ruang (Permukaan Kuadrik:

Paraboloid Hiperbolik / Pelana Kuda)


Soal 1: Gambarkan permukaan kuadrik dari persamaan paraboloid
hiperbolik berikut pada daerah -2 &lt;= x &lt;= 2 dan -2 &lt;= y &lt;= 2 beserta
garis kontur dan bidang konturnya:


$$z = f(x,y) = x^2 - y^2$$\>aspect(1.5);

\>plot3d("x^2 - y^2", r=2, \>spectral, \>contour, \>cp, cpdelta=0.2, ...  
\>     n=80, angle=35°, height=25°, zoom=3.2):


![images/TugasAplikom5Adi25030630001-096.png](images/TugasAplikom5Adi25030630001-096.png)

Penjelasan hasil output: Grafik menampilkan permukaan berbentuk pelana
kuda (hyperbolic paraboloid) dengan titik pelana (saddle point) berada
tepat di pusat koordinat (0,0,0). Ke arah sumbu-x, kurva melengkung ke
atas (warna merah), sedangkan ke arah sumbu-y kurva melengkung ke
bawah (warna biru). Bidang kontur di bagian bawah memperlihatkan
proyeksi garis-garis kontur berbentuk hiperbola.


## 2. Materi Kalkulus Peubah Banyak (Ekstrem Lokal Permukaan Dua

Peubah)


Soal 2: Visualisasikan permukaan fungsi dua peubah berikut pada
interval -2 &lt;= x &lt;= 2 dan -2 &lt;= y &lt;= 2 untuk mengamati titik puncak
(maksimum lokal) dan lembah (minimum lokal):


$$f(x,y) = x \cdot e^{-(x^2 + y^2)}$$\>plot3d("x \* exp(-(x^2 + y^2))", r=2, \>spectral, \>contour, ...  
\>     n=100, angle=45°, height=25°, zoom=3.4):


![images/TugasAplikom5Adi25030630001-098.png](images/TugasAplikom5Adi25030630001-098.png)

Penjelasan hasil output: Permukaan fungsi memperlihatkan dua puncak
ekstrem yang simetris terhadap sumbu-y. Titik maksimum lokal (puncak
tertinggi berwarna merah) terletak di (1/sqrt(2), 0) dengan nilai z
sekitar 0,4289, sedangkan titik minimum lokal (lembah terdalam
berwarna biru) terletak di (-1/sqrt(2), 0) dengan nilai z sekitar
-0,4289. Di luar daerah pusat, permukaan melandai mendekati bidang z =
0.


## 3. Materi Kalkulus Integral (Benda Putar / Surface of Revolution)

Soal 3: Gambarkan permukaan benda putar yang terbentuk apabila kurva
fungsi berikut diputar mengelilingi sumbu-x pada interval 0 &lt;= x &lt;= 4:


$$y = \sqrt{x} + 0.5$$\>plot3d("sqrt(x) + 0.5", a=0, b=4, rotate=1, \>hue, color=blue, grid=8, zoom=3.2):


![images/TugasAplikom5Adi25030630001-100.png](images/TugasAplikom5Adi25030630001-100.png)

Penjelasan hasil output: Dengan menggunakan parameter rotate=1, kurva
y = sqrt(x) + 0.5 diputar sejauh 360 derajat mengelilingi sumbu-x
sehingga membentuk permukaan 3D menyerupai corong/mangkuk yang melebar
ke arah sumbu-x positif, dengan jari-jari lingkaran pangkal sebesar
0,5 di x = 0 dan membesar hingga jari-jari 2,5 pada saat x = 4.


## 4. Materi Trigonometri Ruang (Kurva Heliks Melingkar / Circular

Helix)


Soal 4: Gambarkan kurva parametrik tiga dimensi (heliks) pada selang
parameter 0 &lt;= t &lt;= 6*pi yang didefinisikan oleh persamaan
trigonometri berikut:


$$\mathbf{r}(t) = \left(2\cos(t),\; 2\sin(t),\; \frac{t}{2}\right)$$\>t = linspace(0, 6\*pi, 600);

\>plot3d(2\*cos(t), 2\*sin(t), t/2, \>wire, linewidth=3, wirecolor=red, ...  
\>     angle=30°, height=20°, zoom=3.2):


![images/TugasAplikom5Adi25030630001-102.png](images/TugasAplikom5Adi25030630001-102.png)

Penjelasan hasil output:
Dengan menggunakan opsi &gt;wire pada vektor parametrik x(t), y(t), dan z(t), terbentuk
kurva spiral 3D (heliks) berwarna merah yang melingkar naik secara konstan sebanyak
3 putaran penuh (karena 0 &lt;= t &lt;= 6*pi). Proyeksi kurva ini pada bidang x-y berupa
lingkaran berjari-jari 2, sementara ketinggiannya bertambah secara linear sepanjang sumbu-z.


## 5. Materi Geometri Ruang / Permukaan Implisit (Bola / Sphere)

Soal 5: Gambarkan permukaan implisit dari persamaan bola berjari-jari 2 yang
berpusat di titik asal (0,0,0) berikut:


\>plot3d("x^2 + y^2 + z^2 - 4", r=2.5, \>implicit, angle=35°, height=25°, zoom=3):


![images/TugasAplikom5Adi25030630001-103.png](images/TugasAplikom5Adi25030630001-103.png)

Penjelasan hasil output:
Dengan mengaktifkan flag &gt;implicit, EMT memvisualisasikan himpunan titik (x,y,z) yang
memenuhi x^2 + y^2 + z^2 = 4 berupa irisan-irisan lingkaran yang membentuk permukaan
bola simetris berjari-jari 2 dan berpusat di titik (0,0,0).


