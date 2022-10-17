# Writting test

- ### DAY 1
  
  - fetch
    adalah sebuah teknik untuk melakukan request dan response jaringan

    ```javascript
    fetch("urlnya")
      .then(function (response) {
        return response.json();
      })
      .catch(function (err) {
        console.log(err);
      });
    ```
    pembacaan fetch yang ada diatas yaitu, jika fetch berhasil dilakukan maka blok then akan terpangil dan mengembalikan nilai object sesuai response yang didapat. apabila fungsi fetch gagal dilakukan, maka blok catch akan terpangil dan menampilkan error pada console

  - implementasi fetch pada project tmdb movie api
    ![](https://res.cloudinary.com/ddhkwq4zk/image/upload/v1666016423/fatch_tmfx2s.png)
    cara kerja kode diatas adalah fetch data dari tmdb movie api lalu datanya kita masukkan ke variabel response, lalu kita unboxing variabel response lalu simpan di variabel movieTampil, lalu kita ambil property results yang berisi daftar film kita simpan ke variabel dataMovie, lalu isinya kita looping dan tampilkan berbentuk card yang didalamnya kita akan mengambil gambarnya, judul film, ratingnya dan tanggal release filmnya
  - Async await
    adalah salah satu fitur baru dari javascript yang di gunakan untuk menangani hasil dari sebuah promise. Caranya adalah dengan menambahkan kata ‘async’ di depan sebuah fungsi untuk mengubahnya menjadi asynchronous. Sedangkan await berfungsi untuk menunda sebuah kode di jalankan, sampai proses asynchronous berhasil.
    
    - syntax async await
      ```javascript
      const getUser = async () => {
        const data = await getasUser();
        console.log(data);
      };
      ```
    - penjelasan penggunaan async await
      1. async await adalah salah satu cara untuk mengatasi masalah asynchronous pada javascript selain menggunakan callback dan promise
      2. setiap baris yang menggunakan await akan ditunggu sampai asynchronous promise tersebut di resolve
      3. untuk menggunakan async await, kembalian dari suatu fungsi harus merupakan suatu promise. async await tidak dapat berdiri tanpa adanya promise
      4. pada implementasi async await kita menggunakan kata kunci async sebelum fungsi. await sendiri hanya bisa digunakan pada fungsi yang menggunakan async
      5. tidak seperti promise, dengan async await maka suatu baris kode dapat tersusun dengan rapi mirip kode yang sifatnya synchronous
    - error handling async await
      untuk menghandle erorr async await dapat mengguanakan try catch didalam function yang dibuat, sehingga jika terjadi error dapat menangkap errornya dalam blok catch berikut contohnya:

      ```javascript
      const getAllUser = async ()=> {
          try {
      const result = await getUser()
        console.log(result)
      } catch (error) {
        console.log(error)
      }
      ```
- ### DAY 2
  - Github collab
  - kenapa git dan github wajib digunakan
    * karena git itu bisa untuk kolaborasi dan salah satu tool terpopuler yang digunakan pada pengembangan software, contohnya yaitu seperti google, microsoft, facebook semuanya menggunakan git
    * Karena github adalah merupakan wadah khusus bagi developer untuk menuliskan sebuah code, menyimpan code, melihat referensi code, meninjau project dan berkomunikasi dengan programmer lain
  - perbedaan git dan github
    * Git merupakan software berbasis Version Control System (VCS) yang bertugas untuk mencatat perubahan seluruh file atau repository suatu project. Developer software biasa menggunakan Git untuk distributed revision (VCS terdistribusi), hal ini bertujuan untuk menyimpan database tidak hanya ke satu tempat. Namun semua orang yang terlibat dalam penyusunan kode dapat menyimpan database ini.
    * GitHub merupakan layanan cloud yang berguna untuk menyimpan dan mengelola sebuah project yang dinamakan repository (repo git). Cara kerja pada GitHub harus terkoneksi pada internet sehingga tidak perlu meng-install sebuah software ke dalam perangkat keras. Hal ini memberikan keringanan penyimpanan komputer yang kita gunakan karena file project tersimpan oleh cloud GitHub.
  - alur kerja git dan github
    * cara kerjanya yaitu yang pertama git init untuk membuat sebuah repository baru, lalu git add untuk menambahkan sebuah track file, lalu git commit untuk menyimpan perubahan, git remote untuk menghubungkan ke repository dari github dan yang terakhir git push untuk mengupload kode ke github. cara kerja github yaitu sebagai tempat menyimpan kode secara online ,bisa juga agar bisa lebih mudah diakses oleh orang lain dan dapat untuk mengelola project
  - Cara membuat repository Git
    * git init untuk membuat repository baru
    `git init .` atau bisa menggunakan `git init <nama_project>`
  - Cara commit pada git
    * `git commit -m "pesannya apa"`
  
  - Cara merge pada git
    * merge fungsinya yaitu menggabungkan branch baru yang telah dibuat dengan branch master
    * caranya dengan mengetikan `git merge feature` feature itu di isi dengan nama branch yang ingin di merge
  - Cara menyelesaikan conflict pada git
    . conflict yaitu ketika sebuah code di kerjakan lebih dari 1 orang misalnya di user a menambahkan teks paragraf pada baris kode ke 1 dan user b menambahkan gambar pada baris kode ke 2 maka ketika di merge akan mengalami conflict, dan untuk menyelesaikan conflict bisa melakukan undo dan memulai dari awal bisa menggunakan `git merge -abort` dan `git rebase -abort` cara ini bisa digunakan ketika sudah melakukan banyak cara tetapi masih conflict, lalu bisa juga resolve dengan beberapa pilihan:
    1. keep yours (hanya menerapkan perubahan dari source milikmu )
    2. keep theirs (hanya menerapkan perubahan dari source milik temanmu )
    3. keep both (perubahan dari kedua source milikmu dan temanmu yang akan diterapkan)
    4. remove both (perubahan dari kedua source akan dihapus)
  - cara push/publish ke github
    * yang pertama siapkan repository baru digithub, lalu copy link repositori yang sudah dibuat yang berada di github, lalu lakukan `git remote add origin https://github.com/hadayasyahla/TUGASSKILVUL`, lalu lakukan git push
    
  - Cara clone dari github
    * menggunakan git clone
    
  - Cara berkolaborasi dengan tim di github

- ### DAY 3
  - responsive website
    responsive website adalah sebuah teknik bagi web designer untuk membuat suatu layout website yang dapat menyesuaikan tampilan sesuai dengan ukuran layar pengguna
  - keuntungan menggunakan responsive website
    1. dapat diakses dengan ukuran layar yang berbeda2
    2. biaya yang tidak terlalu banyak
    3. kemudahan dalam maintenance
    4. lebih cepat untuk membuka halaman
  - tools untuke membuat website yang responsive
    1. menggunakan media query
    2. mengguanakn viewport
    3. menggunakan grid
    4. menggunakan css relative unit
    5. menggunakan max-width
    6. menggunakan framework seperti bootsrap, tailwind dan lain lain
    7. menggunakan flex
  - viewport
    dengan menggunakan tag `<meta name='viewport'>` kita bisa mengatur viewport sesuai yang dibutuhkan. setiap kita menggunakan emmet pada html maka akan dibuatkan meta viewport secara otomatis.

    - syntax viewport
      ```html
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      ```
      perhatikan di atribut 'content',  kita menggunakan beberapa variabel untuk viewport:
      1. width untuk mengatur lebar sebuah halaman, jika memberikan nilai 'device-width' maka lebarnya akan mengikuti ukuran lebar dari perangkat
      2. initial-scale untuk mengatur skala (zoom) dari halaman web
  - max-width
    agar gambar mengikuti ukuran layar bisa menggunakan max-width,  ketika layar diperkecil maka gambar akan ikut mengecil secara otomatis mengikuti layarnya
    ```css
    max-width: 100%;
    ```
  - css relative unit
    adalah satuan ukuran yang bersifat mengikuti ukuran layar
     yang sering digunakan untuk responsive:

    1. rem yaitu ukuran yang mengikuti element rootnya, untuk destkop dan laptop biasanya root htmlnya berukuran 16px, jadi misalkan kita menggunakan ukuran 2 rem maka 2\*16 hasilnya 32px
    2. em yaitu ukuran yang mengikuti parent elementnya, misalkan kita membuat tag div lalu didalamnya terdapat tag p, maka ketika tag div kita set ukurannya 20 maka ketika kita menggunakan ukuran 2 em pada tag p maka 2\*20 hasilnya 40px
    3. vh (viewport height) ketika kita menggunakan 50 vh pada gambar maka artinya kita mengatur ukurannya 50 persen dari ukuran tinggi viewport
    4. vw (viewport width) ketika kita menggunakan 50 vw pada gambar maka artinya kita mengatur ukurannya 50 persen dari ukuran lebar viewport
    5. % yaitu ukuran yang mengikuti parentnya, misalnya kita membuat div lalu kita akan menambahkan gambar dan menambahkan ukuran 100% ke gambar maka itu artinya 100% dari ukuran parentnya berarti mengikuti ukuran dari divnya

    - contoh menggunakan css relative unit dengan salah satu ukuran px

    ```css
    h1 {
      font-size: 50px;
    }

    p {
      font-size: 35px;
      line-height: 40px;
    }
    ```

  - media query
    untuk mengatur style supaya ada di ukuran device tertentu maka akan menggunakan style tertentu
    - syntax media query
      ```css
      @media not|only mediatype and (mediafeature and|or|not mediafeature) {
        //CSS-Code;
      }
      ```
    - contoh penulisan media query
      ```css
      @media (max-width: 600px) {
        .card {
          margin-top: 40px;
          margin-bottom: 40px;
        }
      }
      ```
  - flex
    digunakan untuk pengaturan layout, posisi dan tampilan dari suatu konten yang ukurannya belum diketahui atau bernilai dinamis
    - membuat layout flexbox
      ```HTML
      <nav class="container">
          <div>Home</div>
          <div>Search</div>
          <div>Logout</div>
      </nav>
      ```
      tampilan diatas ketika dijalankan akan membuat sebuah navbar secara vertikal, ketika kita ingin navbar tampil secara horizontal bisa menggunakn flex
      ```CSS
      .container {
          display: flex;
      }
      ```
    - justify content
      adalah property css yang membantu mendistribusikan item item didalam sebuah container. diantaranya :
      1. center
      2. flex-end
      3. flex-start
      4. space-evenly
      5. space-between
      6. space-around
  - grid
    css grid adalah css yang dapat membagi kolom pada sebuah website menjadi beberapa bagian sesuai dengan yang diinginkan, baik secara horizontal ataupun vertikal
    - properti display
      properti display pada grid container harus bernilai grid
      ```css
      .container {
        display: grid;
      }
      ```
    - justify-item
      1. start
      2. end
      3. stretch
      4. center
    - align-items
      1. stretch
      2. start
      3. end
      4. center
      5. baseline
    - justify-content
      1. start
      2. end
      3. center
      4. stretch
      5. space-around
      6. space-between
      7. space-evenly

  - perbedaan flex dan grid

    - Flexbox hanya dapat mengatur arah pembagian dimensi tampilan hanya searah secara horizontal saja atau secara vertikal saja.

    - Sebagai contoh, pada flexbox, jika kita mengatur arahnya menjadi "kolom", maka tampilannya hanya akan terbagi rata secara vertikal. Begitu juga dengan arah "baris" yang mengarah secara horizontal.

    - Kalau Grids dapat mengatur arah dimensi tampilan kedua arah yaitu secara horizontal dan vertikal.

  - bootstrap
    bootstrap adalah framework web development berbasis html, css dan javascript yang dirancang untuk mempercepat proses pengembangan web responsive dan mobile first.

    - mengapa menggunakan bootstrap?
      karena bootstrap adalah sebuah framework html,css,javascript yang bisa mempercepat proses pengembangan sebuah web responsive dan mobile first karena kita hanya tinggal copy and paste lalu modifications sesuai yang kita inginkan
    - kapan menggunakan bootstrap?
      pada saat kita ingin membuatsebuah website responsive dengan waktu yang tidak lama / sedikit
    - tampilan bootstrap
      ![](https://res.cloudinary.com/ddhkwq4zk/image/upload/v1666016786/Screenshot_9_oimcfc.png)
    - hal yang bisa kita lakukan di bootstrap
      - bisa mengambil component seperti card, button, carousel, navbar, dan lain lain
      - semua component yang kita ambil semuanya sudah responsive sehingga hanya perlu mengubah ubah sedikit sesuai dengan keinginan kita
    - contoh component di bootstrap
      ```html
      <div class="card" style="width: 18rem;">
        <img src="..." class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
      ```
    - layout pada bootstrap
      kita dapat mengatur berbagai macamm layout, diantaranya:
        1. Breakpoint adalah lebar yang dapat disesuaikan untuk menentukan bagaimana tata letak responsif berperilaku di seluruh perangkat atau ukuran viewport di Bootstrap. disini ada media query, ada X-small, small, medium, large, extra large, extra extra large
        2. Container adalah blok bangunan dasar Bootstrap yang berisi, melapisi, dan menyelaraskan konten  dalam perangkat atau area pandang tertentu.
        3. Grid adalah untuk mengatur sebuah layout, dengan cara dibagi menjadi 12 kolom
        4. Column yaitu mengatur atau memodifikasi sebuah kolom dengan beberapa opsi untuk penyelarasan, pengurutan dan penyeimbangan
        5. Gutters adalah padding diantara kolom , digunakan untuk memberikan ruang secara responsive dan menyelaraskan konten dalam sistem kisi bootstrap
        6. Utilities yaitu untuk pengembangan mobile-friendly dan responsive
        7. Z-index yaitu untuk overlay contohnya jika ada gambar yang menutupi tulisan kita bisa menggunakan z-index agar gambar menjadi dibawah tulisan
    - Content pada bootstrap
      yaitu kita bisa mengatur tulisan, fontnya, typography, gambar, tabel, dan figure
        1. reboot yaitu kumpulan perubahan css khusus elemen dalam satu file
        
        2. Typhography yaitu mengatur sebuah heading, text body, list dan lain lain yang berhubungan dengan penulisan
       
        3. Image yaitu mengatur gambar agar gambar menjadi lebih responsive seperti menggunakan `.img-fluid, max-width: 100%, height: auto`
       
        4. tables
          yaitu kita bisa styling table menggunakan bootstrap
          
          4. figure
            yaitu dokumentasi dan contoh untuk menampilkan gambar dan teks terkait dengan komponen gambar yang ada dibootsrap
           
    - component pada bootstrap
        component pada bootstrap yaitu bagian bagian yang biasanya ada di website seperti tombol, navbar, card, slider, dan lain lain
        1. button
          ```html
          <button type="button" class="btn btn-primary">Primary</button>
          <button type="button" class="btn btn-secondary">Secondary</button>
          <button type="button" class="btn btn-success">Success</button>
          <button type="button" class="btn btn-danger">Danger</button>
          <button type="button" class="btn btn-warning">Warning</button>
          <button type="button" class="btn btn-info">Info</button>
          <button type="button" class="btn btn-light">Light</button>
          <button type="button" class="btn btn-dark">Dark</button>

          <button type="button" class="btn btn-link">Link</button>
          ```
        2. card
          ```html
          <div class="card" style="width: 18rem;">
            <img src="..." class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Card title</h5>
              <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
          ```
        3. navbar
          ```html
          <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <div class="container-fluid">
              <a class="navbar-brand" href="#">Navbar</a>
              <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
              </button>
              <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav">
                  <li class="nav-item">
                    <a class="nav-link active" aria-current="page" href="#">Home</a>
                  </li>
                  <li class="nav-item">
                    <a class="nav-link" href="#">Features</a>
                  </li>
                  <li class="nav-item">
                    <a class="nav-link" href="#">Pricing</a>
                  </li>
                  <li class="nav-item">
                    <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
                  </li>
                </ul>
              </div>
            </div>
          </nav>
          ```
        4. navbar
              ```html
              <div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
                <div class="carousel-inner">
                  <div class="carousel-item active">
                    <img src="..." class="d-block w-100" alt="...">
                  </div>
                  <div class="carousel-item">
                    <img src="..." class="d-block w-100" alt="...">
                  </div>
                  <div class="carousel-item">
                    <img src="..." class="d-block w-100" alt="...">
                  </div>
                </div>
                <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
                  <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                  <span class="visually-hidden">Previous</span>
                </button>
                <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
                  <span class="carousel-control-next-icon" aria-hidden="true"></span>
                  <span class="visually-hidden">Next</span>
                </button>
              </div>
              ```
    - saya juga mengimplementasikan bootstrap pada project tpa3 saya dengan link berikut https://tpa3.netlify.app/
       saya menggunakan card, navbar dari bootstrap sehingga website yang saya gunakan sudah responsive
