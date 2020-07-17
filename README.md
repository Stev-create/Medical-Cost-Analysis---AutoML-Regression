# Medical-Cost-Analysis---AutoML-Regression

<h3> Source dataset: https://www.kaggle.com/mirichoi0218/insurance or https://github.com/stedy/Machine-Learning-with-R-datasets </h3>

## Overview

Project ini menggunakan <b>Tree-based Pipeline Optimization Tool (TPOT) selama dua puluh menit</b>, untuk menemukan model dengan <b>R-squared</b> terbaik dalam memprediksi biaya medis seseorang. Dimana model terbaik yang didapat adalah <b>AdaBoostRegressor</b>. Ringkasan hasil terdapat di bawah ini, namun untuk lengkapnya dapat dilihat di [notebook ini](https://github.com/Stev-create/Medical-Cost-Analysis---AutoML-Regression/edit/master/README.md) 

## Summary

### Bussiness Insight

Kesehatan sangat penting di era ini, itu kenapa dengan membangun model regresi yang dapat memprediksi biaya medis seseorang, akan sangat membantu seseorang untuk merencanakan uangnya atau setidaknya, membuat seseorang sadar berapa besar kisarannya jika dia tidak menjaga kesehatannya. Tentu aja, model ini juga akan dapat membantu pihak asuransi untuk merencanakan strategi yang tepat dalam melihat setiap nasabahnya. 

### Exploratory data analysis

Target pada dataset ini adalah biaya medis atau <i>Charges</i>. Dimana dari distribusinya dapat dilihat di bawah:

![GitHub Logo](/images/a.png)

Distribusi target menunjukkan distribusi yang <b>skew-positive</b>, namun menurut saya, masih di luar kasus <i>highly-imbalanced</i>. Kemudian untuk distribusi umur, dapat dilihat di bawah:

![GitHub Logo](/images/b.png)

Dari visualisasi di atas menunjukkan bahwa di dataset ini kebanyakan adalah anak-anak muda. Tapi bagaimana dengan distribusi Body Mass Index (BMI) di dataset ini? Tapi sebelum, kita melihat distribusinya, ada baiknya saya merujuk ke WHO terlebih dahulu. Dimana menurut WHO, terdapat enam klasifikasi jika kita membicarakan BMI yaitu:

    Underweight jika BMI < 18.5
    Normal weight jika BMI di antara 18.5 dan 24.9
    Overweight jika BMI di antara 25.0 dan 29.9
    Class I obesity jika BMI di antara 30 dan 34.9
    Class II obesity jika BMI di antara 35.0 dan 39.9
    Class III obesity jika BMI >= 40

Source : https://en.wikipedia.org/wiki/Classification_of_obesity#cite_note-16

![GitHub Logo](/images/c.png)

Rata-rata orang di dataset ini punya BMI sekitaran 30.66. Maka ini bisa jadi kabar buruk, mengingat dari klasifikasi di atas, artinya rata-rata orang-orang di dataset ini termasuk dalam kategori obesitas. Dan hubungan BMI dengan biaya medis dapat dilihat di bawah: 

![GitHub Logo](/images/d.png)

Terlihat bahwa garisnya menunjukkan korelasi yang positif (matriks korelasi dapat dilihat di notebook ini) antara fitur BMI dengan biaya medisnya. Namun ini tidaklah mengherankan mengingat bahwa semakin besar BMI-nya, semakin besar juga resiko dia mengalami penyakit-penyakit yang perawatannya tidak murah. Dikutip dari https://www.nhlbi.nih.gov/health/educational/lose_wt/risk.htm

> The higher your BMI, the higher your risk for certain diseases such as heart disease, high blood pressure, type 2 diabetes, gallstones, breathing problems, and certain cancers. 

Dan visualisasi di antara fitur umur dan biaya medis dapat dilihat di bawah:

![GitHub Logo](/images/e.png)

Grafik di atas sangat masuk akal, semakin besar umur seseorang, semakin besar juga biaya medisnya. Karena memang, saat orang yang berumur tua terjangkit suatu penyakit, perawatanya pasti tidak semurah anak-anak muda yang masih kuat secara fisik. Namun memang, kalau dilihat dari garis regresinya, gradiennya tidak terlalu besar. Saya juga mencoba untuk memvisualkan ke tiga fitur yaitu umur, BMI, dan biaya medis:

![GitHub Logo](/images/f.png)

Sepertinya, tidak terlihat adanya yang signifikan antara ke tiga fitur (umur, BMI, dan biaya medis) saat digabungkan. 

![GitHub Logo](/images/g.png)

Terlihat bahwa orang-orang yang bukan perokok memiliki biaya medis lebih murah daripada para perokok. Kemudian juga, biaya medis para perokok lebih bervariasi daripada orang-orang yang bukan perokok. Seakan menunjukkan para perokok perawatannya atau penyakitnya lebih bervariasi.

### AutoML

AutoML yang saya gunakan Tree-based Pipeline Optimization Tool (TPOT), kemudian dijalankan selama dua puluh menit dan model yang didapat adalah <b>AdaBoostRegressor</b>. TPOT bisa dibilang seperti asisten untuk <i>data scientist</i>, seperti yang dikutip dari https://epistasislab.github.io/tpot/using/:

> TPOT is meant to be an assistant that gives you ideas on how to solve a particular machine learning problem by exploring pipeline configurations that you might have never considered, then leaves the fine-tuning to more constrained parameter tuning techniques such as grid search.

![GitHub Logo](/images/8.png)
source : http://epistasislab.github.io/tpot/

Dan Learning Curvesnya dapat dilihat di bawah:

![GitHub Logo](/images/9.png)

