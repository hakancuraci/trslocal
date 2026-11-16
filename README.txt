BALBAL TÜRKÇE — v4, TAŞINABİLİR / AĞ İZOLELİ

ZIP'i tamamen çıkartın. EXE, _internal ve models klasörleri birlikte kalmalıdır.
Python, FFmpeg veya model indirmeniz gerekmez. Yönetici yetkisi gerekmez.

BalbalTurkce.exe: tek dosya için arayüz.
BalbalIzleyici.exe: pencere açıkken aynı dizindeki ses/video dosyalarını izler.
Pencere kapanınca izleyici ve FFmpeg alt işlemi durur.

AĞ ERİŞİMİ
Normal başlangıçta yalnızca standart Python/Windows başlatıcısı çalışır ve
uygulamayı ağ yetkisi olmayan Windows AppContainer içinde yeniden başlatır.
Model motoru ve FFmpeg bu izolasyon içinde çalışır. internetClient, özel ağ veya
sunucu yetkisi verilmez. Yönetici hesabı ve güvenlik duvarı kuralı kullanılmaz.
İzolasyon kurulamazsa uygulama hata verir; normal/ağ erişimli çalışmaya geçmez.
ONNX telemetrisi başlatılmadan kapatılır. Python socket işlemleri de reddedilir.
Hugging Face indirme kütüphanesi ve hf-xet EXE paketine dahil değildir.

DOSYA ERİŞİMİ
İşlenecek ses/video dosyalarını uygulamanın bulunduğu klasöre kopyalayın.
Model yalnızca models\balbal-v2-manas içinden yüklenir. Dosya eksikse indirme
denenmez. Arayüzün TXT kaydetme yeri transcript klasörüdür.
Model/uygulama klasörüne sandbox için okuma/çalıştırma izni; data ve transcript
klasörlerine yazma izni otomatik verilir. Bu iki klasöre düşük bütünlük etiketi
uygulanır. Kullanıcı hesabınızın mevcut erişimi kaldırılmaz.
Windows her paket konumu için yerel bir AppContainer profili oluşturur. Bu profil
ZIP'in parçası değildir; yeni bilgisayarda veya konumda otomatik oluşturulur.
Kurum politikası AppContainer oluşturulmasını engelliyorsa uygulama çalışmaz.

MODELLER
models\balbal-v2-manas\model.json
models\balbal-v2-manas\onnx\model.onnx
models\balbal-v2-manas\onnx\model.onnx.data
models\balbal-v2-manas\lm\model.binary
models\balbal-v2-manas\lm\tokenizer.model

İZLEYİCİ
Dosyalar alfabetik sırayla tek tek işlenir; alt klasörler taranmaz.
Her 5 saniyede tarama yapılır; dosya 10 saniye değişmeden kalınca işlenir.
Örnek: kayit.mp3 -> transcript\kayit.mp3.txt
Aynı TXT mevcutsa üzerine yazılmaz. Hatalı dosya diğerlerini durdurmaz.
Başlangıç, bitiş, süre ve hatalar pencerede; kalıcı günlük transcript\islem.log'da.
data klasöründe yerel hata kayıtları ve geçici dosyalar bulunur.
Kaynak dosyalar değiştirilmez. Bu ZIP çalışma günlükleri ve örnek ses içermez.

Bu bir kayıtlı Windows servisi değildir. Otomatik başlangıca eklenmez.
Eski v2/v3 EXE'ler bu sürümün ağ izolasyonunu kazanmaz; yeni EXE'leri kullanın.

DERLEME: Windows, Python 3.12
.venv\Scripts\python -m pip install -r requirements.txt
Model dosyalarını yukarıdaki yapıda models klasörüne yerleştirin.
powershell -ExecutionPolicy Bypass -File build.ps1
Doğrudan Python betiklerini çalıştırmak otomatik Windows izolasyonunu başlatmaz;
dağıtım için build.ps1 ile üretilen EXE'leri kullanın.

Powered by balbal — https://github.com/erayyap/balbal
Model ağırlıkları: balbal Community License 1.1.
FFmpeg ve diğer bağımlılıklar için licenses klasörüne bakın.
