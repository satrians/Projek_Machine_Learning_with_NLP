# Projek_Machine_Learning_with_NLP
# Dataset
![image](https://github.com/user-attachments/assets/33222fd8-583e-4233-a8e3-85d2bdd887b1)
Topik Dataset : Disaster Tweets
Link : Disaster Tweets - Kaggle
Tentang Dataset : Dataset ini berisi data tweet yang dapat digunakan untuk membangun model klasifikasi teks guna membedakan antara tweet yang berhubungan dengan bencana nyata dan yang tidak berhubungan dengan bencana.

# Latar Belakang dan Masalah
Dalam era digital saat ini, media sosial telah menjadi salah satu sumber informasi utama bagi banyak orang di seluruh dunia. Twitter, sebagai salah satu platform media sosial terbesar, sering digunakan untuk berbagi informasi terkini tentang berbagai kejadian, termasuk bencana alam. Ketika bencana terjadi, banyak pengguna Twitter yang memberikan update real-time mengenai situasi yang terjadi di sekitar mereka. Informasi ini sangat berharga untuk berbagai pihak, termasuk pemerintah, organisasi bantuan, dan masyarakat umum, dalam merespons dengan cepat dan efektif. Namun, tidak semua tweet yang beredar di media sosial benar-benar relevan atau akurat. Oleh karena itu, penting untuk dapat membedakan tweet yang benar-benar memberikan informasi terkait bencana dari tweet yang tidak relevan atau palsu.

Masalah utama yang dihadapi adalah bagaimana mengidentifikasi tweet yang relevan dengan bencana secara otomatis dari sejumlah besar tweet yang diposting setiap hari. Tantangan ini mencakup beberapa aspek, seperti:
- Volume data yang sangat besar: Setiap hari, jutaan tweet diposting, dan mengidentifikasi tweet yang relevan dengan bencana di antara mereka adalah tugas yang sangat menantang.
- Keragaman bahasa dan gaya penulisan: Pengguna Twitter menggunakan berbagai bahasa, slang, dan gaya penulisan yang berbeda, yang dapat menyulitkan proses pengenalan teks.
- Keakuratan informasi: Tidak semua tweet yang menyebutkan kata kunci terkait bencana benar-benar memberikan informasi yang akurat atau relevan. Beberapa mungkin berupa rumor, candaan, atau informasi yang menyesatkan.

# Tujuan dan Target Pencapaian
Tujuan dataset ini adalah:
- Mengumpulkan dan mempersiapkan dataset yang berisi tweet-tweet terkait bencana dan tidak terkait bencana.
- Melakukan eksplorasi dan analisis awal terhadap dataset untuk memahami karakteristik data.
- Mengembangkan dan melatih model NLP yang dapat membedakan antara tweet yang relevan dengan bencana dan yang tidak.
- Mengevaluasi kinerja model dengan menggunakan metrik yang sesuai untuk memastikan keefektifan dan keandalannya dalam kondisi nyata.
- Memberikan wawasan dan rekomendasi mengenai bagaimana model ini dapat digunakan dalam sistem monitoring bencana secara real-time.
Target Pencapaian:
- Akurasi: Mengukur sejauh mana model dapat mengklasifikasikan tweet dengan benar, baik sebagai bencana maupun non-bencana.
- Presisi: Mengukur seberapa akurat model dalam mengklasifikasikan tweet sebagai bencana, dari semua tweet yang diprediksi sebagai bencana.
- Recall: mengukur seberapa baik model dalam menemukan kembali semua instance tweet yang sebenarnya bencana, dari semua tweet yang sebenarnya bencana.
- F1-Score adalah rata-rata harmonik dari presisi dan recall, memberikan keseimbangan antara kedua metrik ini.
  
# Data Loading
- Menggunakan Dataset dari link [Disaster Tweets - Kaggle](https://www.kaggle.com/datasets/vstepanenko/disaster-tweets)
- Membaca dataset ke dalam DataFrame menggunakan pandas.

# Data Cleaning
- Menghapus kolom yang tidak terpakai.
- Melakukan preprocessing kata dengan menggunakan Stopword dan WordNetLemmatizer.

# EDA (Exploratory Data Analysis)
- Menggunakan WordCloud untuk visualisasi kata-kata yang sering muncul dalam tweet bencana.
![image](https://github.com/user-attachments/assets/1ce27351-99be-445c-a6b8-7288f263b4ad)
- Menampilkan distribusi target berdasarkan target
- Menampilkan jumlah kata pada kolom "cleaned_text"
- Menampilkan panjang tweet pada kolom "cleaned_text"
![image](https://github.com/user-attachments/assets/095f35de-df43-497b-b915-5e63c77f6845)

# Feature Engineering
- Melakukan tokenisasi teks pada kolom cleaned_text
![image](https://github.com/user-attachments/assets/0683c4a1-30af-400f-bb70-30f6be98a16f)
- Menggunakan train_test_split untuk membagi dataset menjadi dua subset: satu untuk pelatihan (training set) dan satu lagi untuk pengujian (testing set).
- Untuk kolom yang digunakan untuk membagi subset menjadi dua yaitu kolom target dan kolom cleaned_text
![image](https://github.com/user-attachments/assets/b2f32e20-2f8e-4a5b-b9f3-8b2998e28227)

# Model Architecture Definition
- Arsitektur Model
- Menggunakan model Deep Learning LSTM (Long Short Term Memory)
- Memproses data sekuensial (seperti teks) dan mengklasifikasikannya. Lapisan embedding mengubah kata-kata menjadi tokenizer, LSTM menangani hubungan jangka panjang dalam data sekuensial, dan lapisan dense menghasilkan output klasifikasi. Dropout digunakan di beberapa tempat untuk mencegah overfitting.
- Mengompilasi model jaringan saraf yang telah didefinisikan sebelumnya dengan menetapkan fungsi loss, optimizer, dan metrik evaluasi.
![image](https://github.com/user-attachments/assets/b616841d-a8e7-4f05-b284-4b2527e87a79)
![image](https://github.com/user-attachments/assets/ddf95e9b-7af5-4e9d-a851-cc3c31db0d80)
![image](https://github.com/user-attachments/assets/1e3f0a39-b517-4803-b327-93556c5c6b9b)

# Model Training
- Pelatihan Model
- Membagi dataset menjadi training dan validation set.
- Melatih model dengan minimal 20 epoch.
![image](https://github.com/user-attachments/assets/9cf1f88c-8997-48dd-80a4-1021d0f8244c)

# Model Evaluasi
- Menampilkan diagram loss dan accuracy
- Menghitung metrik evaluasi seperti accuracy, precision, recall, dan F1-score.
- Menampilkan classification report dan confusion matrix.
![image](https://github.com/user-attachments/assets/fad91066-03ea-40c5-95b8-7ab6997510ee)
![image](https://github.com/user-attachments/assets/e805b68d-9ec2-4fa4-941c-0d48cc2f1f59)
![image](https://github.com/user-attachments/assets/f07f03a9-f48e-4c6d-8943-b943b820701b)
![image](https://github.com/user-attachments/assets/c320c80e-1ae8-4238-adac-cc782a042a84)

# Model Saving
Menyimpan model dengan format .h5 (TensorFlow)
![image](https://github.com/user-attachments/assets/6b522722-aeed-4f55-87fb-dd50d6525b2e)

# Model Deployment
- Sebelum masuk ke model Deployment, diharuskan mengubah format Tensorflow (.h5) ke dalam file arsip (.tgz) yang dapat digunakan untuk penyimpanan atau transfer file dengan ukuran yang lebih kecil dibandingkan dengan file aslinya.
- API Key didapat dari web IBM Cloud klik Manage > Access (IAM) > API Keys. Kemudian buatlah nama agar mendapatkan API Keys
- Melakukan deployment pada file arsip (.tgz)
![image](https://github.com/user-attachments/assets/1e623341-7a48-4fb9-a184-6124ebdad253)
![image](https://github.com/user-attachments/assets/1f27db1d-10c0-4b83-bb89-482d602dfa26)
![image](https://github.com/user-attachments/assets/79533902-6e41-4f09-b1c2-f08e2424cfa5)
![image](https://github.com/user-attachments/assets/766e2a42-551e-43d7-a0c5-eabf91bc380e)
![image](https://github.com/user-attachments/assets/0fb993c9-28d6-4457-b5cb-d465f111096b)
![image](https://github.com/user-attachments/assets/d4ee6436-4600-4f16-9f11-5583a46cb357)
![image](https://github.com/user-attachments/assets/729ddf96-75c4-4eca-93de-18463a333cd6)
![image](https://github.com/user-attachments/assets/9c8ddb9c-a63d-4bfc-85aa-7bb0ae4629b5)

# Testing
- Mengetes salah satu kalimat pada salah satu kolom dataset untuk menentukan respon dan nilai prediksi
![image](https://github.com/user-attachments/assets/1aadf346-b5eb-4544-9c85-f15644c8dff4)

# Kesimpulan
Proyek ini berusaha untuk menjawab tantangan dalam mengidentifikasi tweet yang relevan dengan bencana dengan menggunakan teknik NLP dengan model LSTM. Dengan berhasil mengembangkan model yang dapat membedakan tweet yang relevan dari yang tidak, kita dapat:
- Meningkatkan kecepatan dan akurasi dalam merespons situasi bencana, yang pada akhirnya dapat menyelamatkan nyawa dan mengurangi kerugian.
- Menyediakan alat yang berguna bagi pemerintah dan organisasi bantuan dalam mengumpulkan informasi real-time yang dapat diandalkan dari media sosial.
- Memberikan dasar bagi pengembangan lebih lanjut dalam bidang analisis teks dan deteksi informasi kritis di media sosial.














































