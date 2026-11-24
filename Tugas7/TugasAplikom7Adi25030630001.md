# Visualisasi dan Perhitungan Geometri dengan EMT
Euler menyediakan beberapa fungsi untuk melakukan visualisasi dan perhitungan geometri, baik
secara numerik maupun analitik (seperti biasanya tentunya, menggunakan Maxima).
Fungsi-fungsi untuk visualisasi dan perhitungan geometeri tersebut disimpan di dalam file
program "geometry.e", sehingga file tersebut harus dipanggil sebelum menggunakan
fungsi-fungsi atau perintah-perintah untuk geometri.


\>load geometry


    Numerical and symbolic geometry.

## Fungsi-fungsi Geometri

Fungsi-fungsi untuk Menggambar Objek Geometri:


  defaultd:=textheight()*1.5: nilai asli untuk parameter d  
  setPlotrange(x1,x2,y1,y2): menentukan rentang x dan y pada bidang koordinat  
  setPlotRange(r): pusat bidang koordinat (0,0) dan batas-batas sumbu-x dan y adalah -r sd r  
  plotPoint (P, "P"): menggambar titik P dan diberi label "P"  
  plotSegment (A,B, "AB", d): menggambar ruas garis AB, diberi label "AB" sejauh d  
  plotLine (g, "g", d): menggambar garis g diberi label "g" sejauh d  
  plotCircle (c,"c",v,d): Menggambar lingkaran c dan diberi label "c"  
  plotLabel (label, P, V, d): menuliskan label pada posisi P  

Fungsi-fungsi Geometri Analitik (numerik maupun simbolik):


  turn(v, phi): memutar vektor v sejauh phi  
  turnLeft(v):   memutar vektor v ke kiri  
  turnRight(v):  memutar vektor v ke kanan  
  normalize(v): normal vektor v  
  crossProduct(v, w): hasil kali silang vektorv dan w.  
  lineThrough(A, B): garis melalui A dan B, hasilnya [a,b,c] sdh. ax+by=c.  
  lineWithDirection(A,v): garis melalui A searah vektor v  
  getLineDirection(g): vektor arah (gradien) garis g  
  getNormal(g): vektor normal (tegak lurus) garis g  
  getPointOnLine(g):  titik pada garis g  
  perpendicular(A, g):  garis melalui A tegak lurus garis g  
  parallel (A, g):  garis melalui A sejajar garis g  
  lineIntersection(g, h):  titik potong garis g dan h  
  projectToLine(A, g):   proyeksi titik A pada garis g  
  distance(A, B):  jarak titik A dan B  
  distanceSquared(A, B):  kuadrat jarak A dan B  
  quadrance(A, B): kuadrat jarak A dan B  
  areaTriangle(A, B, C):  luas segitiga ABC  
  computeAngle(A, B, C):   besar sudut &lt;ABC  
  angleBisector(A, B, C): garis bagi sudut &lt;ABC  
  circleWithCenter (A, r): lingkaran dengan pusat A dan jari-jari r  
  getCircleCenter(c):  pusat lingkaran c  
  getCircleRadius(c):  jari-jari lingkaran c  
  circleThrough(A,B,C):  lingkaran melalui A, B, C  
  middlePerpendicular(A, B): titik tengah AB  
  lineCircleIntersections(g, c): titik potong garis g dan lingkran c  
  circleCircleIntersections (c1, c2):  titik potong lingkaran c1 dan c2  
  planeThrough(A, B, C):  bidang melalui titik A, B, C  

Fungsi-fungsi Khusus Untuk Geometri Simbolik:


  getLineEquation (g,x,y): persamaan garis g dinyatakan dalam x dan y  
  getHesseForm (g,x,y,A): bentuk Hesse garis g dinyatakan dalam x dan y dengan titik A pada  
  sisi positif (kanan/atas) garis  
  quad(A,B): kuadrat jarak AB  
  spread(a,b,c): Spread segitiga dengan panjang sisi-sisi a,b,c, yakni sin(alpha)^2 dengan  
  alpha sudut yang menghadap sisi a.  
  crosslaw(a,b,c,sa): persamaan 3 quads dan 1 spread pada segitiga dengan panjang sisi a, b, c.  
  triplespread(sa,sb,sc): persamaan 3 spread sa,sb,sc yang memebntuk suatu segitiga  
  doublespread(sa): Spread sudut rangkap Spread 2*phi, dengan sa=sin(phi)^2 spread a.  

## Contoh 1: Luas, Lingkaran Luar, Lingkaran Dalam Segitiga

Untuk menggambar objek-objek geometri, langkah pertama adalah menentukan rentang sumbu-sumbu
koordinat. Semua objek geometri akan digambar pada satu bidang koordinat, sampai didefinisikan
bidang koordinat yang baru.


\>setPlotRange(-0.5,2.5,-0.5,2.5); // mendefinisikan bidang koordinat baru 


Sekarang tentukan tiga titik dan buat plotnya.


\>A=[1,0]; plotPoint(A,"A"); // definisi dan gambar tiga titik

\>B=[0,1]; plotPoint(B,"B");

\>C=[2,2]; plotPoint(C,"C");


Kemudian tiga segmen garis.


\>plotSegment(A,B,"c"); // c=AB

\>plotSegment(B,C,"a"); // a=BC

\>plotSegment(A,C,"b"); // b=AC


Fungsi-fungsi geometri mencakup fungsi untuk membuat garis dan
lingkaran. Format untuk garis tersebut adalah [a,b,c], yang
merepresentasikan garis dengan persamaan ax+by=c.


\>lineThrough(B,C) // garis yang melalui B dan C


    [-1,  2,  2]

Hitung garis tegak lurus yang melalui A pada BC.


\>h=perpendicular(A,lineThrough(B,C)); // garis h tegak lurus BC melalui A


Dan titik potongnya dengan BC.


\>D=lineIntersection(h,lineThrough(B,C)); // D adalah titik potong h dan BC


Buat grafiknya


\>plotPoint(D,value=1); // koordinat D ditampilkan

\>aspect(1); plotSegment(A,D): // tampilkan semua gambar hasil plot...()


![images/TugasAplikom7Adi25030630001-001.png](images/TugasAplikom7Adi25030630001-001.png)

Hitung luas ABC:


$$L_{\triangle ABC}= \frac{1}{2}AD.BC.$$\>norm(A-D)\*norm(B-C)/2 // AD=norm(A-D), BC=norm(B-C)


    1.5

Bandingkan dengan rumus determinan.


\>areaTriangle(A,B,C) // hitung luas segitiga langusng dengan fungsi


    1.5

Cara lain menghitung luas segitigas ABC:


\>distance(A,D)\*distance(B,C)/2


    1.5

Sudut di titik C.


\>degprint(computeAngle(B,C,A))


    36°52'11.63''

Sekarang lingkaran luar segitiga tersebut.


\>c=circleThrough(A,B,C); // lingkaran luar segitiga ABC

\>R=getCircleRadius(c); // jari2 lingkaran luar 

\>O=getCircleCenter(c); // titik pusat lingkaran c 

\>plotPoint(O,"O"); // gambar titik "O"

\>plotCircle(c,"Lingkaran luar segitiga ABC"):


![images/TugasAplikom7Adi25030630001-003.png](images/TugasAplikom7Adi25030630001-003.png)

Tampilkan koordinat titik pusat dan jari-jari lingkaran luar.


\>O, R


    [1.16667,  1.16667]
    1.17851130198

Sekarang akan digambar lingkaran dalam segitiga ABC. Titik pusat lingkaran dalam adalah
titik potong garis-garis bagi sudut.


\>l=angleBisector(A,C,B); // garis bagi <ACB

\>g=angleBisector(C,A,B); // garis bagi <CAB

\>P=lineIntersection(l,g) // titik potong kedua garis bagi sudut


    [0.86038,  0.86038]

Tambahkan semuanya ke plot.


\>color(5); plotLine(l); plotLine(g); color(1); // gambar kedua garis bagi sudut

\>plotPoint(P,"P"); // gambar titik potongnya

\>r=norm(P-projectToLine(P,lineThrough(A,B))) // jari-jari lingkaran dalam


    0.509653732104

\>plotCircle(circleWithCenter(P,r),"Lingkaran dalam segitiga ABC"): // gambar lingkaran dalam


![images/TugasAplikom7Adi25030630001-004.png](images/TugasAplikom7Adi25030630001-004.png)

## Latihan

1. Tentukan ketiga titik singgung lingkaran dalam dengan sisi-sisi
segitiga ABC.


2. Gambar segitiga dengan titik-titik sudut ketiga titik singgung
tersebut. Merupakan segitiga apakah itu?


3. Hitung luas segitiga tersebut.


4. Tunjukkan bahwa garis bagi sudut yang ke tiga juga melalui titik
pusat lingkaran dalam.


5. Gambar jari-jari lingkaran dalam.


6. Hitung luas lingkaran luar dan luas lingkaran dalam segitiga ABC.
Adakah hubungan antara luas kedua lingkaran tersebut dengan luas
segitiga ABC?


\>load geometry;


1. Tentukan Ketiga Titik Singgung Lingkaran Dalam dengan Sisi-Sisi
Segitiga ABC


   a.Inisialisasi Bidang Koordinat dan Segitiga ABC


\>setPlotRange(-0.5,2.5,-0.5,2.5); aspect(1);

\>A=[1,0]; plotPoint(A,"A");

\>B=[0,1]; plotPoint(B,"B");

\>C=[2,2]; plotPoint(C,"C");

\>plotSegment(A,B,"c"); plotSegment(B,C,"a"); plotSegment(A,C,"b");


   b. Pusat Lingkaran Dalam (P) dan Garis Bagi Sudut  

\>l=angleBisector(A,C,B);

\>g=angleBisector(C,A,B);

\>P=lineIntersection(l,g); plotPoint(P,"P");


   c.  Menghitung Titik-Titik Singgung Lingkaran Dalam  

\>T1=projectToLine(P,lineThrough(A,B)); plotPoint(T1,"T1");

\>T2=projectToLine(P,lineThrough(B,C)); plotPoint(T2,"T2");

\>T3=projectToLine(P,lineThrough(A,C)); plotPoint(T3,"T3");


2. Gambar Segitiga dengan Titik-Titik Sudut Ketiga Titik Singgung
Tersebut


\>color(3); plotSegment(T1,T2); plotSegment(T2,T3); plotSegment(T3,T1); color(1);


3. Hitung Luas Segitiga Tersebut


\>LuasSegitigaT1T2T3 = areaTriangle(T1,T2,T3)


    0.324341649025

4. Tunjukkan Bahwa Garis Bagi Sudut yang Ke Tiga Juga Melalui Titik
Pusat Lingkaran Dalam


\>k=angleBisector(A,B,C);

\>color(5); plotLine(k); color(1);


5. Gambar Jari-Jari Lingkaran Dalam


\>r=distance(P,T1);

\>plotCircle(circleWithCenter(P,r),"Lingkaran Dalam");

\>color(2); plotSegment(P,T1); plotSegment(P,T2); plotSegment(P,T3); color(1);


6. Hitung Luas Lingkaran Luar dan Luas Lingkaran Dalam Segitiga ABC


\>lingkaranluar=circleThrough(A,B,C);

\>R=getCircleRadius(lingkaranluar);

\>O=getCircleCenter(lingkaranluar); plotPoint(O,"O");

\>plotCircle(lingkaranluar,"Lingkaran Luar");

\>LuasLingkaranLuar = pi \* R^2


    4.36332312999

\>LuasLingkaranDalam = pi \* r^2


    0.81601903655

\>LuasSegitigaABC = areaTriangle(A,B,C)


    1.5

# Contoh 2: Geometri Simbolik

Kita dapat menghitung geometri eksak dan simbolik menggunakan Maxima.


File geometry.e menyediakan fungsi yang sama (dan lebih banyak lagi)
di Maxima. Namun, kita sekarang dapat menggunakan komputasi simbolik.


\>A &= [1,0]; B &= [0,1]; C &= [2,2]; // menentukan tiga titik A, B, C


Fungsi-fungsi untuk garis dan lingkaran bekerja persis seperti
fungsi-fungsi Euler, tetapi menyediakan komputasi simbolik.


\>c &= lineThrough(B,C) // c=BC


    
                                 [- 1, 2, 2]
    

Kita dapat memperoleh persamaan garis dengan mudah.


\>$getLineEquation(c,x,y), $solve(%,y) | expand // persamaan garis c


