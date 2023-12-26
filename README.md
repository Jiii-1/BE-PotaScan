# PotaScan App API Documentation

Welcome to the PotaScan App API documentation! This guide will provide you with an overview of the available APIs for authentication and retrieving articles. All API responses are in JSON format.

---

## **API Login**

**Base URL:**
><https://potascan-api-fbaiidjkha-uc.a.run.app/>

**Method:**
>POST

- **User Register**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**register**

    This endpoint to create new users.

    **Required:**

  - **Request Body:**

    ```JSON
    {
    "name" : "name",
    "email" : "email@gmail.com",
    "password" : "password",
    "confirmPass" : "password"
    }
    ```

    **Response:**

    ```JSON
    {
      "message": "Successful register"
    }
    ```

- **User Login**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**login**

    **Required:**

  - **Request Body:**

    ```JSON
    {
      "email": "email@gmail.com",
      "password": "password"
    }
    ```

  **Response:**

    ```JSON
    {
    "statusCode": 200,
    "message": "Success",
    "data": {
        "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjksIm5hbWUiOiJuYW1lIiwiZW1haWwiOiJlbWFpbEBnbWFpbC5jb20iLCJpYXQiOjE2ODU1MTk1MjgsImV4cCI6MTY4NTUxOTU0M30.lQtA8XL8gyzgF63chf7V-980cB6yzXO-5nVaPlv7lOA"
    }
    }
    ```

---

**Method:**
>GET

- **Show Users**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**users**

    **Required:**

  - **Request Headers:**

    | Headers | Value |
    | ------ | ------ |
    | Authorization	 | Bearer {accessToken} |

  **Response:**

    ```JSON
    {
        "id": 1,
        "name": "Name",
        "email": "email@gmail.com"
    },...
    ```


- **Refresh Token Login**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**token**

    This endpoint is mainly to get new accessToken.

    **Required:**

  - **Request Headers:**

    | Headers | Value |
    | ------ | ------ |
    | Cookie | refreshToken=xxxxxxxxxxx |

  **Response:**

    ```JSON
    {
      "statusCode": 200,
      "message": "Success",
      "data": {
          "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjksIm5hbWUiOiJuYW1lIiwiZW1haWwiOiJlbWFpbEBnbWFpbC5jb20iLCJpYXQiOjE2ODU1MjI1MTgsImV4cCI6MTY4NTYwODkxOH0.GgwWidMcv2MX6ecwBGh7MBoEBRTNwjgvLC9mKPbzKfM"
      }
    }
    ```

---

**Method:**
>DELETE

- **User logout**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**user/logout**

    This endpoint is mainly to delete session in a way delete refreshToken Cookie.

  **Response:**

    ```JSON
    {
      "message": "Successfull Logout"
    }
    ```

---

## **API Article**


**Method:**
>POST

