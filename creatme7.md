# Writing
* ## PROP TYPE
* PropTypes merupakan library untuk menvalidasi props. Ini sangat membantu dalam meminimalkan bugs saat mengembangkan App besar. Jika props tidak benar type nya maka akan muncul warning

* Macam Macam PropTypes
    
    a. mengecek value dari props menggunakan `data: PropTypes.arrayOf(PropTypes.number)`
    b. data yang dikirimkan bersifat bebas`name: PropTypes.any.isRequired` dan data harus ada `isRequired` 
    c. mengecek nilai dari object menggunakan shape dan tidak harus sama dari jumlah keynya
    d. type data array `data: PropTypes.array` 
    e. array dengan berbagai macam type data`data: PropTypes.arrayOf(PropTypes.oneOfType([PropTypes.number, PropTypes.string]))` 
    f. type data object`info: PropTypes.object`
    g. data yng bisa dikirimkan harus bertipe string`name: PropTypes.string`
    h. data yang bisa dikirimkan diantara tipe data string dan number, selain itu tidak bisa`age: PropTypes.oneOfType([PropTypes.string, PropTypes.number])` 
    i. mengecek nilai dan key dari sebuah object, apabila menggunakan exact nilai dari jumlah key harus sama dengan yang ada di propsnya

    * apabila sebuah data yang dikirimkan tidak sesuai dengan prop types maka akan menampilkan error dikonsol
* Syntax Prop Type
    ```javascript
    import PropTypes from 'prop-types';

    class Greeting extends React.Component {
        render() {
            return (
                <h1>Hello, {this.props.name}</h1>
    );
  }
}

Greeting.propTypes = {
  name: PropTypes.string
};
    ```



* ## React Router
* ## Routing pada React.js
* Dalam web jika ingin berganti halaman satu dan halaman yang lainnya diperlukan suatu proses routing. Routing sendiri adalah proses pemetaan antara sebuah URL ke dalam sebuah halaman yang terdapat konten / UI (User Interface) sesuai dengan URL yang dituju.
* Jika membuat routing menggunakan library tambahan ,karena tidak secara langsung tersedia.Beberapa library bisa digunakan, diantaranya yaitu library react-router dan reach/router. yang digunakan untuk routing di React biasa menggunakan react-router-dom anak dari react-router, selain react-router-dom juga terdapat react-router-native yang bisa digunakan untuk development aplikasi Android dan iOS.
* Library react-router-dom dapat diinstall dengan menjalankan sebuah perintah`yarn add react-router-dom` 
* digunakan untuk membuat tautan yang memungkinkan untuk menavigasi pada URL berbeda dan membuat kontennya tanpa memuat ulang sebuah halaman .`<Link>` 
* komponen NavLink digunakan untuk menambahkan gaya ke rute aktif `<Navlink>` 
* fungsi Routes untuk membungkus/menampung sebuah child route`<Routes><Routes>` 
* route berfungsi untuk menampung alamat yang digunakan untuk berpindah halaman `<Route>` 
* react-router-dom mempunyai 2 jenis router yang dapat di gunakan, HashRouter dan BrowserRouter. meraka mempunyai kegunaannya masing-masing dan tergantung dari jenis Web apa yang akan kita buat nantinya. contohnya seperti , apabila kita akan membuat sebuah web yang static atau tidak ada server untuk me-render data yang dinamis, sebaiknya kita menggunakan HashRouter. Begitupun Sebaliknya, jika kita membuat sebuah web yang menggunakan data dinamis dengan server backend, maka menggunakan BrowserRouter adalah pilihan yang tepat.
* ## Membuat routing dasar
    1. install react router ketikan `npm install react-router-dom@6`  diterminal vscode 
    2. import BrowserRouter di main.js `import { BrowserRouter } from "react-router-dom"`
    3. bungkus app di main.js dengan BrowserRouter,  dibungkus bertujuan agar react mengetahui bahwa di project kita akan memakai react router .
    4. import Routes,  Link dari react router dom, dan Route, fungsi Routes untuk membungkus child route, route yang memiliki fungsi untuk menampung alamat yang digunakan untuk berpindah halaman , dan link yaitu memiliki fungsi yang hampir mirip seperti tag a / biasa disebut pengganti sebuah tag a di react
    5. import semua halaman
    6. kita masukan untuk routingnya, seperti contoh. saya ingin merouting ke halaman HomePage, ketika link url kita tambahi dengan "/"  akan berpindah ke halaman HomePage
        ```javascript
        <Routes>
            <Route path="/" element={<HomePage/>}/>
        </Routes>
        ```
    7. karena tidak mungkin setiap kita berpindah halaman dengan merubah urlnya secara manual, maka kita bisa menggunakan navbar bertujuan agar button homepage di klik maka otomatis akan berpindah ke halaman HomePage, untuk syntaxnya menggunakan `<Link to={"/"}>Home</Link>`, untuk `to={}` kita bisa isikan path halaman yang ingin kita pindah didalamnya 