$$\left[ y=\frac{x}{2}+1 \right] $$![images/TugasAplikom7Adi25030630001-006.png](images/TugasAplikom7Adi25030630001-006.png)

\>$getLineEquation(lineThrough([x1,y1],[x2,y2]),x,y), $solve(%,y) // persamaan garis melalui(x1, y1) dan (x2, y2)


$$\left[ y=\frac{-\left({\it x_1}-x\right)\,{\it y_2}-\left(x-  {\it x_2}\right)\,{\it y_1}}{{\it x_2}-{\it x_1}} \right] $$![images/TugasAplikom7Adi25030630001-008.png](images/TugasAplikom7Adi25030630001-008.png)

\>$getLineEquation(lineThrough(A,[x1,y1]),x,y) // persamaan garis melalui A dan (x1, y1)


$$\left({\it x_1}-1\right)\,y-x\,{\it y_1}=-{\it y_1}$$\>h &= perpendicular(A,lineThrough(B,C)) // h melalui A tegak lurus BC


    
                                  [2, 1, 2]
    

\>Q &= lineIntersection(c,h) // Q titik potong garis c=BC dan h


    
                                     2  6
                                    [-, -]
                                     5  5
    

\>$projectToLine(A,lineThrough(B,C)) // proyeksi A pada BC


$$\left[ \frac{2}{5} , \frac{6}{5} \right] $$\>$distance(A,Q) // jarak AQ


$$\frac{3}{\sqrt{5}}$$\>cc &= circleThrough(A,B,C); $cc // (titik pusat dan jari-jari) lingkaran melalui A, B, C


$$\left[ \frac{7}{6} , \frac{7}{6} , \frac{5}{3\,\sqrt{2}} \right] $$\>r&=getCircleRadius(cc); $r , $float(r) // tampilkan nilai jari-jari


$$1.178511301977579$$![images/TugasAplikom7Adi25030630001-014.png](images/TugasAplikom7Adi25030630001-014.png)

\>$computeAngle(A,C,B) // nilai <ACB


$$\arccos \left(\frac{4}{5}\right)$$\>$solve(getLineEquation(angleBisector(A,C,B),x,y),y)[1] // persamaan garis bagi <ACB


$$y=x$$\>P &= lineIntersection(angleBisector(A,C,B),angleBisector(C,B,A)); $P // titik potong 2 garis bagi sudut


$$\left[ \frac{\sqrt{2}\,\sqrt{5}+2}{6} , \frac{\sqrt{2}\,\sqrt{5}+2  }{6} \right] $$\>P() // hasilnya sama dengan perhitungan sebelumnya


    [0.86038,  0.86038]

## Intersecting Lines and Circles

Tentu saja, kita juga dapat memotongkan garis dengan lingkaran, dan
lingkaran dengan lingkaran.


\>A &:= [1,0]; c=circleWithCenter(A,4);

\>B &:= [1,2]; C &:= [2,1]; l=lineThrough(B,C);

\>setPlotRange(5); plotCircle(c); plotLine(l);


Perpotongan antara garis dan lingkaran menghasilkan dua titik dan
jumlah titik perpotongan.


\>{P1,P2,f}=lineCircleIntersections(l,c);

\>P1, P2, f


    [4.64575,  -1.64575]
    [-0.645751,  3.64575]
    2

\>plotPoint(P1); plotPoint(P2):


![images/TugasAplikom7Adi25030630001-018.png](images/TugasAplikom7Adi25030630001-018.png)

Hal yang sama berlaku di Maxima.


\>c &= circleWithCenter(A,4) // lingkaran dengan pusat A jari-jari 4


    
                                  [1, 0, 4]
    

\>l &= lineThrough(B,C) // garis l melalui B dan C


    
                                  [1, 1, 3]
    

\>$lineCircleIntersections(l,c) | radcan, // titik potong lingkaran c dan garis l


$$\left[ \left[ \sqrt{7}+2 , 1-\sqrt{7} \right]  , \left[ 2-\sqrt{7}   , \sqrt{7}+1 \right]  \right] $$Akan ditunjukkan bahwa sudut-sudut yang menghadap bsuusr yang sama adalah sama besar.


\>C=A+normalize([-2,-3])\*4; plotPoint(C); plotSegment(P1,C); plotSegment(P2,C);

\>degprint(computeAngle(P1,C,P2))


    69°17'42.68''

\>C=A+normalize([-4,-3])\*4; plotPoint(C); plotSegment(P1,C); plotSegment(P2,C);

\>degprint(computeAngle(P1,C,P2))


    69°17'42.68''

\>insimg;


![images/TugasAplikom7Adi25030630001-020.png](images/TugasAplikom7Adi25030630001-020.png)

## Garis Sumbu

Berikut adalah langkah-langkah menggambar garis sumbu ruas garis AB:


1. Gambar lingkaran dengan pusat A melalui B.


2. Gambar lingkaran dengan pusat B melalui A.


3. Tarik garis melallui kedua titik potong kedua lingkaran tersebut. Garis ini merupakan
garis sumbu (melalui titik tengah dan tegak lurus) AB.


\>A=[2,2]; B=[-1,-2];

\>c1=circleWithCenter(A,distance(A,B));

\>c2=circleWithCenter(B,distance(A,B));

\>{P1,P2,f}=circleCircleIntersections(c1,c2);

\>l=lineThrough(P1,P2);

\>setPlotRange(5); plotCircle(c1); plotCircle(c2);

\>plotPoint(A); plotPoint(B); plotSegment(A,B); plotLine(l):


![images/TugasAplikom7Adi25030630001-021.png](images/TugasAplikom7Adi25030630001-021.png)

Berikutnya, kita melakukan hal yang sama di Maxima menggunakan
koordinat umum.


\>A &= [a1,a2]; B &= [b1,b2];

\>c1 &= circleWithCenter(A,distance(A,B));

\>c2 &= circleWithCenter(B,distance(A,B));

\>P &= circleCircleIntersections(c1,c2); P1 &= P[1]; P2 &= P[2];


Persamaan-persamaan untuk titik potong tersebut cukup rumit. Namun,
kita dapat menyederhanakannya jika kita menyelesaikannya terhadap $y$.


\>g &= getLineEquation(lineThrough(P1,P2),x,y);

\>$solve(g,y)


$$\left[ y=\frac{-\left(2\,{\it b_1}-2\,{\it a_1}\right)\,x+{\it b_2}  ^2+{\it b_1}^2-{\it a_2}^2-{\it a_1}^2}{2\,{\it b_2}-2\,{\it a_2}}   \right] $$Ini memang sama dengan garis sumbu, yang dihitung dengan cara yang
sama sekali berbeda.


\>$solve(getLineEquation(middlePerpendicular(A,B),x,y),y)


$$\left[ y=\frac{-\left(2\,{\it b_1}-2\,{\it a_1}\right)\,x+{\it b_2}  ^2+{\it b_1}^2-{\it a_2}^2-{\it a_1}^2}{2\,{\it b_2}-2\,{\it a_2}}   \right] $$\>h &=getLineEquation(lineThrough(A,B),x,y);

\>$solve(h,y)


$$\left[ y=\frac{\left({\it b_2}-{\it a_2}\right)\,x-{\it a_1}\,  {\it b_2}+{\it a_2}\,{\it b_1}}{{\it b_1}-{\it a_1}} \right] $$Perhatikan hasil kali gradien garis g dan h adalah:


$$\frac{-(b_1-a_1)}{(b_2-a_2)}\times \frac{(b_2-a_2)}{(b_1-a_1)} = -1.$$Artinya kedua garis tegak lurus.


# Contoh 3: Rumus Heron

Rumus Heron menyatakan bahwa luas segitiga dengan panjang sisi-sisi a,
b dan c adalah:


$$L = \sqrt{s(s-a)(s-b)(s-c)}\quad \text{ dengan } s=(a+b+c)/2,$$atau bisa ditulis dalam bentuk lain:


$$L = \frac{1}{4}\sqrt{(a+b+c)(b+c-a)(a+c-b)(a+b-c)}$$Untuk membuktikan hal ini kita misalkan C(0,0), B(a,0) dan A(x,y),
b=AC, c=AB. Luas segitiga ABC adalah


$$L_{\triangle ABC}=\frac{1}{2}a\times y.$$Nilai y didapat dengan menyelesaikan sistem persamaan:


$$x^2+y^2=b^2, \quad (x-a)^2+y^2=c^2.$$\>setPlotRange(-1,10,-1,8); plotPoint([0,0], "C(0,0)"); plotPoint([5.5,0], "B(a,0)");  ...  
\>    plotPoint([7.5,6], "A(x,y)");

\>plotSegment([0,0],[5.5,0], "a",25); plotSegment([5.5,0],[7.5,6],"c",15);  ...  
\>   plotSegment([0,0],[7.5,6],"b",25); 

\>plotSegment([7.5,6],[7.5,0],"t=y",25):


![images/TugasAplikom7Adi25030630001-030.png](images/TugasAplikom7Adi25030630001-030.png)

\>&assume(a\>0); sol &= solve([x^2+y^2=b^2,(x-a)^2+y^2=c^2],[x,y])


    
                    2    2    2
                 - c  + b  + a
           [[x = --------------, y = 
                      2 a
              4      2  2      2  2    4      2  2    4
      sqrt(- c  + 2 b  c  + 2 a  c  - b  + 2 a  b  - a )
    - --------------------------------------------------], 
                             2 a
            2    2    2
         - c  + b  + a
    [x = --------------, y = 
              2 a
            4      2  2      2  2    4      2  2    4
    sqrt(- c  + 2 b  c  + 2 a  c  - b  + 2 a  b  - a )
    --------------------------------------------------]]
                           2 a
    

Ekstrak solusinya y.


\>ysol &= y with sol[2][2]; $'y=sqrt(factor(ysol^2))


$$y=\frac{\sqrt{\left(-c+b+a\right)\,\left(c-b+a\right)\,\left(c+b-a  \right)\,\left(c+b+a\right)}}{2\,a}$$Kita mendapatkan rumus Heron.


\>function H(a,b,c) &= sqrt(factor((ysol\*a/2)^2)); $'H(a,b,c)=H(a,b,c)


$$H\left(a , b , c\right)=\frac{\sqrt{\left(-c+b+a\right)\,\left(c-b+  a\right)\,\left(c+b-a\right)\,\left(c+b+a\right)}}{4}$$\>$'Luas=H(2,5,6) // luas segitiga dengan panjang sisi-sisi 2, 5, 6


$${\it Luas}=\frac{3\,\sqrt{39}}{4}$$Tentu saja, setiap segitiga siku-siku merupakan kasus yang sudah
dikenal luas.


\>H(3,4,5) //luas segitiga siku-siku dengan panjang sisi 3, 4, 5


    6

Dan sudah jelas juga bahwa ini adalah segitiga dengan luas maksimal
serta kedua sisi 3 dan 4.


\>aspect (1.5); plot2d(&H(3,4,x),1,7): // Kurva luas segitiga sengan panjang sisi 3, 4, x (1<= x <=7)


![images/TugasAplikom7Adi25030630001-034.png](images/TugasAplikom7Adi25030630001-034.png)

Kasus umum juga berlaku.


\>$solve(diff(H(a,b,c)^2,c)=0,c)


$$\left[ c=-\sqrt{b^2+a^2} , c=\sqrt{b^2+a^2} , c=0 \right] $$Sekarang mari kita cari himpunan semua titik di mana b+c=d untuk suatu
konstanta d. Sudah diketahui secara luas bahwa ini adalah sebuah
elips.


\>s1 &= subst(d-c,b,sol[2]); $s1


$$\left[ x=\frac{\left(d-c\right)^2-c^2+a^2}{2\,a} , y=\frac{\sqrt{-  \left(d-c\right)^4+2\,c^2\,\left(d-c\right)^2+2\,a^2\,\left(d-c  \right)^2-c^4+2\,a^2\,c^2-a^4}}{2\,a} \right] $$Dan buatlah fungsi-fungsi dari hal ini.


\>function fx(a,c,d) &= rhs(s1[1]); $fx(a,c,d), function fy(a,c,d) &= rhs(s1[2]); $fy(a,c,d)


$$\frac{\sqrt{-\left(d-c\right)^4+2\,c^2\,\left(d-c\right)^2+2\,a^2\,  \left(d-c\right)^2-c^4+2\,a^2\,c^2-a^4}}{2\,a}$$![images/TugasAplikom7Adi25030630001-038.png](images/TugasAplikom7Adi25030630001-038.png)

