# Pendahuluan dan Pengenalan Cara Kerja EMT
Selamat datang! Ini adalah pengantar pertama ke Euler Math Toolbox
(disingkat EMT atau Euler). EMT adalah sistem terintegrasi yang
merupakan perpaduan kernel numerik Euler dan program komputer aljabar
Maxima.


* 
Bagian numerik, GUI, dan komunikasi dengan Maxima telah dikembangkan
* oleh R. Grothmann, seorang profesor matematika di Universitas
* Eichstätt, Jerman. Banyak algoritma numerik dan pustaka software open
* source yang digunakan di dalamnya.


* 
Maxima adalah program open source yang matang dan sangat kaya untuk
* perhitungan simbolik dan aritmatika tak terbatas. Software ini
* dikelola oleh sekelompok pengembang di internet.


* 
Beberapa program lain (LaTeX, Povray, Tiny C Compiler, Python) dapat
* digunakan di Euler untuk memungkinkan perhitungan yang lebih cepat
* maupun tampilan atau grafik yang lebih baik.


Yang sedang Anda baca (jika dibaca di EMT) ini adalah berkas notebook
di EMT. Notebook aslinya bawaan EMT (dalam bahasa Inggris) dapat
dibuka melalui menu File, kemudian pilih "Open Tutorias and Example",
lalu pilih file "00 First Steps.en". Perhatikan, file notebook EMT
memiliki ekstensi ".en". Melalui notebook ini Anda akan belajar
menggunakan software Euler untuk menyelesaikan berbagai masalah
matematika.


Panduan ini ditulis dengan Euler dalam bentuk notebook Euler, yang
berisi teks (deskriptif), baris-baris perintah, tampilan hasil
perintah (numerik, ekspresi matematika, atau gambar/plot), dan gambar
yang disisipkan dari file gambar.


Untuk menambah jendela EMT, Anda dapat menekan [F11]. EMT akan
menampilkan jendela grafik di layar desktop Anda. Tekan [F11] lagi
untuk kembali ke tata letak favorit Anda. Tata letak disimpan untuk
sesi berikutnya.


Anda juga dapat menggunakan [Ctrl]+[G] untuk menyembunyikan jendela
grafik. Selanjutnya Anda dapat beralih antara grafik dan teks dengan
tombol [TAB].


Seperti yang Anda baca, notebook ini berisi tulisan (teks) berwarna
hijau, yang dapat Anda edit dengan mengklik kanan teks atau tekan menu
Edit -&gt; Edit Comment atau tekan [F5], dan juga baris perintah EMT yang
ditandai dengan "&gt;" dan berwarna merah. Anda dapat menyisipkan baris
perintah baru dengan cara menekan tiga tombol bersamaan:
[Shift]+[Ctrl]+[Enter].


## Komentar (Teks Uraian)

Komentar atau teks penjelasan dapat berisi beberapa "markup" dengan
sintaks sebagai berikut.


   - * Judul  
   - ** Sub-Judul  
   - latex: F (x) = \int_a^x f (t) \, dt  
   - mathjax: \frac{x^2-1}{x-1} = x + 1  
   - maxima: 'integrate(x^3,x) = integrate(x^3,x) + C  
   - http://www.euler-math-toolbox.de  
   - See: http://www.google.de | Google  
   - image: hati.png  
   - ---  

Hasil sintaks-sintaks di atas (tanpa diawali tanda strip) adalah
sebagai berikut.


# Judul

## Sub-Judul

$$F(x) = \int_a^x f(t) \, dt$$$$\frac{x^2-1}{x-1} = x + 1$$
$$\int {x^3}{\;dx}=C+\frac{x^4}{4}$$  <a href="http://www.euler-math-toolbox.de">http://www.euler-math-toolbox.de</a>  

  <a href="http://www.google.de">Google</a>  



image: hati.png


---

Gambar diambil dari folder images di tempat file notebook berada dan
tidak dapat dibaca dari Web. Untuk "See:", tautan (URL)web lokal dapat
digunakan.