* ## Membuat dynamic route
    a. untuk membuat dynamic route membutuhkan params, dynamic route itu apabila ada daftar menu nomer 1-10 lalu apabila kita klik salah satu daftar menu tersebuat akan berpindah ke halaman detail menu tersebut beserta datanya, contohnya kita memilih menu 5 maka akan membawa dan menampilkan data 5 kedalam routenya
    b. membuat routnya terlebih dahulu ` <Route path='/detail/:id' element={<DetailPage/>}/>` menggunakan `:id` apabila berpindah halaman misalnya 2, maka pathnya akan berubah menjadi `/detail/2`
    c. kita menggunakan data dummy, dengan membuat array of object bernama data yang didalamnya berisikan beberapa data
    d. lalu kita tampilkan daftar datanya terlebih dahulu ke browser dengan mapping dan tambahkan button agar tiap data bisa di pilih dan kita membuat fungsi apabila button di klik maka akan mengirim id sesuai nama tersebut
    e. untuk berpindah dengan membawa data menggunakan params memerlukan useNavigate, fungsinya sama seperti Link tetapi untuk useNavigate bisa membawa data seperti params
    f. misalnya data yang pertama dipilih. maka params akan membawa data pertama, lalu untuk menampilkannya pertama tama kita membuat data baru  yang lebih detail, untuk menangkap id yang dibawa oleh useNavigate menggunakan useParams
    g. untuk menampilkan sesuai dari id yang dibawa oleh useNavigate dan diterima useParams, akan menggunakan filter


* ## membuat nested route
* nested route digunakan ketika sebuah halaman about yang didalamnya berisikan halaman lagi contohnya about teacher dan about student, maka bisa menggunkan nested route. caranya yaitu :
    1. kita membuat agar si parent yaitu Route about tidak single tag yaitu dengan menambahkan tag Route penutup, lalu masukkan Route about teacher dan about student kedalam Route about, jadi akan menjadi child dari about
    2. lalu untuk path about pada about teacher dan about student di hilangkan sehingga menyisakan path teacher dan student sehingga menjadi seperti ini, 
    3. daftarkan anak anak dari about agar bisa berpindah ke halaman student dan teacher menggunakan `Outlet`, caranya tuliskan `<Outlet />` di induknya yaitu halaman about, maka di halaman about akan terdeteksi halaman student dan teacher, kita sudah bisa berpindah ke halaman student dan teacher,
    4. lalu kita ingin memanggil atau berpindah ke halaman about student dan about teacher,  kita menuliskannya seperti dibawah ini yaitu tidak menggunakan slash awal