- **Post Article **
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**article**

  - **Request Headers:**

    | Headers | Value |
    | ------ | ------ |
    | Authorization | Bearer {accessToken} |

  - **Request Body:**

      ```JSON
      {
        "articleId": "a007",
        "title": "Tak Hanya Mudah Diolah, Intip 7 Manfaat Kentang untuk Manusia",
        "category": "Healty",
        "date": "2023-05-24",
        "writer": "Andreas Wilson Setiawan",
        "mainContent": "Kentang adalah salah satu sumber karbohidrat yang cukup digemari sebagai pengganti nasi. Jenis umbi-umbian ini mudah diolah menjadi menu pembuka, utama, maupun penutup yang tentu saja lezat. Tak hanya lezat, Anda bisa mendapatkan berbagai manfaat dari makan kentang.\r\n\r\nKandungan nutrisi dalam kentang\r\nJenis tanaman umbi-umbian ini memiliki nama Latin Solanum tuberosum. Tanaman kentang awalnya berasal dari kawasan Amerika Selatan, lalu menyebar hampir ke seluruh dunia.\r\n\r\nDi Indonesia, kentang umumnya tumbuh di kawasan dataran tinggi dengan iklim yang sejuk.\r\n\r\nKentang menjadi salah satu sumber karbohidrat yang umumnya dijadikan pengganti nasi, selain dari singkong, ubi jalar, maupun jagung.\r\n\r\nSelain dari kandungan karbohidrat tentunya, kentang juga kaya akan berbagai vitamin dan mineral penting bagi kesehatan tubuh.\r\n\r\nDilansir dari laman Data Komposisi Pangan Indonesia (DKPI), per 100 gram kentang memiliki kandungan nutrisi, antara lain:\r\n\r\nAir: 83,4 gram (g).\r\nKalori: 62 kkal.\r\nProtein: 2,1 g.\r\nLemak: 0,2 g.\r\nKarbohidrat: 13,5 g.\r\nSerat: 0,5 g.\r\nKalsium: 63 miligram (mg).\r\nFosfor: 58 mg.\r\nZat besi: 0,7 mg.\r\nNatrium: 7,0 mg.\r\nKalium: 396 mg.\r\nTembaga: 0,4 mikrogram (mcg).\r\nSeng: 0,3 mcg.\r\nThiamin (Vit. B1): 0,09 mg.\r\nRiboflavin (Vit. B2): 0,10 mg.\r\nNiacin (Vit. B3): 1,0 mg.\r\nVitamin C: 21 mg.\r\n\r\nLanjutkan Membaca\r\n\r\nManfaat kentang yang bisa Anda rasakan\r\nDari berbagai kandungan gizi yang dimiliki oleh umbi-umbian yang satu ini, berikut adalah berbagai manfaat kesehatan dari kentang yang bisa Anda rasakan.\r\n\r\n1. Menurunkan risiko penyakit kronis\r\ngejala kanker hati\r\n\r\nKentang sangat kaya akan senyawa flavonoid, karotenoid, dan asam fenolik.\r\n\r\nBerbagai senyawa ini berperan sebagai antioksidan di dalam tubuh yang akan mencegah radikal bebas yang muncul dan bisa merusak sel tubuh Anda.\r\n\r\nRadikal bebas adalah satu faktor pemicu berbagai penyakit kronis, seperti penyakit jantung, diabetes, hingga kanker.\r\n\r\nPenelitian dalam jurnal Nutrition and Cancer pada tahun 2011 menunjukan bahwa antioksidan dalam kentang dapat menekan pertumbuhan kanker hati dan usus besar.\r\n\r\n2. Membantu mengendalikan kadar gula darah\r\nManfaat kentang lainnya adalah membantu mengendalikan kadar gula darah. Sumber karbohidrat yang satu ini cukup aman bagi penderita diabetes.\r\n\r\nKentang banyak mengandung pati resisten yang tidak bisa diserap sepenuhnya oleh tubuh. Penelitian menyatakan bahwa pati resisten dapat mengoptimalkan kerja insulin, yakni hormon pengendali gula darah.\r\n\r\nSebuah penelitian dalam jurnal Medicine pada tahun 2015 juga menunjukan bahwa setelah mengonsumsi makanan dengan pati resisten, gula darah menjadi lebih stabil pada penderita diabetes tipe 2.\r\n\r\n3. Menjaga kesehatan pencernaan\r\nmencegah masalah pencernaan\r\n\r\nKandungan pati resisten dalam kentang ternyata juga bisa membantu memperbaiki sistem pencernaan.\r\n\r\nJadi saat masuk ke dalam usus, pati resisten ini akan dimakan oleh bakteri baik. Bakteri baik tersebut akan mengubah pati menjadi asam lemak rantai pendek.\r\n\r\nAsam lemak rantai pendek ini yang punya segudang manfaat, seperti mengurangi risiko peradangan di usus besar, memperkuat pertahanan usus besar, dan membantu pemulihan penderita infeksi usus (penyakit Crohn atau divertikulitis).\r\n\r\nTahukah Anda?\r\nKandungan pati resisten pada kentang bisa ditingkatkan. Caranya Anda cukup menyimpan kentang rebus di dalam lemari es semalaman, lalu makan selagi dingin pada hari berikutnya.\r\n4. Bebas kandungan gluten\r\nKandungan zat dalam kentang juga bebas gluten alias gluten free.\r\n\r\nBagi orang yang mengalami masalah dalam mengonsumsi makanan mengandung gluten, seperti penyakit celiac, Anda bisa menjadikan kentang sebagai alternatif yang tepat.\r\n\r\nMeskipun kentang sendiri bebas gluten, beberapa hidangan dari olahan kentang bisa mengandung gluten, seperti dalam saus atau roti kentang.\r\n\r\nJika Anda memiliki penyakit Celiac atau kondisi sensitivitas gluten, pastikan membaca daftar komposisi lengkap terlebih dahulu. Saat ini, beberapa produk sudah memiliki label gluten free.\r\n\r\nARTIKEL TERKAIT\r\n\r\nbahaya-gluten-untuk-beberapa-kondisi\r\nFAKTA GIZI\r\n\r\n3 Penyakit yang Membuat Penderitanya Tak Boleh Makan Gluten\r\nBelakangan, semakin banyak orang yang menjalani diet gluten free, dan mulai menghindari konsumsi makanan apapun yang mengandung gluten. Tak heran jika keberadaan gluten dalam makanan kini sering dianggap memberi efek negatif bagi kesehatan. Padahal, sebagian besar penelitian mengklaim bahwa mengonsumsi gluten aman bagi semua orang, kecuali penderita penyakit celiac. Namun di sisi lain, beberapa peneliti […]\r\n\r\n\r\nFoto Penulis\r\nbadge\r\nDitinjau secara medis oleh dr. Tania Savitri• 18/12/2020\r\n\r\n5. Menurunkan tekanan darah\r\nManfaat kentang yang penting lainnya adalah membantu menstabilkan tekanan darah.\r\n\r\nHal ini dikarenakan kentang adalah sumber kalium. Mineral ini bekerja dengan merangsang pembuluh darah untuk melebarkan ukurannya.\r\n\r\nSelain itu, kentang mengandung kalsium dan magnesium yang memiliki peranan penting dalam mengendalikan tekanan darah normal.\r\n\r\nPeneliti dari Institute for Food Research juga menemukan bahwa kentang mengandung kukoamines yang efeknya berhubungan dengan penurunan tekanan darah.\r\n\r\n6. Meningkatkan fungsi saraf dan otak\r\nkinerja otak manusia\r\n\r\nVitamin B6 dalam kentang sangat penting untuk menjaga kesehatan neuron alias sel-sel pembawa sinyal dari dan ke dalam otak.\r\n\r\nVitamin B6 berperan dalam pembentukan bahan kimia otak, yakni serotonin, dopamin, dan noreprinefrin.\r\n\r\nMaka dari itu, makan kentang baik untuk kesehatan saraf dan otak. Kondisi otak yang sehat membantu mengurangi stres, depresi, hingga gangguan kecemasan.\r\n\r\nSelain itu, kalium dalam kentang yang bisa mendorong pelebaran pembuluh darah juga membantu memastikan otak cukup mendapatkan darah.\r\n\r\n7. Menjaga kesehatan jantung\r\nKarotenoid dalam kentang membantu menjaga fungsi jantung dengan baik.\r\n\r\nSenyawa ini memiliki manfaat sebagai agen antiradang untuk mencegah aterosklerosis alias penyumbatan dinding arteri jantung.\r\n\r\nKandungan vitamin C dan vitamin B6 juga membantu mengurangi radikal bebas pada sel jantung dan sel-sel tubuh lainnya.\r\n\r\nVitamin B6 juga memiliki peranan penting dalam proses perubahan homosistein menjadi metionin, sejenis protein. Kadar homosistein yang tinggi dapat merusak dinding pembuluh darah.\r\n\r\nARTIKEL TERKAIT\r\n\r\ncara-menyimpan-kentang-cepat-busuk\r\nTIPS MAKAN SEHAT\r\n\r\nPerhatikan, Begini Cara Menyimpan Kentang Agar Awet dan Tak Cepat Busuk\r\nKentang adalah salah satu sumber karbohidrat baik penyuplai energi tubuh. Kentang sering dijadikan sebagai lauk makan karena mudah diolah menjadi berbagai masakan. Untuk menghasilkan olahan kentang yang baik, tidak hanya proses masaknya yang harus Anda perhatikan, tapi juga penyimpanannya. Lantas, seperti apa cara menyimpan kentang yang tepat untuk menjaga daya simpannya? Simpan di tempat kering dan […]\r\n\r\n\r\nFoto Penulis\r\nDitinjau oleh dr. Yusra Firdaus• 18/12/2020\r\n\r\nTips aman menyimpan dan mengonsumsi kentang\r\nmenu sahur resep kentang\r\n\r\nKentang bisa berbahaya apabila Anda tidak menyimpannya dengan benar.\r\n\r\nKentang yang terkena paparan sinar matahari langsung bisa menghasilkan zat solanine. Solanine menimbulkan rasa pahit dan beracun apabila dikonsumsi dalam jumlah banyak.\r\n\r\nUntuk itu, simpan kentang di tempat yang sejuk, kering, dan sirkulasi udaranya cukup. Jika kentang sudah dikupas, rendam dalam baskom berisi air untuk mencegah timbulnya perubahan warna.\r\n\r\nLangkah pengolahan kentang juga harus diperhatikan. Terlalu banyak makan kentang goreng bisa meningkatkan risiko penyakit, seperti serangan jantung, diabetes, hingga gangguan ginjal.\r\n\r\nKentang goreng mengandung lebih banyak lemak trans dan lemak jenuh, serta kalori tinggi sama halnya seperti nasi.\r\n\r\nDipanggang, ditumis, atau direbus bisa jadi alternatif teknik pengolahan kentang untuk diet yang membantu proses menurunkan berat badan.",
        "image": "https://cdn.hellosehat.com/wp-content/uploads/2018/05/shutterstock_340339607-673x467.jpg"
      }
      ```

  **Response:**

    ```JSON
    {
      "message": "Article berhasil ditambahkan",
    "artikel": {
        "articleId": "a009",
        "title": "Tak Hanya Mudah Diolah, Intip 7 Manfaat Kentang untuk Manusia",
        "category": "Healty",
        "date": "2023-05-24T00:00:00.000Z",
        "writer": "Andreas Wilson Setiawan",
        "mainContent": "Kentang adalah salah satu sumber karbohidrat yang cukup digemari sebagai pengganti nasi. Jenis umbi-umbian ini mudah diolah menjadi menu pembuka, utama, maupun penutup yang tentu saja lezat. Tak hanya lezat, Anda bisa mendapatkan berbagai manfaat dari makan kentang.\r\n\r\nKandungan nutrisi dalam kentang\r\nJenis tanaman umbi-umbian ini memiliki nama Latin Solanum tuberosum. Tanaman kentang awalnya berasal dari kawasan Amerika Selatan, lalu menyebar hampir ke seluruh dunia.\r\n\r\nDi Indonesia, kentang umumnya tumbuh di kawasan dataran tinggi dengan iklim yang sejuk.\r\n\r\nKentang menjadi salah satu sumber karbohidrat yang umumnya dijadikan pengganti nasi, selain dari singkong, ubi jalar, maupun jagung.\r\n\r\nSelain dari kandungan karbohidrat tentunya, kentang juga kaya akan berbagai vitamin dan mineral penting bagi kesehatan tubuh.\r\n\r\nDilansir dari laman Data Komposisi Pangan Indonesia (DKPI), per 100 gram kentang memiliki kandungan nutrisi, antara lain:\r\n\r\nAir: 83,4 gram (g).\r\nKalori: 62 kkal.\r\nProtein: 2,1 g.\r\nLemak: 0,2 g.\r\nKarbohidrat: 13,5 g.\r\nSerat: 0,5 g.\r\nKalsium: 63 miligram (mg).\r\nFosfor: 58 mg.\r\nZat besi: 0,7 mg.\r\nNatrium: 7,0 mg.\r\nKalium: 396 mg.\r\nTembaga: 0,4 mikrogram (mcg).\r\nSeng: 0,3 mcg.\r\nThiamin (Vit. B1): 0,09 mg.\r\nRiboflavin (Vit. B2): 0,10 mg.\r\nNiacin (Vit. B3): 1,0 mg.\r\nVitamin C: 21 mg.\r\n\r\nLanjutkan Membaca\r\n\r\nManfaat kentang yang bisa Anda rasakan\r\nDari berbagai kandungan gizi yang dimiliki oleh umbi-umbian yang satu ini, berikut adalah berbagai manfaat kesehatan dari kentang yang bisa Anda rasakan.\r\n\r\n1. Menurunkan risiko penyakit kronis\r\ngejala kanker hati\r\n\r\nKentang sangat kaya akan senyawa flavonoid, karotenoid, dan asam fenolik.\r\n\r\nBerbagai senyawa ini berperan sebagai antioksidan di dalam tubuh yang akan mencegah radikal bebas yang muncul dan bisa merusak sel tubuh Anda.\r\n\r\nRadikal bebas adalah satu faktor pemicu berbagai penyakit kronis, seperti penyakit jantung, diabetes, hingga kanker.\r\n\r\nPenelitian dalam jurnal Nutrition and Cancer pada tahun 2011 menunjukan bahwa antioksidan dalam kentang dapat menekan pertumbuhan kanker hati dan usus besar.\r\n\r\n2. Membantu mengendalikan kadar gula darah\r\nManfaat kentang lainnya adalah membantu mengendalikan kadar gula darah. Sumber karbohidrat yang satu ini cukup aman bagi penderita diabetes.\r\n\r\nKentang banyak mengandung pati resisten yang tidak bisa diserap sepenuhnya oleh tubuh. Penelitian menyatakan bahwa pati resisten dapat mengoptimalkan kerja insulin, yakni hormon pengendali gula darah.\r\n\r\nSebuah penelitian dalam jurnal Medicine pada tahun 2015 juga menunjukan bahwa setelah mengonsumsi makanan dengan pati resisten, gula darah menjadi lebih stabil pada penderita diabetes tipe 2.\r\n\r\n3. Menjaga kesehatan pencernaan\r\nmencegah masalah pencernaan\r\n\r\nKandungan pati resisten dalam kentang ternyata juga bisa membantu memperbaiki sistem pencernaan.\r\n\r\nJadi saat masuk ke dalam usus, pati resisten ini akan dimakan oleh bakteri baik. Bakteri baik tersebut akan mengubah pati menjadi asam lemak rantai pendek.\r\n\r\nAsam lemak rantai pendek ini yang punya segudang manfaat, seperti mengurangi risiko peradangan di usus besar, memperkuat pertahanan usus besar, dan membantu pemulihan penderita infeksi usus (penyakit Crohn atau divertikulitis).\r\n\r\nTahukah Anda?\r\nKandungan pati resisten pada kentang bisa ditingkatkan. Caranya Anda cukup menyimpan kentang rebus di dalam lemari es semalaman, lalu makan selagi dingin pada hari berikutnya.\r\n4. Bebas kandungan gluten\r\nKandungan zat dalam kentang juga bebas gluten alias gluten free.\r\n\r\nBagi orang yang mengalami masalah dalam mengonsumsi makanan mengandung gluten, seperti penyakit celiac, Anda bisa menjadikan kentang sebagai alternatif yang tepat.\r\n\r\nMeskipun kentang sendiri bebas gluten, beberapa hidangan dari olahan kentang bisa mengandung gluten, seperti dalam saus atau roti kentang.\r\n\r\nJika Anda memiliki penyakit Celiac atau kondisi sensitivitas gluten, pastikan membaca daftar komposisi lengkap terlebih dahulu. Saat ini, beberapa produk sudah memiliki label gluten free.\r\n\r\nARTIKEL TERKAIT\r\n\r\nbahaya-gluten-untuk-beberapa-kondisi\r\nFAKTA GIZI\r\n\r\n3 Penyakit yang Membuat Penderitanya Tak Boleh Makan Gluten\r\nBelakangan, semakin banyak orang yang menjalani diet gluten free, dan mulai menghindari konsumsi makanan apapun yang mengandung gluten. Tak heran jika keberadaan gluten dalam makanan kini sering dianggap memberi efek negatif bagi kesehatan. Padahal, sebagian besar penelitian mengklaim bahwa mengonsumsi gluten aman bagi semua orang, kecuali penderita penyakit celiac. Namun di sisi lain, beberapa peneliti […]\r\n\r\n\r\nFoto Penulis\r\nbadge\r\nDitinjau secara medis oleh dr. Tania Savitri• 18/12/2020\r\n\r\n5. Menurunkan tekanan darah\r\nManfaat kentang yang penting lainnya adalah membantu menstabilkan tekanan darah.\r\n\r\nHal ini dikarenakan kentang adalah sumber kalium. Mineral ini bekerja dengan merangsang pembuluh darah untuk melebarkan ukurannya.\r\n\r\nSelain itu, kentang mengandung kalsium dan magnesium yang memiliki peranan penting dalam mengendalikan tekanan darah normal.\r\n\r\nPeneliti dari Institute for Food Research juga menemukan bahwa kentang mengandung kukoamines yang efeknya berhubungan dengan penurunan tekanan darah.\r\n\r\n6. Meningkatkan fungsi saraf dan otak\r\nkinerja otak manusia\r\n\r\nVitamin B6 dalam kentang sangat penting untuk menjaga kesehatan neuron alias sel-sel pembawa sinyal dari dan ke dalam otak.\r\n\r\nVitamin B6 berperan dalam pembentukan bahan kimia otak, yakni serotonin, dopamin, dan noreprinefrin.\r\n\r\nMaka dari itu, makan kentang baik untuk kesehatan saraf dan otak. Kondisi otak yang sehat membantu mengurangi stres, depresi, hingga gangguan kecemasan.\r\n\r\nSelain itu, kalium dalam kentang yang bisa mendorong pelebaran pembuluh darah juga membantu memastikan otak cukup mendapatkan darah.\r\n\r\n7. Menjaga kesehatan jantung\r\nKarotenoid dalam kentang membantu menjaga fungsi jantung dengan baik.\r\n\r\nSenyawa ini memiliki manfaat sebagai agen antiradang untuk mencegah aterosklerosis alias penyumbatan dinding arteri jantung.\r\n\r\nKandungan vitamin C dan vitamin B6 juga membantu mengurangi radikal bebas pada sel jantung dan sel-sel tubuh lainnya.\r\n\r\nVitamin B6 juga memiliki peranan penting dalam proses perubahan homosistein menjadi metionin, sejenis protein. Kadar homosistein yang tinggi dapat merusak dinding pembuluh darah.\r\n\r\nARTIKEL TERKAIT\r\n\r\ncara-menyimpan-kentang-cepat-busuk\r\nTIPS MAKAN SEHAT\r\n\r\nPerhatikan, Begini Cara Menyimpan Kentang Agar Awet dan Tak Cepat Busuk\r\nKentang adalah salah satu sumber karbohidrat baik penyuplai energi tubuh. Kentang sering dijadikan sebagai lauk makan karena mudah diolah menjadi berbagai masakan. Untuk menghasilkan olahan kentang yang baik, tidak hanya proses masaknya yang harus Anda perhatikan, tapi juga penyimpanannya. Lantas, seperti apa cara menyimpan kentang yang tepat untuk menjaga daya simpannya? Simpan di tempat kering dan […]\r\n\r\n\r\nFoto Penulis\r\nDitinjau oleh dr. Yusra Firdaus• 18/12/2020\r\n\r\nTips aman menyimpan dan mengonsumsi kentang\r\nmenu sahur resep kentang\r\n\r\nKentang bisa berbahaya apabila Anda tidak menyimpannya dengan benar.\r\n\r\nKentang yang terkena paparan sinar matahari langsung bisa menghasilkan zat solanine. Solanine menimbulkan rasa pahit dan beracun apabila dikonsumsi dalam jumlah banyak.\r\n\r\nUntuk itu, simpan kentang di tempat yang sejuk, kering, dan sirkulasi udaranya cukup. Jika kentang sudah dikupas, rendam dalam baskom berisi air untuk mencegah timbulnya perubahan warna.\r\n\r\nLangkah pengolahan kentang juga harus diperhatikan. Terlalu banyak makan kentang goreng bisa meningkatkan risiko penyakit, seperti serangan jantung, diabetes, hingga gangguan ginjal.\r\n\r\nKentang goreng mengandung lebih banyak lemak trans dan lemak jenuh, serta kalori tinggi sama halnya seperti nasi.\r\n\r\nDipanggang, ditumis, atau direbus bisa jadi alternatif teknik pengolahan kentang untuk diet yang membantu proses menurunkan berat badan.",
        "image": "https://cdn.hellosehat.com/wp-content/uploads/2018/05/shutterstock_340339607-673x467.jpg"
    }
    }
    ```

