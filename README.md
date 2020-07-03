# Medical-Cost-Analysis---AutoML-Regression

<h3> Source dataset: https://www.kaggle.com/mirichoi0218/insurance or https://github.com/stedy/Machine-Learning-with-R-datasets </h3>

## Overview

Project ini menggunakan Tree-based Pipeline Optimization Tool (TPOT) selama dua puluh menit, untuk menemukan R-squared terbaik dalam memprediksi biaya medis seseorang. Dimana model terbaik yang didapat adalah <b>AdaBoostRegressor</b>. Untuk ringkasan hasil berada di bawah ini, namun untuk lengkapnya dapat dilihat di [notebook ini](https://github.com/Stev-create/Medical-Cost-Analysis---AutoML-Regression/edit/master/README.md) 

## Results

### EDA

![GitHub Logo](/images/1.png)

Charges adalah target pada dataset ini dan distribusinya memang sedikit imbalanced, namun menurut saya belum masuk kategori <i>highly-imbalanced</i>.

Menurut WHO, terdapat enam klasifikasi jika kita membicarakan BMI yaitu:

    Underweight jika BMI < 18.5
    Normal weight jika BMI di antara 18.5 dan 24.9
    Overweight jika BMI di antara 25.0 dan 29.9
    Class I obesity jika BMI di antara 30 dan 34.9
    Class II obesity jika BMI di antara 35.0 dan 39.9
    Class III obesity jika BMI >= 40

Source : https://en.wikipedia.org/wiki/Classification_of_obesity#cite_note-16

![GitHub Logo](/images/2.png)

![GitHub Logo](/images/3.png)

Rata-rata orang di dataset ini punya BMI 30.66 dimana artinya, orang-orang di dataset ini rata-rata masuk dalam kategori obesitas. 

![GitHub Logo](/images/4.png)

Dapat dilihat semakin besar umur seseorang, semakin besar juga biaya medisnya. Namun memang, kalau dilihat dari garis regresinya, gradiennya tidak terlalu besar. 

![GitHub Logo](/images/6.png)

![GitHub Logo](/images/7.png)

Terlihat bahwa orang-orang yang tidak merokok memiliki biaya medis lebih sedikit daripada orang yang tidak merokok. Dan juga biaya medis orang yang merokok  lebih bervariasi daripada orang yang tidak merokok. Seakan menunjukkan orang-orang yang merokok perawatannya atau penyakitnya lebih bervariasi.

### AutoML

AutoML ini menggunakan Tree-based Pipeline Optimization Tool (TPOT) selama dua puluh menit, dimana model yang didapat adalah <b>AdaBoostRegressor</b>

![GitHub Logo](/images/8.png)
source : http://epistasislab.github.io/tpot/

![GitHub Logo](/images/9.png)

