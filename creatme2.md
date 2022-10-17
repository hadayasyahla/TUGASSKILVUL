# Writting and presentation week2
## DAY 1
* ### Scope
    * Scope
        variabel scope merupakan wilayah program anda yang sudah ditentukan, variabel scope ada dua jenis yaitu global variabel dan local variabel
    * Variabel global
        * variabel global dapat di akses di seluruh dokumen web
        ```javascript
        var buah = "pisang";
        function namaBuah() {

        }
        ```
        * variabel local hanya tersedia di dalam fungsi yang telah dideklarasikan
        ```javascript
        function namaBuah(){
            var buah = "pisang"
        }
        ```
* ### Function
    * function
        yaitu sekumpulan kode yang dirancang untuk melakukan tugas tertentu, atau program yang bisa digunakan kembali baik didalam program itu sendiri maupun di program lain
    * deklarasi function
        ```javascript
        function namaFungsi(){
            //statement
        }
        ```
        ```javascript
        let namaVariabelFungsi = function(){
            //statement
        }
        ```
    * cara memanggil function
        ```javascript
        function sayHello(){
            console.log("Hello world!");
        }
        sayHello();
        ```
## DAY 2
* ### Data type built in prototype and method
    * Data type
        data type atau tipe data adalah jenis jenis data yang bisa disimpan didalam variabel
    * String
        1. String mempunyai properties String.length
        2. String mempunyai banyak method diantara toUppercase, toLowercase dan lain lain
        ```javascript
        let mahasiswa = "LiTa"
        console.log(mahasiswa.length);
        console.log(mahasiswa.toUppercase())
        console.log(mahasiswa.toLowercase())
        console.log(mahasiswa.charAt(3))
        //include bersifat case sensitivity
        console.log(mahasiswa.include("i"))
        ```
    * Number
        ```javascript
        //apakah hai adalah bukan angka?
        isNaN("hai")//true
        //mengubah number menjadi String
        let angka = 20
        angka.toString()//"20"
        //untuk membatasi setelah koma ada berapa digit yang ingin ditampilkan dan hasilnya berbentuk string
        let angkaKoma = 97.1234
        angkaKoma.toFixed(2)//"97.12"
        //ketika ingin nilainya berbentuk angka maka bisa dibungkus dengan Number
        Number(angkaKoma.toFixed(2))//97.12
        ```
    * Math
        ``` JavaScript
        //absolute number tidak boleh negative
        Math.abs(-20)//20
        //pow = pangkat
        Math.pow(5, 2)//25
        //sqrt = akar dari
        Math.sqrt(4)//2
        //round = untuk membulatkan jadi dibelakang koma dihilangkan
        Math.round(221.231)//221
        //floor = untuk membulatkan kebawah
        Math.floor(5.9)//5
        //ceil = untuk membulatkan keatas
        Math.ceil(5.1)//6
        //untuk menampilkan angka random
        Math.random()
        ```
    * prototype
        prototype adalah properti object yang menghubungkan objek ke objek lain misalnya kita ingin membuat function baru yang gunanya untuk membalik suatu kata maka kita buat menggunakan prototype dan didalamnya terdapat function yang menjalankan agar kata menjadi terbalik
        ```javascript
        String.prototype.reverse = function(){
            let s = ""
            for(let i = String(this).length-1; i >= 0; i--) {
                s = s + String(this)[i]
            }
            return s
        }
        console.log("lita".reverse())//atil
        ```
    * Primitive datatype
        adalah tipe data dasar yang tersedia secara langsung pada suatu bahasa pemrograman
        1. Numbers berbentuk angka, angka desima dll
        2. String diapit oleh tanda petik dan backtik
        3. Boolean isinya true or false
        4. undefined
        5. null
    * Non Primitive
        adalah tipe data yang didefinisikan sendiri oleh programmer dan biasanya berisi lebih dari satu nilai
        1. Object
        2. Array
        3. Function