---

**Method:**
>GET

- **Get All Article**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**article**

     This endpoint is mainly to retrieve all articles within database.

     **Response:**

    ```JSON
    [
    "statusCode": 200,
    "message": "Success",
    "data": [
        {
            "articleId": "a001",
            "title": "edited Tak Hanya Mudah Diolah, Intip 7 Manfaat Kentang untuk Tubuh",
            "category": "Healty",
            "date": "2023-05-24",
            "writer": "Andreas Wilson Setiawan",
            "mainContent": "Kentang adalah salah satu sumber karbohidrat yang cukup digemari sebagai pengganti nasi. Jenis umbi-umbian ini mudah diolah menjadi menu pembuka, utama, maupun penutup yang tentu saja lezat. Tak hanya lezat, Anda bisa mendapatkan berbagai manfaat dari makan kentang.\r\n\r\nKandungan nutrisi dalam kentang\r\nJenis tanaman umbi-umbian ini memiliki nama Latin Solanum tuberosum. Tanaman kentang awalnya berasal dari kawasan Amerika Selatan, lalu menyebar hampir ke seluruh dunia.\r\n\r\nDi Indonesia, kentang umumnya tumbuh di kawasan dataran tinggi dengan iklim yang sejuk.\r\n\r\nKentang menjadi salah satu sumber karbohidrat yang umumnya dijadikan pengganti nasi, selain dari singkong, ubi jalar, maupun jagung.\r\n\r\nSelain dari kandungan karbohidrat tentunya, kentang juga kaya akan berbagai vitamin dan mineral penting bagi kesehatan tubuh.\r\n\r\nDilansir dari laman Data Komposisi Pangan Indonesia (DKPI), per 100 gram kentang memiliki kandungan nutrisi, antara lain:\r\n\r\nAir: 83,4 gram (g).\r\nKalori: 62 kkal.\r\nProtein: 2,1 g.\r\nLemak: 0,2 g.\r\nKarbohidrat: 13,5 g.\r\nSerat: 0,5 g.\r\nKalsium: 63 miligram (mg).\r\nFosfor: 58 mg.\r\nZat besi: 0,7 mg.\r\nNatrium: 7,0 mg.\r\nKalium: 396 mg.\r\nTembaga: 0,4 mikrogram (mcg).\r\nSeng: 0,3 mcg.\r\nThiamin (Vit. B1): 0,09 mg.\r\nRiboflavin (Vit. B2): 0,10 mg.\r\nNiacin (Vit. B3): 1,0 mg.\r\nVitamin C: 21 mg.\r\n\r\nLanjutkan Membaca\r\n\r\nManfaat kentang yang bisa Anda rasakan\r\nDari berbagai kandungan gizi yang dimiliki oleh umbi-umbian yang satu ini, berikut adalah berbagai manfaat kesehatan dari kentang yang bisa Anda rasakan.\r\n\r\n1. Menurunkan risiko penyakit kronis\r\ngejala kanker hati\r\n\r\nKentang sangat kaya akan senyawa flavonoid, karotenoid, dan asam fenolik.\r\n\r\nBerbagai senyawa ini berperan sebagai antioksidan di dalam tubuh yang akan mencegah radikal bebas yang muncul dan bisa merusak sel tubuh Anda.\r\n\r\nRadikal bebas adalah satu faktor pemicu berbagai penyakit kronis, seperti penyakit jantung, diabetes, hingga kanker.\r\n\r\nPenelitian dalam jurnal Nutrition and Cancer pada tahun 2011 menunjukan bahwa antioksidan dalam kentang dapat menekan pertumbuhan kanker hati dan usus besar.\r\n\r\n2. Membantu mengendalikan kadar gula darah\r\nManfaat kentang lainnya adalah membantu mengendalikan kadar gula darah. Sumber karbohidrat yang satu ini cukup aman bagi penderita diabetes.\r\n\r\nKentang banyak mengandung pati resisten yang tidak bisa diserap sepenuhnya oleh tubuh. Penelitian menyatakan bahwa pati resisten dapat mengoptimalkan kerja insulin, yakni hormon pengendali gula darah.\r\n\r\nSebuah penelitian dalam jurnal Medicine pada tahun 2015 juga menunjukan bahwa setelah mengonsumsi makanan dengan pati resisten, gula darah menjadi lebih stabil pada penderita diabetes tipe 2.\r\n\r\n3. Menjaga kesehatan pencernaan\r\nmencegah masalah pencernaan\r\n\r\nKandungan pati resisten dalam kentang ternyata juga bisa membantu memperbaiki sistem pencernaan.\r\n\r\nJadi saat masuk ke dalam usus, pati resisten ini akan dimakan oleh bakteri baik. Bakteri baik tersebut akan mengubah pati menjadi asam lemak rantai pendek.\r\n\r\nAsam lemak rantai pendek ini yang punya segudang manfaat, seperti mengurangi risiko peradangan di usus besar, memperkuat pertahanan usus besar, dan membantu pemulihan penderita infeksi usus (penyakit Crohn atau divertikulitis).\r\n\r\nTahukah Anda?\r\nKandungan pati resisten pada kentang bisa ditingkatkan. Caranya Anda cukup menyimpan kentang rebus di dalam lemari es semalaman, lalu makan selagi dingin pada hari berikutnya.\r\n4. Bebas kandungan gluten\r\nKandungan zat dalam kentang juga bebas gluten alias gluten free.\r\n\r\nBagi orang yang mengalami masalah dalam mengonsumsi makanan mengandung gluten, seperti penyakit celiac, Anda bisa menjadikan kentang sebagai alternatif yang tepat.\r\n\r\nMeskipun kentang sendiri bebas gluten, beberapa hidangan dari olahan kentang bisa mengandung gluten, seperti dalam saus atau roti kentang.\r\n\r\nJika Anda memiliki penyakit Celiac atau kondisi sensitivitas gluten, pastikan membaca daftar komposisi lengkap terlebih dahulu. Saat ini, beberapa produk sudah memiliki label gluten free.\r\n\r\nARTIKEL TERKAIT\r\n\r\nbahaya-gluten-untuk-beberapa-kondisi\r\nFAKTA GIZI\r\n\r\n3 Penyakit yang Membuat Penderitanya Tak Boleh Makan Gluten\r\nBelakangan, semakin banyak orang yang menjalani diet gluten free, dan mulai menghindari konsumsi makanan apapun yang mengandung gluten. Tak heran jika keberadaan gluten dalam makanan kini sering dianggap memberi efek negatif bagi kesehatan. Padahal, sebagian besar penelitian mengklaim bahwa mengonsumsi gluten aman bagi semua orang, kecuali penderita penyakit celiac. Namun di sisi lain, beberapa peneliti […]\r\n\r\n\r\nFoto Penulis\r\nbadge\r\nDitinjau secara medis oleh dr. Tania Savitri• 18/12/2020\r\n\r\n5. Menurunkan tekanan darah\r\nManfaat kentang yang penting lainnya adalah membantu menstabilkan tekanan darah.\r\n\r\nHal ini dikarenakan kentang adalah sumber kalium. Mineral ini bekerja dengan merangsang pembuluh darah untuk melebarkan ukurannya.\r\n\r\nSelain itu, kentang mengandung kalsium dan magnesium yang memiliki peranan penting dalam mengendalikan tekanan darah normal.\r\n\r\nPeneliti dari Institute for Food Research juga menemukan bahwa kentang mengandung kukoamines yang efeknya berhubungan dengan penurunan tekanan darah.\r\n\r\n6. Meningkatkan fungsi saraf dan otak\r\nkinerja otak manusia\r\n\r\nVitamin B6 dalam kentang sangat penting untuk menjaga kesehatan neuron alias sel-sel pembawa sinyal dari dan ke dalam otak.\r\n\r\nVitamin B6 berperan dalam pembentukan bahan kimia otak, yakni serotonin, dopamin, dan noreprinefrin.\r\n\r\nMaka dari itu, makan kentang baik untuk kesehatan saraf dan otak. Kondisi otak yang sehat membantu mengurangi stres, depresi, hingga gangguan kecemasan.\r\n\r\nSelain itu, kalium dalam kentang yang bisa mendorong pelebaran pembuluh darah juga membantu memastikan otak cukup mendapatkan darah.\r\n\r\n7. Menjaga kesehatan jantung\r\nKarotenoid dalam kentang membantu menjaga fungsi jantung dengan baik.\r\n\r\nSenyawa ini memiliki manfaat sebagai agen antiradang untuk mencegah aterosklerosis alias penyumbatan dinding arteri jantung.\r\n\r\nKandungan vitamin C dan vitamin B6 juga membantu mengurangi radikal bebas pada sel jantung dan sel-sel tubuh lainnya.\r\n\r\nVitamin B6 juga memiliki peranan penting dalam proses perubahan homosistein menjadi metionin, sejenis protein. Kadar homosistein yang tinggi dapat merusak dinding pembuluh darah.\r\n\r\nARTIKEL TERKAIT\r\n\r\ncara-menyimpan-kentang-cepat-busuk\r\nTIPS MAKAN SEHAT\r\n\r\nPerhatikan, Begini Cara Menyimpan Kentang Agar Awet dan Tak Cepat Busuk\r\nKentang adalah salah satu sumber karbohidrat baik penyuplai energi tubuh. Kentang sering dijadikan sebagai lauk makan karena mudah diolah menjadi berbagai masakan. Untuk menghasilkan olahan kentang yang baik, tidak hanya proses masaknya yang harus Anda perhatikan, tapi juga penyimpanannya. Lantas, seperti apa cara menyimpan kentang yang tepat untuk menjaga daya simpannya? Simpan di tempat kering dan […]\r\n\r\n\r\nFoto Penulis\r\nDitinjau oleh dr. Yusra Firdaus• 18/12/2020\r\n\r\nTips aman menyimpan dan mengonsumsi kentang\r\nmenu sahur resep kentang\r\n\r\nKentang bisa berbahaya apabila Anda tidak menyimpannya dengan benar.\r\n\r\nKentang yang terkena paparan sinar matahari langsung bisa menghasilkan zat solanine. Solanine menimbulkan rasa pahit dan beracun apabila dikonsumsi dalam jumlah banyak.\r\n\r\nUntuk itu, simpan kentang di tempat yang sejuk, kering, dan sirkulasi udaranya cukup. Jika kentang sudah dikupas, rendam dalam baskom berisi air untuk mencegah timbulnya perubahan warna.\r\n\r\nLangkah pengolahan kentang juga harus diperhatikan. Terlalu banyak makan kentang goreng bisa meningkatkan risiko penyakit, seperti serangan jantung, diabetes, hingga gangguan ginjal.\r\n\r\nKentang goreng mengandung lebih banyak lemak trans dan lemak jenuh, serta kalori tinggi sama halnya seperti nasi.\r\n\r\nDipanggang, ditumis, atau direbus bisa jadi alternatif teknik pengolahan kentang untuk diet yang membantu proses menurunkan berat badan.",
            "image": "https://cdn.hellosehat.com/wp-content/uploads/2018/05/shutterstock_340339607-673x467.jpg"
        },,...
    ]
    ```