Sekarang kita dapat menggambar himpunan tersebut. Sisi b bervariasi
dari 1 hingga 4. Sudah diketahui secara luas bahwa kita mendapatkan
sebuah elips.


\>aspect(1); plot2d(&fx(3,x,5),&fy(3,x,5),xmin=1,xmax=4,square=1):


![images/TugasAplikom7Adi25030630001-039.png](images/TugasAplikom7Adi25030630001-039.png)

Kita dapat memeriksa persamaan umum untuk elips ini, yaitu


$$\frac{(x-x_m)^2}{u^2}+\frac{(y-y_m)}{v^2}=1,$$di mana xm,ym adalah pusatnya, dan u serta v adalah setengah
sumbunya..


\>$ratsimp((fx(a,c,d)-a/2)^2/u^2+fy(a,c,d)^2/v^2 with [u=d/2,v=sqrt(d^2-a^2)/2])


$$1$$Kita melihat bahwa tinggi dan dengan demikian luas segitiga mencapai
maksimum untuk x=0. Oleh karena itu, luas segitiga dengan a+b+c=d
bernilai maksimum jika segitiga tersebut merupakan segitiga sama sisi.
Kita ingin menurunkan hal ini secara analitis.


\>eqns &= [diff(H(a,b,d-(a+b))^2,a)=0,diff(H(a,b,d-(a+b))^2,b)=0]; $eqns


$$\left[ \frac{d\,\left(d-2\,a\right)\,\left(d-2\,b\right)}{8}-\frac{  \left(-d+2\,b+2\,a\right)\,d\,\left(d-2\,b\right)}{8}=0 , \frac{d\,  \left(d-2\,a\right)\,\left(d-2\,b\right)}{8}-\frac{\left(-d+2\,b+2\,  a\right)\,d\,\left(d-2\,a\right)}{8}=0 \right] $$Kita mendapatkan beberapa titik minimum, yang bersesuaian dengan
segitiga dengan salah satu sisinya bernilai 0, serta solusi a=b=c=d/3.


\>$solve(eqns,[a,b])


$$\left[ \left[ a=\frac{d}{3} , b=\frac{d}{3} \right]  , \left[ a=0   , b=\frac{d}{2} \right]  , \left[ a=\frac{d}{2} , b=0 \right]  ,   \left[ a=\frac{d}{2} , b=\frac{d}{2} \right]  \right] $$Ada juga metode Lagrange, yaitu memaksimumkan H(a,b,c)^2 terhadap
kendala a+b+c=d.


\>&solve([diff(H(a,b,c)^2,a)=la,diff(H(a,b,c)^2,b)=la, ...  
\>      diff(H(a,b,c)^2,c)=la,a+b+c=d],[a,b,c,la])


    
                         d      d
            [[a = 0, b = -, c = -, la = 0], 
                         2      2
         d             d                d      d
    [a = -, b = 0, c = -, la = 0], [a = -, b = -, c = 0, la = 0], 
         2             2                2      2
                                3
         d      d      d       d
    [a = -, b = -, c = -, la = ---]]
         3      3      3       108
    

Kita dapat membuat grafik/plot dari situasi tersebut.


Pertama, tentukan titik-titik tersebut di Maxima.


\>A &= at([x,y],sol[2]); $A


$$\left[ \frac{-c^2+b^2+a^2}{2\,a} , \frac{\sqrt{-c^4+2\,b^2\,c^2+2\,  a^2\,c^2-b^4+2\,a^2\,b^2-a^4}}{2\,a} \right] $$\>B &= [0,0]; $B, C &= [a,0]; $C


$$\left[ a , 0 \right] $$![images/TugasAplikom7Adi25030630001-046.png](images/TugasAplikom7Adi25030630001-046.png)

Kemudian tentukan rentang grafiknya, dan alurkan titik-titiknya.


\>setPlotRange(0,5,-2,3); ...  
\>   a=4; b=3; c=2; ...  
\>   plotPoint(mxmeval("B"),"B"); plotPoint(mxmeval("C"),"C"); ...  
\>   plotPoint(mxmeval("A"),"A"):


![images/TugasAplikom7Adi25030630001-047.png](images/TugasAplikom7Adi25030630001-047.png)

Alurkan ruas-ruas garis tersebut.


\>plotSegment(mxmeval("A"),mxmeval("C")); ...  
\>   plotSegment(mxmeval("B"),mxmeval("C")); ...  
\>   plotSegment(mxmeval("B"),mxmeval("A")):


![images/TugasAplikom7Adi25030630001-048.png](images/TugasAplikom7Adi25030630001-048.png)

Hitunglah garis sumbu (atau garis tegak lurus di tengah) di Maxima.


\>h &= middlePerpendicular(A,B); g &= middlePerpendicular(B,C);


Dan pusat lingkaran tersebut.


\>U &= lineIntersection(h,g);


Kita mendapatkan rumus untuk jari-jari lingkaran luar.


\>&assume(a\>0,b\>0,c\>0); $distance(U,B) | radcan


$$\frac{i\,a\,b\,c}{\sqrt{c-b-a}\,\sqrt{c-b+a}\,\sqrt{c+b-a}\,\sqrt{c  +b+a}}$$Mari kita tambahkan ini ke dalam grafik (plot).


\>plotPoint(U()); ...  
\>   plotCircle(circleWithCenter(mxmeval("U"),mxmeval("distance(U,C)"))):


![images/TugasAplikom7Adi25030630001-050.png](images/TugasAplikom7Adi25030630001-050.png)

Dengan menggunakan geometri, kita menurunkan rumus sederhana


$$\frac{a}{\sin(\alpha)}=2r$$untuk jari-jari tersebut. Kita dapat memeriksa apakah ini benar-benar
berlaku menggunakan Maxima. Maxima hanya akan memfaktorkannya jika
kita mengkuadratkannya.


\>$c^2/sin(computeAngle(A,B,C))^2  | factor


$$-\frac{4\,a^2\,b^2\,c^2}{\left(c-b-a\right)\,\left(c-b+a\right)\,  \left(c+b-a\right)\,\left(c+b+a\right)}$$# Contoh 4: Garis Euler dan Parabola

Garis Euler adalah garis yang ditentukan dari setiap segitiga yang
bukan segitiga sama sisi. Garis ini merupakan garis sentral dari
segitiga, dan melalui beberapa titik penting yang ditentukan dari
segitiga tersebut, termasuk titik tinggi (ortosenter), titik pusat
lingkaran luar (sirkumsenter), titik berat (sentroid), titik Exeter,
dan pusat lingkaran sembilan titik dari segitiga tersebut.


Sebagai demonstrasi, kita menghitung dan memetakan (membuat plot)
garis Euler dalam sebuah segitiga.


Pertama, kita mendefinisikan titik-titik sudut segitiga tersebut di
Euler. Kita menggunakan definisi yang dapat dilihat dalam ekspresi
simbolik.


\>A::=[-1,-1]; B::=[2,0]; C::=[1,2];


Untuk membuat plot (grafik) objek geometri, kita menyiapkan area plot,
lalu menambahkan titik-titik ke dalamnya. Semua plot objek geometri
ditambahkan ke plot yang sedang aktif saat ini.


\>setPlotRange(3); plotPoint(A,"A"); plotPoint(B,"B"); plotPoint(C,"C");


Kita juga dapat menambahkan sisi-sisi segitiga tersebut.


\>plotSegment(A,B,""); plotSegment(B,C,""); plotSegment(C,A,""):


![images/TugasAplikom7Adi25030630001-053.png](images/TugasAplikom7Adi25030630001-053.png)

Berikut adalah luas segitiga tersebut, dengan menggunakan rumus
determinan. Tentu saja, kita harus mengambil nilai mutlak dari hasil
ini.


\>$areaTriangle(A,B,C)


$$-\frac{7}{2}$$Kita dapat menghitung koefisien dari sisi c.


\>c &= lineThrough(A,B)


    
                                [- 1, 3, - 2]
    

Dan dapatkan pula rumus untuk garis ini.


\>$getLineEquation(c,x,y)


$$3\,y-x=-2$$Untuk bentuk Hesse (Hesse form), kita perlu menentukan sebuah titik
sedemikian rupa sehingga titik tersebut berada di sisi positif dari
bentuk Hesse tersebut. Substitusi (memasukkan) titik tersebut
menghasilkan jarak positif ke garis.


\>$getHesseForm(c,x,y,C), $at(%,[x=C[1],y=C[2]])


$$\frac{7}{\sqrt{10}}$$![images/TugasAplikom7Adi25030630001-057.png](images/TugasAplikom7Adi25030630001-057.png)

Sekarang kita menghitung lingkaran luar ABC.


\>LL &= circleThrough(A,B,C); $getCircleEquation(LL,x,y)


$$\left(y-\frac{5}{14}\right)^2+\left(x-\frac{3}{14}\right)^2=\frac{  325}{98}$$\>O &= getCircleCenter(LL); $O


$$\left[ \frac{3}{14} , \frac{5}{14} \right] $$Buatlah plot lingkaran beserta pusatnya. Cu dan U bersifat simbolik.
Kita mengevaluasi ekspresi-ekspresi ini untuk Euler.


\>plotCircle(LL()); plotPoint(O(),"O"):


![images/TugasAplikom7Adi25030630001-060.png](images/TugasAplikom7Adi25030630001-060.png)

Kita dapat menghitung perpotongan garis-garis tinggi pada segitiga ABC
(titik tinggi atau ortosenter) secara numerik dengan perintah berikut.


\>H &= lineIntersection(perpendicular(A,lineThrough(C,B)),...  
\>     perpendicular(B,lineThrough(A,C))); $H


$$\left[ \frac{11}{7} , \frac{2}{7} \right] $$Sekarang kita dapat menghitung garis Euler dari segitiga tersebut.


\>el &= lineThrough(H,O); $getLineEquation(el,x,y)


$$-\frac{19\,y}{14}-\frac{x}{14}=-\frac{1}{2}$$Tambahkan itu ke dalam plot (grafik) kita.


\>plotPoint(H(),"H"); plotLine(el(),"Garis Euler"):


![images/TugasAplikom7Adi25030630001-063.png](images/TugasAplikom7Adi25030630001-063.png)

Pusat gravitasi (titik berat) seharusnya berada pada garis ini.


\>M &= (A+B+C)/3; $getLineEquation(el,x,y) with [x=M[1],y=M[2]]


$$-\frac{1}{2}=-\frac{1}{2}$$\>plotPoint(M(),"M"): // titik berat


![images/TugasAplikom7Adi25030630001-065.png](images/TugasAplikom7Adi25030630001-065.png)

Teori menyatakan kepada kita bahwa MH = 2 * MO. Kita perlu
menyederhanakannya dengan radcan untuk mencapai hal ini.


\>$distance(M,H)/distance(M,O)|radcan


$$2$$Fungsi-fungsi tersebut mencakup fungsi-fungsi untuk sudut juga.


\>$computeAngle(A,C,B), degprint(%())


$$\arccos \left(\frac{4}{\sqrt{5}\,\sqrt{13}}\right)$$    60°15'18.43''

Persamaan untuk pusat lingkaran dalam tidak begitu bagus.


\>Q &= lineIntersection(angleBisector(A,C,B),angleBisector(C,B,A))|radcan; $Q


$$\left[ \frac{\left(2^{\frac{3}{2}}+1\right)\,\sqrt{5}\,\sqrt{13}-15  \,\sqrt{2}+3}{14} , \frac{\left(\sqrt{2}-3\right)\,\sqrt{5}\,\sqrt{  13}+5\,2^{\frac{3}{2}}+5}{14} \right] $$Mari kita hitung pula ekspresi untuk jari-jari lingkaran dalam.


\>r &= distance(Q,projectToLine(Q,lineThrough(A,B)))|ratsimp; $r


$$\frac{\sqrt{\left(-41\,\sqrt{2}-31\right)\,\sqrt{5}\,\sqrt{13}+115  \,\sqrt{2}+614}}{7\,\sqrt{2}}$$\>LD &=  circleWithCenter(Q,r); // Lingkaran dalam


Mari kita tambahkan ini ke dalam plot.


\>color(5); plotCircle(LD()):


![images/TugasAplikom7Adi25030630001-070.png](images/TugasAplikom7Adi25030630001-070.png)

## Parabola

Selanjutnya akan dicari persamaan tempat kedudukan titik-titik yang berjarak sama ke titik C
dan ke garis AB.


