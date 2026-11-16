BALBAL TÜRKÇE v5 — AppContainer kaldırıldı

GÜNCELLEME: Önce açık Balbal uygulamalarını kapatın. Güncelleme ZIP'inin içindeki
dosyaları v4 paketindeki BalbalTurkce klasörüne çıkartın; aynı adları değiştirin.
models ve _internal klasörlerini koruyun. Modeli yeniden indirmek gerekmez.
Bu güncelleme v4 paketinin üzerine uygulanır; tek başına çalıştırılmaz.

BalbalTurkce.exe ve BalbalIzleyici.exe normal kullanıcı süreçleri olarak açılır.
AppContainer profili oluşturulmaz, klasör ACL/bütünlük etiketleri değiştirilmez.
Önceki sürümün Windows'ta oluşturduğu profiller kullanılmaz.

Model yalnızca EXE yanındaki models\balbal-v2-manas klasöründen yüklenir.
Model indirme kaldırılmıştır. ONNX/Hugging Face telemetrisi kapalı tutulur.
Python socket çağrıları engellenir; Windows düzeyinde ağ izolasyonu YOKTUR.
Bu ayarlar tüm yerel DLL'ler için işletim sistemi düzeyinde ağ engeli sayılmaz.

İzleyici pencere açıkken çalışır, kapanınca alt süreçleri durdurur.
MP3/M4A/video dönüşümü için FFmpeg pakete dahildir.
Çıktılar: transcript\dosya.mp3.txt. Mevcut TXT'ler atlanır.

WINDOWS UYARISI
Bu EXE'ler Authenticode ile imzalı değildir. SmartScreen / Smart App Control
uyarısının AppContainer kaldırılarak giderileceği garanti edilmez.
Güvenilir yayımlayıcı doğrulaması için güvenilir sağlayıcıdan kod imzası gerekir.
Yeni imzalı sürümlerde dahi itibar oluşana kadar uyarı görülebilir.
Bu paket Windows güvenlik ayarlarını değiştirmez ve engelleri aşmaz.

Powered by balbal — https://github.com/erayyap/balbal
Model lisansı: balbal Community License 1.1. Diğer lisanslar licenses klasöründe.