- **Get Article By ArticleId**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**article/{articleId}**

     This endpoint is mainly to retrieve all articles related with {articleId}.

     **Required:**

    - **Path Params**

  **Response:**

    ```JSON
    {
      "statusCode": 200,
    "message": "Success",
    "data": {
        "articleId": "a005",
        "title": "Tak Hanya Mudah Diolah, Intip 7 Manfaat Kentang untuk Tubuh",
        "category": "",
        "date": "2023-05-24",
        "writer": "Andreas Wilson Setiawan",
        "mainContent": "Kentang adalah salah satu sumber karbohidrat yang cukup digemari sebagai pengganti nasi. Jenis umbi-umbian ini mudah diolah menjadi menu pembuka, utama, maupun penutup yang tentu saja lezat. Tak hanya lezat, Anda bisa mendapatkan berbagai manfaat dari makan kentang.\r\n\r\nKandungan nutrisi dalam kentang\r\nJenis tanaman umbi-umbian ini memiliki nama Latin Solanum tuberosum. Tanaman kentang awalnya berasal dari kawasan Amerika Selatan, lalu menyebar hampir ke seluruh dunia.\r\n\r\nDi Indonesia, kentang umumnya tumbuh di kawasan dataran tinggi dengan iklim yang sejuk.\r\n\r\nKentang menjadi salah satu sumber karbohidrat yang umumnya dijadikan pengganti nasi, selain dari singkong, ubi jalar, maupun jagung.\r\n\r\nSelain dari kandungan karbohidrat tentunya, kentang juga kaya akan berbagai vitamin dan mineral penting bagi kesehatan tubuh.\r\n\r\nDilansir dari laman Data Komposisi Pangan Indonesia (DKPI), per 100 gram kentang memiliki kandungan nutrisi, antara lain:\r\n\r\nAir: 83,4 gram (g).\r\nKalori: 62 kkal.\r\nProtein: 2,1 g.\r\nLemak: 0,2 g.\r\nKarbohidrat: 13,5 g.\r\nSerat: 0,5 g.\r\nKalsium: 63 miligram (mg).\r\nFosfor: 58 mg.\r\nZat besi: 0,7 mg.\r\nNatrium: 7,0 mg.\r\nKalium: 396 mg.\r\nTembaga: 0,4 mikrogram (mcg).\r\nSeng: 0,3 mcg.\r\nThiamin (Vit. B1): 0,09 mg.\r\nRiboflavin (Vit. B2): 0,10 mg.\r\nNiacin (Vit. B3): 1,0 mg.\r\nVitamin C: 21 mg.\r\n\r\nLanjutkan Membaca\r\n\r\nManfaat kentang yang bisa Anda rasakan\r\nDari berbagai kandungan gizi yang dimiliki oleh umbi-umbian yang satu ini, berikut adalah berbagai manfaat kesehatan dari kentang yang bisa Anda rasakan.\r\n\r\n1. Menurunkan risiko penyakit kronis\r\ngejala kanker hati\r\n\r\nKentang sangat kaya akan senyawa flavonoid, karotenoid, dan asam fenolik.\r\n\r\nBerbagai senyawa ini berperan sebagai antioksidan di dalam tubuh yang akan mencegah radikal bebas yang muncul dan bisa merusak sel tubuh Anda.\r\n\r\nRadikal bebas adalah satu faktor pemicu berbagai penyakit kronis, seperti penyakit jantung, diabetes, hingga kanker.\r\n\r\nPenelitian dalam jurnal Nutrition and Cancer pada tahun 2011 menunjukan bahwa antioksidan dalam kentang dapat menekan pertumbuhan kanker hati dan usus besar.\r\n\r\n2. Membantu mengendalikan kadar gula darah\r\nManfaat kentang lainnya adalah membantu mengendalikan kadar gula darah. Sumber karbohidrat yang satu ini cukup aman bagi penderita diabetes.\r\n\r\nKentang banyak mengandung pati resisten yang tidak bisa diserap sepenuhnya oleh tubuh. Penelitian menyatakan bahwa pati resisten dapat mengoptimalkan kerja insulin, yakni hormon pengendali gula darah.\r\n\r\nSebuah penelitian dalam jurnal Medicine pada tahun 2015 juga menunjukan bahwa setelah mengonsumsi makanan dengan pati resisten, gula darah menjadi lebih stabil pada penderita diabetes tipe 2.\r\n\r\n3. Menjaga kesehatan pencernaan\r\nmencegah masalah pencernaan\r\n\r\nKandungan pati resisten dalam kentang ternyata juga bisa membantu memperbaiki sistem pencernaan.\r\n\r\nJadi saat masuk ke dalam usus, pati resisten ini akan dimakan oleh bakteri baik. Bakteri baik tersebut akan mengubah pati menjadi asam lemak rantai pendek.\r\n\r\nAsam lemak rantai pendek ini yang punya segudang manfaat, seperti mengurangi risiko peradangan di usus besar, memperkuat pertahanan usus besar, dan membantu pemulihan penderita infeksi usus (penyakit Crohn atau divertikulitis).\r\n\r\nTahukah Anda?\r\nKandungan pati resisten pada kentang bisa ditingkatkan. Caranya Anda cukup menyimpan kentang rebus di dalam lemari es semalaman, lalu makan selagi dingin pada hari berikutnya.\r\n4. Bebas kandungan gluten\r\nKandungan zat dalam kentang juga bebas gluten alias gluten free.\r\n\r\nBagi orang yang mengalami masalah dalam mengonsumsi makanan mengandung gluten, seperti penyakit celiac, Anda bisa menjadikan kentang sebagai alternatif yang tepat.\r\n\r\nMeskipun kentang sendiri bebas gluten, beberapa hidangan dari olahan kentang bisa mengandung gluten, seperti dalam saus atau roti kentang.\r\n\r\nJika Anda memiliki penyakit Celiac atau kondisi sensitivitas gluten, pastikan membaca daftar komposisi lengkap terlebih dahulu. Saat ini, beberapa produk sudah memiliki label gluten free.\r\n\r\nARTIKEL TERKAIT\r\n\r\nbahaya-gluten-untuk-beberapa-kondisi\r\nFAKTA GIZI\r\n\r\n3 Penyakit yang Membuat Penderitanya Tak Boleh Makan Gluten\r\nBelakangan, semakin banyak orang yang menjalani diet gluten free, dan mulai menghindari konsumsi makanan apapun yang mengandung gluten. Tak heran jika keberadaan gluten dalam makanan kini sering dianggap memberi efek negatif bagi kesehatan. Padahal, sebagian besar penelitian mengklaim bahwa mengonsumsi gluten aman bagi semua orang, kecuali penderita penyakit celiac. Namun di sisi lain, beberapa peneliti […]\r\n\r\n\r\nFoto Penulis\r\nbadge\r\nDitinjau secara medis oleh dr. Tania Savitri• 18/12/2020\r\n\r\n5. Menurunkan tekanan darah\r\nManfaat kentang yang penting lainnya adalah membantu menstabilkan tekanan darah.\r\n\r\nHal ini dikarenakan kentang adalah sumber kalium. Mineral ini bekerja dengan merangsang pembuluh darah untuk melebarkan ukurannya.\r\n\r\nSelain itu, kentang mengandung kalsium dan magnesium yang memiliki peranan penting dalam mengendalikan tekanan darah normal.\r\n\r\nPeneliti dari Institute for Food Research juga menemukan bahwa kentang mengandung kukoamines yang efeknya berhubungan dengan penurunan tekanan darah.\r\n\r\n6. Meningkatkan fungsi saraf dan otak\r\nkinerja otak manusia\r\n\r\nVitamin B6 dalam kentang sangat penting untuk menjaga kesehatan neuron alias sel-sel pembawa sinyal dari dan ke dalam otak.\r\n\r\nVitamin B6 berperan dalam pembentukan bahan kimia otak, yakni serotonin, dopamin, dan noreprinefrin.\r\n\r\nMaka dari itu, makan kentang baik untuk kesehatan saraf dan otak. Kondisi otak yang sehat membantu mengurangi stres, depresi, hingga gangguan kecemasan.\r\n\r\nSelain itu, kalium dalam kentang yang bisa mendorong pelebaran pembuluh darah juga membantu memastikan otak cukup mendapatkan darah.\r\n\r\n7. Menjaga kesehatan jantung\r\nKarotenoid dalam kentang membantu menjaga fungsi jantung dengan baik.\r\n\r\nSenyawa ini memiliki manfaat sebagai agen antiradang untuk mencegah aterosklerosis alias penyumbatan dinding arteri jantung.\r\n\r\nKandungan vitamin C dan vitamin B6 juga membantu mengurangi radikal bebas pada sel jantung dan sel-sel tubuh lainnya.\r\n\r\nVitamin B6 juga memiliki peranan penting dalam proses perubahan homosistein menjadi metionin, sejenis protein. Kadar homosistein yang tinggi dapat merusak dinding pembuluh darah.\r\n\r\nARTIKEL TERKAIT\r\n\r\ncara-menyimpan-kentang-cepat-busuk\r\nTIPS MAKAN SEHAT\r\n\r\nPerhatikan, Begini Cara Menyimpan Kentang Agar Awet dan Tak Cepat Busuk\r\nKentang adalah salah satu sumber karbohidrat baik penyuplai energi tubuh. Kentang sering dijadikan sebagai lauk makan karena mudah diolah menjadi berbagai masakan. Untuk menghasilkan olahan kentang yang baik, tidak hanya proses masaknya yang harus Anda perhatikan, tapi juga penyimpanannya. Lantas, seperti apa cara menyimpan kentang yang tepat untuk menjaga daya simpannya? Simpan di tempat kering dan […]\r\n\r\n\r\nFoto Penulis\r\nDitinjau oleh dr. Yusra Firdaus• 18/12/2020\r\n\r\nTips aman menyimpan dan mengonsumsi kentang\r\nmenu sahur resep kentang\r\n\r\nKentang bisa berbahaya apabila Anda tidak menyimpannya dengan benar.\r\n\r\nKentang yang terkena paparan sinar matahari langsung bisa menghasilkan zat solanine. Solanine menimbulkan rasa pahit dan beracun apabila dikonsumsi dalam jumlah banyak.\r\n\r\nUntuk itu, simpan kentang di tempat yang sejuk, kering, dan sirkulasi udaranya cukup. Jika kentang sudah dikupas, rendam dalam baskom berisi air untuk mencegah timbulnya perubahan warna.\r\n\r\nLangkah pengolahan kentang juga harus diperhatikan. Terlalu banyak makan kentang goreng bisa meningkatkan risiko penyakit, seperti serangan jantung, diabetes, hingga gangguan ginjal.\r\n\r\nKentang goreng mengandung lebih banyak lemak trans dan lemak jenuh, serta kalori tinggi sama halnya seperti nasi.\r\n\r\nDipanggang, ditumis, atau direbus bisa jadi alternatif teknik pengolahan kentang untuk diet yang membantu proses menurunkan berat badan.",
        "image": "https://cdn.hellosehat.com/wp-content/uploads/2018/05/shutterstock_340339607-673x467.jpg"
    }
    }
    ```

