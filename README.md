
# Project Deteksi Marka Jalan
Muhammad Tegar Wiratama Pohan
202131169
Pengolahan Citra F

# Teori Garis Tepi 
Deteksi Tepi (Edge)
Tepi (edge) adalah perubahan nilai intensitas derajat keabuan yang mendadak besar 
dalam jarak yang dekat. Suatu titik (x,y) dikatakan sebagai tepi bila titik tersebut mempunyai 
perbedaan nilai piksel yang tinggi dengan nilai piksel tetangganya [3]. Perubahan mencapai
maksimum pada saat nilai turunan pertamanya mencapai nilai maksimum atau nilai turunan 
kedua (2nd derivative) bernilai 0. Deteksi tepi (Edge detection) adalah operasi yang dijalankan 
untuk mendeteksi garis tepi (edges) yang membatasi dua wilayah citra homogen yang memiliki 
tingkat kecerahan yang berbeda. Deteksi tepi pada suatu citra adalah suatu proses yang 
menghasilkan tepi-tepi dari obyek-obyek citra, tujuannya adalah :
a. Untuk menandai bagian yang menjadi detail citra
b. Untuk memperbaiki detail dari citra yang kabur, yang terjadi karena error atau
adanya efek dari proses akuisisi citra.
c. Serta untuk mengubah citra 2D menjadi bentuk kurva
Suatu titik (x,y) dikatakan sebagai tepi (edge) dari suatu citra bila titik 
tersebutmempunyai perbedaan yang tinggi dengan tetangganya [4]. 
# Mengenai Marka Jalan 
Markah jalan digunakan di permukaan jalan untuk mengarahkan dan memberi informasi kepada pengendara maupun pejalan kaki. Keseragaman bentuk markah merupakan faktor penting untuk meminimalkan kebingungan dan keraguan atas arti markah tersebut. Telah ada upaya antarnegara untuk melakukan standardisasi bentuk markah jalan.

Marka jalan membujur utuh adalah tanda lalu lintas berupa garis lurus yang tergambar di tengah-tengah permukaan jalan raya. Fungsinya, bila berada di tengah jalan ialah sebagai larangan bagi kendaraan untuk melintasi garis tersebut atau pun sebagai pembagi lajur kendaraan. 
Namun, bila letaknya di tepi jalan, maka fungsinya adalah sebagai tanda peringatan tepi jalur lalu lintas. Makna garis putih lurus adalah pengendara tidak diperbolehkan mendahului kendaraan lain dan tetap berada di jalur masing-masing.

# Menjelaskan Tahapan Cara  Menyelesaikan Projek
1. Memfoto Objek yang ingin di ubah di sin adalah Marka Jalan
2. Import Library: Langkah pertama adalah mengimpor library yang dibutuhkan, yaitu OpenCV (`import cv2`) dan NumPy (`import numpy as np`).
3. Membaca Gambar: Menggunakan `cv2.imread('path_to_image.jpg')` untuk membaca gambar jalan dari file yang ditentukan. Pastikan Anda mengganti `'path_to_image.jpg'` dengan path yang benar ke gambar jalan yang ingin Anda deteksi markanya
4. Mengubah skema warna gambar dari BGR ke RGB image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
5. Untuk Mencatak Dimensi gambar kita menggunakan perintah print(image.shape)
6. Untuk mengambil tinggi dan lebar gambarnya kita menggunakan perintah height = image.shape[bebas mau berapa ] dan juga untuk lebar nya menggunakan perintah width = image.shape[bebas]
7. Untuk Definisi titik-titik daerah minat (region of interest) region_of_interest_vertices = [ (0, height), (width/2, height/2), (width, height) ]
8. Mengubah gambar menjadi skala abu-abu gray_image = cv2.cvtColor(image, cv2.COLOR_RGB2GRAY)
9. Menerapkan deteksi tepi pada gambar canny_image = cv2.Canny(gray_image, 100, 200)
10. Memotong gambar menggunakan daerah minat cropped_image = region_of_interest(canny_image, np.array([region_of_interest_vertices], np.int32))
11. Menggambar garis-garis pada gambar asli image_with_lines = drow_the_lines(image, lines)
12. Menampilkan gambar dengan garis-garis plt.imshow(image_with_lines) plt.show()
13. Di dalam kode tersebut, pengubahan warna objek dilakukan menggunakan beberapa fungsi dari pustaka OpenCV (cv2) dan NumPy (np). Berikut adalah langkah-langkahnya
14. Pertama, gambar dimuat menggunakan fungsi `cv2.imread('jalan3.jpg')` untuk membaca gambar dari file 'jalan3.jpg' dan menyimpannya dalam variabel `image`.
15. Selanjutnya, gambar dikonversi ke skema warna RGB menggunakan fungsi `cv2.cvtColor(image, cv2.COLOR_BGR2RGB)`. Kode `cv2.COLOR_BGR2RGB` digunakan untuk menentukan konversi warna dari BGR (format default OpenCV) ke RGB.
16. Setelah gambar dikonversi ke skema warna RGB, langkah-langkah berikutnya adalah melakukan operasi pada gambar tersebut. Salah satu langkahnya adalah mengubah gambar ke skala abu-abu menggunakan fungsi `cv2.cvtColor(image, cv2.COLOR_RGB2GRAY)`. Ini menghasilkan gambar dengan tingkat keabuan di setiap pikselnya.
17. Selanjutnya, operasi Canny edge detection dilakukan pada gambar skala abu-abu menggunakan fungsi `cv2.Canny(gray_image, 100, 200)`. Fungsi ini menemukan tepi dalam gambar dengan memanfaatkan perbedaan intensitas piksel.
18. Setelah itu, dilakukan pemangkasan (cropping) pada gambar untuk mendefinisikan area kepentingan menggunakan fungsi `region_of_interest()`. Fungsi ini menghasilkan gambar yang hanya berisi bagian yang penting dari gambar asli (area di dalam poligon yang didefinisikan oleh `region_of_interest_vertices`).
19. Kemudian, deteksi garis dilakukan pada gambar yang telah dipangkas menggunakan fungsi `cv2.HoughLinesP()`. Fungsi ini menggunakan transformasi Hough probabilistik untuk mendeteksi garis-garis dalam gambar.
20. Setelah mendapatkan garis-garis hasil deteksi, gambar asli diubah dengan menambahkan garis-garis tersebut menggunakan fungsi `draw_the_lines()`. Fungsi ini membuat salinan gambar asli dan menggambar garis-garis yang ditemukan pada gambar salinan tersebut.
21. Akhirnya, gambar dengan garis-garis ditampilkan menggunakan `plt.imshow()` dari pustaka Matplotlib, dan `plt.show()` untuk menampilkan plot gambar.
## Acknowledgements

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)