\>p &= getHesseForm(lineThrough(A,B),x,y,C)-distance([x,y],C); $p='0


$$\frac{3\,y-x+2}{\sqrt{10}}-\sqrt{\left(2-y\right)^2+\left(1-x  \right)^2}=0$$Persamaan tersebut dapat digambar menjadi satu dengan gambar sebelumnya.


\>plot2d(p,level=0,add=1,contourcolor=6):


![images/TugasAplikom7Adi25030630001-072.png](images/TugasAplikom7Adi25030630001-072.png)

Ini seharusnya berupa suatu fungsi, tetapi pemecah bawaan Maxima hanya
dapat menemukan solusinya jika kita mengkuadratkan persamaannya.
Akibatnya, kita mendapatkan solusi palsu (extraneous solution).


\>akar &= solve(getHesseForm(lineThrough(A,B),x,y,C)^2-distance([x,y],C)^2,y)


    
            [y = - 3 x - sqrt(70) sqrt(9 - 2 x) + 26, 
                                  y = - 3 x + sqrt(70) sqrt(9 - 2 x) + 26]
    

Solusi pertamanya adalah


$$y=-3\,x-\sqrt{70}\,\sqrt{9-2\,x}+26$$Menambahkan solusi pertama ke plot menunjukkan bahwa itu memang jalur
yang kita cari. Teori menyatakan kepada kita bahwa itu adalah parabola
yang berotasi (diputar).


\>plot2d(&rhs(akar[1]),add=1):


![images/TugasAplikom7Adi25030630001-074.png](images/TugasAplikom7Adi25030630001-074.png)

\>function g(x) &= rhs(akar[1]); $'g(x)= g(x)// fungsi yang mendefinisikan kurva di atas


$$g\left(x\right)=-3\,x-\sqrt{70}\,\sqrt{9-2\,x}+26$$\>T &=[-1, g(-1)]; // ambil sebarang titik pada kurva tersebut

\>dTC &= distance(T,C); $fullratsimp(dTC), $float(%) // jarak T ke C


$$2.135605779339061$$![images/TugasAplikom7Adi25030630001-077.png](images/TugasAplikom7Adi25030630001-077.png)

\>U &= projectToLine(T,lineThrough(A,B)); $U // proyeksi T pada garis AB 


$$\left[ \frac{80-3\,\sqrt{11}\,\sqrt{70}}{10} , \frac{20-\sqrt{11}\,  \sqrt{70}}{10} \right] $$\>dU2AB &= distance(T,U); $fullratsimp(dU2AB), $float(%) // jatak T ke AB


$$2.135605779339061$$![images/TugasAplikom7Adi25030630001-080.png](images/TugasAplikom7Adi25030630001-080.png)

Ternyata jarak T ke C sama dengan jarak T ke AB. Coba Anda pilih titik T yang lain dan
ulangi perhitungan-perhitungan di atas untuk menunjukkan bahwa hasilnya juga sama.


# Contoh 5: Trigonometri Rasional

Hal ini terinspirasi dari sebuah ceramah oleh N.J. Wildberger. Dalam
bukunya "Divine Proportions", Wildberger mengusulkan untuk mengganti
gagasan klasik tentang jarak dan sudut dengan kuadrans dan rentangan.
Menggunakan hal-hal ini, memang dimungkinkan untuk menghindari fungsi
trigonometri dalam banyak contoh, dan untuk tetap berada di ranah
"rasional".


Berikut ini, saya memperkenalkan konsep-konsep tersebut dan
menyelesaikan beberapa masalah. Saya menggunakan komputasi simbolik
Maxima di sini, yang menyembunyikan keunggulan utama dari trigonometri
rasional yaitu bahwa komputasi dapat dilakukan hanya dengan pensil dan
kertas. Anda dipersilakan untuk memeriksa hasil-hasilnya tanpa
komputer.


Intinya adalah bahwa komputasi rasional simbolik sering kali
menghasilkan hasil yang sederhana. Sebaliknya, trigonometri klasik
menghasilkan hasil trigonometri yang rumit, yang hanya menghasilkan
aproksimasi (pendekatan) numerik.


\>load geometry;


Untuk pengantar awal, kita menggunakan segitiga siku-siku dengan
proporsi Mesir yang terkenal yaitu 3, 4, and 5. Perintah-perintah
berikut adalah perintah Euler untuk memetakan geometri bidang yang
terdapat di dalam file Euler "geometry.e".


\>C&:=[0,0]; A&:=[4,0]; B&:=[0,3]; ...  
\>   setPlotRange(-1,5,-1,5); ...  
\>   plotPoint(A,"A"); plotPoint(B,"B"); plotPoint(C,"C"); ...  
\>   plotSegment(B,A,"c"); plotSegment(A,C,"b"); plotSegment(C,B,"a"); ...  
\>   insimg(30);


![images/TugasAplikom7Adi25030630001-081.png](images/TugasAplikom7Adi25030630001-081.png)

Tentu saja,


$$\sin(w_a)=\frac{a}{c},$$di mana wa adalah sudut di titik A. Cara biasa untuk menghitung sudut
ini adalah dengan menggunakan invers dari fungsi sinus. Hasilnya
adalah sudut yang sulit dicerna (tidak praktis), yang hanya dapat
dicetak secara aproksimasi (pendekatan).


\>wa := arcsin(3/5); degprint(wa)


    36°52'11.63''

Trigonometri rasional mencoba untuk menghindari hal ini.


Gagasan pertama dari trigonometri rasional adalah kuadrans, yang
menggantikan jarak. Kenyataannya, kuadrans hanyalah jarak yang
dikuadratkan. Pada bagian berikut, a, b, dan c menyatakan kuadrans
dari sisi-sisi segitiga.


Teorema Pythagoras dengan demikian menjadi sederhana: a + b = c.


\>a &= 3^2; b &= 4^2; c &= 5^2; &a+b=c


    
                                   25 = 25
    

Gagasan kedua dari trigonometri rasional adalah rentangan (spread).
Rentangan mengukur bukaan antara garis-garis. Nilainya adalah 0 jika
garis-garis tersebut sejajar, dan 1 jika garis-garis tersebut tegak
lurus. Rentangan adalah kuadrat dari sinus sudut antara kedua garis
tersebut.


Rentangan dari garis AB dan AC pada gambar di atas didefinisikan
sebagai


$$s_a = \sin(\alpha)^2 = \frac{a}{c},$$dengan a dan c adalah kuadrans dari sebarang segitiga siku-siku dengan
salah satu titik sudutnya berada di A..


\>sa &= a/c; $sa


$$\frac{9}{25}$$Ini lebih mudah dihitung daripada sudut, tentu saja. Tetapi Anda
kehilangan sifat bahwa sudut dapat dijumlahkan dengan mudah.


Tentu saja, kita dapat mengubah nilai aproksimasi kita untuk sudut
$w_a$ menjadi sebuah rentangan (spread), dan mencetaknya sebagai
sebuah pecahan.


\>fracprint(sin(wa)^2)


    9/25

Hukum kosinus pada trigonometri klasik diterjemahkan menjadi 'hukum
silang' (cross law) berikut:


$$(c+b-a)^2 = 4 b c \, (1-s_a)$$Di sini a, b, dan c adalah kuadrans dari sisi-sisi suatu segitiga, dan
sa adalah rentangan (spread) di sudut A. Sisi a adalah sisi yang,
seperti biasa, berada di hadapan sudut A.


Hukum-hukum ini diimplementasikan di dalam berkas geometry.e yang kita
muat ke dalam Euler.


\>$crosslaw(aa,bb,cc,saa)


$$\left({\it cc}+{\it bb}-{\it aa}\right)^2=4\,{\it bb}\,{\it cc}\,  \left(1-{\it saa}\right)$$Dalam kasus kita, kita mendapatkan


\>$crosslaw(a,b,c,sa)


$$1024=1024$$Mari kita gunakan hukum silang (cross law) ini untuk mencari rentangan
(spread) di A. Untuk melakukan ini, kita menyusun hukum silang untuk
kuadrans a, b, dan c, lalu menyelesaikannya terhadap rentangan tak
diketahui sa.


Anda dapat melakukan ini dengan tangan dengan mudah, tetapi saya
menggunakan Maxima. Tentu saja, kita mendapatkan hasil yang sudah kita
miliki sebelumnya.


\>$crosslaw(a,b,c,x), $solve(%,x)


$$\left[ x=\frac{9}{25} \right] $$![images/TugasAplikom7Adi25030630001-089.png](images/TugasAplikom7Adi25030630001-089.png)

Kita sudah mengetahui hal ini. Definisi dari rentangan adalah kasus
khusus dari hukum silang.


Kita juga dapat menyelesaikannya untuk a, b, c secara umum. Hasilnya
adalah sebuah rumus yang menghitung rentangan dari sudut suatu
segitiga jika diberikan kuadrans dari ketiga sisinya.


\>$solve(crosslaw(aa,bb,cc,x),x)


$$\left[ x=\frac{-{\it cc}^2-\left(-2\,{\it bb}-2\,{\it aa}\right)\,  {\it cc}-{\it bb}^2+2\,{\it aa}\,{\it bb}-{\it aa}^2}{4\,{\it bb}\,  {\it cc}} \right] $$Kita dapat membuat sebuah fungsi dari hasil tersebut. Fungsi semacam
itu sudah didefinisikan di dalam berkas geometry.e milik Euler.


\>$spread(a,b,c)


$$\frac{9}{25}$$Sebagai sebuah contoh, kita dapat menggunakannya untuk menghitung
sudut dari sebuah segitiga dengan sisi-sisi


$$a, \quad a, \quad \frac{4a}{7}$$Hasilnya adalah rasional, yang tidak begitu mudah didapatkan jika kita
menggunakan trigonometri klasik.


\>$spread(a,a,4\*a/7)


$$\frac{6}{7}$$Ini adalah sudut dalam derajat.


\>degprint(arcsin(sqrt(6/7)))


    67°47'32.44''

## Another Example

Sekarang, mari kita coba contoh yang lebih tingkat lanjut.


Kita menetapkan tiga titik sudut dari sebuah segitiga sebagai berikut.


\>A&:=[1,2]; B&:=[4,3]; C&:=[0,4]; ...  
\>   setPlotRange(-1,5,1,7); ...  
\>   plotPoint(A,"A"); plotPoint(B,"B"); plotPoint(C,"C"); ...  
\>   plotSegment(B,A,"c"); plotSegment(A,C,"b"); plotSegment(C,B,"a"); ...  
\>   insimg;


![images/TugasAplikom7Adi25030630001-094.png](images/TugasAplikom7Adi25030630001-094.png)

Menggunakan Pythagoras, sangat mudah untuk menghitung jarak antara dua
titik. Saya pertama-tama menggunakan fungsi jarak dari berkas Euler
untuk geometri. Fungsi jarak tersebut menggunakan geometri klasik.


\>$distance(A,B)


$$\sqrt{10}$$Euler juga berisi fungsi-fungsi untuk kuadrans antara dua titik.


Pada contoh berikut, karena c+b tidak sama dengan a, segitiga tersebut
bukanlah segitiga siku-siku.


\>c &= quad(A,B); $c, b &= quad(A,C); $b, a &= quad(B,C); $a,


$$17$$![images/TugasAplikom7Adi25030630001-097.png](images/TugasAplikom7Adi25030630001-097.png)

![images/TugasAplikom7Adi25030630001-098.png](images/TugasAplikom7Adi25030630001-098.png)

Pertama, mari kita hitung sudut tradisional. Fungsi `computeAngle`
menggunakan metode biasa yang didasarkan pada hasil kali titik (*dot
product*) dari dua vektor. Hasilnya adalah beberapa aproksimasi titik
mengambang (*floating point*).


$$A=<1,2>\quad B=<4,3>,\quad C=<0,4>$$$$\mathbf{a}=C-B=<-4,1>,\quad \mathbf{c}=A-B=<-3,-1>,\quad \beta=\angle ABC$$$$\mathbf{a}.\mathbf{c}=|\mathbf{a}|.|\mathbf{c}|\cos \beta$$$$\cos \angle ABC =\cos\beta=\frac{\mathbf{a}.\mathbf{c}}{|\mathbf{a}|.|\mathbf{c}|}=\frac{12-1}{\sqrt{17}\sqrt{10}}=\frac{11}{\sqrt{17}\sqrt{10}}$$\>wb &= computeAngle(A,B,C); $wb, $(wb/pi\*180)()