- **Get article By category**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**category/{category}**

     This endpoint is mainly to retrieve all articles related with category.

     **Required:**

    - **Path Params**

  **Response:**

    ```JSON
    {
      "statusCode": 200,
    "message": "Success",
    "data": {
        "articleId": "a001",
        "title": "edited Tak Hanya Mudah Diolah, Intip 7 Manfaat Kentang untuk Tubuh",
        "category": "Healty",
        "date": "2023-05-24",
        "writer": "Andreas Wilson Setiawan",
        "mainContent": "Kentang adalah salah satu sumber karbohidrat yang cukup digemari sebagai pengganti nasi. Jenis umbi-umbian ini mudah diolah menjadi menu pembuka, utama, maupun penutup yang tentu saja lezat. Tak hanya lezat, Anda bisa mendapatkan berbagai manfaat dari makan kentang.\r\n\r\nKandungan nutrisi dalam kentang\r\nJenis tanaman umbi-umbian ini memiliki nama Latin Solanum tuberosum. Tanaman kentang awalnya berasal dari kawasan Amerika Selatan, lalu menyebar hampir ke seluruh dunia.\r\n\r\nDi Indonesia, kentang umumnya tumbuh di kawasan dataran tinggi dengan iklim yang sejuk.\r\n\r\nKentang menjadi salah satu sumber karbohidrat yang umumnya dijadikan pengganti nasi, selain dari singkong, ubi jalar, maupun jagung.\r\n\r\nSelain dari kandungan karbohidrat tentunya, kentang juga kaya akan berbagai vitamin dan mineral penting bagi kesehatan tubuh.\r\n\r\nDilansir dari laman Data Komposisi Pangan Indonesia (DKPI), per 100 gram kentang memiliki kandungan nutrisi, antara lain:\r\n\r\nAir: 83,4 gram (g).\r\nKalori: 62 kkal.\r\nProtein: 2,1 g.\r\nLemak: 0,2 g.\r\nKarbohidrat: 13,5 g.\r\nSerat: 0,5 g.\r\nKalsium: 63 miligram (mg).\r\nFosfor: 58 mg.\r\nZat besi: 0,7 mg.\r\nNatrium: 7,0 mg.\r\nKalium: 396 mg.\r\nTembaga: 0,4 mikrogram (mcg).\r\nSeng: 0,3 mcg.\r\nThiamin (Vit. B1): 0,09 mg.\r\nRiboflavin (Vit. B2): 0,10 mg.\r\nNiacin (Vit. B3): 1,0 mg.\r\nVitamin C: 21 mg.\r\n\r\nLanjutkan Membaca\r\n\r\nManfaat kentang yang bisa Anda rasakan\r\nDari berbagai kandungan gizi yang dimiliki oleh umbi-umbian yang satu ini, berikut adalah berbagai manfaat kesehatan dari kentang yang bisa Anda rasakan.\r\n\r\n1. Menurunkan risiko penyakit kronis\r\ngejala kanker hati\r\n\r\nKentang sangat kaya akan senyawa flavonoid, karotenoid, dan asam fenolik.\r\n\r\nBerbagai senyawa ini berperan sebagai antioksidan di dalam tubuh yang akan mencegah radikal bebas yang muncul dan bisa merusak sel tubuh Anda.\r\n\r\nRadikal bebas adalah satu faktor pemicu berbagai penyakit kronis, seperti penyakit jantung, diabetes, hingga kanker.\r\n\r\nPenelitian dalam jurnal Nutrition and Cancer pada tahun 2011 menunjukan bahwa antioksidan dalam kentang dapat menekan pertumbuhan kanker hati dan usus besar.\r\n\r\n2. Membantu mengendalikan kadar gula darah\r\nManfaat kentang lainnya adalah membantu mengendalikan kadar gula darah. Sumber karbohidrat yang satu ini cukup aman bagi penderita diabetes.\r\n\r\nKentang banyak mengandung pati resisten yang tidak bisa diserap sepenuhnya oleh tubuh. Penelitian menyatakan bahwa pati resisten dapat mengoptimalkan kerja insulin, yakni hormon pengendali gula darah.\r\n\r\nSebuah penelitian dalam jurnal Medicine pada tahun 2015 juga menunjukan bahwa setelah mengonsumsi makanan dengan pati resisten, gula darah menjadi lebih stabil pada penderita diabetes tipe 2.\r\n\r\n3. Menjaga kesehatan pencernaan\r\nmencegah masalah pencernaan\r\n\r\nKandungan pati resisten dalam kentang ternyata juga bisa membantu memperbaiki sistem pencernaan.\r\n\r\nJadi saat masuk ke dalam usus, pati resisten ini akan dimakan oleh bakteri baik. Bakteri baik tersebut akan mengubah pati menjadi asam lemak rantai pendek.\r\n\r\nAsam lemak rantai pendek ini yang punya segudang manfaat, seperti mengurangi risiko peradangan di usus besar, memperkuat pertahanan usus besar, dan membantu pemulihan penderita infeksi usus (penyakit Crohn atau divertikulitis).\r\n\r\nTahukah Anda?\r\nKandungan pati resisten pada kentang bisa ditingkatkan. Caranya Anda cukup menyimpan kentang rebus di dalam lemari es semalaman, lalu makan selagi dingin pada hari berikutnya.\r\n4. Bebas kandungan gluten\r\nKandungan zat dalam kentang juga bebas gluten alias gluten free.\r\n\r\nBagi orang yang mengalami masalah dalam mengonsumsi makanan mengandung gluten, seperti penyakit celiac, Anda bisa menjadikan kentang sebagai alternatif yang tepat.\r\n\r\nMeskipun kentang sendiri bebas gluten, beberapa hidangan dari olahan kentang bisa mengandung gluten, seperti dalam saus atau roti kentang.\r\n\r\nJika Anda memiliki penyakit Celiac atau kondisi sensitivitas gluten, pastikan membaca daftar komposisi lengkap terlebih dahulu. Saat ini, beberapa produk sudah memiliki label gluten free.\r\n\r\nARTIKEL TERKAIT\r\n\r\nbahaya-gluten-untuk-beberapa-kondisi\r\nFAKTA GIZI\r\n\r\n3 Penyakit yang Membuat Penderitanya Tak Boleh Makan Gluten\r\nBelakangan, semakin banyak orang yang menjalani diet gluten free, dan mulai menghindari konsumsi makanan apapun yang mengandung gluten. Tak heran jika keberadaan gluten dalam makanan kini sering dianggap memberi efek negatif bagi kesehatan. Padahal, sebagian besar penelitian mengklaim bahwa mengonsumsi gluten aman bagi semua orang, kecuali penderita penyakit celiac. Namun di sisi lain, beberapa peneliti […]\r\n\r\n\r\nFoto Penulis\r\nbadge\r\nDitinjau secara medis oleh dr. Tania Savitri• 18/12/2020\r\n\r\n5. Menurunkan tekanan darah\r\nManfaat kentang yang penting lainnya adalah membantu menstabilkan tekanan darah.\r\n\r\nHal ini dikarenakan kentang adalah sumber kalium. Mineral ini bekerja dengan merangsang pembuluh darah untuk melebarkan ukurannya.\r\n\r\nSelain itu, kentang mengandung kalsium dan magnesium yang memiliki peranan penting dalam mengendalikan tekanan darah normal.\r\n\r\nPeneliti dari Institute for Food Research juga menemukan bahwa kentang mengandung kukoamines yang efeknya berhubungan dengan penurunan tekanan darah.\r\n\r\n6. Meningkatkan fungsi saraf dan otak\r\nkinerja otak manusia\r\n\r\nVitamin B6 dalam kentang sangat penting untuk menjaga kesehatan neuron alias sel-sel pembawa sinyal dari dan ke dalam otak.\r\n\r\nVitamin B6 berperan dalam pembentukan bahan kimia otak, yakni serotonin, dopamin, dan noreprinefrin.\r\n\r\nMaka dari itu, makan kentang baik untuk kesehatan saraf dan otak. Kondisi otak yang sehat membantu mengurangi stres, depresi, hingga gangguan kecemasan.\r\n\r\nSelain itu, kalium dalam kentang yang bisa mendorong pelebaran pembuluh darah juga membantu memastikan otak cukup mendapatkan darah.\r\n\r\n7. Menjaga kesehatan jantung\r\nKarotenoid dalam kentang membantu menjaga fungsi jantung dengan baik.\r\n\r\nSenyawa ini memiliki manfaat sebagai agen antiradang untuk mencegah aterosklerosis alias penyumbatan dinding arteri jantung.\r\n\r\nKandungan vitamin C dan vitamin B6 juga membantu mengurangi radikal bebas pada sel jantung dan sel-sel tubuh lainnya.\r\n\r\nVitamin B6 juga memiliki peranan penting dalam proses perubahan homosistein menjadi metionin, sejenis protein. Kadar homosistein yang tinggi dapat merusak dinding pembuluh darah.\r\n\r\nARTIKEL TERKAIT\r\n\r\ncara-menyimpan-kentang-cepat-busuk\r\nTIPS MAKAN SEHAT\r\n\r\nPerhatikan, Begini Cara Menyimpan Kentang Agar Awet dan Tak Cepat Busuk\r\nKentang adalah salah satu sumber karbohidrat baik penyuplai energi tubuh. Kentang sering dijadikan sebagai lauk makan karena mudah diolah menjadi berbagai masakan. Untuk menghasilkan olahan kentang yang baik, tidak hanya proses masaknya yang harus Anda perhatikan, tapi juga penyimpanannya. Lantas, seperti apa cara menyimpan kentang yang tepat untuk menjaga daya simpannya? Simpan di tempat kering dan […]\r\n\r\n\r\nFoto Penulis\r\nDitinjau oleh dr. Yusra Firdaus• 18/12/2020\r\n\r\nTips aman menyimpan dan mengonsumsi kentang\r\nmenu sahur resep kentang\r\n\r\nKentang bisa berbahaya apabila Anda tidak menyimpannya dengan benar.\r\n\r\nKentang yang terkena paparan sinar matahari langsung bisa menghasilkan zat solanine. Solanine menimbulkan rasa pahit dan beracun apabila dikonsumsi dalam jumlah banyak.\r\n\r\nUntuk itu, simpan kentang di tempat yang sejuk, kering, dan sirkulasi udaranya cukup. Jika kentang sudah dikupas, rendam dalam baskom berisi air untuk mencegah timbulnya perubahan warna.\r\n\r\nLangkah pengolahan kentang juga harus diperhatikan. Terlalu banyak makan kentang goreng bisa meningkatkan risiko penyakit, seperti serangan jantung, diabetes, hingga gangguan ginjal.\r\n\r\nKentang goreng mengandung lebih banyak lemak trans dan lemak jenuh, serta kalori tinggi sama halnya seperti nasi.\r\n\r\nDipanggang, ditumis, atau direbus bisa jadi alternatif teknik pengolahan kentang untuk diet yang membantu proses menurunkan berat badan.",
        "image": "https://cdn.hellosehat.com/wp-content/uploads/2018/05/shutterstock_340339607-673x467.jpg"
    }
    }
    ```

