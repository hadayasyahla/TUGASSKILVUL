# Writing test
## React Context
* React Context API adalah struktur komponen, yang memungkinkan kita untuk berbagi data di semua level aplikasi. Tujuan utama dari API Konteks adalah untuk memecahkan masalah pengeboran prop
* Context dirancang untuk berbagi data yang dapat dianggap “global” untuk diagram komponen React, seperti pengguna terotentikasi saat ini, tema, atau bahasa yang disukai
* cara membuat dan menggunakan react context
 a. membuat file component untuk menampung react contextnya
 b. lalu membuat context menggunakan `export const KeranjangCountContext = createContext()` 
 c. didalam return kita membuat pembungkus menggunakan `<KeranjangCountContext.Provider></KeranjangCountContext.Provider>` 
 d. kemudian membuat penampung statenya atau datanya menggunakan useState `const [keranjangCount, setKeranjangCount] = useState(0)`, 
 e. lalu pembungkusnya diberikan value yang isinya adalah state keranjangCount dan setKeranjangCount`<KeranjangCountContext.Provider value={{keranjangCount setKeranjangCount}}>`, 
 f. kemudian karena component context akan membungkus app.jsx maka diberi props children dan panggil children kedalam pembungkus providernya dan kita masuk ke file main.jsx dan bungkus app menggunakan nama function dimana tempat dibuat react contextnya`<kerangjangCountProvider><App /></keranjangCountProvider>` maka app akan masuk kedalam props children di keranjangCountProvider, maka state keranjangCount sudah menjadi state global
 g. untuk menggunakan contexnya dengan cara import useContext terlebih dahulu
 h. untuk memanggil menggunakan useContext(),
 i. masukkan nama contextnya menjadi `useContext(KeranjangCountContext)` 
 j. import juga KeranjangCountContext,  ketika kita mencoba console.log statenya akan  berisi sbuah state dari KeranjangCountContextnya yang artinya berhasil memanggil state dari KeranjangCountContextnya di component lain, karena disini sedang mencoba menggunakan context untuk membuat sebuah aplikasi counter maka yang akan tampil adalah 0 atau state awal dari keranjangCountContext
 k.untuk menghubungkan agar tombol counter + dan - di pencet maka state dari keranjangCountContextnya akan berubah maka kita tambahkan di dalam function increment dan decrement dengan `setKeranjangCount(keranjangCount + 1)` untuk tombol increment, dan untuk tombol decrement menambahkan `setKeranjangCount(keranjangCount - 1)`  ketika tombol button + dan - di pencet maka nilai dari keranjangCount akan mengikuti count dari file counterny
 
## React Testing
* ## Unit testing
* Unit testing Unit Testing Pengujian unit adalah salah satu tes veteran yang masih populer di kalangan pengujian. Seperti namanya, Anda akan menguji setiap bagian kode untuk memverifikasi bahwa mereka berfungsi secara independen seperti yang diharapkan
* Alasan unit testing itu penting diantaranya:
    1. Membantu reusability code pada projek baru
    2. Membantu developer untuk memahami basis kode dan memungkinkan mereka membuat perubahan dengan cepat
    3. Membantu memperbaiki bug di awal pada siklus software development dan menghemat biaya
    4. Berfungsi sebagai dokumentasi proyek
* Unit testing memiliki tujuan untuk mendapatkan hasil yang sesuai ekspektasi
* Kelebihan unit testing
    1. Membantu mendeteksi bug regression (bug yang menyebabkan fitur menjadi berhenti)
    2. Membuat penulisan kode lebih efisien
    3. Membantu menemukan sebuah bug sebelumnya
    4. Membuat kode lebih mudah di refactor
    5. Membantu menulis kode lebih baik
* Kekurangan unit testing
    1. Sangat sulit untuk melakukan test terhadap legacy code
    2. Sedikit sulit untuk melakukan test kode berbasi GUI
    3. Test membutuhkan waktu yang banyak untuk melakukan maintenance
    4. Unit Testing tidak menangkap semua error
    5. Membutuhkan waktu untuk melakukan tes
