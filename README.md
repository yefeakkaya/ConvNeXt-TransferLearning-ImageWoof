# Transfer Learning on ImageWoof200 using ConvNeXt

## Proje Hakkında
Bu proje, birbirine görsel olarak çok benzeyen köpek ırklarını sınıflandırmak gibi zorlu bir bilgisayarlı görü (computer vision) problemini çözmek amacıyla geliştirilmiştir. Modern bir CNN mimarisi olan **ConvNeXt** modeli kullanılarak Transfer Learning (Transfer Öğrenme) yöntemi uygulanmıştır. Özellik çıkarıcı (feature extractor) katmanlar dondurulmuş ve modelin sınıflandırıcı (classifier) katmanı, hedef veri setindeki 10 farklı sınıfı tahmin edecek şekilde yeniden yapılandırılıp eğitilmiştir. 

## Veri Seti: ImageWoof200
Projede, ImageNet veri setinin bir alt kümesi olan ve özellikle sınıflandırılması zor köpek ırklarını barındıran **ImageWoof200** veri seti kullanılmıştır. Veri seti, ince taneli (fine-grained) görsel sınıflandırma yeteneklerini test etmek için idealdir.
**Sınıf Sayısı:** 10 farklı köpek ırkı (Golden Retriever, Samoyed, Shih Tzu, Beagle, vb.)
**Görüntü İşleme:** Yeniden boyutlandırma (224x224), tensöre dönüştürme ve ImageNet standartlarında normalizasyon işlemleri uygulanmıştır.

## Kullanılan Teknolojiler ve Kütüphaneler
**Python** 
**PyTorch & Torchvision:** Modelin yüklenmesi, veri ön işleme, veri yükleyiciler (DataLoader) ve eğitim döngüsünün oluşturulması.
**Torchinfo:** Model mimarisinin ve parametrelerinin özetlenmesi.
***Matplotlib & PIL (Pillow):** Test fotoğraflarının görselleştirilmesi ve dışarıdan yüklenen görsellerin tahmini.

## Test ve Çıkarım (Inference)
Eğitim tamamlandıktan sonra model, veri setinde bulunmayan dış kaynaklı fotoğraflar (örneğin kullanıcının kendi yüklediği `golden.jpg`, `samoyed.jpg` gibi) üzerinde test edilebilir. Görüntüler modelin beklediği formatta ön işlemden geçirilir ve modelin sınıflara ait olasılık tahminleri (softmax) ekrana yazdırılır.