---

**Method:**
>PUT

- **Update Article**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**article**

     This endpoint is mainly to update Article.

     **Required:**

  - **Path Params**

  - **Request Headers:**

    | Headers | Value |
    | ------ | ------ |
    | Authorization | Bearer {accessToken} |

  - **Request Body:**

      ```JSON
      {
        "articleId": "a001",
        "title": "edited Tak Hanya Mudah Diolah, Intip 7 Manfaat Kentang untuk Tubuh",
        "category": "Healty",
        "date": "2023-05-24",
        "writer": "Andreas Wilson Setiawan",
        "mainContent": "Kentang adalah salah satu sumber karbohidrat yang cukup digemari sebagai pengganti nasi. Jenis umbi-umbian ini mudah diolah menjadi menu pembuka, utama, maupun penutup yang tentu saja lezat. Tak hanya lezat, Anda bisa mendapatkan berbagai manfaat dari makan kentang.\r\n\r\nKandungan nutrisi dalam kentang\r\nJenis tanaman umbi-umbian ini memiliki nama Latin Solanum tuberosum. Tanaman kentang awalnya berasal dari kawasan Amerika Selatan, lalu menyebar hampir ke seluruh dunia.\r\n\r\nDi Indonesia, kentang umumnya tumbuh di kawasan dataran tinggi dengan iklim yang sejuk.\r\n\r\nKentang menjadi salah satu sumber karbohidrat yang umumnya dijadikan pengganti nasi, selain dari singkong, ubi jalar, maupun jagung.\r\n\r\nSelain dari kandungan karbohidrat tentunya, kentang juga kaya akan berbagai vitamin dan mineral penting bagi kesehatan tubuh.\r\n\r\nDilansir dari laman Data Komposisi Pangan Indonesia (DKPI), per 100 gram kentang memiliki kandungan nutrisi, antara lain:\r\n\r\nAir: 83,4 gram (g).\r\nKalori: 62 kkal.\r\nProtein: 2,1 g.\r\nLemak: 0,2 g.\r\nKarbohidrat: 13,5 g.\r\nSerat: 0,5 g.\r\nKalsium: 63 miligram (mg).\r\nFosfor: 58 mg.\r\nZat besi: 0,7 mg.\r\nNatrium: 7,0 mg.\r\nKalium: 396 mg.\r\nTembaga: 0,4 mikrogram (mcg).\r\nSeng: 0,3 mcg.\r\nThiamin (Vit. B1): 0,09 mg.\r\nRiboflavin (Vit. B2): 0,10 mg.\r\nNiacin (Vit. B3): 1,0 mg.\r\nVitamin C: 21 mg.\r\n\r\nLanjutkan Membaca\r\n\r\nManfaat kentang yang bisa Anda rasakan\r\nDari berbagai kandungan gizi yang dimiliki oleh umbi-umbian yang satu ini, berikut adalah berbagai manfaat kesehatan dari kentang yang bisa Anda rasakan.\r\n\r\n1. Menurunkan risiko penyakit kronis\r\ngejala kanker hati\r\n\r\nKentang sangat kaya akan senyawa flavonoid, karotenoid, dan asam fenolik.\r\n\r\nBerbagai senyawa ini berperan sebagai antioksidan di dalam tubuh yang akan mencegah radikal bebas yang muncul dan bisa merusak sel tubuh Anda.\r\n\r\nRadikal bebas adalah satu faktor pemicu berbagai penyakit kronis, seperti penyakit jantung, diabetes, hingga kanker.\r\n\r\nPenelitian dalam jurnal Nutrition and Cancer pada tahun 2011 menunjukan bahwa antioksidan dalam kentang dapat menekan pertumbuhan kanker hati dan usus besar.\r\n\r\n2. Membantu mengendalikan kadar gula darah\r\nManfaat kentang lainnya adalah membantu mengendalikan kadar gula darah. Sumber karbohidrat yang satu ini cukup aman bagi penderita diabetes.\r\n\r\nKentang banyak mengandung pati resisten yang tidak bisa diserap sepenuhnya oleh tubuh. Penelitian menyatakan bahwa pati resisten dapat mengoptimalkan kerja insulin, yakni hormon pengendali gula darah.\r\n\r\nSebuah penelitian dalam jurnal Medicine pada tahun 2015 juga menunjukan bahwa setelah mengonsumsi makanan dengan pati resisten, gula darah menjadi lebih stabil pada penderita diabetes tipe 2.\r\n\r\n3. Menjaga kesehatan pencernaan\r\nmencegah masalah pencernaan\r\n\r\nKandungan pati resisten dalam kentang ternyata juga bisa membantu memperbaiki sistem pencernaan.\r\n\r\nJadi saat masuk ke dalam usus, pati resisten ini akan dimakan oleh bakteri baik. Bakteri baik tersebut akan mengubah pati menjadi asam lemak rantai pendek.\r\n\r\nAsam lemak rantai pendek ini yang punya segudang manfaat, seperti mengurangi risiko peradangan di usus besar, memperkuat pertahanan usus besar, dan membantu pemulihan penderita infeksi usus (penyakit Crohn atau divertikulitis).\r\n\r\nTahukah Anda?\r\nKandungan pati resisten pada kentang bisa ditingkatkan. Caranya Anda cukup menyimpan kentang rebus di dalam lemari es semalaman, lalu makan selagi dingin pada hari berikutnya.\r\n4. Bebas kandungan gluten\r\nKandungan zat dalam kentang juga bebas gluten alias gluten free.\r\n\r\nBagi orang yang mengalami masalah dalam mengonsumsi makanan mengandung gluten, seperti penyakit celiac, Anda bisa menjadikan kentang sebagai alternatif yang tepat.\r\n\r\nMeskipun kentang sendiri bebas gluten, beberapa hidangan dari olahan kentang bisa mengandung gluten, seperti dalam saus atau roti kentang.\r\n\r\nJika Anda memiliki penyakit Celiac atau kondisi sensitivitas gluten, pastikan membaca daftar komposisi lengkap terlebih dahulu. Saat ini, beberapa produk sudah memiliki label gluten free.\r\n\r\nARTIKEL TERKAIT\r\n\r\nbahaya-gluten-untuk-beberapa-kondisi\r\nFAKTA GIZI\r\n\r\n3 Penyakit yang Membuat Penderitanya Tak Boleh Makan Gluten\r\nBelakangan, semakin banyak orang yang menjalani diet gluten free, dan mulai menghindari konsumsi makanan apapun yang mengandung gluten. Tak heran jika keberadaan gluten dalam makanan kini sering dianggap memberi efek negatif bagi kesehatan. Padahal, sebagian besar penelitian mengklaim bahwa mengonsumsi gluten aman bagi semua orang, kecuali penderita penyakit celiac. Namun di sisi lain, beberapa peneliti […]\r\n\r\n\r\nFoto Penulis\r\nbadge\r\nDitinjau secara medis oleh dr. Tania Savitri• 18/12/2020\r\n\r\n5. Menurunkan tekanan darah\r\nManfaat kentang yang penting lainnya adalah membantu menstabilkan tekanan darah.\r\n\r\nHal ini dikarenakan kentang adalah sumber kalium. Mineral ini bekerja dengan merangsang pembuluh darah untuk melebarkan ukurannya.\r\n\r\nSelain itu, kentang mengandung kalsium dan magnesium yang memiliki peranan penting dalam mengendalikan tekanan darah normal.\r\n\r\nPeneliti dari Institute for Food Research juga menemukan bahwa kentang mengandung kukoamines yang efeknya berhubungan dengan penurunan tekanan darah.\r\n\r\n6. Meningkatkan fungsi saraf dan otak\r\nkinerja otak manusia\r\n\r\nVitamin B6 dalam kentang sangat penting untuk menjaga kesehatan neuron alias sel-sel pembawa sinyal dari dan ke dalam otak.\r\n\r\nVitamin B6 berperan dalam pembentukan bahan kimia otak, yakni serotonin, dopamin, dan noreprinefrin.\r\n\r\nMaka dari itu, makan kentang baik untuk kesehatan saraf dan otak. Kondisi otak yang sehat membantu mengurangi stres, depresi, hingga gangguan kecemasan.\r\n\r\nSelain itu, kalium dalam kentang yang bisa mendorong pelebaran pembuluh darah juga membantu memastikan otak cukup mendapatkan darah.\r\n\r\n7. Menjaga kesehatan jantung\r\nKarotenoid dalam kentang membantu menjaga fungsi jantung dengan baik.\r\n\r\nSenyawa ini memiliki manfaat sebagai agen antiradang untuk mencegah aterosklerosis alias penyumbatan dinding arteri jantung.\r\n\r\nKandungan vitamin C dan vitamin B6 juga membantu mengurangi radikal bebas pada sel jantung dan sel-sel tubuh lainnya.\r\n\r\nVitamin B6 juga memiliki peranan penting dalam proses perubahan homosistein menjadi metionin, sejenis protein. Kadar homosistein yang tinggi dapat merusak dinding pembuluh darah.\r\n\r\nARTIKEL TERKAIT\r\n\r\ncara-menyimpan-kentang-cepat-busuk\r\nTIPS MAKAN SEHAT\r\n\r\nPerhatikan, Begini Cara Menyimpan Kentang Agar Awet dan Tak Cepat Busuk\r\nKentang adalah salah satu sumber karbohidrat baik penyuplai energi tubuh. Kentang sering dijadikan sebagai lauk makan karena mudah diolah menjadi berbagai masakan. Untuk menghasilkan olahan kentang yang baik, tidak hanya proses masaknya yang harus Anda perhatikan, tapi juga penyimpanannya. Lantas, seperti apa cara menyimpan kentang yang tepat untuk menjaga daya simpannya? Simpan di tempat kering dan […]\r\n\r\n\r\nFoto Penulis\r\nDitinjau oleh dr. Yusra Firdaus• 18/12/2020\r\n\r\nTips aman menyimpan dan mengonsumsi kentang\r\nmenu sahur resep kentang\r\n\r\nKentang bisa berbahaya apabila Anda tidak menyimpannya dengan benar.\r\n\r\nKentang yang terkena paparan sinar matahari langsung bisa menghasilkan zat solanine. Solanine menimbulkan rasa pahit dan beracun apabila dikonsumsi dalam jumlah banyak.\r\n\r\nUntuk itu, simpan kentang di tempat yang sejuk, kering, dan sirkulasi udaranya cukup. Jika kentang sudah dikupas, rendam dalam baskom berisi air untuk mencegah timbulnya perubahan warna.\r\n\r\nLangkah pengolahan kentang juga harus diperhatikan. Terlalu banyak makan kentang goreng bisa meningkatkan risiko penyakit, seperti serangan jantung, diabetes, hingga gangguan ginjal.\r\n\r\nKentang goreng mengandung lebih banyak lemak trans dan lemak jenuh, serta kalori tinggi sama halnya seperti nasi.\r\n\r\nDipanggang, ditumis, atau direbus bisa jadi alternatif teknik pengolahan kentang untuk diet yang membantu proses menurunkan berat badan.",
        "image": "https://cdn.hellosehat.com/wp-content/uploads/2018/05/shutterstock_340339607-673x467.jpg"
      }
      ```

  **Response:**

    ```JSON
    {
      "message": "Article berhasil diubah",
    "artikel": {
        "articleId": "a001",
        "title": "edited Tak Hanya Mudah Diolah, Intip 7 Manfaat Kentang untuk Tubuh",
        "category": "Healty",
        "date": "2023-05-24T00:00:00.000Z",
        "writer": "Andreas Wilson Setiawan",
        "mainContent": "Kentang adalah salah satu sumber karbohidrat yang cukup digemari sebagai pengganti nasi. Jenis umbi-umbian ini mudah diolah menjadi menu pembuka, utama, maupun penutup yang tentu saja lezat. Tak hanya lezat, Anda bisa mendapatkan berbagai manfaat dari makan kentang.\r\n\r\nKandungan nutrisi dalam kentang\r\nJenis tanaman umbi-umbian ini memiliki nama Latin Solanum tuberosum. Tanaman kentang awalnya berasal dari kawasan Amerika Selatan, lalu menyebar hampir ke seluruh dunia.\r\n\r\nDi Indonesia, kentang umumnya tumbuh di kawasan dataran tinggi dengan iklim yang sejuk.\r\n\r\nKentang menjadi salah satu sumber karbohidrat yang umumnya dijadikan pengganti nasi, selain dari singkong, ubi jalar, maupun jagung.\r\n\r\nSelain dari kandungan karbohidrat tentunya, kentang juga kaya akan berbagai vitamin dan mineral penting bagi kesehatan tubuh.\r\n\r\nDilansir dari laman Data Komposisi Pangan Indonesia (DKPI), per 100 gram kentang memiliki kandungan nutrisi, antara lain:\r\n\r\nAir: 83,4 gram (g).\r\nKalori: 62 kkal.\r\nProtein: 2,1 g.\r\nLemak: 0,2 g.\r\nKarbohidrat: 13,5 g.\r\nSerat: 0,5 g.\r\nKalsium: 63 miligram (mg).\r\nFosfor: 58 mg.\r\nZat besi: 0,7 mg.\r\nNatrium: 7,0 mg.\r\nKalium: 396 mg.\r\nTembaga: 0,4 mikrogram (mcg).\r\nSeng: 0,3 mcg.\r\nThiamin (Vit. B1): 0,09 mg.\r\nRiboflavin (Vit. B2): 0,10 mg.\r\nNiacin (Vit. B3): 1,0 mg.\r\nVitamin C: 21 mg.\r\n\r\nLanjutkan Membaca\r\n\r\nManfaat kentang yang bisa Anda rasakan\r\nDari berbagai kandungan gizi yang dimiliki oleh umbi-umbian yang satu ini, berikut adalah berbagai manfaat kesehatan dari kentang yang bisa Anda rasakan.\r\n\r\n1. Menurunkan risiko penyakit kronis\r\ngejala kanker hati\r\n\r\nKentang sangat kaya akan senyawa flavonoid, karotenoid, dan asam fenolik.\r\n\r\nBerbagai senyawa ini berperan sebagai antioksidan di dalam tubuh yang akan mencegah radikal bebas yang muncul dan bisa merusak sel tubuh Anda.\r\n\r\nRadikal bebas adalah satu faktor pemicu berbagai penyakit kronis, seperti penyakit jantung, diabetes, hingga kanker.\r\n\r\nPenelitian dalam jurnal Nutrition and Cancer pada tahun 2011 menunjukan bahwa antioksidan dalam kentang dapat menekan pertumbuhan kanker hati dan usus besar.\r\n\r\n2. Membantu mengendalikan kadar gula darah\r\nManfaat kentang lainnya adalah membantu mengendalikan kadar gula darah. Sumber karbohidrat yang satu ini cukup aman bagi penderita diabetes.\r\n\r\nKentang banyak mengandung pati resisten yang tidak bisa diserap sepenuhnya oleh tubuh. Penelitian menyatakan bahwa pati resisten dapat mengoptimalkan kerja insulin, yakni hormon pengendali gula darah.\r\n\r\nSebuah penelitian dalam jurnal Medicine pada tahun 2015 juga menunjukan bahwa setelah mengonsumsi makanan dengan pati resisten, gula darah menjadi lebih stabil pada penderita diabetes tipe 2.\r\n\r\n3. Menjaga kesehatan pencernaan\r\nmencegah masalah pencernaan\r\n\r\nKandungan pati resisten dalam kentang ternyata juga bisa membantu memperbaiki sistem pencernaan.\r\n\r\nJadi saat masuk ke dalam usus, pati resisten ini akan dimakan oleh bakteri baik. Bakteri baik tersebut akan mengubah pati menjadi asam lemak rantai pendek.\r\n\r\nAsam lemak rantai pendek ini yang punya segudang manfaat, seperti mengurangi risiko peradangan di usus besar, memperkuat pertahanan usus besar, dan membantu pemulihan penderita infeksi usus (penyakit Crohn atau divertikulitis).\r\n\r\nTahukah Anda?\r\nKandungan pati resisten pada kentang bisa ditingkatkan. Caranya Anda cukup menyimpan kentang rebus di dalam lemari es semalaman, lalu makan selagi dingin pada hari berikutnya.\r\n4. Bebas kandungan gluten\r\nKandungan zat dalam kentang juga bebas gluten alias gluten free.\r\n\r\nBagi orang yang mengalami masalah dalam mengonsumsi makanan mengandung gluten, seperti penyakit celiac, Anda bisa menjadikan kentang sebagai alternatif yang tepat.\r\n\r\nMeskipun kentang sendiri bebas gluten, beberapa hidangan dari olahan kentang bisa mengandung gluten, seperti dalam saus atau roti kentang.\r\n\r\nJika Anda memiliki penyakit Celiac atau kondisi sensitivitas gluten, pastikan membaca daftar komposisi lengkap terlebih dahulu. Saat ini, beberapa produk sudah memiliki label gluten free.\r\n\r\nARTIKEL TERKAIT\r\n\r\nbahaya-gluten-untuk-beberapa-kondisi\r\nFAKTA GIZI\r\n\r\n3 Penyakit yang Membuat Penderitanya Tak Boleh Makan Gluten\r\nBelakangan, semakin banyak orang yang menjalani diet gluten free, dan mulai menghindari konsumsi makanan apapun yang mengandung gluten. Tak heran jika keberadaan gluten dalam makanan kini sering dianggap memberi efek negatif bagi kesehatan. Padahal, sebagian besar penelitian mengklaim bahwa mengonsumsi gluten aman bagi semua orang, kecuali penderita penyakit celiac. Namun di sisi lain, beberapa peneliti […]\r\n\r\n\r\nFoto Penulis\r\nbadge\r\nDitinjau secara medis oleh dr. Tania Savitri• 18/12/2020\r\n\r\n5. Menurunkan tekanan darah\r\nManfaat kentang yang penting lainnya adalah membantu menstabilkan tekanan darah.\r\n\r\nHal ini dikarenakan kentang adalah sumber kalium. Mineral ini bekerja dengan merangsang pembuluh darah untuk melebarkan ukurannya.\r\n\r\nSelain itu, kentang mengandung kalsium dan magnesium yang memiliki peranan penting dalam mengendalikan tekanan darah normal.\r\n\r\nPeneliti dari Institute for Food Research juga menemukan bahwa kentang mengandung kukoamines yang efeknya berhubungan dengan penurunan tekanan darah.\r\n\r\n6. Meningkatkan fungsi saraf dan otak\r\nkinerja otak manusia\r\n\r\nVitamin B6 dalam kentang sangat penting untuk menjaga kesehatan neuron alias sel-sel pembawa sinyal dari dan ke dalam otak.\r\n\r\nVitamin B6 berperan dalam pembentukan bahan kimia otak, yakni serotonin, dopamin, dan noreprinefrin.\r\n\r\nMaka dari itu, makan kentang baik untuk kesehatan saraf dan otak. Kondisi otak yang sehat membantu mengurangi stres, depresi, hingga gangguan kecemasan.\r\n\r\nSelain itu, kalium dalam kentang yang bisa mendorong pelebaran pembuluh darah juga membantu memastikan otak cukup mendapatkan darah.\r\n\r\n7. Menjaga kesehatan jantung\r\nKarotenoid dalam kentang membantu menjaga fungsi jantung dengan baik.\r\n\r\nSenyawa ini memiliki manfaat sebagai agen antiradang untuk mencegah aterosklerosis alias penyumbatan dinding arteri jantung.\r\n\r\nKandungan vitamin C dan vitamin B6 juga membantu mengurangi radikal bebas pada sel jantung dan sel-sel tubuh lainnya.\r\n\r\nVitamin B6 juga memiliki peranan penting dalam proses perubahan homosistein menjadi metionin, sejenis protein. Kadar homosistein yang tinggi dapat merusak dinding pembuluh darah.\r\n\r\nARTIKEL TERKAIT\r\n\r\ncara-menyimpan-kentang-cepat-busuk\r\nTIPS MAKAN SEHAT\r\n\r\nPerhatikan, Begini Cara Menyimpan Kentang Agar Awet dan Tak Cepat Busuk\r\nKentang adalah salah satu sumber karbohidrat baik penyuplai energi tubuh. Kentang sering dijadikan sebagai lauk makan karena mudah diolah menjadi berbagai masakan. Untuk menghasilkan olahan kentang yang baik, tidak hanya proses masaknya yang harus Anda perhatikan, tapi juga penyimpanannya. Lantas, seperti apa cara menyimpan kentang yang tepat untuk menjaga daya simpannya? Simpan di tempat kering dan […]\r\n\r\n\r\nFoto Penulis\r\nDitinjau oleh dr. Yusra Firdaus• 18/12/2020\r\n\r\nTips aman menyimpan dan mengonsumsi kentang\r\nmenu sahur resep kentang\r\n\r\nKentang bisa berbahaya apabila Anda tidak menyimpannya dengan benar.\r\n\r\nKentang yang terkena paparan sinar matahari langsung bisa menghasilkan zat solanine. Solanine menimbulkan rasa pahit dan beracun apabila dikonsumsi dalam jumlah banyak.\r\n\r\nUntuk itu, simpan kentang di tempat yang sejuk, kering, dan sirkulasi udaranya cukup. Jika kentang sudah dikupas, rendam dalam baskom berisi air untuk mencegah timbulnya perubahan warna.\r\n\r\nLangkah pengolahan kentang juga harus diperhatikan. Terlalu banyak makan kentang goreng bisa meningkatkan risiko penyakit, seperti serangan jantung, diabetes, hingga gangguan ginjal.\r\n\r\nKentang goreng mengandung lebih banyak lemak trans dan lemak jenuh, serta kalori tinggi sama halnya seperti nasi.\r\n\r\nDipanggang, ditumis, atau direbus bisa jadi alternatif teknik pengolahan kentang untuk diet yang membantu proses menurunkan berat badan.",
        "image": "https://cdn.hellosehat.com/wp-content/uploads/2018/05/shutterstock_340339607-673x467.jpg"
    }
    ```

---

**Method:**
>DELETE

- **Delete Article By Article Id**
    ><https://potascan-api-fbaiidjkha-uc.a.run.app/>**article/{articleId}**

     This endpoint is mainly to delete specific Article related with {articleId}.

     **Required:**

  - **Path Params**

  - **Request Headers:**

    | Headers | Value |
    | ------ | ------ |
    | Authorization | Bearer {accessToken} |

  **Response:**

    ```JSON
    {
      "message": "Article successfully deleted"
    }
    ```
