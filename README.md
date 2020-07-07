# Medical-Cost-Analysis---AutoML-Regression

<h3> Source dataset: https://www.kaggle.com/mirichoi0218/insurance or https://github.com/stedy/Machine-Learning-with-R-datasets </h3>

## Overview

Project ini menggunakan <b>Tree-based Pipeline Optimization Tool (TPOT) selama dua puluh menit</b>, untuk menemukan model dengan <b>R-squared</b> terbaik dalam memprediksi biaya medis seseorang. Dimana model terbaik yang didapat adalah <b>AdaBoostRegressor</b>. Ringkasan hasil terdapat di bawah ini, namun untuk lengkapnya dapat dilihat di [notebook ini](https://github.com/Stev-create/Medical-Cost-Analysis---AutoML-Regression/edit/master/README.md) 

## Summary

### Bussiness Insight

Kesehatan sangat penting di era ini, itu kenapa dengan membangun model regresi yang dapat memprediksi biaya medis seseorang, akan sangat membantu seseorang untuk merencanakan uangnya atau setidaknya, membuat seseorang sadar berapa besar kisarannya jika dia tidak menjaga kesehatannya. Tentu aja, model ini juga akan dapat membantu pihak asuransi untuk merencanakan strategi yang tepat dalam melihat setiap nasabahnya. 

### Exploratory data analysis

Target pada dataset ini adalah biaya medis atau <i>Charges</i>. Dimana dari distribusinya dapat dilihat di bawah:

![GitHub Logo](/images/1.png)

Distribusi target menunjukkan distribusi yang <b>skew-positive</b>, namun menurut saya, masih di luar kasus <i>highly-imbalanced</i>. Kemudian untuk distribusi umur, dapat dilihat di bawah:

![GitHub Logo](/images/10.png)

Dari visualisasi di atas menunjukkan bahwa di dataset ini kebanyakan adalah anak-anak muda. Tapi bagaimana dengan BMInya? Sebelum, kita melihat distribusinya, ada baiknya saya merujuk WHO. Dimana menurut WHO, terdapat enam klasifikasi jika kita membicarakan BMI yaitu:

    Underweight jika BMI < 18.5
    Normal weight jika BMI di antara 18.5 dan 24.9
    Overweight jika BMI di antara 25.0 dan 29.9
    Class I obesity jika BMI di antara 30 dan 34.9
    Class II obesity jika BMI di antara 35.0 dan 39.9
    Class III obesity jika BMI >= 40

Source : https://en.wikipedia.org/wiki/Classification_of_obesity#cite_note-16

![GitHub Logo](/images/2.png)

![GitHub Logo](/images/3.png)

Rata-rata orang di dataset ini punya BMI 30.66. Maka ini bisa jadi kabar buruk, artinya orang-orang di dataset ini rata-rata masuk dalam kategori obesitas.

![GitHub Logo](/images/4.png)

Grafik di atas sangat masuk akal, semakin besar umur seseorang, semakin besar juga biaya medisnya. Namun memang, kalau dilihat dari garis regresinya, gradiennya tidak terlalu besar. 

![GitHub Logo](/images/6.png)

Sepertinya, tidak terlihat adanya yang signifikan antara tiga fitur (umur, bmi, dan biaya) ini. 

![GitHub Logo](/images/7.png)

Terlihat bahwa orang-orang yang tidak merokok memiliki biaya medis lebih sedikit daripada orang yang tidak merokok. Dan juga biaya medis orang yang merokok  lebih bervariasi daripada orang yang tidak merokok. Seakan menunjukkan orang-orang yang merokok perawatannya atau penyakitnya lebih bervariasi.

### AutoML

AutoML yang saya gunakan Tree-based Pipeline Optimization Tool (TPOT), kemudian dijalankan selama dua puluh menit dan model yang didapat adalah <b>AdaBoostRegressor</b>. TPOT bisa dibilang seperti asisten untuk data scientist, seperti yang dikutip dari https://epistasislab.github.io/tpot/using/:

> TPOT is meant to be an assistant that gives you ideas on how to solve a particular machine learning problem by exploring pipeline configurations that you might have never considered, then leaves the fine-tuning to more constrained parameter tuning techniques such as grid search.

![GitHub Logo](/images/8.png)
source : http://epistasislab.github.io/tpot/

Dan Learning Curvesnya dapat dilihat di bawah:

![GitHub Logo](/images/9.png)