* hal sederhana yaitu membuat sebuah function yang memiliki tujuan function  untuk melakukan pengurangan, Misal kita mempunyai ‘value1’ bernilai 50 dan ‘value2’ bernilai 5 maka kita mengharapkan dari function tersebut bisa menghasilkan nilai 45. Di sini lah unit testing melakukan pengujian, apakah dari function tersebut menghasilkan nilai sesuai dengan yang diharapkan? Jika iya, maka test tersebut berhasil dan jika tidak, maka test tersebut gagal.

* React Testing Library adalah solusi yang sangat ringan untuk menguji komponen React. Ini menyediakan fungsi utilitas ringan di atas react-dom dan react-dom/test-utils, dengan cara yang mendorong praktik pengujian yang lebih baik.
* contoh testing
    1. buat ekspektasi terlebih dahulu dari function yang ketika dibuat akan menjumlahkan 2 parameter
    2. lalu buat functionnya
* Testing Jest
 1. `npm install -D jest` install jest 
 2. kita buat testingnya terlebih dahulu(ekspektasi) dengan menuliskan test yang berisi 2 argumen, argumen pertama menjelaskan isi testnya apa lalu parameter yang kedua adalah callback
 3. lalu buat functionnya
 4. tambahkan `  "scripts": {"test": "jest"},` pada dependencies agar bisa dirun
 5. `npm run test` untuk menjalankan dengan mengetikan 
 6. ketika test yang dijalankan sesuai dengan ekspektasi(benar) maka akan menampilkan
 7. tetapi ketika test tidak sesuai dengan ekspektasi(salah) maka akan menampilkan
 8. ketika kita menambahkan `--coverage` di script setelah text `"test": "jest --coverage"` maka ketika di test dijalankan maka akan dikasih tau berapa persen kodingan kita sudah tercoverage ke dalam testing
 
 

 * RTL (React Testing Library)
    1. install rtl menggunakan `npm install --save-dev @testing-library/react `
    2. kita membuat test block, didalam test block ada proses render component, find element, interact with element dan assert the result
    3. kita akan membuat project react yang didalamnya sudah mengimplementasikan rtl dengan mengetikan `npx create-react-app rtl` biasanya untuk pembuat project react menggunakan cra akan otomatis didalamnya ada rtl dan ketika di jalankan akan menampilkan logo react dan dibawahnya ada tulisan Learn React, lalu apa yang sebenarnya dilakukan oleh rtl, yang pertama di file App.test.js akan ada test yang didalamnya terdapat parameter bahwa ini akan merender learn react link, lalu parameter kedua melakukan callback yang didalamnya akan melakukan render terhadap file `<App />` setelah component app dirender lalu ambil menggunakan `screen.getByText(/learn react/i)` screen lalu getByText maksudnya akan mencari learn react didalam component app, untuk penulisannya dalam bentuk regex. atau secara singkat screen akan mencari text yang berupa `learn react` didalam component app. lalu `expect(linkElement).toBeinTheDocument()` maksudnya yaitu ekspektasinya adalah linkElementnya ada di dalam documentnya

    4. dari kumpulan test block bisa kita masukkan kedalam describe block
    5. contohnya kita akan mengetes counter, kita buat component counter dengan button - dan button +
    6. lalu kita bungkus counternya
    7. lalu kita buat testnya di file counter.test.js dan buat testnya
    8. test pertama kita akan mencari di screen apakah text dengan isi "-" ada?. cara membacanya yaitu kita buat test lalu ketika merender component counter kita cari di layar(screen) apakah ada text dengan isi "-" menggunakan `getByText("-")` dan ekspektasinya minBtn yang berisi getByText harusnya ada di dalam document, ketika di jalankan maka akan pass atau berhasil karena memang di dalam component Counter ada text - yaitu di button -
* Test ID
    1. getByTestId
* Access by everyone
    1. getByPlaceholderText
    2. getByRole
    3. getByText
    4. getByLabelText
* Sematic Queries
    1. getByAltText
    2. getByTitle
