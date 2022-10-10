# Day1
* ### Struktur data array
    * Apa itu Array?
    Sebelum kita membahas Array, kita bahas dulu apa itu struktur data?

    Struktur data merupakan cara-cara atau metode yang digunakan untuk menyimpan data di dalam memori komputer.

    Salah satu struktur data yang sering digunakan dalam pemrograman adalah Array.

    Array merupakan struktur data yang digunakan untuk menyimpan sekumpulan data dalam satu tempat.

    Setiap data dalam Array memiliki indeks, sehingga kita akan mudah memprosesnya.
    * Pada javascript, array dapat kita buat dengan tanda kurung siku ([...]).

    Contoh:
    ```javaScript
    var product = [];
    ```
    maka variabel `products` akan berisikan sebuah array kosong.
    kita juga bisa mengisi kedalam array, kemudian setiap data dipisah dengan menggunakan tanda (`,`)
    contoh:
    ```javaScript
    var products = ["Flashdisk", "ssd", "monitor"];
    ```
     karena javascript merupakan bahasa pemrograman yang dynamic typing(bahasa pemrograman yang hanya mengetahui tipe variabel saat program berjalan dan dilakukan assignment)
     maka kita bisa menyimpan dan mencampur apapun kedalam array.
     Contoh:
     ```javaScript
     var myData = [12, 2.1, true, 'C', "petanikode"];
     ```
     * Cara Mengambil Data dari Array
     Array akan menyimpan sekumpulan data dan memberinya nomer indeks agar lebih mudah diakses.
     Indeks array selalu dimulai dari `0`
     contoh:
     ```javaScript
     var makan = ["Nasi Padang", "Seblak", "Soto"];
     ```
     Bagaimana cara mengambil Nilai`"Seblak"`?
     ```javaScript
     makan[1] //-> "Seblak"
     ```
     kenapa tidak pakai `2`?
     karna indeks array selalu dimulai dari nol

     contoh:

     ![](https://res.cloudinary.com/ddhkwq4zk/image/upload/v1665296961/Screenshot_7_tsds6b.png)

    akan menampilkan seperti gambar dibawah
    ![](https://res.cloudinary.com/ddhkwq4zk/image/upload/v1665296626/Screenshot_6_k9cmhq.png)
    
    * Cara Menambahkan Data ke Dalam Array
    Ada dua cara yang bisa dilakukan untuk menambah data ke dalam array:
    1. Mengisi menggunakan indeks;
    2. Mengisi menggunakan method push().
    Mengisi dengan indeks maksudnya, Misal kita punya array dengan isi sebagai berikut:
    ```javaScript
    var buah =["anggur", "nanas", "apel"];
    ```
    ada 3 data didalam array `buah` dengan berisikan indeks:
    `0` : `"anggur"`
    `1` : `"nanas"`
    `2` : `"apel"`
    kita ingin menambahkan data lagi indeks ke `3` maka kita bisa ketikan
    ```javaScript
    buah[3] = "Manggis";
    ```

    * Cara Menghapus Data Array
    Sama seperti menambahkan data ke array, menghapus data juga memiliki dua cara:

    1. Menggunakan `delete`;
    2. Menggunakan method `pop()`.
    Contoh:
    ```javaScript
    delete buah[2];
    ```
    Kita juga dapat menghapus data dari depan dengan menggunakan method `shift()`.

    Contoh:
    ```javaScript
    var bunga = ["Mawar", "Melati", "Anggrek", "Sakura"];
    // hapus data dari depan
    bunga.shift();
    ```
# Day2
* ### JS intermediate-object
    * Objek sebenarnya adalah sebuah variabel yang menyimpan nilai (properti) dan fungsi (method).
    * cara membuat object
    ```javaScript
    var Sneakers = "Air jordan";
    ```
    Tapi variabel Sneakers hanya akan menyimpan nama mobil saja. Karena itu, kita harus menggunakan objek.

    Objek pada javascript, dapat dibuat dengan tanda kurung kurawal dengan isi berupa key dan value.

    ```javaScript
    var Home = {
        type:"Air jordan",
        model:"2021",
        color:"black"
    }
    ```
    * cara mengakses properti dan method dari objek yaitu dengan caramenggunakan tanda titik atau dot (`.`), lalu diikuti dengan nama properti atau method.

    ```javaScript
    console.log(Sneakers.type);
    console.log(Sneakers.Color);

    Sneakers.bagus();
    Sneakers.awet();
    ```
    Untuk mengakses properti, kita cukup gunakan nama `objek.properti`. Sedangkan untuk method, kita harus menggunakan tanda kurung. Ini menyatakan kalau kita ingin mengeksekusi fungsi.

    * Mengupdate value properti dari object 
    ```javaScript
    let film = {
    judul: "Train to busan",
    series: "Zombie",
    "jumlah series": 1,
    };
    console.log(film.judul);//train to busan
    //kita akan mengganti judul train to busan dengan al off us
    film.judul = "al off us";
    console.log(film.judul);//all off us
    ```
    * Assign object/Object.assign() metode untuk menyalin semua properti sendiri yang dapat dihitung dari satu atau lebih objek sumber ke objek target. Ini mengembalikan objek target yang dimodifikasi. 
    ```javaScript
    let user = { name: 'john' };

    let admin = user;

    admin.name = 'anggun';

    alert(user.name);
    ```

    * Menghapus properti dari object
    ```javaScript
    let film = {
    judul: "Train to busan",
    series: "zombie",
    "jumlah series": 1
    };
    console.log(film);
    //maka akan tampil {judul: "train to busan", series: "zombie", "jumlah series": 1}
    //lalu kita akan menghapus properti series
    delete film.series;
    console.log(film);
    //maka akan tampil {judul: "Train to busan", "jumlah series": 1}
    ```
    * Nested Object
    ```javaScript
    let film = {
    judul: "Train to busan",
    series: "zombie",
    "jumlah series": 1,
    pemeran: {
        pemeran1: {
            nama: "goong ryo",
            umur: 41
            },
            pemeran2: {
            nama: "lee jong suk",
            umur: 32
            },
        },
    };

    console.log(film);
    console.log(film.pemeran.pemeran1.nama);//goong ryo
    console.log(film.pemeran.pemeran2.umur);//32
    ```
    * Array of object
    ```javaScript
    let siswa = [
    {
        nama: "arya",
        umur: 15
    },
    {
        nama: "billy",
        umur: 16
    },
        {
        nama: "jihan",
        umur: 15
        },
    ];

    console.log(siswa);
    ```
### Day3
* ### Javascript Modules

    * Javascript module yaitu cara untuk memisahkan kode ke file yang berbeda
    * apa saja yang bisa di export dan import

    1. array
    2. object
    3. function
    4. dan lain lain

    * cara melakukan import dan export module
    1. tambahkan type="module" pada script utama
    2. siapkan script kedua dan seterusnya untuk    melakukan export
    3. lalu lakukan import pada script utama

    * aturan aturan import export

    1. file yang di tuliskan didalam html <script src="./indonesia.js" type="module"></script> yaitu indonesia.js hanya bisa import, tidak bisa mengeksport
    2. kita bisa merubah nama variabel menggunakan kata kunci as atau artinya alias
    3. export default hanya bisa 1 saja
    4. script utama tidak bisa diakses oleh script kedua dan seterusnya
    5. tapi script kedua dan seterusnya bisa di akses oleh script utama

    * keuntungan:

    1. mudah untuk mengelola kode
    2. kode ga numpuk di 1 file

    * membuat export 
    ```javaScript
    export let Bedak = ["luxurime", "hanasui", "makeover", "purbasari"]
    export let lipstik = ["implora", "madamegie","hanasui"]
    //alternative
    //as itu alias, jadi kita bisa merubah lipstik menjadi foundation dengan alias, maka ketika import bisa menggunakan variabel foundation
    export {bedak, lipstik as foundation}
    //membuat export default yaitu hanya bisa 1 saja yang di export
    let makeup = ["alis", "maskara", "eyelener"]
    export default makeup
    ```
    * memanggil import 
    ```javaScript
    import {bedak, lipstik} from "./indo.js"
    //menangkap export dengan export default yaitu makeup
    import makeup, {bedak, lipstik} from "./indo"
    ```
    * menampilkan yang sudah di import 
    ```javaScript
    console.log(makeup);
    console.log(bedak);
    console.log(foundatiom);
    ```
* ### Javascript rekursive
    * Rekursive yaitu function yang memanggil dirinya sendiri sampai keadaan terpenuhi atau berhenti

    contoh kasus rekursive

    ```javaScript
    function deretAngka(n){
    //basecase
    if (n == 1){
        console.log(n);
    }else{
        //recursive case
            deretAngka(n-1)
            console.log(n);
        }
    }
    deretAngka(2)
    ```
### Day4
* ### asynchronous, callback dan promise
    * sifat javascript
    1. single-thread yaitu hanya memiliki 1 jalur
    2. non-blocking yaitu mengijinkan proses selanjutnya untuk mendahului jika proses yang sebelumnya lebih lama dari yang mau mendahului
    3. asynchronous yaitu urutan perintah yang acak karena harus memanggil perintah yang belum selesai
    * kunci javascript asynchronous
    1. callback
    2. promise
    3. async await
    * Promise secara sederhana  adalah sebuah janji yang bisa pending, terpenuhi atau bisa juga ditolak
    * statement yang ada di promise
    1. pending(sedang dalam proses)
    2. fulfilled(terpenuhi)
    3. rejected(dibatalkan/gagal)
    * contoh promise
    ```javaScript
    let ada = new Promise((resolve, reject) =>{
    if(true){
        resolve("ada")//artinya berhasil
    }
    reject("tidak ada"); //artinya tertolak
    });

    ada.then((result) =>{
        console.log(result)
    })
    .catch((err) =>{
        console.log(err);
    });
    //hasilnya maka akan tampil jadi ada
    ```

### Day5
* ### web storage
    * web storage adalah salah satu Web API yang dapat menyimpan data secara lokal pada sisi client
    * web api membagi dua tipe web storage
    1. session storage yaitu penyimpanan data ketika website atau aplikasi ditutup maka datanya akan hilang
    2. local storage yaitu penyimpanan data ketika website atau aplikasi ditutup atau dimatikan perangkatnya maka datanya tetap tidak akan hilang

    * contoh aplikasi yang mengimplementasikan webstorage aplikasi yang menerapkan toggle darkmode, ketika default temanya terang dan kita pencet darkmode lalu kita close browsernya dan coba buka lagi dan jika websitenya masih dalam darkmode maka web tersebut mengimplementasikan web storage tepatnya local storage

    * contoh menyimpan data ke lokal storage 
    ```javaScript
    localStorage.setItem('Lari', 'pagi');
    localStorage.setItem('jalan', 'santai');
    ```

    * contoh menyimpan data ke session storage 
    ```javaScript
    sessionStorage.setItem('lari', 'pagi');
    sessionStorage.setItem('jalan', 'santai');
    ```

    * contoh menampilkan data dari lokal storage 
    ```javaScript
    let tampil = localStorage.getItem('lari');
    console.log(tampil)
    //maka akan tampil pagi
    ```

    * contoh menambahkan data dari session storage 
    ```javaScript
    let tampil2 = sessionStorage.getItem('laro');
    console.log(tampil2)
    //maka akan tampil pagi
    ```
    * menghapus salah satu dari local storage
    ```javaScript
    localStorage.removeItem('jalan')
    //maka jalan akan dihapus
    ```

    * menghapus salah satu dari session storage
    ```javaScript
    sessionStorage.removeItem('jalan')
    //maka jalan akan dihapus dari session storage
    ```

    * menghapus seluruh data dari storage
    ```javaScript
    localStorage.clear()
    sessionStorage.clear()
    ```

    * contoh penggunaan local storage pada website yang menggunakan darkmode
    ```javaScript
    if (localStorage.getItem("theme") === "dark") {
        document.body.classList.add("dark");
    } else {
        document.body.classList.remove("dark");
    }

    document.getElementById("toggle").onclick = () => {
        if (localStorage.getItem("theme")) {
            localStorage.removeItem("theme");
            document.body.classList.remove("dark");
        } else {
            localStorage.setItem("theme", "dark");
            document.body.classList.add("dark");
        }
    };
    ```
