$$\arccos \left(\frac{11}{\sqrt{10}\,\sqrt{17}}\right)$$    32.4711922908

Dengan menggunakan pensil dan kertas, kita dapat melakukan hal yang
sama dengan hukum silang. Kita memasukkan kuadrans a, b, dan c ke
dalam hukum silang dan menyelesaikannya untuk x.


\>$crosslaw(a,b,c,x), $solve(%,x), //(b+c-a)^=4b.c(1-x)


$$\left[ x=\frac{49}{50} \right] $$![images/TugasAplikom7Adi25030630001-105.png](images/TugasAplikom7Adi25030630001-105.png)

Yaitu, apa yang dilakukan oleh fungsi rentangan (*spread*) yang
didefinisikan dalam "geometry.e".


\>sb &= spread(b,a,c); $sb


$$\frac{49}{170}$$Maxima mendapatkan hasil yang sama menggunakan trigonometri biasa,
jika kita memaksanya. Ia menyelesaikan suku sin(arccos(...)) menjadi
hasil berupa pecahan. Sebagian besar mahasiswa tidak akan mampu
melakukan ini.


\>$sin(computeAngle(A,B,C))^2


$$\frac{49}{170}$$Begitu kita memiliki rentangan di B, kita dapat menghitung tinggi ha
pada sisi a. Ingatlah bahwa


$$s_b=\frac{h_a}{c}$$menurut definisi.


\>ha &= c\*sb; $ha


$$\frac{49}{17}$$Gambar berikut telah dihasilkan dengan program geometri C.a.R., yang
dapat menggambar kuadrans dan rentangan.


image: (20) Rational_Geometry_CaR.png


Berdasarkan definisi, panjang ha adalah akar kuadrat dari kuadransnya.


\>$sqrt(ha)


$$\frac{7}{\sqrt{17}}$$Sekarang kita dapat menghitung luas segitiga tersebut. Jangan lupa,
bahwa kita sedang berurusan dengan kuadrans!


\>$sqrt(ha)\*sqrt(a)/2


$$\frac{7}{2}$$Rumus determinan biasa menghasilkan hasil yang sama.


\>$areaTriangle(B,A,C)


$$\frac{7}{2}$$## The Heron Formula

Sekarang, mari kita selesaikan masalah ini secara umum!


\>&remvalue(a,b,c,sb,ha);


Kita terlebih dahulu menghitung rentangan di B untuk sebuah segitiga
dengan sisi-sisi a, b, dan c. Kemudian kita menghitung kuadrat luasnya
("kuadrea"?), memfaktorkannya dengan Maxima, dan kita mendapatkan
rumus Heron yang terkenal.


Harus diakui, ini cukup sulit untuk dikerjakan dengan pensil dan
kertas.


\>$spread(b^2,c^2,a^2), $factor(%\*c^2\*a^2/4)


$$\frac{\left(-c+b+a\right)\,\left(c-b+a\right)\,\left(c+b-a\right)\,  \left(c+b+a\right)}{16}$$![images/TugasAplikom7Adi25030630001-114.png](images/TugasAplikom7Adi25030630001-114.png)

## The Triple Spread Rule

Kelemahan dari rentangan adalah bahwa nilainya tidak lagi dapat
dijumlahkan secara sederhana seperti halnya sudut.


Meskipun demikian, ketiga rentangan dari sebuah segitiga memenuhi
aturan "rentangan tripel" (*triple spread rule*) berikut.


\>&remvalue(sa,sb,sc); $triplespread(sa,sb,sc)


$$\left({\it sc}+{\it sb}+{\it sa}\right)^2=2\,\left({\it sc}^2+  {\it sb}^2+{\it sa}^2\right)+4\,{\it sa}\,{\it sb}\,{\it sc}$$Aturan ini berlaku untuk tiga sudut mana pun yang jumlahnya 180°.


$$\alpha+\beta+\gamma=\pi$$Karena rentangan-rentangan dari


$$\alpha, \pi-\alpha$$sama, aturan rentangan tripel juga berlaku, jika


$$\alpha+\beta=\gamma$$Karena rentangan dari sudut negatif adalah sama, aturan rentangan
tripel juga berlaku, jika


$$\alpha+\beta+\gamma=0$$Sebagai contoh, kita dapat menghitung rentangan dari sudut 60°.
Nilainya adalah 3/4.Namun, persamaan tersebut memiliki solusi kedua,
di mana semua rentangan bernilai 0.


\>$solve(triplespread(x,x,x),x)


$$\left[ x=\frac{3}{4} , x=0 \right] $$Rentangan dari 90° jelas adalah 1. Jika dua sudut berjumlah 90°,
rentangan keduanya memenuhi persamaan rentangan tripel dengan a, b, 1.
Melalui perhitungan berikut, kita mendapatkan a+b=1.


\>$triplespread(x,y,1), $solve(%,x)


$$\left[ x=1-y \right] $$![images/TugasAplikom7Adi25030630001-122.png](images/TugasAplikom7Adi25030630001-122.png)

Karena rentangan dari 180°-t sama dengan rentangan dari t, rumus
rentangan tripel juga berlaku jika satu sudut merupakan jumlah atau
selisih dari dua sudut lainnya.


Dengan demikian, kita dapat mencari rentangan dari sudut rangkap.
Perhatikan bahwa ada dua solusi lagi. Kita jadikan ini sebagai sebuah
fungsi.


\>$solve(triplespread(a,a,x),x), function doublespread(a) &= factor(rhs(%[1]))


$$\left[ x=4\,a-4\,a^2 , x=0 \right] $$    
                                - 4 (a - 1) a
    

## Angle Bisectors

Ini adalah situasi yang telah kita ketahui.


\>C&:=[0,0]; A&:=[4,0]; B&:=[0,3]; ...  
\>   setPlotRange(-1,5,-1,5); ...  
\>   plotPoint(A,"A"); plotPoint(B,"B"); plotPoint(C,"C"); ...  
\>   plotSegment(B,A,"c"); plotSegment(A,C,"b"); plotSegment(C,B,"a"); ...  
\>   insimg;


![images/TugasAplikom7Adi25030630001-124.png](images/TugasAplikom7Adi25030630001-124.png)

Mari kita hitung panjang garis bagi sudut di A. Namun, kita ingin
menyelesaikannya untuk a, b, c secara umum.


\>&remvalue(a,b,c);


Jadi, kita terlebih dahulu menghitung rentangan dari sudut yang
dibelah dua di A, dengan menggunakan rumus rentangan tripel.


Masalah dari rumus ini muncul kembali. Rumus ini memiliki dua solusi.
Kita harus memilih solusi yang benar. Solusi lainnya mengacu pada
sudut yang dibelah dua 180°-wa.


\>$triplespread(x,x,a/(a+b)), $solve(%,x), sa2 &= rhs(%[1]); $sa2


$$\frac{-\sqrt{b}\,\sqrt{b+a}+b+a}{2\,b+2\,a}$$![images/TugasAplikom7Adi25030630001-126.png](images/TugasAplikom7Adi25030630001-126.png)

![images/TugasAplikom7Adi25030630001-127.png](images/TugasAplikom7Adi25030630001-127.png)

Mari kita periksa persegi panjang Mesir.


\>$sa2 with [a=3^2,b=4^2]


$$\frac{1}{10}$$Kita dapat mencetak sudut di Euler, setelah mentransfer rentangan ke
radian.


\>wa2 := arcsin(sqrt(1/10)); degprint(wa2)


    18°26'5.82''

Titik P adalah perpotongan garis bagi sudut dengan sumbu-y.


\>P := [0,tan(wa2)\*4]


    [0,  1.33333]

\>plotPoint(P,"P"); plotSegment(A,P):


![images/TugasAplikom7Adi25030630001-129.png](images/TugasAplikom7Adi25030630001-129.png)

Mari kita periksa sudut-sudut dalam contoh khusus kita.


\>computeAngle(C,A,P), computeAngle(P,A,B)


    0.321750554397
    0.321750554397

Sekarang kita menghitung panjang garis bagi AP.


Kita menggunakan aturan sinus pada segitiga APC. Aturan ini menyatakan
bahwa


$$\frac{BC}{\sin(w_a)} = \frac{AC}{\sin(w_b)} = \frac{AB}{\sin(w_c)}$$berlaku pada sebarang segitiga. Jika dikuadratkan, hal ini
diterjemahkan menjadi apa yang disebut sebagai 'hukum rentangan'.


$$\frac{a}{s_a} = \frac{b}{s_b} = \frac{c}{s_b}$$dengan a, b, c menyatakan kuadrans.


Karena rentangan CPA adalah 1-sa2, dari situ kita peroleh
ba/1=b/(1-sa2) dan dapat menghitung ba (kuadrans dari garis bagi
sudut).


\>&factor(ratsimp(b/(1-sa2))); bisa &= %; $bisa


$$\frac{2\,b\,\left(b+a\right)}{\sqrt{b}\,\sqrt{b+a}+b+a}$$Mari kita periksa rumus ini untuk nilai-nilai Mesir kita.


\>sqrt(mxmeval("at(bisa,[a=3^2,b=4^2])")), distance(A,P)


    4.21637021356
    4.21637021356

Kita juga dapat menghitung P menggunakan rumus rentangan.


\>py&=factor(ratsimp(sa2\*bisa)); $py


$$-\frac{b\,\left(\sqrt{b}\,\sqrt{b+a}-b-a\right)}{\sqrt{b}\,\sqrt{b+  a}+b+a}$$Nilai tersebut sama dengan yang kita peroleh menggunakan rumus-rumus
trigonometri.


\>sqrt(mxmeval("at(py,[a=3^2,b=4^2])"))


    1.33333333333

## The Chord Angle

Lihatlah situasi berikut.


\>setPlotRange(1.2); ...  
\>   color(1); plotCircle(circleWithCenter([0,0],1)); ...  
\>   A:=[cos(1),sin(1)]; B:=[cos(2),sin(2)]; C:=[cos(6),sin(6)]; ...  
\>   plotPoint(A,"A"); plotPoint(B,"B"); plotPoint(C,"C"); ...  
\>   color(3); plotSegment(A,B,"c"); plotSegment(A,C,"b"); plotSegment(C,B,"a"); ...  
\>   color(1); O:=[0,0];  plotPoint(O,"0"); ...  
\>   plotSegment(A,O); plotSegment(B,O); plotSegment(C,O,"r"); ...  
\>   insimg;


![images/TugasAplikom7Adi25030630001-134.png](images/TugasAplikom7Adi25030630001-134.png)

Kita dapat menggunakan Maxima untuk menyelesaikan rumus rentangan
tripel untuk sudut-sudut di pusat O terhadap r. Dengan demikian, kita
memperoleh rumus untuk kuadrans jari-jari lingkaran luar (pericircle)
dalam bentuk kuadrans dari sisi-sisinya.


Kali ini, Maxima menghasilkan beberapa akar kompleks, yang kita
abaikan.


\>&remvalue(a,b,c,r); // hapus nilai-nilai sebelumnya untuk perhitungan baru

\>rabc &= rhs(solve(triplespread(spread(b,r,r),spread(a,r,r),spread(c,r,r)),r)[4]); $rabc


$$-\frac{a\,b\,c}{c^2-2\,b\,c+a\,\left(-2\,c-2\,b\right)+b^2+a^2}$$Kita dapat menjadikannya fungsi Euler.


\>function periradius(a,b,c) &= rabc;


Mari kita periksa hasilnya untuk titik-titik kita A, B, C.


\>a:=quadrance(B,C); b:=quadrance(A,C); c:=quadrance(A,B);


Jari-jarinya memang 1.


\>periradius(a,b,c)


    1

Faktanya, rentangan CBA hanya bergantung pada b dan c. Ini adalah
teorema sudut tali busur.


\>$spread(b,a,c)\*rabc | ratsimp


$$\frac{b}{4}$$Faktanya, rentangan adalah b/(4r), dan kita melihat bahwa sudut tali
busur dari tali busur b adalah setengah dari sudut pusat.


\>$doublespread(b/(4\*r))-spread(b,r,r) | ratsimp


$$0$$# Contoh 6: Jarak Minimal pada Bidang

## Preliminary remark

Fungsi yang, untuk suatu titik M pada bidang, memetakan jarak AM
antara titik tetap A dan M, memiliki kurva ketinggian (level lines)
yang cukup sederhana: lingkaran-lingkaran yang berpusat di A.


\>&remvalue();

\>A=[-1,-1];

\>function d1(x,y):=sqrt((x-A[1])^2+(y-A[2])^2)