## DAY 3
* ### DOM
    * DOM
        DOM (Document Object Model) adalah sebuah API yang menyediakan fungsi fungsi untuk memanipulasi halaman website dari segi struktur, tampilan dan kontennya. saya disini mencontohkan list sebgai id,classname
    * DOM Node
        DOM Node adalah sebuah objek yang merepresentasikan sebuah elemen HTML atau CSS. DOM Node memiliki properti dan metode yang dapat digunakan untuk mengakses dan memanipulasi elemen HTML atau CSS. DOM Node memiliki tipe yang berbeda. Tipe dari DOM Node dapat dilihat pada gambar di bawah ini.
    * Manfaat DOM
        1. Memanipulasi elemen HTML dan CSS
        2. Mengubah struktur halaman web
        3. Mengubah style halaman web
        4. Mengubah konten halaman web
        5. Membuat aplikasi yang interaktif dan menarik
    * Mengakses DOM
        * mengambil berdasarkan id
            ```javascript
            document.getElementById("#list")
            ```
        * mengambil berdasarkan class name
            akan mendapatkan HTML Collection karena class itu jamak
            ```javascript
            document.getElementByClassName(".list")
            ```
        * mengambil berdasarkan tag name
            ```javascript
            document.getElementsByTagName("h1")
            ```
        * mengambil berdasarkan query selector
            ```javascript
            document.querySelector("#list")
            document.querySelector(".list")
            document.querySelector("h1")
            ```
        * mengambil berdasarkan querySelectorAll akan menghasilkan nodeList
            ```javascript
            document.querySelectorAll(".list")
            ```
    * DOM child dan parent
        * mengambil elemen di dalam sebuah elemen menggunakan child
            ```javascript
            let list = document.getElementsByClassName("list")
            console.log(list[0].children)
            //hasilnya adalah HTMLCollection { 0: li.item, 1: li.item, length: 2 }
            ```
        * mengambil elemen yang membungkus element menggunakan parent
            ```javascript
            let itemQuery = document.querySelector(".item")
            console.log(itemQuery.parentElement)
            //bisa juga menggunakan closest
            console.log(itemQuery.closest(".list"))
            ```
        * mengambil elemen yang masih satu parent menggunakan sibling
            ```javascript
            console.log(itemQuery.previousElementSibling)
            console.log(itemQuery.nextElementSibling)
            ```
## DAY 4
* ### menyisipkan dan style element menggunakan DOM
    * Mengubah DOM
    * menambahkan/menyisipkan menggunakan innerHTML
        ```javascript
        let salam = document.getElementById("salam");
        salam.innerHTML = "hai guys"
        ```
    * menambahkan/menyisipkan menggunakan innerText
        ```javascript
        let salam = document.getElementById("salam");
        salam.innerText = "hai guys"
        ```
    * Text content
        ```javascript
        let salam = document.getElementById("salam");
        salam.textContent = "hai guys"
        ```
    * class list
        ```javascript
        let salam = document.getElementById("salam");
        salam.classList.add("green")
        salam.classList.toggle("green")
        salam.classList.remove("green")
        ```
    * membuat element html menggunakan createElement()
        ```javascript
        let h1 = document.createElement("h1")
        h1.innerText = "contoh heading"
        ```
    * menyisipkan elemen kedalam elemen menggunakan append()
        ```javascript
        let h1 = document.createElement("h1")
        h1.innerText = "contoh heading"
        salam.append(h1)
        ```
    * untuk menghapus element html
        ```javascript
        let h1 = document.getElementById("h1")
        h1.remove()
        ```
    * menampilkan attribute
        ```javascript
        let salam = document.getElementById("salam")
        salam.setAttribute("id", "salam")
        title.removeAttribute("id")
        ```
    * menambahkan style
        ```javascript
        let salam = document.getElementById("salam")
        salam.style.color = "red"
        salam.style.backgroundColor = "green"
        salam.style.fontSize = "10px"
        salam.style.border = "1px solid red"
        ```
    * menggunakan CSS
        ```javascript
        let salam = document.getElementById("salam")
        salam.style.cssText = "backgroundColor: red; color: green; fontSize : 10px";
        ```
## DAY 5
* ### Event
    * cara menambahkan event
        1. HTML attribute
            ```Javascript
            <h1 onClick="alert("halo guys")">click saya</h1>
            ```
        2. Event property
            ```Javascript
            let heading = document.getElementById("heading")
            paragraf.onclick = tampilkanAlert
            function tampilkanAlert(){
                alert("halo guys")
            }
            ```
        3. addEventListener
            ```Javascript
            let button = document.getElementById("btn")
            button.addEventListener("click", function(){
                console.log("contoh dari addEventListener")
            })
            ```
* ### Forms
    * form merupakan bagian pada html yang dapat digunakan untuk membuat element form pada halaman web, element form terdiri dari check bpx, radio button, menu, text box, text area, dan button
    * menggunakan Form
        ```javascript
        let form = document.getElementById('form')
        ```
    * menggunakan form.input
        ```javascript
        let form = document.getElementById('form')
        let input = form.input
        ```
    * menggunakan form input value
        ```javascript
        let form = document.getElementById('form')
        let input = form.input
        let value = input.value
        ```
    * menggunakan form input type
        ```javascript
        let form = document.getElementById('form');
        let input = form.input
        let type = input.type
        ```
    * menggunakan form input placeholder
        ```javascript
        let form = document.getElementById('form');
        let input = form.input
        let placeholder = input.placeholder
        ```
    * menggunakan form input checked
        ```javascript
        let form = document.getElementById('form');
        let input = form.input
        let checked = input.checked
        ```
    * menggunakan form input disabled
        ```javascript
        let form = document.getElementById('form');
        let input = form.input
        let disabled = input.disabled
        ```
    * menggunakan form input max length
        ```javascript
        let form = document.getElementById('form');
        let input = form.input
        let maxLength = input.maxLength
        ```
    * menggunakan form input min length
        ```javascript
        let form = document.getElementById('form');
        let input = form.input
        let minLength = input.minLength
        ```