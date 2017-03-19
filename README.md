# webservice - XML & DTD

<!DOCTYPE logbooks SYSTEM "logbooks.dtd">

1. DTD diawali dengan <! DOCTYPE pembatas atau delimiter.
2. logbooks sebagai nama root elemen
3. logbooks.dtd sebagai identifier untuk pengidentifikasi untuk definisi jenis dokumen, dan menjadi path atau jalan ke file di sistem, jika DTD menunjukan path eksternal, maka itu disebut subset eksternal.

Untuk tugas kali ini, saya memakai DTD eksetrnal, jadi DTD dideklarasikan diluar file XML, file ini diaksse dengan menentukan atribut sistem yang berupa file .dtd. Untuk mereferensikan itu sebagai DTD eksternal, atribut yang stand alone atau berdiri sendiri di pada pendeklarasian XML harus di atur 'no'.

isi dari file tgs1.dtd adalah

<?xml encoding="UTF-8"?>

<!ELEMENT logbooks (book)+> // ELEMENT berarti tag deklarasi elemen. sedangkan loognooks adalah nama elemennya, dan books adalah elemen dan setiap elemen harus memiliki pendeklarasian sendiri pada DTD.
<!ATTLIST logbooks // atribut DTD dimulai pada baris ini, jika elemen mengandung atribut.
    xmlns CDATA #FIXED ''> // pada baris ini menggunakan kata kunci #fixed, dimana hal inin menunjukan bahwa nilai untuk nama atribut dari elemen <book>
<!ELEMENT book (title,year,details,publisher)> // pada baris ini, book adalah elemen induk, sedangkan title, year, details, publisher adalah anak elemen.
<!ATTLIST book
    xmlns CDATA #FIXED ''>  // pada baris ini menggunakan kata kunci #fixed, dimana hal ini menunjukan bahwa nilai untuk nama atribut dari elemen <title,year,details,publisher>, CDATA adalah teks yang tidak akan bisa parsed oleh parser, tag didalam teks tidak akan diperlakukan sebagai markup dan entitinya tidak akan membesar/meluas.

<!ELEMENT title (#PCDATA)> // pada baris ini mendefinisikan nama elemen menjadi tipe #PCDATA sedangkan #PCDATA itu sendiri berarti data yang bisa mengurangi teksnya.
<!ATTLIST title
    xmlns CDATA #FIXED ''>

<!ELEMENT year (#PCDATA)> // pada baris ini mendefinisikan nama elemen menjadi tipe #PCDATA sedangkan #PCDATA itu sendiri berarti data yang bisa mengurangi teksnya.
<!ATTLIST year
    xmlns CDATA #FIXED ''>

<!ELEMENT details (writer,age)> // pada baris ini, details adalah elemen induk, sedangkan writer dan age adalah anak elemen.
<!ATTLIST details
    xmlns CDATA #FIXED ''> // pada baris ini menggunakan kata kunci #fixed, dimana hal inin menunjukan bahwa nilai untuk nama atribut dari elemen <writer,age>

<!ELEMENT publisher (company|location)+> //baris ini menunjukan bahwa saya perlu mengizinkan satu elemen atau yang lain, tetapi bukan keduanya, jadi perlu mengunakan simbol | simbol ini berfungsi sebagai 'atau'
<!ATTLIST publisher
    xmlns CDATA #FIXED ''> // pada baris ini menggunakan kata kunci #fixed, dimana hal inin menunjukan bahwa nilai untuk nama atribut dari elemen <company|location>

<!ELEMENT writer (#PCDATA)> // pada baris ini mendefinisikan nama elemen menjadi tipe #PCDATA sedangkan #PCDATA itu sendiri berarti data yang bisa mengurangi teksnya.
<!ATTLIST writer
    xmlns CDATA #FIXED ''>

<!ELEMENT age (#PCDATA)> // pada baris ini mendefinisikan nama elemen menjadi tipe #PCDATA sedangkan #PCDATA itu sendiri berarti data yang bisa mengurangi teksnya.
<!ATTLIST age
    xmlns CDATA #FIXED ''>

<!ELEMENT company (#PCDATA)> // pada baris ini mendefinisikan nama elemen menjadi tipe #PCDATA sedangkan #PCDATA itu sendiri berarti data yang bisa mengurangi teksnya.
<!ATTLIST company
    xmlns CDATA #FIXED ''>

<!ELEMENT location (#PCDATA)> // pada baris ini mendefinisikan nama elemen menjadi tipe #PCDATA sedangkan #PCDATA itu sendiri berarti data yang bisa mengurangi teksnya.
<!ATTLIST location
    xmlns CDATA #FIXED ''>
    
    
    REFERENSI:
    http://www.w3ii.com/xml/default.html