\>fcontour("d1",xmin=-2,xmax=0,ymin=-2,ymax=0,hue=1, ...  
\>   title="If you see ellipses, please set your window square"):


![images/TugasAplikom7Adi25030630001-138.png](images/TugasAplikom7Adi25030630001-138.png)

dan grafiknya juga cukup sederhana: bagian atas dari sebuah kerucut:


\>plot3d("d1",xmin=-2,xmax=0,ymin=-2,ymax=0):


![images/TugasAplikom7Adi25030630001-139.png](images/TugasAplikom7Adi25030630001-139.png)

Tentu saja minimum 0 dicapai di titik $A$.


## Two points

Sekarang kita melihat fungsi $MA+MB$ dengan A dan B adalah dua titik
(tetap). Merupakan fakta yang sudah umum bahwa kurva ketinggiannya
adalah elips, dengan titik-titik fokusnya adalah A dan B; kecuali
untuk nilai minimum AB yang bernilai konstan pada ruas garis [AB]:


\>B=[1,-1];

\>function d2(x,y):=d1(x,y)+sqrt((x-B[1])^2+(y-B[2])^2)

\>fcontour("d2",xmin=-2,xmax=2,ymin=-3,ymax=1,hue=1):


![images/TugasAplikom7Adi25030630001-140.png](images/TugasAplikom7Adi25030630001-140.png)

Grafiknya lebih menarik:


\>plot3d("d2",xmin=-2,xmax=2,ymin=-3,ymax=1):


![images/TugasAplikom7Adi25030630001-141.png](images/TugasAplikom7Adi25030630001-141.png)

Pembatasan pada garis (AB) lebih terkenal:


\>plot2d("abs(x+1)+abs(x-1)",xmin=-3,xmax=3):


![images/TugasAplikom7Adi25030630001-142.png](images/TugasAplikom7Adi25030630001-142.png)

## Three points

Sekarang keadaannya menjadi tidak begitu sederhana: Sedikit kurang
terkenal bahwa MA+MB+MC mencapai nilai minimumnya di satu titik pada
bidang, namun untuk menentukannya tidaklah sesederhana itu:


1) Jika salah satu sudut dari segitiga ABC lebih besar dari 120°
(misalnya di A), maka nilai minimum dicapai tepat di titik tersebut
(yaitu AB+AC).


Contoh:


\>C=[-4,1];

\>function d3(x,y):=d2(x,y)+sqrt((x-C[1])^2+(y-C[2])^2)

\>plot3d("d3",xmin=-5,xmax=3,ymin=-4,ymax=4);

\>insimg;


![images/TugasAplikom7Adi25030630001-143.png](images/TugasAplikom7Adi25030630001-143.png)

\>fcontour("d3",xmin=-4,xmax=1,ymin=-2,ymax=2,hue=1,title="The minimum is on A");

\>P=(A\_B\_C\_A)'; plot2d(P[1],P[2],add=1,color=12);

\>insimg;


![images/TugasAplikom7Adi25030630001-144.png](images/TugasAplikom7Adi25030630001-144.png)

2) Tetapi jika semua sudut dari segitiga ABC kurang dari 120°, nilai
minimumnya berada pada suatu titik F di bagian interior segitiga, yang
merupakan satu-satunya titik yang melihat sisi-sisi ABC dengan sudut
yang sama (masing-masing 120°):


\>C=[-0.5,1];

\>plot3d("d3",xmin=-2,xmax=2,ymin=-2,ymax=2):


![images/TugasAplikom7Adi25030630001-145.png](images/TugasAplikom7Adi25030630001-145.png)

\>fcontour("d3",xmin=-2,xmax=2,ymin=-2,ymax=2,hue=1,title="The Fermat point");

\>P=(A\_B\_C\_A)'; plot2d(P[1],P[2],add=1,color=12);

\>insimg;


![images/TugasAplikom7Adi25030630001-146.png](images/TugasAplikom7Adi25030630001-146.png)

Merupakan kegiatan yang menarik untuk merealisasikan gambar di atas
dengan perangkat lunak geometri; misalnya, saya tahu perangkat lunak
yang ditulis dalam bahasa Java yang memiliki perintah 


Semua hal di atas telah ditemukan oleh seorang hakim asal Prancis
bernama Pierre de Fermat; ia menulis surat kepada para peminat amatir
lainnya seperti pastur Marin Mersenne dan Blaise Pascal yang bekerja
di bidang pajak pendapatan. Oleh karena itu, satu-satunya titik F
sedemikian rupa sehingga FA+FB+FC bernilai minimum, disebut sebagai
titik Fermat dari segitiga tersebut. Namun, tampaknya beberapa tahun
sebelumnya, matematikawan asal Italia, Torricelli, telah menemukan
titik ini terlebih dahulu sebelum Fermat! Bagaimanapun juga, sudah
menjadi tradisi untuk melambangkan titik ini dengan huruf F...


## Four points

Langkah berikutnya adalah menambahkan titik ke-4 D dan mencoba
meminimalkan MA+MB+MC+MD; katakanlah Anda adalah seorang operator
televisi kabel dan ingin mencari di ladang mana Anda harus meletakkan
antena Anda sehingga Anda dapat melayani empat desa dan menggunakan
panjang kabel sesedikit mungkin!


\>D=[1,1];

\>function d4(x,y):=d3(x,y)+sqrt((x-D[1])^2+(y-D[2])^2)

\>plot3d("d4",xmin=-1.5,xmax=1.5,ymin=-1.5,ymax=1.5):


![images/TugasAplikom7Adi25030630001-147.png](images/TugasAplikom7Adi25030630001-147.png)

\>fcontour("d4",xmin=-1.5,xmax=1.5,ymin=-1.5,ymax=1.5,hue=1);

\>P=(A\_B\_C\_D)'; plot2d(P[1],P[2],points=1,add=1,color=12);

\>insimg;


![images/TugasAplikom7Adi25030630001-148.png](images/TugasAplikom7Adi25030630001-148.png)

Masih terdapat nilai minimum dan nilai tersebut tidak dicapai pada
titik-titik sudut A, B, C maupun D:


\>function f(x):=d4(x[1],x[2])

\>neldermin("f",[0.2,0.2])


    [0.142858,  0.142857]

Tampaknya dalam kasus ini, koordinat titik optimal tersebut berupa
bilangan rasional atau mendekati rasional...


Sekarang jika $ABCD$ adalah sebuah persegi, kita memperkirakan bahwa
titik optimalnya adalah pusat dari ABCD:


\>C=[-1,1];

\>plot3d("d4",xmin=-1,xmax=1,ymin=-1,ymax=1):


![images/TugasAplikom7Adi25030630001-149.png](images/TugasAplikom7Adi25030630001-149.png)

\>fcontour("d4",xmin=-1.5,xmax=1.5,ymin=-1.5,ymax=1.5,hue=1);

\>P=(A\_B\_C\_D)'; plot2d(P[1],P[2],add=1,color=12,points=1);

\>insimg;


![images/TugasAplikom7Adi25030630001-150.png](images/TugasAplikom7Adi25030630001-150.png)

# Contoh 7: Bola Dandelin dengan Povray

Anda dapat menjalankan demonstrasi ini, jika Anda telah memasang
Povray, dan pvengine.exe berada di jalur program.


Pertama, kita menghitung jari-jari bola-bola tersebut.


Jika Anda melihat gambar di bawah ini, Anda akan melihat bahwa kita
memerlukan dua lingkaran yang menyinggung dua garis yang membentuk
kerucut, dan satu garis yang membentuk bidang yang memotong kerucut.


Kita menggunakan berkas geometry.e milik Euler untuk keperluan ini.


\>load geometry;


Pertama, dua garis yang membentuk kerucut.


\>g1 &= lineThrough([0,0],[1,a])


    
                                 [- a, 1, 0]
    

\>g2 &= lineThrough([0,0],[-1,a])


    
                                [- a, - 1, 0]
    

Kemudian garis ketiga.


\>g &= lineThrough([-1,0],[1,1])


    
                                 [- 1, 2, 1]
    

Kita memetakan semuanya sejauh ini.


\>setPlotRange(-1,1,0,2);

\>color(black); plotLine(g(),"")

\>a:=2; color(blue); plotLine(g1(),""), plotLine(g2(),""):


![images/TugasAplikom7Adi25030630001-151.png](images/TugasAplikom7Adi25030630001-151.png)

Sekarang kita mengambil titik umum pada sumbu-y.


\>P &= [0,u]


    
                                    [0, u]
    

Hitung jarak ke g1.


\>d1 &= distance(P,projectToLine(P,g1)); $d1


$$\sqrt{\left(\frac{a^2\,u}{a^2+1}-u\right)^2+\frac{a^2\,u^2}{\left(a  ^2+1\right)^2}}$$Hitung jarak ke g.


\>d &= distance(P,projectToLine(P,g)); $d


$$\sqrt{\left(\frac{u+2}{5}-u\right)^2+\frac{\left(2\,u-1\right)^2}{  25}}$$Dan tentukan pusat dari kedua lingkaran tersebut, dengan
jarak-jaraknya bernilai sama.


\>sol &= solve(d1^2=d^2,u); $sol


$$\left[ u=\frac{-\sqrt{5}\,\sqrt{a^2+1}+2\,a^2+2}{4\,a^2-1} , u=  \frac{\sqrt{5}\,\sqrt{a^2+1}+2\,a^2+2}{4\,a^2-1} \right] $$Terdapat dua solusi.


Kita mengevaluasi solusi simbolik tersebut, dan mencari kedua pusat
serta kedua jarak tersebut.


\>u := sol()


    [0.333333,  1]

\>dd := d()


    [0.149071,  0.447214]

Petakan lingkaran-lingkaran tersebut ke dalam gambar.


\>color(red);

\>plotCircle(circleWithCenter([0,u[1]],dd[1]),"");

\>plotCircle(circleWithCenter([0,u[2]],dd[2]),"");

\>insimg;


![images/TugasAplikom7Adi25030630001-155.png](images/TugasAplikom7Adi25030630001-155.png)

## Plot with Povray

Selanjutnya kita memetakan semuanya dengan Povray. Perhatikan bahwa
Anda dapat mengubah perintah apa pun dalam urutan perintah Povray
berikut, dan menjalankan ulang semua perintah dengan Shift-Return.


Pertama, kita memuat fungsi-fungsi povray.


\>load povray;

\>defaultpovray="C:\\Program Files\\POV-Ray\\v3.7\\bin\\pvengine.exe"


    C:\Program Files\POV-Ray\v3.7\bin\pvengine.exe

Kita mengatur adegan secara tepat.


\>povstart(zoom=11,center=[0,0,0.5],height=10°,angle=140°);


Selanjutnya kita menulis kedua bola tersebut ke dalam berkas Povray.


\>writeln(povsphere([0,0,u[1]],dd[1],povlook(red)));

\>writeln(povsphere([0,0,u[2]],dd[2],povlook(red)));


Dan kerucutnya, buat transparan.


\>writeln(povcone([0,0,0],0,[0,0,a],1,povlook(lightgray,1)));


Kita menghasilkan sebuah bidang yang dibatasi pada kerucut.


\>gp=g();

\>pc=povcone([0,0,0],0,[0,0,a],1,"");

\>vp=[gp[1],0,gp[2]]; dp=gp[3];

\>writeln(povplane(vp,dp,povlook(blue,0.5),pc));


Sekarang kita menghasilkan dua titik pada lingkaran-lingkaran
tersebut, tempat bola-bola tersebut menyinggung kerucut.


\>function turnz(v) := return [-v[2],v[1],v[3]]

\>P1=projectToLine([0,u[1]],g1()); P1=turnz([P1[1],0,P1[2]]);

\>writeln(povpoint(P1,povlook(yellow)));

\>P2=projectToLine([0,u[2]],g1()); P2=turnz([P2[1],0,P2[2]]);

\>writeln(povpoint(P2,povlook(yellow)));


Kemudian kita menghasilkan dua titik tempat bola-bola tersebut
menyinggung bidang. Titik-titik ini adalah fokus dari elips.


\>P3=projectToLine([0,u[1]],g()); P3=[P3[1],0,P3[2]];

\>writeln(povpoint(P3,povlook(yellow)));

\>P4=projectToLine([0,u[2]],g()); P4=[P4[1],0,P4[2]];

\>writeln(povpoint(P4,povlook(yellow)));


Selanjutnya kita menghitung perpotongan P1P2 dengan bidang.