Paragraf terdiri atas satu baris panjang di editor. Pergantian baris
akan memulai baris baru. Paragraf harus dipisahkan dengan baris
kosong.


\>// baris perintah diawali dengan \>, komentar (keterangan) diawali dengan //


# Baris Perintah

Mari kita tunjukkan cara menggunakan EMT sebagai kalkulator yang sangat
canggih.


EMT berorientasi pada baris perintah. Anda dapat menuliskan satu atau lebih
perintah dalam satu baris perintah. Setiap perintah harus diakhiri dengan koma
atau titik koma.


* 
Titik koma menyembunyikan output (hasil) dari perintah.

* 
Sebuah koma mencetak hasilnya.

* 
Setelah perintah terakhir, koma diasumsikan secara otomatis (boleh tidak
* ditulis).


Dalam contoh berikut, kita mendefinisikan variabel r yang diberi nilai 1,25.
Output dari definisi ini adalah nilai variabel. Tetapi karena tanda titik koma,
nilai ini tidak ditampilkan. Pada kedua perintah di belakangnya, hasil kedua
perhitungan tersebut ditampilkan.


\>r=1.25; pi\*r^2, 2\*pi\*r


    4.90873852123
    7.85398163397

## Latihan untuk Anda

* 
Sisipkan beberapa baris perintah baru

* 
Tulis perintah-perintah baru untuk melakukan suatu perhitungan yang
* Anda inginkan, boleh menggunakan variabel, boleh tanpa variabel.
* ---
* Beberapa catatan yang harus Anda perhatikan tentang penulisan sintaks
* perintah EMT.


* 
Pastikan untuk menggunakan titik desimal, bukan koma desimal untuk
* bilangan!

* 
Gunakan * untuk perkalian dan ^ untuk eksponen (pangkat).

* 
Seperti biasa, * dan / bersifat lebih kuat daripada + atau -.

* 
^ mengikat lebih kuat dari *, sehingga pi * r ^ 2 merupakan rumus
* luas lingkaran.

* 
Jika perlu, Anda harus menambahkan tanda kurung, seperti pada 2 ^ (2
* ^ 3).


Perintah r = 1.25 adalah menyimpan nilai ke variabel di EMT. Anda juga
dapat menulis r: = 1.25 jika mau. Anda dapat menggunakan spasi sesuka
Anda.