* ## Konsep dan cara menggunakan redux
* Redux adalah sebuah aplikasi state management. adalah cara untuk memfasilitasi komunikasi dan berbagai data lintas komponen. State management menciptakan struktur data yang nyata untuk mewakili keadaan aplikasi Anda yang dapat Anda gunakan untuk membaca dan menulis.
* gunakan Redux jika Banyak data yang berubah dari waktu ke waktu. 
* hal hal yang dilakukan store yaitu menyimpan state, memberikan akses ke state, mengupdate state
* action adalah object javascript sederhana yang digunakan untuk mengirim informasi dari aplikasi ke store
* provider adalah untuk memberi tahu bahwa store tersedia untuk component yang dibungkus yaitu App sehingga App bisa mengambil data dari store
* useSelector digunakan untuk mengabil data dari store
* dispatch digunakan untuk mengirim action ke reducer
* Store adalah tempat untuk menyimpan semua state secara global.
* combine reducer adalah cara ketika mempunyai 2 atau lebih reducer dan menggabungkannya menggunakan combineReducer
* reducer adalah function yang didalamnya terdapat function switch case, mereka mengambil state dan action sebagai argumen dan mengembalikan ke statenya
* install package redux dan react redux `npm install redux react-redux`



* langkah menggunakan redux
    1. membuat store menggunakan createStore()
    2. membuat reducer adalah function didalam store, didalamnya ada switch case, untuk return dari switch case mengikuti initialState, misalkan menggunakan object {}, maka di return switch casenya juga menggunakan object {}, jika berbentuk array maka return juga array 
    3. membuat provider, memberi tahu bahwa store tersedia untuk component app, provider membungkus component app, sehingga app bisa mengambil data dari store
    4. mengambil state menggunakan useSelector ngambil state dari store,useSelector untuk mengambil data dari store
    5. membuat action misalnya jika casenya increment maka akan mereturn data + 1 di dalam reducer
    6. sebelum menggunakan action, kita buat dispatch dari useDispatch, dispatch digunakan untuk mengirim action kedalam reducer
* useSelector itu hook yang otomatis menuju ke store, file yang ada createStore, lalu didalam store = createStore(Reducer) ada reducer, di reducer ada state, maka secara singkat useSelector itu isinya state yang ada di reducer<br>

* array function bisa mempersingkat syntax, contoh:
    ```javascript
    const myFunction = (state) => {
        return state
    }
    ```
    bisa menjadi
    ```javascript
    const myFunction = (state) => state
    ```
* ## Redux Thunk
* Redux Thunk adalah middleware yang memungkinkan Anda memanggil pembuat aksi yang mengembalikan fungsi sebagai ganti objek aksi. Fungsi itu menerima metode pengiriman penyimpanan, yang kemudian digunakan untuk mengirim aksi sinkron di dalam isi fungsi setelah operasi asinkron selesai.
* install redux dengan mengetikan `npm install redux react-redux`
* install redux thunk dan thunk `npm install thunk redux-thunk` 
* install axios `npm install axios`


1. buat store dan buat function allReducer menggunakan combineReducers, combineReducers digunakan ketika ada 2 atau lebih reducer dalam satu project, yang beda dari pembuatan store redux dengan redux thunk adalah dengan mengimport thunk dan applyMiddleware dan menambahkan applyMiddleware(thunk) didalam variabel store
2. buat action untuk ambil data dari api menggunakan thunk, dispatch sifat bawaan dispatch adalah langsung mengirimkan data ke reducer(synchronous), sehingga ketika membutuhkan asyncronous atau yang membutuhkan delay membutuhkan thunk, disini kita menggunakan mock api dan untuk handlenya menggunakan axios. 
3. buat reducer disini initial state akan berisi array todos dan variabel isLoading: false dan didalam switch case akan ada case FETCH_START untuk menampilkan semua isi state dan mengubah isLoading menjadi true, lalu case SUCCESS_GET_TODO untuk menampilkan semua isi state dan akan menjalankan action.payload dan merubah isLoading menjadi false dan menampilkan data yang telah di fetch tadi
4. provider file main.jsx, provider menggunakan store={store}
5. useSelector, kita menggunakan useSelector dan useDispatch, pertama kita useSelector statenya kemudian kita return dan melakukan destrukturing menjadi todos dan isLoading, kemudian ketika kode dijalankan atau merender maka akan menggunakan sideEffect, disini sideEffectnya akan melakukan dispatch getTodo  akan dilooping di dalam return function TodoListnya.