\>t1=scalp(vp,P1)-dp; t2=scalp(vp,P2)-dp; P5=P1+t1/(t1-t2)\*(P2-P1);

\>writeln(povpoint(P5,povlook(yellow)));


Kita menghubungkan titik-titik tersebut dengan ruas garis.


\>writeln(povsegment(P1,P2,povlook(yellow)));

\>writeln(povsegment(P5,P3,povlook(yellow)));

\>writeln(povsegment(P5,P4,povlook(yellow)));


Sekarang kita menghasilkan sebuah pita abu-abu, tempat bola-bola
tersebut menyinggung kerucut.


\>pcw=povcone([0,0,0],0,[0,0,a],1.01);

\>pc1=povcylinder([0,0,P1[3]-defaultpointsize/2],[0,0,P1[3]+defaultpointsize/2],1);

\>writeln(povintersection([pcw,pc1],povlook(gray)));

\>pc2=povcylinder([0,0,P2[3]-defaultpointsize/2],[0,0,P2[3]+defaultpointsize/2],1);

\>writeln(povintersection([pcw,pc2],povlook(gray)));


Jalankan program Povray.


\>povend();


![images/TugasAplikom7Adi25030630001-156.png](images/TugasAplikom7Adi25030630001-156.png)

Untuk mendapatkan Anaglif dari ini, kita perlu memasukkan semuanya ke
dalam fungsi adegan. Fungsi ini akan digunakan dua kali nanti.


\>function scene () ...


    global a,u,dd,g,g1,defaultpointsize;
    writeln(povsphere([0,0,u[1]],dd[1],povlook(red)));
    writeln(povsphere([0,0,u[2]],dd[2],povlook(red)));
    writeln(povcone([0,0,0],0,[0,0,a],1,povlook(lightgray,1)));
    gp=g();
    pc=povcone([0,0,0],0,[0,0,a],1,"");
    vp=[gp[1],0,gp[2]]; dp=gp[3];
    writeln(povplane(vp,dp,povlook(blue,0.5),pc));
    P1=projectToLine([0,u[1]],g1()); P1=turnz([P1[1],0,P1[2]]);
    writeln(povpoint(P1,povlook(yellow)));
    P2=projectToLine([0,u[2]],g1()); P2=turnz([P2[1],0,P2[2]]);
    writeln(povpoint(P2,povlook(yellow)));
    P3=projectToLine([0,u[1]],g()); P3=[P3[1],0,P3[2]];
    writeln(povpoint(P3,povlook(yellow)));
    P4=projectToLine([0,u[2]],g()); P4=[P4[1],0,P4[2]];
    writeln(povpoint(P4,povlook(yellow)));
    t1=scalp(vp,P1)-dp; t2=scalp(vp,P2)-dp; P5=P1+t1/(t1-t2)*(P2-P1);
    writeln(povpoint(P5,povlook(yellow)));
    writeln(povsegment(P1,P2,povlook(yellow)));
    writeln(povsegment(P5,P3,povlook(yellow)));
    writeln(povsegment(P5,P4,povlook(yellow)));
    pcw=povcone([0,0,0],0,[0,0,a],1.01);
    pc1=povcylinder([0,0,P1[3]-defaultpointsize/2],[0,0,P1[3]+defaultpointsize/2],1);
    writeln(povintersection([pcw,pc1],povlook(gray)));
    pc2=povcylinder([0,0,P2[3]-defaultpointsize/2],[0,0,P2[3]+defaultpointsize/2],1);
    writeln(povintersection([pcw,pc2],povlook(gray)));
    endfunction
</pre>
Anda memerlukan kacamata merah/cyan untuk menikmati efek berikut.


\>povanaglyph("scene",zoom=11,center=[0,0,0.5],height=10°,angle=140°);


![images/TugasAplikom7Adi25030630001-157.png](images/TugasAplikom7Adi25030630001-157.png)

# Contoh 8: Geometri Bumi

Dalam buku catatan ini, kita ingin melakukan beberapa perhitungan
bola. Fungsi-fungsi tersebut terdapat dalam berkas "spherical.e" di
dalam folder contoh. Kita perlu memuat berkas tersebut terlebih
dahulu.


\>load "spherical.e";


Untuk memasukkan posisi geografis, kita menggunakan vektor dengan dua
koordinat dalam radian (utara dan timur, nilai negatif untuk selatan
dan barat). Berikut adalah koordinat untuk Kampus FMIPA UNY.


\>FMIPA=[rad(-7,-46.467),rad(110,23.05)]


    [-0.13569,  1.92657]

Anda dapat mencetak posisi ini dengan sposprint (cetak posisi bola).


\>sposprint(FMIPA) // posisi garis lintang dan garis bujur FMIPA UNY


    S 7°46.467' E 110°23.050'

Mari kita tambahkan dua kota lagi, Solo dan Semarang.


\>Solo=[rad(-7,-34.333),rad(110,49.683)]; Semarang=[rad(-6,-59.05),rad(110,24.533)];

\>sposprint(Solo), sposprint(Semarang),


    S 7°34.333' E 110°49.683'
    S 6°59.050' E 110°24.533'

Pertama, kita menghitung vektor dari satu titik ke titik lainnya pada
bola ideal. Vektor ini berupa [arah, jarak] dalam radian. Untuk
menghitung jarak di bumi, kita mengalikannya dengan jari-jari bumi
pada lintang 7°.


\>br=svector(FMIPA,Solo); degprint(br[1]), br[2]\*rearth(7°)-\>km // perkiraan jarak FMIPA-Solo


    65°20'26.60''
    53.8945384608

Ini adalah pendekatan yang bagus. Rutinitas berikut menggunakan
pendekatan yang bahkan lebih baik. Pada jarak yang begitu pendek,
hasilnya hampir sama.


\> esdist(FMIPA,Semarang)-\>km // perkiraan jarak FMIPA-Semarang


    88.0114026318

Ada sebuah fungsi untuk arah, yang memperhitungkan bentuk eliptis
bumi. Sekali lagi, kita mencetak dengan cara yang lebih canggih.


\>sdegprint(esdir(FMIPA,Solo))


         65.34°

Sudut suatu segitiga melebihi 180° pada bola.


\>asum=sangle(Solo,FMIPA,Semarang)+sangle(FMIPA,Solo,Semarang)+sangle(FMIPA,Semarang,Solo); degprint(asum)


    180°0'10.77''

Ini dapat digunakan untuk menghitung luas segitiga. Catatan: Untuk
segitiga kecil, ini tidak akurat karena adanya galat pengurangan dalam
asum-pi.


\>(asum-pi)\*rearth(48°)^2-\>km^2 // perkiraan luas segitiga FMIPA-Solo-Semarang


    2116.02948749

Ada sebuah fungsi untuk ini, yang menggunakan lintang rata-rata
segitiga untuk menghitung jari-jari bumi, dan menangani galat
pembulatan untuk segitiga yang sangat kecil.


\>esarea(Solo,FMIPA,Semarang)-\>km^2, //perkiraan yang sama dengan fungsi esarea()


    2123.64310526

Kita juga dapat menambahkan vektor ke posisi. Sebuah vektor berisi
arah dan jarak, keduanya dalam radian. Untuk mendapatkan vektor, kita
menggunakan svector. Untuk menambahkan vektor ke suatu posisi, kita
menggunakan saddvector.


\>v=svector(FMIPA,Solo); sposprint(saddvector(FMIPA,v)), sposprint(Solo),


    S 7°34.333' E 110°49.683'
    S 7°34.333' E 110°49.683'

Fungsi-fungsi ini mengasumsikan bola ideal. Hal yang sama berlaku pada
bumi.


\>sposprint(esadd(FMIPA,esdir(FMIPA,Solo),esdist(FMIPA,Solo))), sposprint(Solo),


    S 7°34.333' E 110°49.683'
    S 7°34.333' E 110°49.683'

Mari kita beralih ke contoh yang lebih besar, Tugu Jogja dan Monas
Jakarta (menggunakan Google Earth untuk mencari koordinatnya).


\>Tugu=[-7.7833°,110.3661°]; Monas=[-6.175°,106.811944°];

\>sposprint(Tugu), sposprint(Monas)


    S 7°46.998' E 110°21.966'
    S 6°10.500' E 106°48.717'

Menurut Google Earth, jaraknya adalah 429.66 km. Kita mendapatkan
pendekatan yang bagus.


\>esdist(Tugu,Monas)-\>km // perkiraan jarak Tugu Jogja - Monas Jakarta


    431.565659488

Arahnya sama dengan yang dihitung di Google Earth.


\>degprint(esdir(Tugu,Monas))


    294°17'2.85''

Namun, kita tidak lagi mendapatkan posisi target yang persis, jika
kita menambahkan arah dan jarak ke posisi awal. Hal ini terjadi karena
kita tidak menghitung fungsi invers secara tepat, melainkan mengambil
perkiraan jari-jari bumi di sepanjang jalur tersebut.


\>sposprint(esadd(Tugu,esdir(Tugu,Monas),esdist(Tugu,Monas)))


    S 6°10.500' E 106°48.717'

Namun, galatnya tidak besar.


\>sposprint(Monas),


    S 6°10.500' E 106°48.717'

Tentu saja, kita tidak dapat berlayar dengan arah yang sama dari satu
destinasi ke destinasi lainnya, jika kita ingin mengambil jalur
terpendek. Bayangkan, Anda terbang ke arah Timur Laut (NE) mulai dari
titik mana pun di bumi. Maka Anda akan berputar spiral menuju kutub
utara. Lingkaran besar tidak mengikuti arah yang konstan!


Perhitungan berikut menunjukkan bahwa kita melenceng jauh dari
destinasi yang benar, jika kita menggunakan arah yang sama selama
perjalanan kita.


\>dist=esdist(Tugu,Monas); hd=esdir(Tugu,Monas);


Sekarang kita menambahkan 10 kali sepersepuluh dari jarak, menggunakan
arah ke Monas, yang kita peroleh di Tugu.


\>p=Tugu; loop 1 to 10; p=esadd(p,hd,dist/10); end;


Hasilnya jauh meleset.


\>sposprint(p), skmprint(esdist(p,Monas))


    S 6°11.250' E 106°48.372'
         1.529km

Sebagai contoh lain, mari kita ambil dua titik di bumi pada lintang
yang sama.


\>P1=[30°,10°]; P2=[30°,50°];


Jalur terpendek dari P1 ke P2 bukanlah lingkaran lintang 30°,
melainkan sebuah jalur yang lebih pendek yang dimulai 10° lebih ke
utara pada P1.


\>sdegprint(esdir(P1,P2))


         79.69°

Namun, jika kita mengikuti pembacaan kompas ini, kita akan berputar
spiral menuju kutub utara! Jadi kita harus menyesuaikan arah kita di
sepanjang jalan. Untuk keperluan kasar, kita menyesuaikannya pada 1/10
dari total jarak.


\>p=P1;  dist=esdist(P1,P2); ...  
\>     loop 1 to 10; dir=esdir(p,P2); sdegprint(dir), p=esadd(p,dir,dist/10); end;


         79.69°
         81.67°
         83.71°
         85.78°
         87.89°
         90.00°
         92.12°
         94.22°
         96.29°
         98.33°

Jaraknya tidak tepat, karena kita akan menambahkan sedikit galat, jika
kita mengikuti arah yang sama terlalu lama.


\>skmprint(esdist(p,P2))


         0.203km

Kita mendapatkan pendekatan yang bagus, jika kita menyesuaikan arah
kita setelah setiap 1/100 dari total jarak dari Tugu ke Monas.


\>p=Tugu; dist=esdist(Tugu,Monas); ...  
\>     loop 1 to 100; p=esadd(p,esdir(p,Monas),dist/100); end;

\>skmprint(esdist(p,Monas))


         0.000km

Untuk keperluan navigasi, kita bisa mendapatkan serangkaian posisi GPS
di sepanjang lingkaran besar ke Monas dengan fungsi navigate.


