# TugasAplikom3Adi25030630001
# EMT untuk Perhitungan Aljabar

Pada notebook ini Anda belajar menggunakan EMT untuk melakukan
berbagai perhitungan terkait dengan materi atau topik dalam Aljabar.
Kegiatan yang harus Anda lakukan adalah sebagai berikut:


* 
Membaca secara cermat dan teliti notebook ini;

* 
Menerjemahkan teks bahasa Inggris ke bahasa Indonesia;

* 
Mencoba contoh-contoh perhitungan (perintah EMT) dengan cara
* meng-ENTER setiap perintah EMT yang ada (pindahkan kursor ke baris
* perintah)

* 
Jika perlu Anda dapat memodifikasi perintah yang ada dan memberikan
* keterangan/penjelasan tambahan terkait hasilnya.

* 
Menyisipkan baris-baris perintah baru untuk mengerjakan soal-soal
* Aljabar dari file PDF yang saya berikan;

* 
Memberi catatan hasilnya.

* 
Jika perlu tuliskan soalnya pada teks notebook (menggunakan format
* LaTeX).

* 
Gunakan tampilan hasil semua perhitungan yang eksak atau simbolik
* dengan format LaTeX. (Seperti contoh-contoh pada notebook ini.)


## Contoh pertama

Menyederhanakan bentuk aljabar:


$$6x^{-3}y^5\times -7x^2y^{-9}$$\>$&6\*x^(-3)\*y^5\*-7\*x^2\*y^(-9)


$$-\frac{42}{x\,y^4}$$Hukum-Hukum Eksponen:ebook algebra and trigonometry, 4th edition


Halaman 19


1. a^ma^n=a^m+n


2. a^m/a^n=a^m-n


3. (a^m)^n=a^mn


4. (ab)^n=a^nb^n


5. (a/b)^n=a^n/b^n


6. (a/b)^-n=(b/a)n


7. a^-n/b^-m=b^m/a^n


Cara pengerjaan yang sesuai ebook algebra and trigonometry, 4th
edition


Halaman 24


Soal :


$$(2a^{3}b^2)\times (3ab^{4})^3$$

Solusi:


Gunakan Hukum 4: (ab)^n=a^nb^n, sehingga :


$$(2a^{3}b^2)\times [3^3a^3(b^{4})^3]$$

Gunakan hukum 3: (a^m)^n=a^mn


$$(2a^{3}b^2)\times (27a^3b^{12})$$

Kelompokkan faktor-faktor yang memiliki basis yang sama


$$(2)(27)a^{3}a^3b^2b^{12}$$

Gunakan hukum 1: a^ma^n=a^m+n


$$54a^{6}b^{14}$$Mari kita cek apakah hasilnya sama dengan pengerjaan di emt


\>$&(2\*a^3\*b^2)\*(3\*a\*b^4)^3


$$54\,a^6\,b^{14}$$Terbukti pengerjaan manual dan pengerjaan EMT mendapatkan hasil yang
sama


Menjabarkan:


