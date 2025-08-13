# MNIST ANN Classifier

## Proje Hakkında
Bu proje, **yapay sinir ağı (ANN)** kullanarak MNIST veri setindeki el yazısı rakamları sınıflandırmayı hedefler.  
Amaç, ANN temel mantığını anlamak ve basit bir sınıflandırma modeli ile sonuçları gözlemlemektir.

## Kullanılan Teknolojiler
- Python 3.x
- TensorFlow / Keras
- NumPy
- Matplotlib

## Yapay Sinir Ağı Mantığı

### Veri Hazırlama
- Giriş verisi (X): 28x28 piksel değerleri normalize edilir (0-1 arası float).  
- Etiketler (Y): 0-9 rakamları, one-hot encoding ile `[0,0,...,1,...]` vektörleri.

### Katmanlar
| Katman        | İşlev                          | Aktivasyon       |
|---------------|--------------------------------|----------------|
| Giriş         | Görüntüyü tek boyutlu vektöre çevirir | Flatten        |
| Gizli Katman  | Özellikleri öğrenir            | ReLU (128 nöron)|
| Çıkış         | Sınıflandırma tahmini üretir   | Softmax (10 nöron)|

### Aktivasyon Fonksiyonları
- ReLU: Negatifleri 0, pozitifleri geçirir.  
- Sigmoid: 0-1 arası, ikili sınıflandırma.  
- Softmax: Çok sınıflı olasılık dağılımı üretir.  

### Öğrenme Algoritması
- Optimizer: Adam  
- Loss: Categorical Crossentropy  
- Eğitim Mantığı: Forward pass → Loss → Backpropagation → Ağırlık güncelle

## Eğitim Parametreleri
- Batch size: 32  
- Epoch: 5  
- Validation split: 10%
  
## Özet 
Giriş (28x28) -> Flatten(784) -> Gizli Katman (128 nöron, ReLU) -> Çıkış Katmanı (10 nöron, Softmax)