\>load spherical; v=navigate(Tugu,Monas,10); ...  
\>     loop 1 to rows(v); sposprint(v[#]), end;


    S 7°46.998' E 110°21.966'
    S 7°37.422' E 110°0.573'
    S 7°27.829' E 109°39.196'
    S 7°18.219' E 109°17.834'
    S 7°8.592' E 108°56.488'
    S 6°58.948' E 108°35.157'
    S 6°49.289' E 108°13.841'
    S 6°39.614' E 107°52.539'
    S 6°29.924' E 107°31.251'
    S 6°20.219' E 107°9.977'
    S 6°10.500' E 106°48.717'

Kita menulis sebuah fungsi, yang memetakan (menggambar) bumi, kedua
posisi, dan posisi-posisi di antaranya.


\>function testplot ...


    useglobal;
    plotearth;
    plotpos(Tugu,"Tugu Jogja"); plotpos(Monas,"Tugu Monas");
    plotposline(v);
    endfunction
</pre>
Sekarang plot semuanya.


\>plot3d("testplot",angle=25, height=6,\>own,\>user,zoom=4):


![images/TugasAplikom7Adi25030630001-158.png](images/TugasAplikom7Adi25030630001-158.png)

Atau gunakan plot3d untuk mendapatkan tampilan anaglif darinya. Ini
terlihat sangat bagus dengan kacamata merah/sian.


\>plot3d("testplot",angle=25,height=6,distance=5,own=1,anaglyph=1,zoom=4):


![images/TugasAplikom7Adi25030630001-159.png](images/TugasAplikom7Adi25030630001-159.png)

# Latihan

1. Gambarlah segi-n beraturan jika diketahui titik pusat O, n, dan
jarak titik pusat ke titik-titik sudut segi-n tersebut (jari-jari
lingkaran luar segi-n), r.


Petunjuk:


* 
Besar sudut pusat yang menghadap masing-masing sisi segi-n adalah
* (360/n).

* 
Titik-titik sudut segi-n merupakan perpotongan lingkaran luar segi-n
* dan garis-garis yang melalui pusat dan saling membentuk sudut sebesar
* kelipatan (360/n).

* 
Untuk n ganjil, pilih salah satu titik sudut adalah di atas.

* 
Untuk n genap, pilih 2 titik di kanan dan kiri lurus dengan titik
* pusat.

* 
Anda dapat menggambar segi-3, 4, 5, 6, 7, dst beraturan.


Penyelesaian:


Fungsi untuk menggambar segi-n beraturan


\>load geometry


    Numerical and symbolic geometry.

\>load "C:\\Users\\ab368\\Euler\\EulerTemp.e"

\>gambarsegin([0, 0], 3, 5)

\>gambarsegin([0, 0], 4, 5)

\>gambarsegin([0, 0], 5, 5)

\>gambarsegin([0, 0], 6, 5)     


<pre class="udf">    
</pre>
\>    


2. Gambarlah suatu parabola yang melalui 3 titik yang diketahui.


Petunjuk:


- Misalkan persamaan parabolanya y= ax^2+bx+c.


- Substitusikan koordinat titik-titik yang diketahui ke persamaan
tersebut.


- Selesaikan SPL yang terbentuk untuk mendapatkan nilai-nilai a, b, c.


\>load "C:\\Users\\ab368\\Euler\\EulerTemp.e"

\>gambarparabola([-1, 6], [1, 2], [2, 3])   


3. Gambarlah suatu segi-4 yang diketahui keempat titik sudutnya,
misalnya A, B, C, D.


   - Tentukan apakah segi-4 tersebut merupakan segi-4 garis singgung
(sisinya-sisintya merupakan garis singgung lingkaran yang sama yakni
lingkaran dalam segi-4 tersebut).


   - Suatu segi-4 merupakan segi-4 garis singgung apabila keempat
garis bagi sudutnya bertemu di satu titik.


   - Jika segi-4 tersebut merupakan segi-4 garis singgung, gambar
lingkaran dalamnya.


   - Tunjukkan bahwa syarat suatu segi-4 merupakan segi-4 garis
singgung apabila hasil kali panjang sisi-sisi yang berhadapan sama.


\>load "C:\\Users\\ab368\\Euler\\EulerTemp.e"

\>segiempatgs([0, 0], [4, 0], [4, 4], [0, 4]):


    Panjang sisi: AB=4, BC=4, CD=4, DA=4
    Jumlah sisi berhadapan: AB + CD = 8 | BC + DA = 8
    Hasil kali sisi berhadapan: AB * CD = 16 | BC * DA = 16
    Kesimpulan: Segi-4 ABCD adalah SEGI-4 GARIS SINGGUNG (keempat garis bagi berpotongan di satu titik I).

![images/TugasAplikom7Adi25030630001-160.png](images/TugasAplikom7Adi25030630001-160.png)

\>segiempatgs([0, 0], [6, 0], [6, 3], [0, 3]):


    Panjang sisi: AB=6, BC=3, CD=6, DA=3
    Jumlah sisi berhadapan: AB + CD = 12 | BC + DA = 6
    Hasil kali sisi berhadapan: AB * CD = 36 | BC * DA = 9
    Kesimpulan: Segi-4 ABCD BUKAN segi-4 garis singgung (garis bagi tidak bertemu di satu titik).

![images/TugasAplikom7Adi25030630001-161.png](images/TugasAplikom7Adi25030630001-161.png)

4. Gambarlah suatu ellips jika diketahui kedua titik fokusnya,
misalnya P dan Q. Ingat ellips dengan fokus P dan Q adalah tempat
kedudukan titik-titik yang jumlah jarak ke P dan ke Q selalu sama
(konstan).


\>load "C:\\Users\\ab368\\Euler\\EulerTemp.e"

\>gambarellips([-3, 0], [3, 0], 10):


![images/TugasAplikom7Adi25030630001-162.png](images/TugasAplikom7Adi25030630001-162.png)

5. Gambarlah suatu hiperbola jika diketahui kedua titik fokusnya,
misalnya P dan Q. Ingat ellips dengan fokus P dan Q adalah tempat
kedudukan titik-titik yang selisih jarak ke P dan ke Q selalu sama
(konstan).


\>load "C:\\Users\\ab368\\Euler\\EulerTemp.e"

\>gambarhiperbola([-5, 0], [5, 0], 6):


![images/TugasAplikom7Adi25030630001-163.png](images/TugasAplikom7Adi25030630001-163.png)

\>gambarhiperbola([-3, -2], [3, 2], 4):


![images/TugasAplikom7Adi25030630001-164.png](images/TugasAplikom7Adi25030630001-164.png)

# Tugas Eksplorasi Geometri

Berikut adalah eksplorasi dua teorema klasik dalam Geometri Euclid
(Teorema Ceva dan Teorema Menelaus) yang diselesaikan secara numerik
dan simbolik menggunakan Euler Math Toolbox (EMT).


## Masalah 1: Teorema Ceva (Garis-Garis Konkuren pada Segitiga)

## (1) Uraian Materi (Teori)

Dalam buku-buku Geometri Euclid (seperti *College Geometry* oleh
Nathan Altshiller-Court atau *Geometry Revisited* oleh H.S.M.
Coxeter), **Teorema Ceva** menyatakan bahwa:


Diberikan segitiga ABC, dan titik-titik D, E, F berturut-turut
terletak pada garis sisi BC, CA, dan AB (atau perpanjangannya). Ketiga
ruas garis AD, BE, dan CF (yang disebut *cevian*) berpotongan di satu
titik (konkuren) jika dan hanya jika:


$$\frac{AF}{FB} \cdot \frac{BD}{DC} \cdot \frac{CE}{EA} = 1$$## (2) Penyelesaian Menggunakan EMT

\>load geometry;

\>setPlotRange(-1, 7, -1, 6);

\>A := [1, 5]; B := [0, 0]; C := [6, 0];

\>plotPoint(A, "A"); plotPoint(B, "B"); plotPoint(C, "C");

\>plotSegment(A, B); plotSegment(B, C); plotSegment(C, A);


Misalkan titik D pada BC dengan perbandingan BD : DC = 2 : 1, dan titik E pada CA dengan perbandingan CE : EA = 3 : 2. Agar ketiga cevian konkuren, maka harus berlaku AF : FB = 1 : 3.


\>D := (1\*B + 2\*C)/3; // BD : DC = 2 : 1

\>E := (2\*C + 3\*A)/5; // CE : EA = 3 : 2

\>F := (3\*A + 1\*B)/4; // AF : FB = 1 : 3

\>plotPoint(D, "D"); plotPoint(E, "E"); plotPoint(F, "F");

\>color(4); plotSegment(A, D); plotSegment(B, E); plotSegment(C, F); color(1);


Hitung titik potong cevian AD dan BE, lalu periksa apakah titik potong tersebut juga dilalui oleh cevian CF.


\>gAD := lineThrough(A, D);

\>gBE := lineThrough(B, E);

\>gCF := lineThrough(C, F);

\>P1 := lineIntersection(gAD, gBE);

\>P2 := lineIntersection(gBE, gCF);

\>plotPoint(P1, "P");

\>insimg;


![images/TugasAplikom7Adi25030630001-166.png](images/TugasAplikom7Adi25030630001-166.png)

Verifikasi syarat Teorema Ceva dan jarak antara dua titik potong P1 dan P2:


\>rasioceva := (distance(A,F)/distance(F,B)) \* (distance(B,D)/distance(D,C)) \* (distance(C,E)/distance(E,A))


    1

\>selisihtitikpotong := distance(P1, P2)


    0

## (3) Penjelasan Hasil Penyelesaian

1. Nilai perkalian rasio segmen menghasilkan `rasio_ceva = 1`, sesuai
dengan syarat Teorema Ceva. 2. Hasil perhitungan koordinat titik
potong antara AD dan BE (`P1`) dengan titik potong antara BE dan CF
(`P2`) memiliki jarak `0` (`selisih_titik_potong = 0`), yang
membuktikan secara numerik dan visual bahwa ketiga garis cevian AD,
BE, dan CF benar-benar konkuren (berpotongan tepat di satu titik P).


## Masalah 2: Teorema Menelaus (Titik-Titik Kolinear pada Sisi

Segitiga)


## (1) Uraian Materi (Teori)

Dalam buku Geometri Euclid, **Teorema Menelaus** merupakan dual dari
Teorema Ceva yang membahas titik-titik segaris (*kolinear*). Teorema
ini menyatakan bahwa:


Jika suatu garis transversal memotong garis-garis sisi AB, BC, dan CA
dari segitiga ABC berturut-turut di titik F, D, dan E (yang tidak
berimpit dengan titik sudut segitiga), maka titik D, E, dan F segaris
(kolinear) jika dan hanya jika perkalian rasio berarahnya memenuhi:


$$\frac{AF}{FB} \cdot \frac{BD}{DC} \cdot \frac{CE}{EA} = -1$$## (2) Penyelesaian Menggunakan EMT

\>setPlotRange(-2, 9, -2, 6);

\>A := [1, 4]; B := [0, 0]; C := [5, 0];

\>plotPoint(A, "A"); plotPoint(B, "B"); plotPoint(C, "C");

\>plotSegment(A, B); plotSegment(B, C); plotSegment(C, A);


Ambil titik F pada AB dan titik E pada AC, lalu tarik garis transversal melalui E dan F untuk memotong perpanjangan sisi BC di titik D.


\>F := (A + B)/2; // Titik tengah AB (AF/FB = 1)

\>E := (A + 2\*C)/3; // Titik pada AC (CE/EA = 1/2)

\>gEF := lineThrough(E, F);

\>gBC := lineThrough(B, C);

\>D := lineIntersection(gEF, gBC); // Titik potong pada perpanjangan BC

\>plotPoint(F, "F"); plotPoint(E, "E"); plotPoint(D, "D");

\>color(2); plotSegment(C, D); plotLine(gEF); color(1);

\>insimg;


![images/TugasAplikom7Adi25030630001-168.png](images/TugasAplikom7Adi25030630001-168.png)

Verifikasi kolinearitas D, E, F melalui luas segitiga DEF (harus bernilai 0) dan besar rasio mutlak segmen:


\>luasDEF := areaTriangle(D, E, F)


    0

\>rasiomutlak := (distance(A,F)/distance(F,B)) \* (distance(B,D)/distance(D,C)) \* (distance(C,E)/distance(E,A))


    1

## (3) Penjelasan Hasil Penyelesaian

1. Dari hasil output EMT diperoleh `luas_DEF = 0`, yang menunjukkan
bahwa ketiga titik D, E, dan F tidak membentuk segitiga melainkan
terletak pada satu garis lurus yang sama (kolinear). 2. Besar
perkalian rasio jarak segmen menghasilkan `rasio_mutlak = 1`, dan
karena titik D terletak di luar ruas garis BC (pada perpanjangan BC),
rasio berarah BD/DC bernilai negatif sehingga hasil kali rasio
berarahnya tepat sama dengan `-1` sesuai Teorema Menelaus.


