# Recommendation System using Collaborative Filtering (KNN and Funk SVD Model) for Movie Recommendations
## A.	Business Problem 

Industri hiburan dan streaming telah berkembang pesat selama beberapa tahun terakhir, dengan banyak platform bersaing untuk menarik perhatian dan mempertahankan User mereka. Cinema-Iflix.com, salah satu platform streaming yang telah ada dalam industri ini, saat ini sedang menghadapi tantangan serius dalam hal retensi User. Retensi User adalah salah satu komponen kritis dalam mengukur keberhasilan platform streaming, karena mencerminkan kemampuan platform untuk mempertahankan User yang telah mendaftar dan memperpanjang langganan mereka.

Dalam 6 bulan terakhir, Cinema-Iflix.com telah mengalami penurunan yang signifikan dalam tingkat retensi User mereka. Penurunan tajam ini mencapai hampir 10%, yang merupakan penurunan yang mencolok dalam waktu yang relatif singkat. Dampak dari penurunan ini sangat dirasakan pada pendapatan Cinema-Iflix.com. Penurunan 10% dalam tingkat retensi User berarti bahwa sejumlah besar User yang sebelumnya setia kepada platform ini, sekarang telah beralih ke platform pesaing atau mungkin bahkan memutuskan untuk tidak berlangganan atau menggunakan platform streaming sama sekali. Ini secara langsung mengancam pendapatan Cinema-Iflix.com yang bergantung pada berlangganan bulanan, iklan, dan penjualan konten.

Setelah melakukan penelitian User yang mendesak, tim Cinema-Iflix.com menemukan masalah mendasar yang perlu dipecahkan. User platform ini menghadapi kesulitan signifikan saat mencari film di Cinema-Iflix.com. Meskipun platform ini memiliki koleksi film yang mengesankan dengan hampir 4.000 judul, User mengalami kesulitan dalam menavigasi dan menemukan film yang sesuai dengan preferensi mereka. Hal ini mempengaruhi pengalaman User secara keseluruhan dan menjadi salah satu penyebab utama penurunan retensi User.
Selain latar belakang masalah di atas, terdapat beberapa masalah lain yang perlu dipertimbangkan dalam konteks ini:

1.	Kompetisi yang Ketat: 
Industri streaming adalah pasar yang sangat kompetitif dengan banyak pesaing yang menawarkan konten serupa. User memiliki banyak opsi untuk beralih ke platform lain jika pengalaman mereka di Cinema-Iflix.com tidak memuaskan.

2.	Perubahan Preferensi User: 
Selain masalah navigasi, perubahan preferensi User terhadap konten dan pengalaman streaming juga dapat memengaruhi retensi. Asumsi ini mengasumsikan bahwa perubahan dalam selera User mungkin juga berkontribusi pada penurunan retensi.

4.	Tantangan Teknis: 
Mengelola dan menyajikan lebih dari 4.000 film dalam platform streaming dapat menghadirkan tantangan teknis seperti performa dan kecepatan akses. Ini bisa menjadi faktor yang berperan dalam masalah navigasi yang dihadapi oleh User.

6.	Ketidakpuasan Konten: 
Selain navigasi, ketidakpuasan terhadap kualitas konten yang tersedia juga dapat mempengaruhi retensi. User yang tidak menemukan konten yang mereka nikmati atau kualitas yang diharapkan mungkin cenderung meninggalkan platform.

8.	Pendekatan Pengalaman User (User Experience): 
Asumsi lain adalah bahwa meningkatkan pengalaman User secara keseluruhan, termasuk navigasi yang lebih baik dan rekomendasi yang lebih cerdas, dapat membantu memperbaiki retensi User.

Dengan memahami latar belakang masalah bisnis dan asumsi-asumsi yang terkait, Cinema-Iflix.com dapat merumuskan strategi yang efektif untuk mengatasi penurunan retensi User dan memulihkan pendapatan mereka.


## B.	Business Objective

Cinema-Iflix.com telah mengidentifikasi penurunan yang signifikan dalam tingkat retensi User sebagai masalah kritis dalam bisnis mereka. Oleh karena itu, tujuan bisnis utama yang telah ditetapkan adalah meningkatkan tingkat retensi User menjadi 10% dalam jangka waktu 6 bulan. Meskipun ini adalah asumsi, tujuan ini memiliki implikasi penting dalam upaya untuk mengembalikan pertumbuhan dan stabilitas bisnis Cinema-Iflix.com.

Rasionalisasi Tujuan:

1.	Mengatasi Penurunan Pendapatan:
   
Penurunan 10% dalam tingkat retensi User telah memberikan dampak negatif pada pendapatan Cinema-Iflix.com. Dengan meningkatkan tingkat retensi, diharapkan akan terjadi peningkatan pendapatan yang signifikan karena lebih banyak User akan tetap setia dan berlangganan.

2.	Meningkatkan Keunggulan Bersaing:
   
Dalam industri streaming yang kompetitif, memiliki tingkat retensi User yang tinggi adalah aset berharga. Dengan mencapai tujuan ini, Cinema-Iflix.com dapat mempertahankan dan bahkan meningkatkan pangsa pasar mereka dengan menghadirkan pengalaman User yang lebih baik dibandingkan dengan pesaing.

3.	Mengembangkan Kepuasan User:
   
Meningkatkan retensi User juga berarti memperbaiki pengalaman User secara keseluruhan. User yang merasa puas dan dapat dengan mudah menemukan konten yang mereka nikmati akan lebih cenderung tetap setia.

4.	Pemulihan Kepercayaan User:
   
Jatuhnya tingkat retensi User dapat menciptakan ketidakpercayaan terhadap platform. Dengan mencapai tujuan ini, Cinema-Iflix.com dapat memulihkan kepercayaan User yang mungkin telah hilang akibat pengalaman sebelumnya.

5.	Stabilitas Bisnis Jangka Panjang:
   
Pencapaian tujuan ini adalah langkah kunci dalam memastikan kelangsungan bisnis jangka panjang Cinema-Iflix.com. Retensi User yang stabil akan membantu menciptakan pendapatan berkelanjutan dan memperkuat posisi platform di pasar streaming yang berubah-ubah.

6.	Peningkatan Nilai Pelanggan:
   
Retensi User yang lebih tinggi juga berarti pelanggan akan menghasilkan lebih banyak nilai bagi Cinema-Iflix.com dalam jangka panjang, baik melalui berlangganan bulanan maupun melalui partisipasi dalam berbagai promosi dan penjualan konten tambahan.

Dengan mengadopsi tujuan ini, Cinema-Iflix.com mengambil langkah proaktif untuk memecahkan masalah utama dalam bisnis mereka. Dalam jangka waktu 6 bulan, perusahaan berkomitmen untuk mencapai pertumbuhan signifikan dalam retensi User dengan meluncurkan strategi dan inisiatif yang bertujuan untuk mengatasi kendala-kendala yang menyebabkan penurunan retensi dan meningkatkan pengalaman User secara keseluruhan. Ini adalah langkah kunci menuju pemulihan dan pertumbuhan yang berkelanjutan dalam industri streaming yang dinamis.

## C.	Business Solution
Platform Cinema-Iflix.com menghadapi tantangan umum yang biasa dihadapi oleh layanan streaming, yaitu membantu User menelusuri dan menemukan film dalam katalog yang sangat besar. Untuk mengatasi masalah ini dan meningkatkan pengalaman User, platform ini bermaksud untuk mengimplementasikan sistem rekomendasi film. Tujuan utama dari sistem rekomendasi ini adalah memberikan rekomendasi film yang sesuai dengan preferensi User. 