$$(6x^{-3}+y^5)(-7x^2-y^{-9})$$\>$&showev('expand((6\*x^(-3)+y^5)\*(-7\*x^2-y^(-9))))


$${\it expand}\left(\left(-\frac{1}{y^9}-7\,x^2\right)\,\left(y^5+  \frac{6}{x^3}\right)\right)=-7\,x^2\,y^5-\frac{1}{y^4}-\frac{6}{x^3  \,y^9}-\frac{42}{x}$$Gunakan rumus perkalian bentuk aljabar:ebook algebra and trigonometry,
4th edition


Halaman 33


(a+b)(c+d)=a(c+d)+b(c+d)=ac+ad+bc+bd


Cara pengerjaan yang sesuai ebook algebra and trigonometry, 4th
edition


Halaman 33


Soal :


$$(2x+1)\times (3x-5)$$

Solusi:


Gunakan rumus perkalian bentuk aljabar:
(a+b)(c+d)=a(c+d)+b(c+d)=ac+ad+bc+bd , sehingga :


$$(2x+1)\times (3x-5)=6x^2-10x+3x-5$$

Gabungkan suku-suku sejenis:


$$6x^2-7x-5$$Mari kita cek apakah hasilnya sama dengan pengerjaan di emt


\>$&showev('expand((2\*x + 1)\*(3\*x - 5)))


$${\it expand}\left(\left(2\,x+1\right)\,\left(3\,x-5\right)\right)=6  \,x^2-7\,x-5$$Terbukti pengerjaan manual dan pengerjaan EMT mendapatkan hasil yang
sama.


## Baris Perintah

Baris perintah Euler terdiri dari satu atau beberapa perintah Euler
yang diikuti oleh titik koma ";" atau koma ",". Titik koma mencegah
pencetakan hasil. Koma setelah perintah terakhir dapat diabaikan.


Baris perintah berikut hanya akan mencetak hasil dari ekspresi, bukan
penetapan nilai atau perintah format.


\>r:=2; h:=4; pi\*r^2\*h/3


    16.7551608191

Mari kita hitung manual operasi di atas


Diketahui


r=2, h=4, Kita gunakan nilai pi=3.14


Ditanya pi*r^2*h/3


Penyelesaian:


3.14*(2^2)*4/3= 3.14*4*4/3=16.7466666666666


Terlihat ada perbedaan karena nilai pi yang dipakai berbeda dengan
nilai pi di EMT


Perintah-perintah harus dipisahkan dengan spasi. Baris perintah
berikut mencetak dua hasilnya.


\>pi\*2\*r\*h, %+2\*pi\*r\*h // Ingat tanda % menyatakan hasil perhitungan terakhir sebelumnya


    50.2654824574
    100.530964915

Mari kita hitung manual operasi di atas


Diketahui


r=2, h=4, Kita gunakan nilai pi=3.14


Ditanya pi*r^2*h dan (pi*r^2*h)+(2*pi*r*h)


Penyelesaian:


3.14*(2^2)*4= 3.14*4*4=50.24


(50.24)+(2*3.14*2*4)=50.24+50.24=100.48


Terlihat ada perbedaan karena nilai pi yang dipakai berbeda dengan
nilai pi di EMT


Baris perintah dieksekusi sesuai urutan pengguna menekan tombol Enter.
Jadi Anda akan mendapatkan nilai baru setiap kali Anda mengeksekusi
baris kedua.


\>x := 1;

\>x := cos(x) // nilai cosinus (x dalam radian)


    0.540302305868

\>x := cos(x)


    0.857553215846

Jika dua baris dihubungkan dengan "...", kedua baris tersebut akan
selalu dieksekusi secara bersamaan.


\>x := 1.5; ...  
\>   x := (x+2/x)/2, x := (x+2/x)/2, x := (x+2/x)/2, 


    1.41666666667
    1.41421568627
    1.41421356237

Ini juga merupakan cara yang baik untuk membagi perintah yang panjang
ke dalam dua baris atau lebih. Anda dapat menekan Ctrl+Enter untuk
membagi satu baris menjadi dua di posisi kursor saat ini, atau
Ctrl+Backspace untuk menggabungkan baris-baris tersebut.


Untuk melipat semua baris ganda, tekan Ctrl+L. Maka baris-baris
berikutnya hanya akan terlihat jika salah satunya sedang dipilih
(fokus). Untuk melipat satu baris ganda saja, awali baris pertama
dengan "%+ ".


\>%+ x=4+5; ...  
\>    // This line will not be visible once the cursor is off the line


Baris yang dimulai dengan %% akan tidak terlihat sama sekali.


    81

Euler mendukung perulangan (loop) dalam baris perintah, selama
perulangan tersebut muat dalam satu baris tunggal atau beberapa baris
(multi-line). Dalam program, batasan ini tentu saja tidak berlaku.
Untuk informasi lebih lanjut, silakan konsultasikan panduan pengenalan
berikut.


\>x=1; for i=1 to 5; x := (x+2/x)/2, end; // menghitung akar 2


    1.5
    1.41666666667
    1.41421568627
    1.41421356237
    1.41421356237

Boleh menggunakan multi-line (beberapa baris). Pastikan baris tersebut
diakhiri dengan  " ...".


\>x := 1.5; // comments go here before the ...  
\>   repeat xnew:=(x+2/x)/2; until xnew~=x; ...  
\>      x := xnew; ...  
\>   end; ...  
\>   x,


    1.41421356237

Struktur kondisional (conditional structures) juga dapat berfungsi.


\>if E^pi\>pi^E; then "Thought so!", endif;


    Thought so!

Saat Anda mengeksekusi suatu perintah, kursor dapat berada di posisi
mana saja pada baris perintah tersebut. Anda dapat kembali ke perintah
sebelumnya atau beralih ke perintah berikutnya menggunakan tombol
panah. Anda juga dapat mengklik bagian komentar di atas perintah untuk
berpindah ke perintah tersebut.


Saat Anda menggeser kursor di sepanjang baris, pasangan tanda kurung
buka dan tutup (baik kurung siku [] maupun kurung biasa ()) akan
tersorot (highlight). Perhatikan juga baris status (status line).
Setelah tanda kurung buka dari fungsi sqrt(), baris status akan
menampilkan teks bantuan untuk fungsi tersebut. Eksekusi perintah
tersebut dengan menekan tombol Enter (return key).


\>sqrt(sin(10°)/cos(20°))


    0.429875017772

Untuk melihat bantuan untuk perintah terbaru, buka jendela bantuan
(*help window*) dengan menekan **F1**. Di sana, Anda dapat memasukkan
teks untuk dicari. Pada baris kosong, bantuan mengenai jendela bantuan
akan ditampilkan. Anda dapat menekan **Escape** untuk mengosongkan
baris atau untuk menutup jendela bantuan.


Anda dapat mengklik ganda (*double click*) pada perintah apa pun untuk
membuka bantuan untuk perintah tersebut. Coba klik ganda pada perintah
`exp` di bawah ini pada baris perintah.


\>exp(log(2.5))


    2.5

Saat double click, yang muncul yaitu :


Topics


---

exp


The most frequent usual mathematical functions. They work for real,


complex and intervals scalars, vectors and matrices. The functions


work element-wise for matrices, and obey to the rules of the Euler


matrix language.


  abs(x) : absolute value  
  exp(x) : exponential function  
  log(x) : natural logarithm, main branch for complex  
  sign(x) : sign of reals  
  sqrt(x) : square root function, with main branch for complex values  

To compute the exponential etc. for a matrix, use "matrixfunction".


The underflows that exp produces are caught to 0, if underflows is off


(the default). This can be changed with "errors off" and "errors on". 


  &gt;log(E)  
  &gt;abs(1+I);  
  &gt;sqrt(complex(-1))^2  
  &gt;plot2d("sign",-1,1);  

Anda juga dapat menyalin dan menempel (*copy and paste*) di Euler.
Gunakan **Ctrl-C** dan **Ctrl-V** untuk melakukan ini. Untuk menandai
teks, seret mouse atau gunakan tombol **Shift** bersamaan dengan
tombol panah kursor apa saja. Selain itu, Anda juga dapat menyalin
tanda kurung yang tersorot.


## Sintaks dasar

Euler mengenal fungsi-fungsi matematika pada umumnya. Seperti yang
telah Anda lihat di atas, fungsi trigonometri dapat bekerja dalam
radian atau derajat. Untuk mengubah ke derajat, tambahkan simbol
derajat (dengan tombol F7) pada nilainya, atau gunakan fungsi rad(x).
Fungsi akar kuadrat di Euler dinamakan sqrt. Tentu saja, penggunaan
x^(1/2) juga dimungkinkan.


Untuk menetapkan variabel, gunakan "=" atau ":=". Demi kejelasan,
pengenalan ini menggunakan bentuk yang terakhir (:=). Spasi tidak
memengaruhi proses, tetapi spasi antaperintah tetap diperlukan..


Untuk menetapkan variabel, gunakan "=" atau ":=". Demi kejelasan,
pengenalan ini menggunakan bentuk yang terakhir. Spasi tidak
berpengaruh. Namun, spasi antaperintah tetap diperlukan.


\>g:=9.81; t:=2.5; 1/2\*g\*t^2


    30.65625

EMT menggunakan sintaks pemrograman untuk ekspresi. Untuk memasukkan


$$e^2 \cdot \left( \frac{1}{3+4 \log(0.6)}+\frac{1}{7} \right)$$Anda harus mengatur tanda kurung dengan benar dan menggunakan / untuk
pecahan. Perhatikan tanda kurung yang tersorot untuk membantu Anda.
Perhatikan bahwa konstanta Euler $e$ dinamakan E di EMT.


\>E^2\*(1/(3+4\*log(0.6))+1/7)


    8.77908249441

Untuk menghitung ekspresi rumit seperti


$$\left(\frac{\frac17 + \frac18 + 2}{\frac13 + \frac12}\right)^2 \pi$$Anda harus memasukkannya dalam bentuk satu baris (line form).


\>((1/7 + 1/8 + 2) / (1/3 + 1/2))^2 \* pi


    23.2671801626

Letakkan tanda kurung secara hati-hati di sekitar sub-ekspresi yang
perlu dihitung terlebih dahulu. EMT membantu Anda dengan menyorot
ekspresi yang diakhiri oleh tanda kurung tutup tersebut. Anda juga
harus memasukkan nama "pi" untuk huruf Yunani pi.


Hasil dari perhitungan ini adalah angka titik kambang (floating point
number). Secara standar, angka ini dicetak dengan akurasi sekitar 12
digit. Pada baris perintah berikut, kita juga akan mempelajari
bagaimana cara mengacu pada hasil sebelumnya dalam baris yang sama.


\>1/3+1/7, fraction %


    0.47619047619
    10/21

Perintah Euler dapat berupa sebuah ekspresi atau perintah primitif.
Sebuah ekspresi terdiri dari operator dan fungsi. Jika diperlukan,
ekspresi tersebut harus memuat tanda kurung untuk memaksa urutan
eksekusi yang benar. Jika ragu, menambahkan tanda kurung adalah
langkah yang baik. Perhatikan bahwa EMT menampilkan tanda kurung buka
dan tutup saat Anda mengedit baris perintah.


\>(cos(pi/4)+1)^3\*(sin(pi/4)+1)^2


    14.4978445072

Operator numerik di Euler meliputi:


 + uner atau operator plus  
 - uner atau operator minus  
 *, /  
 . perkalian matriks  
 a^b perpangkatan untuk a positif atau b bulat (ab juga dapat  

digunakan)


 n! operator faktorial


dan masih banyak lagi.


Berikut adalah beberapa fungsi yang mungkin Anda perlukan. Ada banyak
fungsi lainnya.


sin,cos,tan,atan,asin,acos,rad,deg


og,exp,log10,sqrt,logbase


in,logbin,logfac,mod,floor,ceil,round,abs,sign


onj,re,im,arg,conj,real,complex


eta,betai,gamma,complexgamma,ellrf,ellf,ellrd,elle


itand,bitor,bitxor,bitnot


Beberapa perintah memiliki alias (nama lain), misalnya ln untuk log.


\>ln(E^2), arctan(tan(0.5))


    2
    0.5

\>sin(30°)


    0.5

Pastikan untuk menggunakan tanda kurung (kurung biasa) kapan pun ada
keraguan tentang urutan eksekusi! Perintah berikut tidak sama dengan
(2^3)^4, yang merupakan standar untuk 2^3^4 di EMT (beberapa sistem
numerik melakukannya dengan cara sebaliknya).


\>2^3^4, (2^3)^4, 2^(3^4)


    2.41785163923e+24
    4096
    2.41785163923e+24

## Bilangan Real

Tipe data utama di Euler adalah bilangan real. Bilangan real diwakili
dalam format IEEE dengan akurasi sekitar 16 digit desimal


\>longest 1/3


         0.3333333333333333 

Representasi ganda internal membutuhkan 8 byte.


\>printdual(1/3)


    1.0101010101010101010101010101010101010101010101010101*2^-2

\>printhex(1/3)


    5.5555555555554*16^-1

## Strings

String di Euler didefinisikan dengan "...".


\>"A string can contain anything."


    A string can contain anything.

String dapat digabungkan dengan operator | atau +. Hal ini juga
berlaku untuk angka, yang mana angka tersebut akan dikonversi menjadi
string terlebih dahulu.


\>"The area of the circle with radius " + 2 + " cm is " + pi\*4 + " cm^2."


    The area of the circle with radius 2 cm is 12.5663706144 cm^2.

Fungsi print juga dapat mengonversi angka menjadi string. Fungsi ini
dapat menerima jumlah digit, jumlah tempat desimal (0 untuk output
yang rapat), dan secara optimal sebuah satuan.


\>"Golden Ratio : " + print((1+sqrt(5))/2,5,0)


    Golden Ratio : 1.61803

Terdapat string khusus none, yang tidak dicetak. String ini
dikembalikan oleh beberapa fungsi ketika hasilnya tidak penting.
(String ini dikembalikan secara otomatis jika fungsi tersebut tidak
memiliki pernyataan return).


\>none


Untuk mengonversi string menjadi angka, cukup evaluasi string
tersebut. Cara ini juga berlaku untuk ekspresi (lihat di bawah).


\>"1234.5"()


    1234.5

Untuk mendefinisikan vektor string, gunakan notasi vektor [...].


\>v:=["affe","charlie","bravo"]


    affe
    charlie
    bravo

Vektor string kosong dilambangkan dengan [none]. Vektor string dapat
digabungkan.


\>w:=[none]; w|v|v


    affe
    charlie
    bravo
    affe
    charlie
    bravo

String dapat memuat karakter Unicode. Secara internal, string ini
berisi kode UTF-8. Untuk menghasilkan string tersebut, gunakan u"..."
dan salah satu entitas HTML.


String Unicode dapat digabungkan seperti string lainnya.


\>u"&alpha; = " + 45 + u"&deg;" // pdfLaTeX mungkin gagal menampilkan secara benar


    Î± = 45Â°

I


Dalam komentar, entitas yang sama seperti α, β, dan
sebagainya dapat digunakan. Ini bisa menjadi alternatif cepat untuk
LaTeX. (Rincian lebih lanjut tentang komentar ada di bawah).


Terdapat beberapa fungsi untuk membuat atau menganalisis string
Unicode. Fungsi strtochar() akan mengenali string Unicode dan
menerjemahkannya dengan benar.


\>v=strtochar(u"&Auml; is a German letter")


    [196,  32,  105,  115,  32,  97,  32,  71,  101,  114,  109,  97,  110,
    32,  108,  101,  116,  116,  101,  114]

Hasilnya berupa vektor angka Unicode. Fungsi kebalikannya adalah
chartoutf().


\>v[1]=strtochar(u"&Uuml;")[1]; chartoutf(v)


    Ãœ is a German letter

Fungsi utf() dapat menerjemahkan string yang berisi entitas di dalam
sebuah variabel menjadi string Unicode.


\>s="We have &alpha;=&beta;."; utf(s) // pdfLaTeX mungkin gagal menampilkan secara benar


    We have Î±=Î².

Juga dimungkinkan untuk menggunakan entitas numerik.


\>u"&#196;hnliches"


    Ã„hnliches

## Nilai Boolean

Nilai Boolean diwakili dengan 1=true atau 0=false di Euler. String
dapat dibandingkan, sama seperti angka.


\>2<1, "apel"<"banana"


    0
    1

"and" adalah operator "&amp;&amp;" dan "or" adalah operator "||", seperti
dalam bahasa C. (Kata "and" dan "or" hanya dapat digunakan dalam
kondisi untuk "if".)


\>2<E && E<3


    1

Operator Boolean mematuhi aturan bahasa matriks.


\>(1:10)\>5, nonzeros(%)


    [0,  0,  0,  0,  0,  1,  1,  1,  1,  1]
    [6,  7,  8,  9,  10]

Anda dapat menggunakan fungsi nonzeros() untuk mengekstrak elemen
tertentu dari sebuah vektor. Dalam contoh ini, kita menggunakan
kondisi isprime(n).


\>N=2|3:2:99 // N berisi elemen 2 dan bilangan2 ganjil dari 3 s.d. 99


    [2,  3,  5,  7,  9,  11,  13,  15,  17,  19,  21,  23,  25,  27,  29,
    31,  33,  35,  37,  39,  41,  43,  45,  47,  49,  51,  53,  55,  57,
    59,  61,  63,  65,  67,  69,  71,  73,  75,  77,  79,  81,  83,  85,
    87,  89,  91,  93,  95,  97,  99]

\>N[nonzeros(isprime(N))] //pilih anggota2 N yang prima


    [2,  3,  5,  7,  11,  13,  17,  19,  23,  29,  31,  37,  41,  43,  47,
    53,  59,  61,  67,  71,  73,  79,  83,  89,  97]

## Format Output

Format output bawaan (default) pada EMT mencetak 12 digit. Untuk
memastikan bahwa kita melihat format bawaan, kita mereset format
tersebut.


\>defformat; pi


    3.14159265359

Secara internal, EMT menggunakan standar IEEE untuk angka presisi
ganda (double) dengan sekitar 16 digit desimal. Untuk melihat jumlah
digit selengkapnya, gunakan perintah "longestformat", atau kita
menggunakan operator "longest" untuk menampilkan hasil dalam format
terpanjang.


\>longest pi


          3.141592653589793 

Berikut adalah representasi heksadesimal internal dari angka double.


\>printhex(pi)


    3.243F6A8885A30*16^0

Format output dapat diubah secara permanen dengan perintah format.


\>format(12,5); 1/3, pi, sin(1)


        0.33333 
        3.14159 
        0.84147 

Format bawaan adalah format(12).


\>format(12); 1/3


         0.333333333333 

Fungsi seperti "shortestformat", "shortformat", dan "longformat"
bekerja untuk vektor dengan cara berikut.


\>shortestformat; random(3,8)


      0.66    0.2   0.89   0.28   0.53   0.31   0.44    0.3 
      0.28   0.88   0.27    0.7   0.22   0.45   0.31   0.91 
      0.19   0.46  0.095    0.6   0.43   0.73   0.47   0.32 

Format bawaan untuk skalar adalah format(12). Namun, hal ini dapat
diubah.


\>setscalarformat(5); pi


    3.1416

Fungsi "longestformat" juga mengatur format skalar.


\>longestformat; pi


    3.141592653589793

Sebagai referensi, berikut adalah daftar format output yang paling
penting.


shortestformat shortformat longformat, longestformat


ormat(length,digits) goodformat(length)


racformat(length)


efformat


Akurasi internal EMT adalah sekitar 16 tempat desimal, yang merupakan
standar IEEE. Angka disimpan dalam format internal ini.


Namun, format output EMT dapat diatur secara fleksibel.


\>longestformat; pi,


    3.141592653589793

\>format(10,5); pi


      3.14159 

Nilai bawaan adalah defformat().


\>defformat; // default


Terdapat operator singkat yang hanya mencetak satu nilai. Operator
"longest" akan mencetak semua digit valid dari suatu angka.


\>longest pi^2/2


          4.934802200544679 

Terdapat juga operator singkat untuk mencetak hasil dalam format
pecahan (fractional format). Kita telah menggunakannya di atas.


\>fraction 1+1/2+1/3+1/4


    25/12

Karena format internal menggunakan cara biner untuk menyimpan angka,
nilai 0,1 tidak akan terwakili secara persis. Galat (error) tersebut
akan terakumulasi sedikit, seperti yang Anda lihat pada perhitungan
berikut.


\>longest 0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1-1


     -1.110223024625157e-16 

Namun, dengan "longformat" bawaan, Anda tidak akan menyadarinya. Untuk
kemudahan, output dari angka yang sangat kecil adalah 0.


\>0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1+0.1-1


    0

# Ekspresi

String atau nama dapat digunakan untuk menyimpan ekspresi matematika,
yang kemudian dapat dievaluasi oleh EMT. Untuk melakukan ini, gunakan
tanda kurung setelah ekspresi. Jika Anda bermaksud menggunakan string
sebagai ekspresi, gunakan konvensi penamaan seperti "fx" atau "fxy",
dan seterusnya. Ekspresi memiliki prioritas lebih tinggi daripada
fungsi.


Variabel global dapat digunakan dalam evaluasi tersebut.


\>r:=2; fx:="pi\*r^2"; longest fx()


          12.56637061435917 

Parameter ditetapkan ke x, y, dan z sesuai urutan tersebut. Parameter
tambahan dapat ditambahkan menggunakan parameter yang ditetapkan.


\>fx:="a\*sin(x)^2"; fx(5,a=-1)


    -0.919535764538

Perlu dicatat bahwa ekspresi akan selalu menggunakan variabel global,
bahkan jika terdapat variabel dengan nama yang sama di dalam sebuah
fungsi. (Jika tidak demikian, evaluasi ekspresi di dalam fungsi dapat
memberikan hasil yang sangat membingungkan bagi pengguna yang
memanggil fungsi tersebut.)


\>at:=4; function f(expr,x,at) := expr(x); ...  
\>   f("at\*x^2",3,5) // computes 4\*3^2 not 5\*3^2


    36

Jika Anda ingin menggunakan nilai "at" yang berbeda dari nilai global,
Anda perlu menambahkan at=nilai.


\>at:=4; function f(expr,x,a) := expr(x,at=a); ...  
\>   f("at\*x^2",3,5)


    45

Sebagai referensi, perlu dicatat bahwa call collections (yang dibahas
di tempat lain) dapat berisi ekspresi. Dengan demikian, kita dapat
membuat contoh di atas sebagai berikut.


\>at:=4; function f(expr,x) := expr(x); ...  
\>   f({{"at\*x^2",at=5}},3)


    45

Ekspresi dalam x sering kali digunakan persis seperti fungsi.


Perlu dicatat bahwa mendefinisikan sebuah fungsi dengan nama yang sama
seperti ekspresi simbolik global akan menghapus variabel tersebut
untuk menghindari kebingungan antara ekspresi simbolik dan fungsi.


\>f &= 5\*x;

\>function f(x) := 6\*x;

\>f(2)


    12

Sesuai konvensi, ekspresi simbolik atau numerik sebaiknya diberi nama
fx, fxy, dan sejenisnya. Skema penamaan ini tidak boleh digunakan
untuk fungsi.


\>fx &= diff(x^x,x); $&fx


$$x^{x}\,\left(\log x+1\right)$$Bentuk khusus dari suatu ekspresi memungkinkan variabel apa pun
digunakan sebagai parameter tanpa nama (unnamed parameter) dalam
evaluasi ekspresi tersebut, tidak hanya "x", "y", dan sejenisnya.
Untuk melakukan ini, awali ekspresi dengan @(variabel) ... .


\>"@(a,b) a^2+b^2", %(4,5)


    @(a,b) a^2+b^2
    41

Hal ini memungkinkan untuk memanipulasi ekspresi dalam variabel lain
untuk fungsi-fungsi EMT yang membutuhkan ekspresi dalam variabel "x".


Cara paling dasar untuk mendefinisikan fungsi sederhana adalah dengan
menyimpan rumusnya dalam ekspresi simbolik atau numerik. Jika variabel
utamanya adalah x, ekspresi tersebut dapat dievaluasi layaknya sebuah
fungsi.


Seperti yang Anda lihat pada contoh berikut, variabel global tetap
dapat diakses (visible) selama proses evaluasi.


\>fx &= x^3-a\*x;  ...  
\>   a=1.2; fx(0.5)


    -0.475

Semua variabel lain dalam ekspresi tersebut dapat ditentukan saat
evaluasi menggunakan parameter yang telah diberikan.


\>fx(0.5,a=1.1)


    -0.425

Sebuah ekspresi tidak harus bersifat simbolik. Hal ini diperlukan jika
ekspresi tersebut mengandung fungsi-fungsi yang hanya dikenali di
dalam kernel numerik, bukan di dalam Maxima.


# Matematika Simbolik

EMT melakukan komputasi matematika simbolik dengan bantuan Maxima.
Untuk detail lebih lanjut, mulailah dengan tutorial berikut, atau
telusuri referensi untuk Maxima. Bagi para ahli Maxima, perlu dicatat
bahwa terdapat perbedaan sintaksis antara sintaks asli Maxima dan
sintaks bawaan (default) untuk ekspresi simbolik di EMT.


Matematika simbolik terintegrasi secara mulus ke dalam Euler
menggunakan simbol &amp;. Setiap ekspresi yang diawali dengan &amp; merupakan
ekspresi simbolik. Ekspresi tersebut akan dievaluasi dan ditampilkan
oleh Maxima.


Pertama-tama, Maxima memiliki aritmatika "tak terbatas" yang dapat
menangani angka-angka berukuran sangat besar.


\>$&44!


$$2658271574788448768043625811014615890319638528000000000$$Dengan cara ini, Anda dapat menghitung hasil yang besar secara tepat.
Mari kita hitung


$$C(44,10) = \frac{44!}{34! \cdot 10!}$$\>$& 44!/(34!\*10!) // nilai C(44,10)


$$2481256778$$Tentu saja, Maxima memiliki fungsi yang lebih efisien untuk hal ini
(seperti halnya pada bagian numerik di EMT).


\>$binomial(44,10) //menghitung C(44,10) menggunakan fungsi binomial()


$$2481256778$$Untuk mempelajari lebih lanjut tentang fungsi tertentu, klik dua kali
pada fungsi tersebut. Contohnya, cobalah mengklik dua kali pada
"&amp;binomial" di baris perintah sebelumnya. Ini akan membuka dokumentasi
Maxima seperti yang disediakan oleh pembuat program tersebut.


Anda akan mempelajari bahwa cara berikut juga dapat bekerja.


$$C(x,3)=\frac{x!}{(x-3)!3!}=\frac{(x-2)(x-1)x}{6}$$\>$binomial(x,3) // C(x,3)


$$\frac{\left(x-2\right)\,\left(x-1\right)\,x}{6}$$Jika Anda ingin mengganti x dengan nilai tertentu, gunakan "with".


\>$&binomial(x,3) with x=10 // substitusi x=10 ke C(x,3)


$$120$$Dengan cara itu, Anda dapat menggunakan solusi dari suatu persamaan ke
dalam persamaan lainnya.


Ekspresi simbolik ditampilkan oleh Maxima dalam bentuk 2D. Alasan di
balik hal ini adalah adanya bendera (flag) simbolik khusus di dalam
string.


Seperti yang telah Anda lihat pada contoh-contoh sebelumnya dan
selanjutnya, jika Anda telah menginstal LaTeX, Anda dapat menampilkan
ekspresi simbolik menggunakan LaTeX. Jika tidak, perintah berikut akan
mengeluarkan pesan kesalahan.


Untuk menampilkan ekspresi simbolik dengan LaTeX, gunakan simbol $ di
depan &amp; (atau Anda dapat menghilangkan &amp;) sebelum perintah tersebut.
Jangan jalankan perintah Maxima menggunakan $ jika Anda tidak
menginstal LaTeX.


\>$(3+x)/(x^2+1)


$$\frac{x+3}{x^2+1}$$Ekspresi simbolik diproses (parsed) oleh Euler. Jika Anda membutuhkan
sintaksis yang kompleks dalam satu ekspresi, Anda dapat mengapit
ekspresi tersebut dengan tanda petik "...". Menggunakan lebih dari
satu ekspresi sederhana memang dimungkinkan, tetapi sangat tidak
disarankan.


\>&"v := 5; v^2"


    
                                      25
    

Sebagai pelengkap, perlu kami sampaikan bahwa ekspresi simbolik dapat
digunakan dalam program, tetapi harus diapit dengan tanda petik.
Selain itu, jauh lebih efektif untuk memanggil Maxima pada saat proses
kompilasi (compile time) jika memungkinkan.


\>$&expand((1+x)^4), $&factor(diff(%,x)) // diff: turunan, factor: faktor


$$4\,\left(x+1\right)^3$$![images/TugasAplikom3Adi25030630001-027.png](images/TugasAplikom3Adi25030630001-027.png)

Sekali lagi, % mengacu pada hasil sebelumnya.


Untuk mempermudah, kita menyimpan solusinya ke dalam variabel
simbolik. Variabel simbolik didefinisikan dengan &amp;=.


\>fx &= (x+1)/(x^4+1); $&fx


$$\frac{x+1}{x^4+1}$$Ekspresi simbolik dapat digunakan di dalam ekspresi simbolik lainnya.


\>$&factor(diff(fx,x))


$$\frac{-3\,x^4-4\,x^3+1}{\left(x^4+1\right)^2}$$Input langsung untuk perintah Maxima juga tersedia. Mulailah baris
perintah dengan ::. Sintaksis Maxima telah disesuaikan dengan
sintaksis EMT (yang disebut "mode kompatibilitas" atau compatibility
mode).


\>&factor(20!)


    
                             2432902008176640000
    

\>::: factor(10!)


    
                                   8  4  2
                                  2  3  5  7
    

\>:: factor(20!)


    
                            18  8  4  2
                           2   3  5  7  11 13 17 19
    

Jika Anda seorang ahli dalam Maxima, Anda mungkin ingin menggunakan
sintaksis asli dari Maxima. Anda dapat melakukannya dengan :::.


\>::: av:g$ av^2;


    
                                       2
                                      g
    

\>fx &= x^3\*exp(x), $fx


    
                                     3  x
                                    x  E
    

$$x^3\,e^{x}$$Such variables can be used in other symbolic expressions. Note, that in the
following command the right hand side of &amp;= is evaluated before the
assignment to Fx.


\>&(fx with x=5), $%, &float(%)


    
                                         5
                                    125 E
    

$$125\,e^5$$    
                              18551.64488782208
    

\>fx(5)


    18551.6448878

Untuk mengevaluasi suatu ekspresi dengan nilai variabel tertentu, Anda
dapat menggunakan operator "with".


Baris perintah berikut juga menunjukkan bahwa Maxima dapat
mengevaluasi suatu ekspresi secara numerik menggunakan float().


\>&(fx with x=10)-(fx with x=5), &float(%)


    
                                    10        5
                              1000 E   - 125 E
    
    
                             2.20079141499189e+7
    

\>$factor(diff(fx,x,2))


$$x\,\left(x^2+6\,x+6\right)\,e^{x}$$Untuk mendapatkan kode LaTeX dari suatu ekspresi, Anda dapat
menggunakan perintah tex.


\>tex(fx)


    x^3\,e^{x}

Ekspresi simbolik dapat dievaluasi sama seperti ekspresi numerik.


\>fx(0.5)


    0.206090158838

Dalam ekspresi simbolik, hal ini tidak berlaku karena Maxima tidak
mendukungnya. Sebagai gantinya, gunakan sintaksis "with" (bentuk yang
lebih baik dari perintah at(...) pada Maxima).


\>$&fx with x=1/2


$$\frac{\sqrt{e}}{8}$$Penugasan (assignment) juga dapat bersifat simbolik.


\>$&fx with x=1+t


$$\left(t+1\right)^3\,e^{t+1}$$Perintah solve menyelesaikan ekspresi simbolik untuk suatu variabel di
Maxima. Hasilnya berupa vektor solusi.


\>$&solve(x^2+x=4,x)


$$\left[ x=\frac{-\sqrt{17}-1}{2} , x=\frac{\sqrt{17}-1}{2} \right] $$Bandingkan dengan perintah "solve" numerik di Euler, yang memerlukan
nilai awal, dan secara opsional nilai target.


\>solve("x^2+x",1,y=4)


    1.56155281281

Nilai-nilai numerik dari solusi simbolik dapat dihitung dengan
mengevaluasi hasil simbolik tersebut. Euler akan membaca penugasan
seperti x= dan seterusnya. Jika Anda tidak memerlukan hasil numerik
untuk perhitungan lebih lanjut, Anda juga dapat membiarkan Maxima
menemukan nilai-nilai numerik tersebut.


\>sol &= solve(x^2+2\*x=4,x); $&sol, sol(), $&float(sol)


$$\left[ x=-\sqrt{5}-1 , x=\sqrt{5}-1 \right] $$    [-3.23607,  1.23607]

$$\left[ x=-3.23606797749979 , x=1.23606797749979 \right] $$Untuk mendapatkan solusi simbolik tertentu, Anda dapat menggunakan
"with" dan sebuah indeks.


\>$&solve(x^2+x=1,x), x2 &= x with %[2]; $&x2


$$\frac{\sqrt{5}-1}{2}$$![images/TugasAplikom3Adi25030630001-039.png](images/TugasAplikom3Adi25030630001-039.png)

Untuk menyelesaikan sistem persamaan, gunakan vektor persamaan.
Hasilnya berupa vektor solusi.


\>sol &= solve([x+y=3,x^2+y^2=5],[x,y]); $&sol, $&x\*y with sol[1]


$$2$$![images/TugasAplikom3Adi25030630001-041.png](images/TugasAplikom3Adi25030630001-041.png)

SymEkspresi simbolik dapat memiliki flag, yang menunjukkan penanganan
khusus di Maxima. Beberapa flag juga dapat digunakan sebagai perintah,
sementara yang lain tidak bisa. Flag ditambahkan dengan tanda "|"
(bentuk yang lebih baik dari "ev(..., flags)")


\>$& diff((x^3-1)/(x+1),x) //turunan bentuk pecahan


$$\frac{3\,x^2}{x+1}-\frac{x^3-1}{\left(x+1\right)^2}$$\>$& diff((x^3-1)/(x+1),x) | ratsimp //menyederhanakan pecahan


$$\frac{2\,x^3+3\,x^2+1}{x^2+2\,x+1}$$\>$&factor(%)


$$\frac{2\,x^3+3\,x^2+1}{\left(x+1\right)^2}$$# Fungsi

Di EMT, fungsi adalah program yang didefinisikan dengan perintah
"function". Fungsi dapat berupa fungsi satu baris (one-line function)
atau fungsi banyak baris (multiline function).


ungsi satu baris dapat bersifat numerik atau simbolik. Fungsi satu
baris yang bersifat numerik didefinisikan dengan ":=".


\>function f(x) := x\*sqrt(x^2+1)


Sebagai gambaran umum, kami menampilkan semua kemungkinan definisi
untuk fungsi satu baris. Sebuah fungsi dapat dievaluasi seperti halnya
fungsi bawaan Euler mana pun.


\>f(2)


    4.472135955

Fungsi ini juga dapat bekerja untuk vektor, mengikuti bahasa matriks
dari Euler, karena ekspresi yang digunakan dalam fungsi tersebut sudah
tervektorisasi (vectorized).


\>f(0:0.1:1)


    [0,  0.100499,  0.203961,  0.313209,  0.430813,  0.559017,  0.699714,
    0.854459,  1.0245,  1.21083,  1.41421]

Fungsi dapat diplot. Sebagai ganti ekspresi, kita hanya perlu
memberikan nama fungsinya.


Berbeda dengan ekspresi simbolik atau numerik, nama fungsi harus
diberikan dalam bentuk string.


\>solve("f",1,y=1)


    0.786151377757

Secara bawaan (by default), jika Anda perlu menimpa fungsi bawaan
(built-in function), Anda harus menambahkan kata kunci "overwrite".
Menimpa fungsi bawaan sangat berbahaya dan dapat menyebabkan masalah
bagi fungsi-fungsi lain yang mengandalkannya.


Anda masih dapat memanggil fungsi bawaan tersebut sebagai "_...", jika
fungsi tersebut berada di dalam core Euler.


\>function overwrite sin (x) := \_sin(x°) // redine sine in degrees

\>sin(45)


    0.707106781187

Sebaiknya kita menghapus pendefinisian ulang sin ini.


\>forget sin; sin(pi/4)


    0.707106781187

## Parameter Bawaan (Default Parameters)

Fungsi numerik dapat memiliki parameter bawaan (default parameters).


\>function f(x,a=1) := a\*x^2


Mengosongkan parameter ini akan menggunakan nilai bawaannya (default
value).


\>f(4)


    16

Menyetel (setting) nilai parameter tersebut akan menimpa nilai
bawaannya (default value).


\>f(4,5)


    80

Parameter yang ditetapkan secara eksplisit (assigned parameter) juga
akan menimpa nilai bawaan tersebut. Mekanisme ini digunakan oleh
banyak fungsi di Euler, seperti plot2d dan plot3d.


\>f(4,a=1)


    16

Jika sebuah variabel bukan merupakan parameter, variabel tersebut
haruslah bernilai global. Fungsi satu baris (one-line function) dapat
membaca dan mengakses variabel-variabel global.


\>function f(x) := a\*x^2

\>a=6; f(2)


    24

Tetapi, parameter yang ditetapkan (assigned parameter) akan menimpa
nilai global tersebut.


Jika argumen tersebut tidak ada dalam daftar parameter yang telah
ditentukan sebelumnya, argumen harus dideklarasikan menggunakan ":="!


\>f(2,a:=5)


    20

Fungsi simbolik didefinisikan dengan "&amp;=". Fungsi ini didefinisikan di
Euler dan Maxima, serta dapat bekerja di kedua lingkungan tersebut.
Ekspresi pendefinisiannya diproses melalui Maxima terlebih dahulu
sebelum didefinisikan.


\>function g(x) &= x^3-x\*exp(-x); $&g(x)


$$x^3-x\,e^ {- x }$$Fungsi simbolik dapat digunakan dalam ekspresi simbolik.


\>$&diff(g(x),x), $&% with x=4/3


$$\frac{e^ {- \frac{4}{3} }}{3}+\frac{16}{3}$$![images/TugasAplikom3Adi25030630001-047.png](images/TugasAplikom3Adi25030630001-047.png)

Fungsi tersebut juga dapat digunakan dalam ekspresi numerik. Tentu
saja, hal ini hanya akan bekerja jika EMT dapat menginterpretasikan
seluruh isi di dalam fungsi tersebut.


\>g(5+g(1))


    178.635099908

Fungsi simbolik dapat digunakan untuk mendefinisikan fungsi atau
ekspresi simbolik lainnya.


\>function G(x) &= factor(integrate(g(x),x)); $&G(c) // integrate: mengintegralkan


$$\frac{e^ {- c }\,\left(c^4\,e^{c}+4\,c+4\right)}{4}$$\>solve(&g(x),0.5)


    0.703467422498

Proses ini juga dapat bekerja, karena Euler akan menggunakan ekspresi
simbolik dalam fungsi g jika tidak menemukan variabel simbolik g,
serta jika terdapat fungsi simbolik g.


\>solve(&g,0.5)


    0.703467422498

\>function P(x,n) &= (2\*x-1)^n; $&P(x,n)


$$\left(2\,x-1\right)^{n}$$\>function Q(x,n) &= (x+2)^n; $&Q(x,n)


$$\left(x+2\right)^{n}$$\>$&P(x,4), $&expand(%)


$$16\,x^4-32\,x^3+24\,x^2-8\,x+1$$![images/TugasAplikom3Adi25030630001-052.png](images/TugasAplikom3Adi25030630001-052.png)

\>P(3,4)


    625

\>$&P(x,4)+ Q(x,3), $&expand(%)


$$16\,x^4-31\,x^3+30\,x^2+4\,x+9$$![images/TugasAplikom3Adi25030630001-054.png](images/TugasAplikom3Adi25030630001-054.png)

\>$&P(x,4)-Q(x,3), $&expand(%), $&factor(%)


$$16\,x^4-33\,x^3+18\,x^2-20\,x-7$$![images/TugasAplikom3Adi25030630001-056.png](images/TugasAplikom3Adi25030630001-056.png)

![images/TugasAplikom3Adi25030630001-057.png](images/TugasAplikom3Adi25030630001-057.png)

\>$&P(x,4)\*Q(x,3), $&expand(%), $&factor(%)


$$\left(x+2\right)^3\,\left(2\,x-1\right)^4$$![images/TugasAplikom3Adi25030630001-059.png](images/TugasAplikom3Adi25030630001-059.png)

![images/TugasAplikom3Adi25030630001-060.png](images/TugasAplikom3Adi25030630001-060.png)

\>$&P(x,4)/Q(x,1), $&expand(%), $&factor(%)


$$\frac{\left(2\,x-1\right)^4}{x+2}$$![images/TugasAplikom3Adi25030630001-062.png](images/TugasAplikom3Adi25030630001-062.png)

![images/TugasAplikom3Adi25030630001-063.png](images/TugasAplikom3Adi25030630001-063.png)

\>function f(x) &= x^3-x; $&f(x)


$$x^3-x$$Dengan perintah &amp;=, fungsi tersebut bersifat simbolik dan dapat
digunakan dalam ekspresi simbolik lainnya.


\>$&integrate(f(x),x)


$$\frac{x^4}{4}-\frac{x^2}{2}$$Dengan :=, fungsi tersebut bersifat numerik. Contoh yang baik adalah
integral tentu seperti


$$f(x) = \int_1^x t^t \, dt,$$yang tidak dapat dievaluasi secara simbolik.


Jika kita mendefinisikan ulang fungsi tersebut dengan kata kunci
"map", fungsi dapat digunakan untuk vektor x. Secara internal, fungsi
akan dipanggil untuk setiap nilai dalam x satu per satu, lalu hasilnya
disimpan dan dikembalikan dalam bentuk vektor.


\>function map f(x) := integrate("x^x",1,x)

\>f(0:0.5:2)


    [-0.783431,  -0.410816,  0,  0.676863,  2.05045]

Fungsi dapat memiliki nilai bawaan (default values) untuk
parameter-parameternya.


\>function mylog (x,base=10) := ln(x)/ln(base);


Sekarang, fungsi tersebut dapat dipanggil dengan atau tanpa parameter
"base".


\>mylog(100), mylog(2^6.7,2)


    2
    6.7

Selain itu, kita juga dapat menggunakan parameter yang ditetapkan
secara eksplisit (assigned parameters).


\>mylog(E^2,base=E)


    2

Sering kali, kita ingin menggunakan fungsi untuk vektor di satu
tempat, dan untuk elemen individual di tempat lain. Hal ini dapat
dilakukan dengan menggunakan parameter vektor (*vector parameters*).


\>function f([a,b]) &= a^2+b^2-a\*b+b; $&f(a,b), $&f(x,y)


$$y^2-x\,y+y+x^2$$![images/TugasAplikom3Adi25030630001-068.png](images/TugasAplikom3Adi25030630001-068.png)

Fungsi simbolik tersebut dapat digunakan untuk variabel simbolik.


Namun, fungsi ini juga dapat digunakan langsung untuk vektor numerik.


\>v=[3,4]; f(v)


    17

Ada juga fungsi yang murni simbolik, yang tidak dapat digunakan secara
numerik.


\>function lapl(expr,x,y) &&= diff(expr,x,2)+diff(expr,y,2)//turunan parsial kedua


    
                     diff(expr, y, 2) + diff(expr, x, 2)
    

\>$&realpart((x+I\*y)^4), $&lapl(%,x,y)


$$0$$![images/TugasAplikom3Adi25030630001-070.png](images/TugasAplikom3Adi25030630001-070.png)

Namun tentu saja, fungsi tersebut dapat digunakan dalam ekspresi
simbolik atau dalam pendefinisian fungsi simbolik lainnya.


\>function f(x,y) &= factor(lapl((x+y^2)^5,x,y)); $&f(x,y)


$$10\,\left(y^2+x\right)^3\,\left(9\,y^2+x+2\right)$$Ringkasan:


* 
&amp;= mendefinisikan fungsi simbolik,

* 
:= mendefinisikan fungsi numerik,

* 
&amp;&amp;= mendefinisikan fungsi murni simbolik.
* Menyelesaikan Ekspresi


Ekspresi dapat diselesaikan secara numerik dan simbolik.


Untuk menyelesaikan ekspresi sederhana dari satu variabel, kita dapat
menggunakan fungsi solve(). Fungsi ini memerlukan nilai awal untuk
memulai pencarian. Secara internal, solve() menggunakan metode secant.


\>solve("x^2-2",1)


    1.41421356237

Hal ini berlaku juga untuk ekspresi simbolik. Perhatikan fungsi
berikut.


\>$&solve(x^2=2,x)


$$\left[ x=-\sqrt{2} , x=\sqrt{2} \right] $$\>$&solve(x^2-2,x)


$$\left[ x=-\sqrt{2} , x=\sqrt{2} \right] $$\>$&solve(a\*x^2+b\*x+c=0,x)


$$\left[ x=\frac{-\sqrt{b^2-4\,a\,c}-b}{2\,a} , x=\frac{\sqrt{b^2-4\,  a\,c}-b}{2\,a} \right] $$\>$&solve([a\*x+b\*y=c,d\*x+e\*y=f],[x,y])


$$\left[ \left[ x=-\frac{c\,e}{b\,\left(d-5\right)-a\,e} , y=\frac{c  \,\left(d-5\right)}{b\,\left(d-5\right)-a\,e} \right]  \right] $$\> px &= 4\*x^8+x^7-x^4-x; $&px


$$4\,x^8+x^7-x^4-x$$Sekarang kita mencari titik, di mana polinomial bernilai 2. Dalam
solve(), nilai target bawaan y=0 dapat diubah dengan variabel yang
ditetapkan. Kita menggunakan y=2 dan memeriksanya dengan mengevaluasi
polinomial pada hasil sebelumnya.


\>solve(px,1,y=2), px(%)


    0.966715594851
    2

Menyelesaikan ekspresi simbolik dalam bentuk simbolik akan
mengembalikan daftar solusi. Kita menggunakan pemecah simbolik
(*symbolic solver*) `solve()` yang disediakan oleh Maxima.


\>sol &= solve(x^2-x-1,x); $&sol


$$\left[ x=\frac{1-\sqrt{5}}{2} , x=\frac{\sqrt{5}+1}{2} \right] $$Cara termudah untuk mendapatkan nilai numeriknya adalah dengan
mengevaluasi solusi tersebut secara numerik persis seperti sebuah
ekspresi.


\>longest sol()


        -0.6180339887498949       1.618033988749895 

Cara termudah untuk menggunakan solusi tersebut secara simbolik dalam
ekspresi lain adalah dengan menggunakan perintah "with".


\>$&x^2 with sol[1], $&expand(x^2-x-1 with sol[2])


$$0$$![images/TugasAplikom3Adi25030630001-079.png](images/TugasAplikom3Adi25030630001-079.png)

Menyelesaikan sistem persamaan secara simbolik dapat dilakukan dengan
vektor persamaan dan pemecah simbolik `solve()`. Jawabannya berupa
daftar dari daftar persamaan (*list of lists of equations*).


\>$&solve([x+y=2,x^3+2\*y+x=4],[x,y])


$$\left[ \left[ x=-1 , y=3 \right]  , \left[ x=1 , y=1 \right]  ,   \left[ x=0 , y=2 \right]  \right] $$Fungsi f() dapat melihat variabel global. Namun sering kali kita ingin
menggunakan parameter lokal.


$$a^x-x^a = 0.1$$dengan a=3.


\>function f(x,a) := x^a-a^x;


Salah satu cara untuk meneruskan parameter tambahan ke f() adalah
dengan menggunakan daftar berisi nama fungsi dan parameternya (cara
lainnya adalah parameter titik koma).


\>solve({{"f",3}},2,y=0.1)


    2.54116291558

Hal ini juga berlaku untuk ekspresi. Namun untuk kasus ini, elemen
daftar yang dinamai (*named list element*) harus digunakan.
(Penjelasan lebih lanjut mengenai daftar dapat dilihat pada tutorial
tentang sintaks EMT).


\>solve({{"x^a-a^x",a=3}},2,y=0.1)


    2.54116291558

# Menyelesaikan Pertidaksamaan

Untuk menyelesaikan pertidaksamaan, EMT tidak akan dapat melakukannya,
melainkan dengan bantuan Maxima, artinya secara eksak (simbolik).
Perintah Maxima yang digunakan adalah fourier_elim(), yang harus
dipanggil dengan perintah "load(fourier_elim)" terlebih dahulu.


\>&load(fourier\_elim)


    
            C:/Program Files/Euler x64/maxima/share/maxima/5.35.1/share/f\
    ourier_elim/fourier_elim.lisp
    

\>$&fourier\_elim([x^2 - 1\>0],[x]) // x^2-1 \> 0


$$\left[ 1<x \right] \lor \left[ x<-1 \right] $$\>$&fourier\_elim([x^2 - 1<0],[x]) // x^2-1 < 0


$$\left[ -1<x , x<1 \right] $$\>$&fourier\_elim([x^2 - 1 # 0],[x]) // x^-1 <\> 0


$$\left[ -1<x , x<1 \right] \lor \left[ 1<x \right] \lor \left[ x<-1   \right] $$\>$&fourier\_elim([x # 6],[x])


$$\left[ x<6 \right] \lor \left[ 6<x \right] $$\>$&fourier\_elim([x < 1, x \> 1],[x]) // tidak memiliki penyelesaian


$${\it emptyset}$$\>$&fourier\_elim([minf < x, x < inf],[x]) // solusinya R


$${\it universalset}$$\>$&fourier\_elim([x^3 - 1 \> 0],[x])


$$\left[ 1<x , x^2+x+1>0 \right] \lor \left[ x<1 , -x^2-x-1>0   \right] $$\>$&fourier\_elim([cos(x) < 1/2],[x]) // ??? gagal


$$\left[ 1-2\,\cos x>0 \right] $$\>$&fourier\_elim([y-x < 5, x - y < 7, 10 < y],[x,y]) // sistem pertidaksamaan


$$\left[ y-5<x , x<y+7 , 10<y \right] $$\>$&fourier\_elim([y-x < 5, x - y < 7, 10 < y],[y,x])


$$\left[ {\it max}\left(10 , x-7\right)<y , y<x+5 , 5<x \right] $$\>$&fourier\_elim((x + y < 5) and (x - y \>8),[x,y])


$$\left[ y+8<x , x<5-y , y<-\frac{3}{2} \right] $$\>$&fourier\_elim(((x + y < 5) and x < 1) or  (x - y \>8),[x,y])


$$\left[ y+8<x \right] \lor \left[ x<{\it min}\left(1 , 5-y\right)   \right] $$\>&fourier\_elim([max(x,y) \> 6, x # 8, abs(y-1) \> 12],[x,y])


    
            [6 &lt; x, x &lt; 8, y &lt; - 11] or [8 &lt; x, y &lt; - 11]
     or [x &lt; 8, 13 &lt; y] or [x = y, 13 &lt; y] or [8 &lt; x, x &lt; y, 13 &lt; y]
     or [y &lt; x, 13 &lt; y]
    

\>$&fourier\_elim([(x+6)/(x-9) <= 6],[x])


$$\left[ x=12 \right] \lor \left[ 12<x \right] \lor \left[ x<9   \right] $$# Bahasa Matriks

Dokumentasi inti EMT berisi pembahasan terperinci mengenai bahasa
matriks Euler.


Vektor dan matriks dimasukkan dengan tanda kurung siku, elemen
dipisahkan oleh koma, baris dipisahkan oleh titik koma.


\>A=[1,2;3,4]


                1             2 
                3             4 

Perkalian matriks dilambangkan dengan tanda titik.


\>b=[3;4]


                3 
                4 

\>b' // transpose b


    [3,  4]

\>inv(A) //inverse A


               -2             1 
              1.5          -0.5 

\>A.b //perkalian matriks


               11 
               25 

\>A.inv(A)


                1             0 
                0             1 

Poin utama dari bahasa matriks adalah bahwa semua fungsi dan operator
bekerja elemen demi elemen.


\>A.A


                7            10 
               15            22 

\>A^2 //perpangkatan elemen2 A


                1             4 
                9            16 

\>A.A.A


               37            54 
               81           118 

\>power(A,3) //perpangkatan matriks


               37            54 
               81           118 

\>A/A //pembagian elemen-elemen matriks yang seletak


                1             1 
                1             1 

\>A/b //pembagian elemen2 A oleh elemen2 b kolom demi kolom (karena b vektor kolom)


         0.333333      0.666667 
             0.75             1 

\>A\\b // hasilkali invers A dan b, A^(-1)b 


               -2 
              2.5 

\>inv(A).b


               -2 
              2.5 

\>A\\A   //A^(-1)A


                1             0 
                0             1 

\>inv(A).A


                1             0 
                0             1 

\>A\*A //perkalin elemen-elemen matriks seletak


                1             4 
                9            16 

Ini bukanlah perkalian matriks, melainkan perkalian elemen demi
elemen. Hal yang sama berlaku untuk vektor.


\>b^2 // perpangkatan elemen-elemen matriks/vektor


                9 
               16 

Jika salah satu operan berupa vektor atau skalar, operan tersebut
diekspansikan dengan cara yang alami (*natural way*).


\>2\*A


                2             4 
                6             8 

Sebagai contoh, jika operan berupa vektor kolom, elemen-elemennya
diterapkan ke semua baris A.


\>[1,2]\*A


                1             4 
                3             8 

Jika berupa vektor baris, operan tersebut diterapkan ke semua kolom A.


\>A\*[2,3]


                2             6 
                6            12 

Seseorang dapat membayangkan perkalian ini seolah-olah vektor baris v
telah diduplikasi untuk membentuk matriks dengan ukuran yang sama
dengan A.


\>dup([1,2],2) // dup: menduplikasi/menggandakan vektor [1,2] sebanyak 2 kali (baris)


                1             2 
                1             2 

\>A\*dup([1,2],2) 


                1             4 
                3             8 

Hal ini juga berlaku untuk dua vektor di mana salah satunya berupa
vektor baris dan yang lainnya berupa vektor kolom. Kita menghitung i*j
untuk i,j dari 1 hingga 5. Triknya adalah mengalikan 1:5 dengan
transposnya. Bahasa matriks Euler secara otomatis menghasilkan tabel
nilai.


\>(1:5)\*(1:5)' // hasilkali elemen-elemen vektor baris dan vektor kolom


                1             2             3             4             5 
                2             4             6             8            10 
                3             6             9            12            15 
                4             8            12            16            20 
                5            10            15            20            25 

Sekali lagi, ingat bahwa ini bukanlah perkalian matriks!


\>(1:5).(1:5)' // hasilkali vektor baris dan vektor kolom


    55

\>sum((1:5)\*(1:5)) // sama hasilnya


    55

Bahkan operator seperti &lt; atau == bekerja dengan cara yang sama.


\>(1:10)<6 // menguji elemen-elemen yang kurang dari 6


    [1,  1,  1,  1,  1,  0,  0,  0,  0,  0]

Misalnya, kita dapat menghitung jumlah elemen yang memenuhi kondisi
tertentu dengan fungsi sum().


\>sum((1:10)<6) // banyak elemen yang kurang dari 6


    5

Euler memiliki operator perbandingan, seperti "==", yang
memeriksa kesamaan.


Kita mendapatkan vektor berisi 0 dan 1, di mana 1 mewakili nilai benar
(true).


\>t=(1:10)^2; t==25 //menguji elemen2 t yang sama dengan 25 (hanya ada 1)


    [0,  0,  0,  0,  1,  0,  0,  0,  0,  0]

Dari vektor tersebut, "nonzeros" memilih elemen-elemen yang
tidak bernilai nol.


Dalam hal ini, kita mendapatkan indeks dari semua elemen yang lebih
besar dari 50.


\>nonzeros(t\>50) //indeks elemen2 t yang lebih besar daripada 50


    [8,  9,  10]

Tentu saja, kita dapat menggunakan vektor indeks ini untuk mendapatkan
nilai-nilai yang sesuai di t.


\>t[nonzeros(t\>50)] //elemen2 t yang lebih besar daripada 50


    [64,  81,  100]

Sebagai contoh, mari kita temukan semua kuadrat dari bilangan 1 sampai
1000, yang bernilai 5 modulo 11 dan 3 modulo 13.


\>t=1:1000; nonzeros(mod(t^2,11)==5 && mod(t^2,13)==3)


    [4,  48,  95,  139,  147,  191,  238,  282,  290,  334,  381,  425,
    433,  477,  524,  568,  576,  620,  667,  711,  719,  763,  810,  854,
    862,  906,  953,  997]

EMT tidak sepenuhnya efektif untuk komputasi bilangan bulat karena
menggunakan presisi ganda floating point secara internal. Meskipun
demikian, alat ini sering kali sangat berguna.


Kita dapat memeriksa sifat keprimaan suatu bilangan. Mari kita cari
tahu, berapa banyak kuadrat ditambah 1 yang merupakan bilangan prima.


\>t=1:1000; length(nonzeros(isprime(t^2+1)))


    112

Fungsi nonzeros() hanya bekerja untuk vektor. Untuk matriks, terdapat
mnonzeros().


\>seed(2); A=random(3,4)


         0.765761      0.401188      0.406347      0.267829 
          0.13673      0.390567      0.495975      0.952814 
         0.548138      0.006085      0.444255      0.539246 

Fungsi ini mengembalikan indeks dari elemen-elemen yang tidak bernilai
nol.


\>k=mnonzeros(A<0.4) //indeks elemen2 A yang kurang dari 0,4


                1             4 
                2             1 
                2             2 
                3             2 

Indeks-indeks ini dapat digunakan untuk menetapkan nilai tertentu pada
elemen-elemen tersebut.


\>mset(A,k,0) //mengganti elemen2 suatu matriks pada indeks tertentu


         0.765761      0.401188      0.406347             0 
                0             0      0.495975      0.952814 
         0.548138             0      0.444255      0.539246 

Fungsi mset() juga dapat menetapkan elemen-elemen pada indeks tersebut
dengan nilai-nilai dari matriks lain.


\>mset(A,k,-random(size(A)))


         0.765761      0.401188      0.406347     -0.126917 
        -0.122404     -0.691673      0.495975      0.952814 
         0.548138     -0.483902      0.444255      0.539246 

Dan dimungkinkan untuk mendapatkan elemen-elemen tersebut dalam bentuk
vektor.


\>mget(A,k)


    [0.267829,  0.13673,  0.390567,  0.006085]

Fungsi berguna lainnya adalah extrema, yang mengembalikan nilai
minimum dan maksimum pada setiap baris matriks beserta posisinya.


\>ex=extrema(A)


         0.267829             4      0.765761             1 
          0.13673             1      0.952814             4 
         0.006085             2      0.548138             1 

Kita dapat menggunakan ini untuk mengekstrak nilai-nilai maksimum pada
setiap baris.


\>ex[,3]'


    [0.765761,  0.952814,  0.548138]

Hal ini, tentu saja, sama dengan fungsi max().


\>max(A)'


    [0.765761,  0.952814,  0.548138]

Namun dengan mget(), kita dapat mengekstrak indeks tersebut dan
menggunakan informasi ini untuk mengambil elemen-elemen pada posisi
yang sama dari matriks lain.


\>j=(1:rows(A))'|ex[,4], mget(-A,j)


                1             1 
                2             4 
                3             1 
    [-0.765761,  -0.952814,  -0.548138]

# Fungsi Matriks Lainnya (Membuat Matriks)

Untuk membuat matriks, kita dapat menumpuk satu matriks di atas
matriks lainnya. Jika keduanya tidak memiliki jumlah kolom yang sama,
matriks yang lebih pendek akan diisi dengan angka 0.


\>v=1:3; v\_v


                1             2             3 
                1             2             3 

Demikian pula, kita dapat menggabungkan satu matriks ke samping
matriks lainnya, dengan syarat keduanya memiliki jumlah baris yang
sama.


\>A=random(3,4); A|v'


         0.032444     0.0534171      0.595713      0.564454             1 
          0.83916      0.175552      0.396988       0.83514             2 
        0.0257573      0.658585      0.629832      0.770895             3 

Jika keduanya tidak memiliki jumlah baris yang sama, matriks yang
lebih pendek akan diisi dengan angka 0.


Terdapat pengecualian untuk aturan ini. Sebuah bilangan real yang
digabungkan ke suatu matriks akan digunakan sebagai satu kolom yang
diisi penuh dengan bilangan real tersebut.


\>A|1


         0.032444     0.0534171      0.595713      0.564454             1 
          0.83916      0.175552      0.396988       0.83514             1 
        0.0257573      0.658585      0.629832      0.770895             1 

Sangat dimungkinkan untuk membuat matriks dari vektor baris dan vektor
kolom.


\>[v;v]


                1             2             3 
                1             2             3 

\>[v',v']


                1             1 
                2             2 
                3             3 

Tujuan utama dari hal ini adalah untuk menginterpretasikan vektor
ekspresi bagi vektor-vektor kolom.


\>"[x,x^2]"(v')


                1             1 
                2             4 
                3             9 

Untuk mendapatkan ukuran dari A, kita dapat menggunakan fungsi-fungsi
berikut.


\>C=zeros(2,4); rows(C), cols(C), size(C), length(C)


    2
    4
    [2,  4]
    4

Untuk vektor, terdapat fungsi length().


\>length(2:10)


    9

Terdapat banyak fungsi lainnya yang menghasilkan matriks.


\>ones(2,2)


                1             1 
                1             1 

Ini juga dapat digunakan dengan satu parameter. Untuk mendapatkan
vektor dengan angka selain 1, gunakan perintah berikut.


\>ones(5)\*6


    [6,  6,  6,  6,  6]

Selain itu, matriks dengan angka acak dapat dihasilkan menggunakan
fungsi random (distribusi seragam) atau normal (distribusi Gauss).


\>random(2,2)


          0.66566      0.831835 
            0.977      0.544258 

Berikut adalah fungsi berguna lainnya, yang mengubah struktur
elemen-elemen suatu matriks menjadi matriks lain.


\>redim(1:9,3,3) // menyusun elemen2 1, 2, 3, ..., 9 ke bentuk matriks 3x3


                1             2             3 
                4             5             6 
                7             8             9 

Dengan fungsi berikut, kita dapat menggunakan fungsi ini bersama
fungsi dup untuk menulis fungsi rep(), yang mengulang suatu vektor
sebanyak n kali.


\>function rep(v,n) := redim(dup(v,n),1,n\*cols(v))


Mari kita uji.


\>rep(1:3,5)


    [1,  2,  3,  1,  2,  3,  1,  2,  3,  1,  2,  3,  1,  2,  3]

Fungsi multdup() menduplikasi elemen-elemen dari suatu vektor.


\>multdup(1:3,5), multdup(1:3,[2,3,2])


    [1,  1,  1,  1,  1,  2,  2,  2,  2,  2,  3,  3,  3,  3,  3]
    [1,  1,  2,  2,  2,  3,  3]

Fungsi flipx() dan flipy() membalikkan urutan baris atau kolom dari
suatu matriks. Yaitu, fungsi flipx() membalikkan matriks secara
horizontal.


\>flipx(1:5) //membalik elemen2 vektor baris


    [5,  4,  3,  2,  1]

Untuk rotasi, Euler memiliki fungsi rotleft() dan rotright().


\>rotleft(1:5) // memutar elemen2 vektor baris


    [2,  3,  4,  5,  1]

Fungsi khusus drop(v,i) menghapus elemen-elemen dengan indeks yang ada
pada i dari vektor v.


\>drop(10:20,3)


    [10,  11,  13,  14,  15,  16,  17,  18,  19,  20]

Perlu dicatat bahwa vektor i pada drop(v,i) mengacu pada indeks
elemen-elemen di dalam v, bukan nilai dari elemen tersebut. Jika Anda
ingin menghapus elemen tertentu berdasarkan nilainya, Anda perlu
menemukan posisi elemen tersebut terlebih dahulu. Fungsi indexof(v,x)
dapat digunakan untuk mencari elemen x di dalam vektor v yang terurut.


\>v=primes(50), i=indexof(v,10:20), drop(v,i)


    [2,  3,  5,  7,  11,  13,  17,  19,  23,  29,  31,  37,  41,  43,  47]
    [0,  5,  0,  6,  0,  0,  0,  7,  0,  8,  0]
    [2,  3,  5,  7,  23,  29,  31,  37,  41,  43,  47]

Seperti yang Anda lihat, memasukkan indeks di luar jangkauan (seperti
0), indeks ganda, atau indeks yang tidak terurut tidak akan
menimbulkan masalah.


\>drop(1:10,shuffle([0,0,5,5,7,12,12]))


    [1,  2,  3,  4,  6,  8,  9,  10]

Terdapat beberapa fungsi khusus untuk mengatur diagonal atau untuk
menghasilkan matriks diagonal.


Kita mulai dengan matriks identitas.


\>A=id(5) // matriks identitas 5x5


                1             0             0             0             0 
                0             1             0             0             0 
                0             0             1             0             0 
                0             0             0             1             0 
                0             0             0             0             1 

Kemudian kita mengatur diagonal bawah (-1) menjadi 1:4.


\>setdiag(A,-1,1:4) //mengganti diagonal di bawah diagonal utama


                1             0             0             0             0 
                1             1             0             0             0 
                0             2             1             0             0 
                0             0             3             1             0 
                0             0             0             4             1 

Perlu dicatat bahwa kita tidak mengubah matriks A. Kita mendapatkan
matriks baru sebagai hasil dari setdiag().


Berikut adalah fungsi yang mengembalikan matriks tridiagonal.


\>function tridiag (n,a,b,c) := setdiag(setdiag(b\*id(n),1,c),-1,a); ...  
\>   tridiag(5,1,2,3)


                2             3             0             0             0 
                1             2             3             0             0 
                0             1             2             3             0 
                0             0             1             2             3 
                0             0             0             1             2 

Diagonal dari suatu matriks juga dapat diekstrak dari matriks
tersebut. Untuk mendemonstrasikannya, kita merestrukturisasi vektor
1:9 menjadi matriks berukuran 3x3.


\>A=redim(1:9,3,3)


                1             2             3 
                4             5             6 
                7             8             9 

Sekarang kita dapat mengekstrak diagonalnya.


\>d=getdiag(A,0)


    [1,  5,  9]

Sebagai contoh, kita dapat membagi matriks dengan diagonalnya. Bahasa
matriks memastikan bahwa vektor kolom d diterapkan ke matriks secara
baris demi baris.


\>fraction A/d'


            1         2         3 
          4/5         1       6/5 
          7/9       8/9         1 

# Vektorisasi

Hampir semua fungsi di Euler dapat bekerja untuk masukan berupa
matriks dan vektor, sejauh hal tersebut masuk akal.


Sebagai contoh, fungsi sqrt() menghitung akar kuadrat dari semua
elemen pada vektor atau matriks tersebut.   


\>sqrt(1:3)


    [1,  1.41421,  1.73205]

Dengan demikian, Anda dapat membuat tabel nilai dengan mudah. Ini
adalah salah satu cara untuk membuat plot suatu fungsi (cara
alternatifnya menggunakan ekspresi).


\>x=1:0.01:5; y=log(x)/x^2; // terlalu panjang untuk ditampikan


Dengan fitur ini dan operator titik dua a:delta:b, vektor nilai fungsi
dapat dibuat dengan mudah.


Pada contoh berikut, kita membuat vektor nilai t[i] dengan jarak 0,1
dari -1 hingga 1. Kemudian kita membuat vektor nilai dari fungsi
tersebut


$$s = t^3-t$$\>t=-1:0.1:15; s=t^3-t


    [0,  0.171,  0.288,  0.357,  0.384,  0.375,  0.336,  0.273,  0.192,
    0.099,  0,  -0.099,  -0.192,  -0.273,  -0.336,  -0.375,  -0.384,
    -0.357,  -0.288,  -0.171,  0,  0.231,  0.528,  0.897,  1.344,  1.875,
    2.496,  3.213,  4.032,  4.959,  6,  7.161,  8.448,  9.867,  11.424,
    13.125,  14.976,  16.983,  19.152,  21.489,  24,  26.691,  29.568,
    32.637,  35.904,  39.375,  43.056,  46.953,  51.072,  55.419,  60,
    64.821,  69.888,  75.207,  80.784,  86.625,  92.736,  99.123,
    105.792,  112.749,  120,  127.551,  135.408,  143.577,  152.064,
    160.875,  170.016,  179.493,  189.312,  199.479,  210,  220.881,
    232.128,  243.747,  255.744,  268.125,  280.896,  294.063,  307.632,
    321.609,  336,  350.811,  366.048,  381.717,  397.824,  414.375,
    431.376,  448.833,  466.752,  485.139,  504,  523.341,  543.168,
    563.487,  584.304,  605.625,  627.456,  649.803,  672.672,  696.069,
    720,  744.471,  769.488,  795.057,  821.184,  847.875,  875.136,
    902.973,  931.392,  960.399,  990,  1020.2,  1051.01,  1082.43,
    1114.46,  1147.12,  1180.42,  1214.34,  1248.91,  1284.13,  1320,
    1356.53,  1393.73,  1431.6,  1470.14,  1509.37,  1549.3,  1589.91,
    1631.23,  1673.26,  1716,  1759.46,  1803.65,  1848.57,  1894.22,
    1940.62,  1987.78,  2035.68,  2084.35,  2133.79,  2184,  2234.99,
    2286.77,  2339.34,  2392.7,  2446.87,  2501.86,  2557.65,  2614.27,
     ... ]

EMT memperluas operator untuk skalar, vektor, dan matriks dengan cara
yang intuitif.


Sebagai contoh, vektor kolom dikalikan dengan vektor baris akan
diperluas menjadi matriks jika suatu operator diterapkan. Pada contoh
berikut, v' adalah vektor transpos (sebuah vektor kolom).


\>shortest (1:5)\*(1:5)'


         1      2      3      4      5 
         2      4      6      8     10 
         3      6      9     12     15 
         4      8     12     16     20 
         5     10     15     20     25 

Perlu dicatat bahwa hal ini sangat berbeda dengan perkalian matriks.
Perkalian matriks dalam EMT dilambangkan dengan titik ".".


\>(1:5).(1:5)'


    55

Secara bawaan, vektor baris ditampilkan dalam format yang ringkas.


\>[1,2,3,4]


    [1,  2,  3,  4]

Untuk matriks, operator khusus . menyatakan perkalian matriks, dan A'
menyatakan transposisi. Matriks berukuran 1x1 dapat digunakan persis
seperti bilangan riil.


\>v:=[1,2]; v.v', %^2


    5
    25

Untuk mentranspos suatu matriks, kita menggunakan tanda petik tunggal.


\>v=1:4; v'


                1 
                2 
                3 
                4 

Dengan demikian, kita dapat menghitung perkalian matriks A dengan
vektor b.


\>A=[1,2,3,4;5,6,7,8]; A.v'


               30 
               70 

Perlu dicatat bahwa v masih berupa vektor baris. Oleh karena itu,
hasil v'.v berbeda dengan v.v'.


\>v'.v


                1             2             3             4 
                2             4             6             8 
                3             6             9            12 
                4             8            12            16 

v.v' menghitung kuadrat dari norma v untuk vektor baris v. Hasilnya
adalah vektor 1x1, yang dapat bekerja persis seperti bilangan riil.


\>v.v'


    30

Terdapat pula fungsi norm (bersama dengan banyak fungsi Aljabar Linier
lainnya).


\>norm(v)^2


    30

Operator dan fungsi mematuhi aturan bahasa matriks pada Euler.


Berikut adalah ringkasan dariaturan-aturan tersebut:


* 
Fungsi yang diterapkan pada vektor atau matriks akan diterapkan ke
* setiap elemen.


* 
Operator yang beroperasi pada dua matriks berukuran sama akan
* diterapkan secara berpasangan pada elemen-elemen matriks tersebut.


* 
Jika kedua matriks memiliki dimensi yang berbeda, keduanya akan
* diperluas dengan cara yang logis sehingga memiliki ukuran yang sama.


Sebagai contoh, nilai skalar dikalikan dengan vektor akan mengalikan
nilai tersebut dengan setiap elemen vektor. Atau matriks dikalikan
dengan vektor (menggunakan *, bukan .) akan memperluas vektor ke
ukuran matriks dengan cara menggandakannya.


Berikut adalah kasus sederhana dengan operator ^.


\>[1,2,3]^2


    [1,  4,  9]

Berikut adalah kasus yang lebih rumit. Vektor baris yang dikalikan
dengan vektor kolom akan memperluas keduanya dengan cara
menggandakannya.


\>v:=[1,2,3]; v\*v'


                1             2             3 
                2             4             6 
                3             6             9 

Perlu dicatat bahwa hasil kali skalar (skalar darab) menggunakan
perkalian matriks, bukan operator *!


\>v.v'


    14

Terdapat banyak fungsi untuk matriks. Kami menyajikan daftar singkat
berikut. Anda disarankan untuk merujuk ke dokumentasi untuk informasi
lebih lanjut mengenai perintah-perintah ini.


  sum,prod menghitung jumlah dan hasil kali dari baris-baris matriks  
  cumsum,cumprod melakukan hal yang sama secara kumulatif  
  min,max menghitung nilai ekstrem dari setiap baris  
  extrema mengembalikan vektor dengan informasi nilai ekstrem  
  diag(A,i) mengembalikan diagonal ke-i  
  setdiag(A,i,v) mengatur/mengisi diagonal ke-i  
  id(n) matriks identitas  
  det(A) determinan  
  charpoly(A) polinomial karakteristik  
  eigenvalues(A) nilai-nilai eigen  

\>v\*v, sum(v\*v), cumsum(v\*v)


    [1,  4,  9]
    14
    [1,  5,  14]

Operator : menghasilkan vektor baris berjarak sama, secara opsional
dengan ukuran langkah (step size).


\>1:4, 1:2:10


    [1,  2,  3,  4]
    [1,  3,  5,  7,  9]

Untuk menggabungkan (mengonkatener) matriks dan vektor, terdapat
operator "|" and "_".


\>[1,2,3]|[4,5], [1,2,3]\_1


    [1,  2,  3,  4,  5]
                1             2             3 
                1             1             1 

Elemen-elemen suatu matriks dirujuk menggunakan format "A[i,j]".


\>A:=[1,2,3;4,5,6;7,8,9]; A[2,3]


    6

Untuk vektor baris atau kolom, v[i] merupakan elemen ke-i dari vektor
tersebut. Untuk matriks, bentuk ini mengembalikan seluruh baris ke-i
dari matriks.


\>v:=[2,4,6,8]; v[3], A[3]


    6
    [7,  8,  9]

Indeks juga dapat berupa vektor baris dari indeks-indeks. Simbol :
menyatakan semua indeks.


\>v[1:2], A[:,2]


    [2,  4]
                2 
                5 
                8 

Bentuk singkat untuk : adalah mengosongkan indeks secara keseluruhan.


\>A[,2:3]


                2             3 
                5             6 
                8             9 

Untuk tujuan vektorisasi, elemen-elemen suatu matriks dapat diakses
seolah-olah elemen tersebut adalah vektor.


\>A{4}


    4

Suatu matriks juga dapat diratakan (flatten) menggunakan fungsi
redim(). Hal ini diimplementasikan dalam fungsi flatten().


\>redim(A,1,prod(size(A))), flatten(A)


    [1,  2,  3,  4,  5,  6,  7,  8,  9]
    [1,  2,  3,  4,  5,  6,  7,  8,  9]

Untuk menggunakan matriks sebagai tabel, mari kita atur ulang ke
format bawaan (default), lalu hitung tabel nilai sinus dan kosinus.
Perlu dicatat bahwa sudut secara default dinyatakan dalam radian.


\>defformat; w=0°:45°:360°; w=w'; deg(w)


                0 
               45 
               90 
              135 
              180 
              225 
              270 
              315 
              360 

Sekarang kita menambahkan kolom-kolom pada suatu matriks.


\>M = deg(w)|w|cos(w)|sin(w)


                0             0             1             0 
               45      0.785398      0.707107      0.707107 
               90        1.5708             0             1 
              135       2.35619     -0.707107      0.707107 
              180       3.14159            -1             0 
              225       3.92699     -0.707107     -0.707107 
              270       4.71239             0            -1 
              315       5.49779      0.707107     -0.707107 
              360       6.28319             1             0 

Dengan menggunakan bahasa matriks, kita dapat membuat beberapa tabel
dari beberapa fungsi secara bersamaan.


Pada contoh berikut, kita menghitung t[j]^i untuk i dari 1 hingga n.
Kita memperoleh matriks, di mana setiap barisnya merupakan tabel dari
t^i untuk satu i. Yaitu, matriks tersebut memiliki elemen-elemen


$$a_{i,j} = t_j^i, \quad 1 \le j \le 101, \quad 1 \le i \le n$$Fungsi yang tidak bekerja untuk masukan vektor harus "divektorisasi".
Hal ini dapat dicapai dengan kata kunci "map" dalam definisi fungsi.
Kemudian fungsi tersebut akan dievaluasi untuk setiap elemen dari
parameter vektor.


Integrasi numerik integrate() hanya bekerja untuk batas interval
skalar. Jadi kita perlu memvektorisasikannya.


\>function map f(x) := integrate("x^x",1,x)


Kata kunci "map" memvektorisasi fungsi tersebut. Fungsi tersebut kini
akan bekerja untuk vektor-vektor angka.


\>f([1:5])


    [0,  2.05045,  13.7251,  113.336,  1241.03]

# Sub-Matriks dan Elemen-Matriks

Untuk mengakses elemen matriks, gunakan notasi kurung siku.


\>A=[1,2,3;4,5,6;7,8,9], A[2,2]


                1             2             3 
                4             5             6 
                7             8             9 
    5

Kita dapat mengakses satu baris utuh dari suatu matriks.


\>A[2]


    [4,  5,  6]

Dalam kasus vektor baris atau kolom, bentuk ini mengembalikan satu
elemen dari vektor tersebut.


\>v=1:3; v[2]


    2

Untuk memastikan Anda mendapatkan baris pertama untuk matriks 1xn dan
mxn, tentukan semua kolom menggunakan indeks kedua yang kosong.


\>A[2,]


    [4,  5,  6]

Jika indeks berupa vektor indeks, Euler akan mengembalikan baris-baris
matriks yang bersesuaian.


Di sini kita menginginkan baris pertama dan kedua dari A.


\>A[[1,2]]


                1             2             3 
                4             5             6 

Kita bahkan dapat mengurutkan ulang A menggunakan vektor-vektor
indeks. Tepatnya, kita tidak mengubah A di sini, melainkan menghitung
versi A yang telah diurutkan ulang.


\>A[[3,2,1]]


                7             8             9 
                4             5             6 
                1             2             3 

Trik indeks ini juga berlaku untuk kolom.


Contoh ini memilih semua baris dari A serta kolom kedua dan ketiga.


\>A[1:3,2:3]


                2             3 
                5             6 
                8             9 

Sebagai singkatan, ":" menyatakan semua indeks baris atau kolom.


\>A[:,3]


                3 
                6 
                9 

Sebagai alternatif, biarkan indeks pertama kosong.


\>A[,2:3]


                2             3 
                5             6 
                8             9 

Kita juga dapat memperoleh baris terakhir dari A.


\>A[-1]


    [7,  8,  9]

Sekarang mari kita ubah elemen-elemen dari A dengan menetapkan
submatriks dari A ke suatu nilai tertentu. Hal ini secara langsung
akan mengubah matriks A yang tersimpan.


\>A[1,1]=4


                4             2             3 
                4             5             6 
                7             8             9 

Kita juga dapat menetapkan suatu nilai ke satu baris dari A.


\>A[1]=[-1,-1,-1]


               -1            -1            -1 
                4             5             6 
                7             8             9 

Kita bahkan dapat menetapkan nilai ke suatu submatriks jika ukurannya
sesuai.


\>A[1:2,1:2]=[5,6;7,8]


                5             6            -1 
                7             8             6 
                7             8             9 

Selain itu, beberapa jalan pintas (shortcut) diperbolehkan.


\>A[1:2,1:2]=0


                0             0            -1 
                0             0             6 
                7             8             9 

Peringatan: Indeks di luar batas akan mengembalikan matriks kosong,
atau pesan kesalahan, tergantung pada pengaturan sistem. Pengaturan
bawaan (default) adalah pesan kesalahan. Namun, perlu diingat bahwa
indeks negatif dapat digunakan untuk mengakses elemen-elemen matriks
yang dihitung dari belakang.


\>A[4]


    Row index 4 out of bounds!
    Error in:
    A[4] ...
        ^

# Pengurutan dan Pengacak (Sorting and Shuffling)

Fungsi sort() mengurutkan sebuah vektor baris.


\>sort([5,6,4,8,1,9])


    [1,  4,  5,  6,  8,  9]

Sering kali kita perlu mengetahui indeks dari vektor yang telah
diurutkan dalam vektor aslinya. Hal ini dapat digunakan untuk
mengurutkan ulang vektor lain dengan cara yang sama.


Mari kita mengacak sebuah vektor.


\>v=shuffle(1:10)


    [4,  5,  10,  6,  8,  9,  1,  7,  2,  3]

Indeks-indeks tersebut berisi urutan v yang sesuai.


\>{vs,ind}=sort(v); v[ind]


    [1,  2,  3,  4,  5,  6,  7,  8,  9,  10]

Hal ini juga berlaku untuk vektor string.


\>s=["a","d","e","a","aa","e"]


    a
    d
    e
    a
    aa
    e

\>{ss,ind}=sort(s); ss


    a
    a
    aa
    d
    e
    e

Seperti yang Anda lihat, posisi entri ganda agak acak.


\>ind


    [4,  1,  5,  2,  6,  3]

Fungsi unique() mengembalikan daftar elemen unik dari suatu vektor
yang telah diurutkan.


\>intrandom(1,10,10), unique(%)


    [4,  4,  9,  2,  6,  5,  10,  6,  5,  1]
    [1,  2,  4,  5,  6,  9,  10]

Hal ini juga berlaku untuk vektor string.


\>unique(s)


    a
    aa
    d
    e

# Aljabar Linear

EMT has lots of functions to solve linear systems, sparse systems, or
regression EMT memiliki banyak fungsi untuk menyelesaikan sistem
linear, sistem jarang (sparse systems), atau masalah regresi.


Untuk sistem linear Ax=b, Anda dapat menggunakan algoritma Gauss,
matriks invers, atau pencocokan linear (linear fit). Operator A\b
menggunakan salah satu versi dari algoritma Gauss.


\>A=[1,2;3,4]; b=[5;6]; A\\b


               -4 
              4.5 

Sebagai contoh lain, kita membangkitkan matriks berukuran 200x200 dan
jumlah dari baris-barisnya. Kemudian kita menyelesaikan Ax=b
menggunakan matriks invers. Kita mengukur galat (error) sebagai
deviasi maksimal seluruh elemen dari nilai 1, yang tentunya merupakan
solusi yang benar.


\>A=normal(200,200); b=sum(A); longest totalmax(abs(inv(A).b-1))


      8.790745908981989e-13 

Jika sistem tidak memiliki solusi, pencocokan linear (linear fit) akan
meminimalkan norma dari galat Ax-b.


\>A=[1,2,3;4,5,6;7,8,9]


                1             2             3 
                4             5             6 
                7             8             9 

Determinan dari matriks ini adalah 0.


\>det(A)


    0

# Matriks Simbolik

Maxima memiliki matriks simbolik. Tentu saja, Maxima dapat digunakan
untuk masalah aljabar linear sederhana seperti ini. Kita dapat
mendefinisikan matriks untuk Euler dan Maxima menggunakan &amp;:=, lalu
menggunakannya dalam ekspresi simbolik. Bentuk umum [...] untuk
mendefinisikan matriks dapat digunakan di Euler untuk mendefinisikan
matriks simbolik.


\>A &= [a,1,1;1,a,1;1,1,a]; $A


$$\begin{pmatrix}a & 1 & 1 \\ 1 & a & 1 \\ 1 & 1 & a \\ \end{pmatrix}$$\>$&det(A), $&factor(%)


$$\left(a-1\right)^2\,\left(a+2\right)$$![images/TugasAplikom3Adi25030630001-099.png](images/TugasAplikom3Adi25030630001-099.png)

\>$&invert(A) with a=0


$$\begin{pmatrix}-\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\ \frac{1  }{2} & -\frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} & -  \frac{1}{2} \\ \end{pmatrix}$$\>A &= [1,a;b,2]; $A


$$\begin{pmatrix}1 & a \\ b & 2 \\ \end{pmatrix}$$Seperti halnya semua variabel simbolik, matriks-matriks ini dapat
digunakan dalam ekspresi simbolik lainnya.


\>$&det(A-x\*ident(2)), $&solve(%,x)


$$\left[ x=\frac{3-\sqrt{4\,a\,b+1}}{2} , x=\frac{\sqrt{4\,a\,b+1}+3  }{2} \right] $$![images/TugasAplikom3Adi25030630001-103.png](images/TugasAplikom3Adi25030630001-103.png)

Nilai-nilai eigen (eigenvalues) juga dapat dihitung secara otomatis.
Hasilnya berupa vektor yang berisi dua vektor: nilai eigen dan
kelipatan (multiplicities)-nya.


\>$&eigenvalues([a,1;1,a])


$$\left[ \left[ a-1 , a+1 \right]  , \left[ 1 , 1 \right]  \right] $$Untuk mengekstrak vektor eigen (eigenvector) tertentu, diperlukan
pengindeksan yang cermat.


\>$&eigenvectors([a,1;1,a]), &%[2][1][1]


$$\left[ \left[ \left[ a-1 , a+1 \right]  , \left[ 1 , 1 \right]    \right]  , \left[ \left[ \left[ 1 , -1 \right]  \right]  , \left[   \left[ 1 , 1 \right]  \right]  \right]  \right] $$    
                                   [1, - 1]
    

Matriks simbolik dapat dievaluasi secara numerik di Euler sama seperti
ekspresi simbolik lainnya.


\>A(a=4,b=5)


                1             4 
                5             2 

Dalam ekspresi simbolik, gunakan kata kunci with.


\>$&A with [a=4,b=5]


$$\begin{pmatrix}1 & 4 \\ 5 & 2 \\ \end{pmatrix}$$Akses ke baris-baris matriks simbolik bekerja persis sama seperti pada
matriks numerik.


\>$&A[1]


$$\left[ 1 , a \right] $$Sebuah ekspresi simbolik dapat memuat penugasan (assignment). Dan hal
tersebut mengubah matriks A.


\>&A[1,1]:=t+1; $&A


$$\begin{pmatrix}t+1 & a \\ b & 2 \\ \end{pmatrix}$$Terdapat fungsi-fungsi simbolik di Maxima untuk membuat vektor dan
matriks. Untuk hal ini, silakan merujuk ke dokumentasi Maxima atau ke
tutorial mengenai Maxima di EMT.


\>v &= makelist(1/(i+j),i,1,3); $v


$$\left[ \frac{1}{j+1} , \frac{1}{j+2} , \frac{1}{j+3} \right] $$\>B &:= [1,2;3,4]; $B, $&invert(B)


$$\begin{pmatrix}-2 & 1 \\ \frac{3}{2} & -\frac{1}{2} \\   \end{pmatrix}$$![images/TugasAplikom3Adi25030630001-111.png](images/TugasAplikom3Adi25030630001-111.png)

Hasilnya dapat dievaluasi secara numerik di Euler. Untuk informasi
lebih lanjut mengenai Maxima, silakan lihat bagian pengantar Maxima.


\>$&invert(B)()


               -2             1 
              1.5          -0.5 

Euler juga memiliki fungsi yang andal, yaitu xinv(), yang melakukan
kalkulasi lebih intensif untuk mendapatkan hasil yang lebih akurat.


Catatan, dengan &amp;:=, matriks B telah didefinisikan sebagai matriks
simbolik dalam ekspresi simbolik dan sebagai matriks numerik dalam
ekspresi numerik. Jadi kita dapat menggunakannya di sini.


\>longest B.xinv(B)


                          1                       0 
                          0                       1 

Sebagai contoh, nilai-nilai eigen (eigenvalues) dari A dapat dihitung
secara numerik.


\>A=[1,2,3;4,5,6;7,8,9]; real(eigenvalues(A))


    [16.1168,  -1.11684,  0]

Atau secara simbolik. Lihat tutorial mengenai Maxima untuk detail
lebih lanjut tentang hal ini.


\>$&eigenvalues(@A)


$$\left[ \left[ \frac{15-3\,\sqrt{33}}{2} , \frac{3\,\sqrt{33}+15}{2}   , 0 \right]  , \left[ 1 , 1 , 1 \right]  \right] $$# Nilai Numerik dalam Ekspresi Simbolik

Sebuah ekspresi simbolik hanyalah sebuah string yang berisi ekspresi.
Jika kita ingin mendefinisikan sebuah nilai untuk ekspresi simbolik
sekaligus ekspresi numerik, kita harus menggunakan "&amp;:=".


\>A &:= [51,pi;4,5]


               51       3.14159 
                4             5 

Masih terdapat perbedaan antara bentuk numerik dan bentuk simbolik.
Saat memindahkan matriks ke bentuk simbolik, pendekatan pecahan
(fractional approximations) untuk bilangan riil akan digunakan.


\>$&A


$$\begin{pmatrix}51 & \frac{1146408}{364913} \\ 4 & 5 \\   \end{pmatrix}$$Untuk menghindari hal tersebut, terdapat fungsi mxmset(variable).


\>mxmset(A); $&A


$$\begin{pmatrix}51 & 3.141592653589793 \\ 4 & 5 \\ \end{pmatrix}$$Maxima juga dapat melakukan kalkulasi dengan bilangan titik kambang
(floating-point numbers), dan bahkan dengan big floating numbers
hingga 32 digit. Namun, proses evaluasinya jauh lebih lambat.


\>$&bfloat(sqrt(2)), $&float(sqrt(2))


$$1.414213562373095$$![images/TugasAplikom3Adi25030630001-116.png](images/TugasAplikom3Adi25030630001-116.png)

Presisi dari big floating point numbers dapat diubah.


\>&fpprec:=100; &bfloat(pi)


    
            3.14159265358979323846264338327950288419716939937510582097494\
    4592307816406286208998628034825342117068b0
    

Variabel numerik dapat digunakan dalam ekspresi simbolik mana pun
dengan menggunakan @var.


Catatan bahwa hal ini hanya diperlukan jika variabel tersebut telah
didefinisikan dengan := atau = sebagai variabel numerik.


\>B:=[1,pi;3,4]; $&det(@B)


$$-5.424777960769379$$# Demo - Suku Bunga

Di bawah ini, kita menggunakan Euler Math Toolbox (EMT) untuk
menghitung suku bunga. Kita melakukan hal tersebut secara numerik dan
simbolik untuk menunjukkan kepada Anda bagaimana Euler dapat digunakan
untuk menyelesaikan masalah dunia nyata.


Asumsikan Anda memiliki modal awal sebesar 5000 (misalnya dalam
dolar).


\>K=5000


    5000

Sekarang kita mengasumsikan suku bunga sebesar 3% per tahun. Mari kita
tambahkan satu bunga tunggal dan hitung hasilnya.


\>K\*1.03


    5150

Euler juga dapat memahami sintaksis berikut.


\>K+K\*3%


    5150

Namun, akan lebih mudah untuk menggunakan faktor tersebut.


\>q=1+3%, K\*q


    1.03
    5150

Untuk periode 10 tahun, kita dapat mengalikan faktor-faktornya secara
langsung untuk mendapatkan nilai akhir dengan suku bunga majemuk.


\>K\*q^10


    6719.58189672

Untuk kebutuhan kita, kita dapat mengatur formatnya menjadi 2 angka di
belakang koma.


\>format(12,2); K\*q^10


        6719.58 

Mari kita cetak hasil yang dibulatkan hingga 2 angka di belakang koma
dalam satu kalimat utuh.


\>"Starting from " + K + "$ you get " + round(K\*q^10,2) + "$."


    Starting from 5000$ you get 6719.58$.

Jika kita ingin mengetahui hasil antara dari tahun ke-1 hingga tahun
ke-9, bahasa matriks Euler (Euler's matrix language) sangat membantu.
Anda tidak perlu menulis perulangan (loop), melainkan cukup memasukkan


\>K\*q^(0:10)


    Real 1 x 11 matrix
    
        5000.00     5150.00     5304.50     5463.64     ...

Bagaimana keajaiban ini bekerja? Pertama, ekspresi 0:10 menghasilkan
sebuah vektor yang berisi bilangan bulat.


\>short 0:10


    [0,  1,  2,  3,  4,  5,  6,  7,  8,  9,  10]

Kemudian, semua operator dan fungsi di Euler dapat diterapkan ke
vektor elemen demi elemen. Jadi


\>short q^(0:10)


    [1,  1.03,  1.0609,  1.0927,  1.1255,  1.1593,  1.1941,  1.2299,
    1.2668,  1.3048,  1.3439]

merupakan sebuah vektor dari faktor q^0 hingga q^{10}. Vektor ini
kemudian dikalikan dengan $K$, sehingga kita mendapatkan vektor dari
nilai-nilai tersebut.


\>VK=K\*q^(0:10);


Tentu saja, cara yang realistis untuk menghitung suku bunga ini adalah
dengan membulatkannya ke sen terdekat setiap tahunnya. Mari kita
tambahkan sebuah fungsi untuk hal ini.


\>function oneyear (K) := round(K\*q,2)


Mari kita bandingkan kedua hasilnya, baik dengan pembulatan maupun
tanpa pembulatan.


\>longest oneyear(1234.57), longest 1234.57\*q


                    1271.61 
                  1271.6071 

Kini tidak ada rumus sederhana untuk tahun ke-$n$, dan kita harus
melakukan perulangan (loop) melewati tahun-tahun tersebut. Euler
menyediakan banyak solusi untuk hal ini.


Cara termudah adalah dengan menggunakan fungsi iterate, yang melakukan
iterasi pada fungsi yang diberikan sebanyak beberapa kali.


\>VKr=iterate("oneyear",5000,10)


    Real 1 x 11 matrix
    
        5000.00     5150.00     5304.50     5463.64     ...

Kita dapat mencetaknya dengan tampilan yang lebih rapi menggunakan
format kita yang memiliki jumlah angka di belakang koma yang tetap.


\>VKr'


        5000.00 
        5150.00 
        5304.50 
        5463.64 
        5627.55 
        5796.38 
        5970.27 
        6149.38 
        6333.86 
        6523.88 
        6719.60 

Untuk mendapatkan elemen tertentu dari vektor tersebut, kita
menggunakan indeks di dalam kurung siku.


\>VKr[2], VKr[1:3]


        5150.00 
        5000.00     5150.00     5304.50 

Secara mengejutkan, kita juga dapat menggunakan sebuah vektor indeks.
Ingat kembali bahwa `1:3` menghasilkan vektor `[1,2,3]`.


Mari kita bandingkan elemen terakhir dari nilai yang telah dibulatkan
dengan nilai yang utuh.


\>VKr[-1], VK[-1]


        6719.60 
        6719.58 

Perbedaannya sangat kecil.


# Menyelesaikan Persamaan

Sekarang kita menggunakan fungsi yang lebih tingkat lanjut, yang
menambahkan sejumlah uang tertentu setiap tahunnya.


\>function onepay (K) := K\*q+R


Kita tidak perlu menentukan nilai $q$ atau $R$ untuk mendefinisikan
fungsi tersebut. Kita hanya perlu mendefinisikan nilai-nilai ini saat
menjalankan perintahnya. Kita memilih R=200.


\>R=200; iterate("onepay",5000,10)


    Real 1 x 11 matrix
    
        5000.00     5350.00     5710.50     6081.82     ...

Bagaimana jika kita mengambil/mengurangi jumlah uang yang sama setiap
tahunnya?


\>R=-200; iterate("onepay",5000,10)


    Real 1 x 11 matrix
    
        5000.00     4950.00     4898.50     4845.45     ...

Kita dapat melihat bahwa jumlah uang tersebut berkurang. Jelas sekali,
jika kita hanya mendapatkan bunga sebesar 150 pada tahun pertama,
tetapi mengambil 200, kita akan kehilangan uang setiap tahunnya.


Bagaimana cara kita menentukan berapa tahun uang tersebut dapat
bertahan? Kita harus menulis perulangan (loop) untuk ini. Cara
termudah adalah melakukan iterasi yang cukup panjang.


\>VKR=iterate("onepay",5000,50)


    Real 1 x 51 matrix
    
        5000.00     4950.00     4898.50     4845.45     ...

Dengan menggunakan bahasa matriks, kita dapat menentukan nilai negatif
pertama dengan cara berikut.


\>min(nonzeros(VKR<0))


          48.00 

Alasannya adalah bahwa nonzeros(VKR&lt;0) mengembalikan vektor indeks i,
di mana VKR[i]&lt;0, dan min menghitung indeks terkecilnya.


Karena vektor selalu dimulai dengan indeks 1, jawabannya adalah 47
tahun.Fungsi iterate() memiliki satu keunggulan lagi.


Fungsi ini dapat menerima kondisi akhir sebagai argumen. Dengan
demikian, fungsi tersebut akan mengembalikan nilai beserta jumlah
iterasinya.


\>{x,n}=iterate("onepay",5000,till="x<0"); x, n,


         -19.83 
          47.00 

Mari kita coba menjawab pertanyaan yang lebih ambigu. Anggaplah kita
tahu bahwa nilainya menjadi 0 setelah 50 tahun. Berapakah suku
bunganya?


Ini adalah pertanyaan yang hanya dapat dijawab secara numerik. Di
bawah ini, kita akan menurunkan rumus-rumus yang diperlukan. Kemudian
Anda akan melihat bahwa tidak ada rumus yang mudah untuk suku bunga
tersebut. Namun untuk saat ini, kita bertujuan untuk mendapatkan
solusi numerik.


Langkah pertama adalah mendefinisikan fungsi yang melakukan iterasi
sebanyak n kali. Kita menambahkan semua parameter ke dalam fungsi ini.


\>function f(K,R,P,n) := iterate("x\*(1+P/100)+R",K,n;P,R)[-1]


Proses iterasinya persis seperti di atas:


$$x_{n+1} = x_n \cdot \left(1+ \frac{P}{100}\right) + R$$


$$x_{n+1} = x_n \cdot \left(1+ \frac{P}{100}\right) + R$$Namun kita tidak lagi menggunakan nilai global $R$ di dalam ekspresi
kita. Fungsi seperti iterate() memiliki keunggulan khusus di Euler.
Anda dapat meneruskan nilai variabel dalam ekspresi sebagai parameter
titik koma (;), dalam hal ini P dan R.


Selain itu, kita hanya tertarik pada nilai terakhirnya. Jadi kita
mengambil indeks [-1].Mari kita coba lakukan pengujian:


\>f(5000,-200,3,47)


         -19.83 

Sekarang kita dapat menyelesaikan masalah kita.


\>solve("f(5000,-200,x,50)",3)


           3.15 

Fungsi solve menyelesaikan ekspresi=0 untuk variabel x. Jawabannya
adalah 3.15% per tahun. Kita mengambil nilai awal 3% untuk
algoritmanya. Fungsi solve() selalu memerlukan nilai awal.


Kita dapat menggunakan fungsi yang sama untuk menyelesaikan pertanyaan
berikut: Berapa banyak yang dapat kita ambil per tahun sehingga modal
awal habis setelah 20 tahun dengan asumsi suku bunga 3% per tahun.


\>solve("f(5000,x,3,20)",-200)


        -336.08 

Perhatikan bahwa Anda tidak dapat menyelesaikan persamaan untuk
mencari jumlah tahun, karena fungsi kita mengasumsikan $n$ berupa
nilai integer (bilangan bulat).


## Solusi Simbolis untuk Masalah Suku Bunga

Kita dapat menggunakan bagian simbolis dari Euler untuk mempelajari
masalah ini. Pertama, kita mendefinisikan fungsi onepay() kita secara
simbolis:


\>function op(K) &= K\*q+R; $&op(K)


$$R+q\,K$$Kita sekarang dapat melakukan iterasi pada fungsi ini.


\>$&op(op(op(op(K)))), $&expand(%)


$$q^3\,R+q^2\,R+q\,R+R+q^4\,K$$![images/TugasAplikom3Adi25030630001-121.png](images/TugasAplikom3Adi25030630001-121.png)

Kita dapat melihat sebuah pola. Setelah $n$ periode, kita memperoleh:


$$K_n = q^n K + R (1+q+\ldots+q^{n-1}) = q^n K + \frac{q^n-1}{q-1} R$$Rumus ini merupakan rumus jumlah deret geometri, yang sudah dikenal
oleh Maxima.


\>&sum(q^k,k,0,n-1); $& % = ev(%,simpsum)


$$\sum_{k=0}^{n-1}{q^{k}}=\frac{q^{n}-1}{q-1}$$Hal ini memang sedikit rumit. Deret tersebut dievaluasi dengan flag
simpsum untuk menyederhanakannya menjadi bentuk pecahan (kuosien).


Mari kita buat sebuah fungsi untuk hal ini.


\>function fs(K,R,P,n) &= (1+P/100)^n\*K + ((1+P/100)^n-1)/(P/100)\*R; $&fs(K,R,P,n)


$$\frac{100\,\left(\left(\frac{P}{100}+1\right)^{n}-1\right)\,R}{P}+K  \,\left(\frac{P}{100}+1\right)^{n}$$Fungsi tersebut melakukan hal yang sama seperti fungsi f kita
sebelumnya. Namun fungsi ini jauh lebih efisien.


\>longest f(5000,-200,3,47), longest fs(5000,-200,3,47)


         -19.82504734650985 
         -19.82504734652684 

Kita sekarang dapat menggunakannya untuk mencari waktu n. Kapan modal
kita akan habis? Tebakan awal kita adalah 30 tahun.


\>solve("fs(5000,-330,3,x)",30)


          20.51 

Jawaban ini menunjukkan bahwa nilainya akan menjadi negatif setelah 21
tahun.


Kita juga dapat menggunakan fitur simbolis dari Euler untuk menghitung
rumus-rumus pembayaran.


Asumsikan kita mendapatkan pinjaman sebesar K, dan melakukan n kali
pembayaran sebesar R (dimulai setelah tahun pertama) dengan menyisakan
sisa utang sebesar Kn (pada saat pembayaran terakhir). Rumus untuk hal
ini secara jelas adalah


\>equ &= fs(K,R,P,n)=Kn; $&equ


$$\frac{100\,\left(\left(\frac{P}{100}+1\right)^{n}-1\right)\,R}{P}+K  \,\left(\frac{P}{100}+1\right)^{n}={\it Kn}$$Biasanya rumus ini dinyatakan dalam bentuk


$$i = \frac{P}{100}$$\>equ &= (equ with P=100\*i); $&equ


$$\frac{\left(\left(i+1\right)^{n}-1\right)\,R}{i}+\left(i+1\right)^{  n}\,K={\it Kn}$$Kita dapat menyelesaikan tingkat pembayaran R secara simbolis.


\>$&solve(equ,R)


$$\left[ R=\frac{i\,{\it Kn}-i\,\left(i+1\right)^{n}\,K}{\left(i+1  \right)^{n}-1} \right] $$Seperti yang dapat Anda lihat dari rumus tersebut, fungsi ini
menghasilkan floating point error untuk $i=0$. Meskipun demikian,
Euler tetap membuat plotnya.


Tentu saja, kita memiliki nilai limit berikut:


\>$&limit(R(5000,0,x,10),x,0)


$$\lim_{x\rightarrow 0}{R\left(5000 , 0 , x , 10\right)}$$Jelas sekali, tanpa bunga kita harus membayar kembali 10 kali angsuran
sebesar 500.


Persamaan tersebut juga dapat diselesaikan untuk mencari variabel n.
Persamaan ini akan terlihat lebih rapi jika kita menerapkan beberapa
penyederhanaan padanya.


\> fn &= solve(equ,n) | ratsimp; $&fn


$$\left[ n=\frac{\log \left(\frac{R+i\,{\it Kn}}{R+i\,K}\right)}{  \log \left(i+1\right)} \right] $$# Penyelesaian Soal-Soal Latihan Aljabar

## 1. Penyederhanaan dan Penjabaran Bentuk Aljabar

Soal 1: Sederhanakan dan jabarkan bentuk aljabar berikut:


$$\frac{(2x^2 - 8)(x + 3)}{x^2 + x - 6}$$\>$&factor((2\*x^2 - 8)\*(x + 3)/(x^2 + x - 6))


$$2\,\left(x+2\right)$$Penjelasan hasil: Perintah factor() pada Maxima menyederhanakan bentuk
pecahan aljabar di atas dengan memfaktorkan pembilang dan penyebutnya
terlebih dahulu, sehingga diperoleh hasil eksak 2(x + 2).


## 2. Penyelesaian Persamaan Polinomial / Kuadrat

Soal 2: Tentukan himpunan penyelesaian eksak dari persamaan berikut:


$$2x^2 - 5x - 3 = 0$$\>$&solve(2\*x^2 - 5\*x - 3 = 0, x)


$$\left[ x=3 , x=-\frac{1}{2} \right] $$Penjelasan hasil: Perintah solve() mencari akar-akar persamaan secara
simbolik terhadap variabel x, menghasilkan dua akar rasional yaitu x =
-1/2 dan x = 3.


## Sistem Persamaan Linear Dua Variabel (SPLDV)

Soal 3: Selesaikan sistem persamaan linear berikut:


$$\begin{cases} 3x + 2y = 12 \\ 5x - y = 7 \end{cases}$$\>$&solve([3\*x + 2\*y = 12, 5\*x - y = 7], [x, y])


$$\left[ \left[ x=2 , y=3 \right]  \right] $$Penjelasan hasil: Dengan memasukkan vektor persamaan dan vektor
variabel [x, y] ke dalam fungsi solve(), diperoleh titik potong
tunggal yang memenuhi kedua persamaan, yaitu x = 2 dan y = 3.


## 4. Penyelesaian Pertidaksamaan Aljabar

Soal 4: Tentukan himpunan penyelesaian pertidaksamaan rasional
berikut:


$$\frac{x + 4}{x - 2} \le 3$$\>&load(fourier\_elim);

\>$&fourier\_elim([(x + 4)/(x - 2) <= 3], [x])


$$\left[ x=5 \right] \lor \left[ 5<x \right] \lor \left[ x<2 \right] $$Penjelasan hasil: Setelah memuat paket fourier_elim, perintah
fourier_elim() menyelesaikan pertidaksamaan secara eksak. Hasilnya
menunjukkan himpunan penyelesaian x &lt; 2 atau x &gt;= 5 (ditampilkan
sebagai x = 5 atau 5 &lt; x atau x &lt; 2).


## 5. Determinan dan Invers Matriks Simbolik

Soal 5: Diketahui matriks A berikut. Tentukan determinan (dalam bentuk
faktor) dan inversnya!


$$A = \begin{pmatrix} x & 2 \\ 3 & x+1 \end{pmatrix}$$\>A &= [x, 2; 3, x+1]; $&A


$$\begin{pmatrix}x & 2 \\ 3 & x+1 \\ \end{pmatrix}$$\>$&factor(det(A)), $&invert(A)


$$\begin{pmatrix}\frac{x+1}{x\,\left(x+1\right)-6} & -\frac{2}{x\,  \left(x+1\right)-6} \\ -\frac{3}{x\,\left(x+1\right)-6} & \frac{x}{x  \,\left(x+1\right)-6} \\ \end{pmatrix}$$![images/TugasAplikom3Adi25030630001-142.png](images/TugasAplikom3Adi25030630001-142.png)

Penjelasan hasil: Matriks simbolik didefinisikan menggunakan operator
"&amp;=". Fungsi det(A) yang digabung dengan factor() menghasilkan
determinan (x - 2)(x + 3), sedangkan invert(A) menampilkan matriks
invers eksak dalam variabel x.