Anda juga dapat mengakhiri baris perintah dengan komentar yang diawali
dengan dua garis miring (//).


Contoh Perintah :


Contoh 1: Perhitungan Luas Persegi Panjang (Menggunakan Variabel)


\>panjang = 10; lebar = 6; luas = panjang \* lebar


    60

Contoh 2: Perhitungan Aritmatika Bebas (Tanpa Variabel)


\>(15 + 25) \* 3 / 2


    60

Contoh 3: Menghitung Nilai Eksponensial / Pangkat


\>2^8 - 50


    206

\>r := 1.25 // Komentar: Menggunakan  := sebagai ganti =


    1.25

Argumen atau input untuk fungsi ditulis di dalam tanda kurung.


\>sin(45°), cos(pi), log(sqrt(E))


    0.707106781187
    -1
    0.5

Contoh 1: Kombinasi Fungsi Trigonometri, Akar, dan Eksponensial


\>tan(45°), sqrt(16), exp(1)


    1
    4
    2.71828182846

Contoh 2: Perhitungan Logaritma dan Nilai Mutlak


\>log(10), abs(-25), floor(4.7)


    2.30258509299
    25
    4

Contoh 3: Fungsi Pembulatan dan Faktorial


\>ceil(4.2), round(3.7)


    5
    4

Seperti yang Anda lihat, fungsi trigonometri bekerja dengan radian,
dan derajat dapat diubah dengan °. Jika keyboard Anda tidak memiliki
karakter derajat tekan [F7], atau gunakan fungsi deg() untuk
mengonversi.


EMT menyediakan banyak sekali fungsi dan operator matematika.Hampir
semua fungsi matematika sudah tersedia di EMT. Anda dapat melihat
daftar lengkap fungsi-fungsi matematika di EMT pada berkas Referensi
(klik menu Help -&gt; Reference)


Untuk membuat rangkaian komputasi lebih mudah, Anda dapat merujuk ke
hasil sebelumnya dengan "%". Cara ini sebaiknya hanya digunakan untuk
merujuk hasil perhitungan dalam baris perintah yang sama.


\>  

\>(sqrt(5)+1)/2, %^2-%+1 // Memeriksa solusi x^2-x+1=0


    1.61803398875
    2

Contoh lain


\> sin(60°), %^2, deg(arcsin(%))


    0.866025403784
    0.75
    48.5903778907

## Latihan untuk Anda

* 
Buka berkas Reference dan baca fungsi-fungsi matematika yang
* tersedia di EMT.

* 
Sisipkan beberapa baris perintah baru.

* 
Lakukan contoh-contoh perhitungan menggunakan fungsi-fungsi
* matematika di EMT.


Fungsi Pembulatan &amp; Nilai Mutlak:


\> abs(-15), floor(5.8), ceil(3.2), round(4.5)


    15
    5
    4
    5

Fungsi Eksponensial &amp; Logaritma:


\> exp(2), ln(10), log10(100)


    7.38905609893
    2.30258509299
    2

Fungsi Trigonometri Lanjut:


\> sinh(1), cosh(1), tan(0.5)


    1.17520119364
    1.54308063482
    0.546302489844

# Satuan

EMT dapat mengubah unit satuan menjadi sistem standar internasional
(SI). Tambahkan satuan di belakang angka untuk konversi sederhana.


\>1miles  // 1 mil = 1609,344 m


    1609.344

Beberapa satuan yang sudah dikenal di dalam EMT adalah sebagai
berikut. Semua unit diakhiri dengan tanda dolar ($), namun boleh tidak
perlu ditulis dengan mengaktifkan easyunits. 


kilometer$:=1000;


km$:=kilometer$;


cm$:=0.01;


mm$:=0.001;


minute$:=60;


min$:=minute$;


minutes$:=minute$;


hour$:=60*minute$;


h$:=hour$;


hours$:=hour$;


day$:=24*hour$;


days$:=day$;


d$:=day$;


year$:=365.2425*day$;


years$:=year$;


y$:=year$;


inch$:=0.0254;


in$:=inch$;


feet$:=12*inch$;


foot$:=feet$;


ft$:=feet$;


yard$:=3*feet$;


yards$:=yard$;


yd$:=yard$;


mile$:=1760*yard$;


miles$:=mile$;


kg$:=1;


sec$:=1;


ha$:=10000;


Ar$:=100;


Tagwerk$:=3408;


Acre$:=4046.8564224;


pt$:=0.376mm;


Untuk konversi ke dan antar unit, EMT menggunakan operator khusus,
yakni -&gt;.


\>4km -\> miles, 4inch -\> " mm"


    2.48548476895
    101.6 mm

Contoh 1: Konversi Waktu (Hari ke Jam &amp; Menit)Mengonversi 2.5 hari ke
satuan jam, serta 3 jam ke satuan menit:


\> 2.5days -\> " hours", 3hours -\> " minutes"


    60 hours
    180 minutes

Contoh 2: Konversi Luas (Hektar ke Meter Persegi &amp; Acre)Mengonversi 2
hektar (ha) ke satuan meter persegi m^2, serta 1 hektar ke satuan 


\> 2ha, 1ha -\> " Acre"


    20000
    2.47105381467 Acre

Contoh 3: Konversi Panjang (Yard ke Meter &amp; Feet ke Inci)Mengonversi
10 yard ke satuan meter, serta 6 feet (kaki) ke satuan inci (inch): 


\> 10yard, 6feet -\> " inch"


    9.144
    72 inch

# Format Tampilan Nilai

Akurasi internal untuk nilai bilangan di EMT adalah standar IEEE,
sekitar 16 digit desimal. Aslinya, EMT tidak mencetak semua digit
suatu bilangan. Ini untuk menghemat tempat dan agar terlihat lebih
baik. Untuk mengatrtamilan satu bilangan, operator berikut dapat
digunakan.


\>pi


    3.14159265359

\>longest pi


          3.141592653589793 

\>long pi


    3.14159265359

\>short pi


    3.1416

\>shortest pi


       3.1 

\>fraction pi


    312689/99532

\>short 1200\*1.03^10, long E, longest pi


    1612.7
    2.71828182846
          3.141592653589793 

Format aslinya untuk menampilkan nilai menggunakan sekitar 10 digit.
Format tampilan nilai dapat diatur secara global atau hanya untuk satu
nilai.


Anda dapat mengganti format tampilan bilangan untuk semua perintah
selanjutnya. Untuk mengembalikan ke format aslinya dapat digunakan
perintah "defformat" atau "reset".


\>longestformat; pi, defformat; pi


    3.141592653589793
    3.14159265359

\>longestformat; pi, reset; pi


    3.141592653589793
    3.14159265359

Kernel numerik EMT bekerja dengan bilangan titik mengambang (floating point)
dalam presisi ganda IEEE (berbeda dengan bagian simbolik EMT). Hasil numerik
dapat ditampilkan dalam bentuk pecahan.


\>1/7+1/4, fraction %


    0.392857142857
    11/28

# Perintah Multibaris

Perintah multi-baris membentang di beberapa baris yang terhubung
dengan "..." di setiap akhir baris, kecuali baris terakhir. Untuk
menghasilkan tanda pindah baris tersebut, gunakan tombol
[Ctrl]+[Enter]. Ini akan menyambung perintah ke baris berikutnya dan
menambahkan "..." di akhir baris sebelumnya. Untuk menggabungkan suatu
baris ke baris sebelumnya, gunakan [Ctrl]+[Backspace].


Contoh perintah multi-baris berikut dapat dijalankan setiap kali
kursor berada di salah satu barisnya. Ini juga menunjukkan bahwa ...
harus berada di akhir suatu baris meskipun baris tersebut memuat
komentar.


\>a=4; b=15; c=2; // menyelesaikan a\*x^2+b\*x+c=0 secara manual ...  
\>   D=sqrt(b^2/(a^2\*4)-c/a); ...  
\>   -b/(2\*a) + D, ...  
\>   -b/(2\*a) - D


    -0.138444501319
    -3.61155549868

# Menampilkan Daftar Variabe

Untuk menampilkan semua variabel yang sudah pernah Anda definisikan
sebelumnya (dan dapat dilihat kembali nilainya), gunakan perintah
"listvar".


\>listvar


    r                   1.25
    panjang             10
    lebar               6
    luas                60
    a                   4
    b                   15
    c                   2
    D                   1.73655549868123

Perintah listvar hanya menampilkan variabel buatan pengguna.
Dimungkinkan untuk menampilkan variabel lain, dengan menambahkan
string  termuat di dalam nama variabel yang diinginkan.


Perlu Anda perhatikan, bahwa EMT membedakan huruf besar dan huruf
kecil. Jadi variabel "d" berbeda dengan variabel "D".


Contoh berikut ini menampilkan semua unit yang diakhiri dengan "m"
dengan mencari semua variabel yang berisi "m$".


\>listvar m$


    km$                 1000
    cm$                 0.01
    mm$                 0.001
    nm$                 1853.24496
    gram$               0.001
    m$                  1
    hquantum$           6.62606957e-34
    atm$                101325

Untuk menghapus variabel tanpa harus memulai ulang EMT gunakan
perintah "remvalue".


\> remvalue a,b,c,D

\>listvar 


    r                   1.25
    panjang             10
    lebar               6
    luas                60

# Menampilkan Panduan

Untuk mendapatkan panduan tentang penggunaan perintah atau fungsi di EMT, buka
jendela panduan dengan menekan [F1] dan cari fungsinya. Anda juga dapat
mengklik dua kali pada fungsi yang tertulis di baris perintah atau di teks
untuk membuka jendela panduan.


Coba klik dua kali pada perintah "intrandom" berikut ini!


\> intrandom(10,6)


    [4,  2,  6,  2,  4,  2,  3,  2,  2,  6]

Di jendela panduan, Anda dapat mengklik kata apa saja untuk menemukan
referensi atau fungsi.


Misalnya, coba klik kata "random" di jendela panduan. Kata tersebut
boleh ada dalam teks atau di bagian "See:" pada panduan. Anda akan
menemukan penjelasan fungsi "random", untuk menghasilkan bilangan acak
berdistribusi uniform antara 0,0 dan 1,0. Dari panduan untuk "random"
Anda dapat menampilkan panduan untuk fungsi "normal", dll.


\>random()


    0.270905975731

\>random(10)


    [0.704419,  0.217693,  0.445363,  0.308411,  0.914541,  0.193585,
    0.463387,  0.095153,  0.595017,  0.431184]

\>random(10,6)


    Real 10 x 6 matrix
    
          0.72868      0.465164      0.323032      0.525184     ...
         0.262253      0.866587      0.536137      0.493453     ...
         0.967468      0.193151      0.935921     0.0728753     ...
         0.356626       0.52143      0.428893      0.168134     ...
         0.750042      0.472935      0.324407      0.340388     ...
         0.216545      0.598477      0.729271      0.950019     ...
         0.469159      0.898763      0.388543      0.674114     ...
         0.123222      0.205006      0.465049     0.0281269     ...
         0.615836      0.217391      0.962872      0.842267     ...
         0.918802      0.997492      0.473212      0.185709     ...

\>random(6)


    [0.247804,  0.834083,  0.44372,  0.371866,  0.775718,  0.37468]

\>random(6,10)


    Real 6 x 10 matrix
    
         0.224336     0.0102885      0.164816      0.356866     ...
         0.906718      0.916402     0.0960726      0.385195     ...
         0.189678      0.777528      0.237424      0.978964     ...
         0.983636       0.21102      0.552777      0.494142     ...
         0.240796      0.635967      0.151086      0.251504     ...
         0.320241      0.353311      0.433255      0.424885     ...

\>normal()


    0.781251242538

\>normal(10)


    [-1.34758,  0.750155,  -2.73261,  -0.82989,  1.79506,  0.655748,
    0.525446,  -0.151307,  1.5537,  0.138615]

\>normal(10,6)


    Real 10 x 6 matrix
    
        -0.664663     -0.500398      0.442711       1.81325     ...
        -0.497936       2.16221      0.370564     0.0685002     ...
         0.409036     -0.975825     -0.955783     -0.532637     ...
          2.96967         1.517     -0.860983      0.369119     ...
          -2.2573     -0.446321     0.0685365     -0.623588     ...
         0.839849     -0.254001      0.464111       1.66108     ...
         -1.32777     -0.432742      -0.35504     -0.461074     ...
          0.13651      -1.18485     -0.167833       1.18944     ...
        -0.742837      0.731665     -0.263558     -0.761708     ...
         -2.00135      0.970173     -0.579265       -1.3363     ...

\>normal(6)


    [-0.19087,  0.740958,  -0.245381,  -0.817244,  0.722786,  -1.42903]

\>normal(6,10)


    Real 6 x 10 matrix
    
        -0.272536      0.138854        1.8903      0.202249     ...
         -1.13844     -0.340822       1.25018     -0.410963     ...
         0.408107      0.540024      -1.47271     -0.247446     ...
        -0.501904      0.280532      0.339487      -1.19993     ...
         -1.00777       1.27634    -0.0105417       1.17266     ...
          1.44749     -0.208488      0.789992      -1.64448     ...

# Matriks dan Vektor

EMT merupakan suatu aplikasi matematika yang mengerti "bahasa matriks". Artinya,
EMT menggunakan vektor dan matriks untuk perhitungan-perhitungan tingkat lanjut.
Suatu vektor atau matriks dapat didefinisikan dengan tanda kurung siku.
Elemen-elemennya dituliskan di dalam tanda kurung siku, antar elemen dalam satu
baris dipisahkan oleh koma(,), antar baris dipisahkan oleh titik koma (;).


Vektor dan matriks dapat diberi nama seperti variabel biasa.


\>v=[4,5,6,3,2,1]


    [4,  5,  6,  3,  2,  1]

\>A=[1,2,3;4,5,6;7,8,9]


                1             2             3 
                4             5             6 
                7             8             9 

Karena EMT mengerti bahasa matriks, EMT memiliki kemampuan yang sangat canggih
untuk melakukan perhitungan matematis untuk masalah-masalah aljabar linier,
statistika, dan optimisasi.


Vektor juga dapat didefinisikan dengan menggunakan rentang nilai dengan interval
tertentu menggunakan tanda titik dua (:),seperti contoh berikut ini.


\>c=1:5


    [1,  2,  3,  4,  5]

\>w=0:0.1:1


    [0,  0.1,  0.2,  0.3,  0.4,  0.5,  0.6,  0.7,  0.8,  0.9,  1]

\>mean(w^2)


    0.35

# Bilangan Kompleks

EMT juga dapat menggunakan bilangan kompleks. Tersedia banyak fungsi untuk
bilangan kompleks di EMT. Bilangan imaginer


dituliskan dengan huruf I (huruf besar I), namun akan ditampilkan dengan huruf i
(i kecil).


  re(x) : bagian riil pada bilangan kompleks x.  
  im(x) : bagian imaginer pada bilangan kompleks x.  
  complex(x) : mengubah bilangan riil x menjadi bilangan kompleks.  
  conj(x) : Konjugat untuk bilangan bilangan komplkes x.  
  arg(x) : argumen (sudut dalam radian) bilangan kompleks x.  
  real(x) : mengubah x menjadi bilangan riil.  

Apabila bagian imaginer x terlalu besar, hasilnya akan menampilkan pesan
kesalahan.


  &gt;sqrt(-1) // Error!  
  &gt;sqrt(complex(-1))  

\>z=2+3\*I, re(z), im(z), conj(z), arg(z), deg(arg(z)), deg(arctan(3/2))


    2+3i
    2
    3
    2-3i
    0.982793723247
    56.309932474
    56.309932474

\>deg(arg(I)) // 90°


    90

\>sqrt(-1)


    Floating point error!
    Error in sqrt
    Error in:
    sqrt(-1) ...
            ^

\>sqrt(complex(-1))


    0+1i

EMT selalu menganggap semua hasil perhitungan berupa bilangan riil dan tidak
akan secara otomatis mengubah ke bilangan kompleks.


Jadi akar kuadrat -1 akan menghasilkan kesalahan, tetapi akar kuadrat kompleks
didefinisikan untuk bidang koordinat dengan cara seperti biasa. Untuk mengubah
bilangan riil menjadi kompleks, Anda dapat menambahkan 0i atau menggunakan
fungsi "complex".


\>complex(-1), sqrt(%)


    -1+0i 
    0+1i

# Matematika Simbolik

EMT dapat melakukan perhitungan matematika simbolis (eksak) dengan bantuan
software Maxima. Software Maxima otomatis sudah terpasang di komputer Anda ketika
Anda memasang EMT. Meskipun demikian, Anda dapat juga memasang software Maxima
tersendiri (yang terpisah dengan instalasi Maxima di EMT).


Pengguna Maxima yang sudah mahir harus memperhatikan bahwa terdapat sedikit
perbedaan dalam sintaks antara sintaks asli Maxima dan sintaks ekspresi simbolik
di EMT.


Untuk melakukan perhitungan matematika simbolis di EMT, awali perintah Maxima
dengan tanda "&amp;". Setiap ekspresi yang dimulai dengan "&amp;" adalah ekspresi
simbolis dan dikerjakan oleh Maxima.


\>&(a+b)^2


    
                                          2
                                   (b + a)
    

\>&expand((a+b)^2), &factor(x^2+5\*x+6)


    
                                2            2
                               b  + 2 a b + a
    
    
                               (x + 2) (x + 3)
    

\>&solve(a\*x^2+b\*x+c,x) // rumus abc


    
                         2                         2
                 - sqrt(b  - 4 a c) - b      sqrt(b  - 4 a c) - b
            [x = ----------------------, x = --------------------]
                          2 a                        2 a
    

\>&(a^2-b^2)/(a+b), &ratsimp(%) // ratsimp menyederhanakan bentuk pecahan


    
                                    2    2
                                   a  - b
                                   -------
                                    b + a
    
    
                                    a - b
    

\>10! // nilai faktorial (modus EMT)


    3628800

\>&10! //nilai faktorial (simbolik dengan Maxima)


    
                                   3628800
    

Untuk menggunakan perintah Maxima secara langsung (seperti perintah pada layar
Maxima) awali perintahnya dengan tanda "::" pada baris perintah EMT. Sintaks
Maxima disesuaikan dengan sintaks EMT (disebut "modus kompatibilitas").


\>factor(1000) // mencari semua faktor 1000 (EMT)


    [2,  2,  2,  5,  5,  5]

\>:: factor(1000) // faktorisasi prima 1000 (dengan Maxima) 


    
                                     3  3
                                    2  5
    

\>:: factor(20!)


    
                            18  8  4  2
                           2   3  5  7  11 13 17 19
    

Jika Anda sudah mahir menggunakan Maxima, Anda dapat menggunakan sintaks asli
perintah Maxima dengan menggunakan tanda ":::" untuk mengawali setiap perintah
Maxima di EMT. Perhatikan, harus ada spasi antara ":::" dan perintahnya.


\>::: binomial(5,2); // nilai C(5,2)


    
                                      10
    

\>::: binomial(m,4); // C(m,4)=m!/(4!(m-4)!)


    
                          (m - 3) (m - 2) (m - 1) m
                          -------------------------
                                     24
    

\>::: trigexpand(cos(x+y)); // rumus cos(x+y)=cos(x) cos(y)-sin(x)sin(y) 


    
                        cos(x) cos(y) - sin(x) sin(y)
    

\>::: trigexpand(sin(x+y));


    
                        cos(x) sin(y) + sin(x) cos(y)
    

\>::: trigsimp(((1-sin(x)^2)\*cos(x))/cos(x)^2+tan(x)\*sec(x)^2) //menyederhanakan fungsi trigonometri


    
                                           4
                               sin(x) + cos (x)
                               ----------------
                                      3
                                   cos (x)
    

Untuk menyimpan ekspresi simbolik ke dalam suatu variabel digunakan tanda "&amp;=".


\>p1 &= (x^3+1)/(x+1)


    
                                     3
                                    x  + 1
                                    ------
                                    x + 1
    

\>&ratsimp(p1)


    
                                   2
                                  x  - x + 1
    

Untuk mensubstitusikan suatu nilai ke dalam variabel dapat digunakan perintah
"with".


\>&p1 with x=3 // (3^3+1)/(3+1)


    
                                      7
    

\>&p1 with x=a+b, &ratsimp(%) //substitusi dengan variabel baru


    
                                        3
                                 (b + a)  + 1
                                 ------------
                                  b + a + 1
    
    
                         2                  2
                        b  + (2 a - 1) b + a  - a + 1
    

\>&diff(p1,x) //turunan p1 terhadap x


    
                                  2      3
                               3 x      x  + 1
                               ----- - --------
                               x + 1          2
                                       (x + 1)
    

\>&integrate(p1,x) // integral p1 terhadap x


    
                                 3      2
                              2 x  - 3 x  + 6 x
                              -----------------
                                      6
    

# Tampilan Matematika Simbolik dengan LaTeX

Anda dapat menampilkan hasil perhitunagn simbolik secara lebih bagus
menggunakan LaTeX. Untuk melakukan hal ini, tambahkan tanda dolar ($) di depan
tanda &amp; pada setiap perintah Maxima.


Perhatikan, hal ini hanya dapat menghasilkan tampilan yang diinginkan apabila
komputer Anda sudah terpasang software LaTeX.


\>$&(a+b)^2


$$\left(b+a\right)^2$$\>$&expand((a+b)^2), $&factor(x^2+5\*x+6)


$$\left(x+2\right)\,\left(x+3\right)$$![images/EMT00-FisrtSteps%20kukerjakan-006.png](images/EMT00-FisrtSteps%20kukerjakan-006.png)

\>$&solve(a\*x^2+b\*x+c,x) // rumus abc


$$\left[ x=\frac{-\sqrt{b^2-4\,a\,c}-b}{2\,a} , x=\frac{\sqrt{b^2-4\,  a\,c}-b}{2\,a} \right] $$\>$&(a^2-b^2)/(a+b), $&ratsimp(%)


$$a-b$$![images/EMT00-FisrtSteps%20kukerjakan-009.png](images/EMT00-FisrtSteps%20kukerjakan-009.png)

\>  


# Selamat Belajar dan Berlatih!

Baik, itulah sekilas pengantar penggunaan software EMT. Masih banyak
kemampuan EMT yang akan Anda pelajari dan praktikkan.


Sebagai latihan untuk memperlancar penggunaan perintah-perintah EMT
yang sudah dijelaskan di atas, silakan Anda lakukan hal-hal sebagai
berikut.


* 
Carilah soal-soal matematika dari buku-buku Matematika.

* 
Tambahkan beberapa baris perintah EMT pada notebook ini.

* 
Selesaikan soal-soal matematika tersebut dengan menggunakan EMT.
* Pilih soal-soal yang sesuai dengan perintah-perintah yang sudah
* dijelaskan dan dicontohkan di atas.


1. Perhitungan Aritmatika dan Trigonometri


Hitung nilai dari r = 2.5, lalu cari luas lingkaran pi*r^2 dan
kelilingnya 2pi*r, serta hitung sin(30^\circ) + cos(\pi/3):


\>r:=2.5; pi\*r^2, 2\*pi\*r


    19.6349540849
    15.7079632679

\>sin(30°), cos(pi/3)


    0.5
    0.5

\> 


2. Konversi Satuan


Konversikan jarak 15 km ke satuan mil (miles) dan 5 inci ke milimeter
(mm):


\> 15km -\> miles 


    9.32056788356

\>5inch -\> " mm"


    127 mm

3. Vektor, Matriks, dan Statistik Sederhana


Buat vektor v dari 1 sampai 10 dengan interval 0.5, hitung
rata-ratanya, lalu definisikan matriks A berukuran 2 * 2:


\>v=1:0.5:10


    [1,  1.5,  2,  2.5,  3,  3.5,  4,  4.5,  5,  5.5,  6,  6.5,  7,  7.5,
    8,  8.5,  9,  9.5,  10]

\>mean(v)


    5.5

\>A=[3,4; 1,2]


                3             4 
                1             2 

4. Operasi Bilangan Kompleks


Tentukan bagian riil, imaginer, dan konjugat dari bilangan kompleks z
= 4 + 5i:


\>z=4+5\*I


    4+5i

\>re(z)


    4

\>im(z)


    5

\>conj(z)


    4-5i

5. Matematika Simbolik (Ekspresi Aljabar &amp; Faktorisasi)


Jabarkan bentuk (x+3)^3 dan faktorkan persamaan x^2 - 7x + 12
menggunakan Maxima:


\>&expand((x+3)^3)


    
                             3      2
                            x  + 9 x  + 27 x + 27
    

\>&factor(x^2 - 7\*x + 12)


    
                               (x - 4) (x - 3)
    

6. Turunan, Integral, dan Substitusi Simbolik


Tentukan turunan serta integral dari fungsi p(x) = \frac{x^2 - 4}{x -
2) terhadap x, lalu substitusikan x = 5


\>p1 &= (x^2-4)/(x-2)


    
                                     2
                                    x  - 4
                                    ------
                                    x - 2
    

\>&ratsimp(p1)


    
                                    x + 2
    

\>&diff(p1, x)


    
                                         2
                                2 x     x  - 4
                               ----- - --------
                               x - 2          2
                                       (x - 2)
    

\>&integrate(p1, x)


    
                                    2
                                   x  + 4 x
                                   --------
                                      2
    

\>&p1 with x=5


    
                                      7
    

