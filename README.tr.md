# Kuantum Labirenti

Bu repo, **graf teorisi** temelli, **tarayıcıda çalışan** ve **3B (Three.js) görselleştirmeye sahip** etkileşimli bir bulmaca/oyun içerir.

25 seviyeden oluşan bu “kriz yönetimi simülasyonunda” amaç; **A (giriş)** düğümünden başlayıp **G (çıkış)** düğümüne, bağlantılı düğümleri seçerek ilerlemektir.  
Oyunun temel mekaniği **maliyet dalgalanmasıdır**: her hamlede bazı yolların maliyeti değişebilir; bu yüzden en kısa yol her zaman en iyi yol değildir.

---

## Özellikler

### 1. 3B Graf Labirenti (Three.js)
- Etkileşimli 3B sahne
- Sürükle-bırak ile döndürme
- Mouse tekerleği / pinch ile zoom
- Düğümlere tıklayarak/dokunarak hareket

### 2. 25 Seviye (Prosedürel Üretim)
- Toplam **25 aşama** (`1 / 25`)
- Seviye arttıkça:
  - düğüm sayısı artar
  - süre ve maliyet kısıtları zorlaşır

### 3. Strateji: Maliyet ve Verimlilik
- Yollar üzerindeki sayılar **kaynak tüketimini (maliyet)** temsil eder
- Her hamlede maliyetler **dalgalanabilir**
- Hedef: “en kısa” değil, **en verimli** rotayı kurmak

### 4. Puanlama ve Sonuç Ekranları
- Puan; kalan süre ve maliyet bütçesi üzerinden hesaplanır
- Başarı/başarısızlık ekranları:
  - tekrar dene
  - sistemi sıfırla (sayfayı yenile)

### 5. Ses ve Müzik Kontrolü
- Web Audio API ile basit SFX (adım / kazanma / kaybetme)
- `mp3/music.mp3` ile arka plan müziği
- Müzik aç/kapat butonu

### 6. Mobil Kullanım
- **Yatay ekran** uyarısı (portrait modda oyun kilitlenir)
- Dokunmatik destek (düğmeye dokunarak seçme, pinch zoom)

---

## Proje Yapısı

- `index.html` — uygulamanın tamamı (UI + stiller + oyun mantığı + Three.js)
- `mp3/music.mp3` — arka plan müziği

CDN ile yüklenen kütüphaneler:
- jQuery
- Three.js (r128)

---

## Başlangıç

### Yerelde çalıştırma
1. Repoyu klonlayın:
   ```bash
   git clone https://github.com/miyigun/kuantum_labirenti.git
   ```
2. Klasöre girin:
   ```bash
   cd kuantum_labirenti
   ```
3. Local server başlatın (önerilir):
   ```bash
   python -m http.server 8000
   ```
4. Tarayıcıda açın:
   - `http://localhost:8000`

> Not: Local server, tarayıcı kısıtları ve özellikle ses davranışları açısından daha stabil çalışır.

---

## 🛠️ Kullanılan Teknolojiler
- HTML (tek sayfa)
- JavaScript (inline)
- Three.js (3B görselleştirme)
- jQuery (arayüz/olay yönetimi)
- Web Audio API (ses efektleri)
- MP3 çalma (`mp3/music.mp3`)

---

## 📌 Notlar
- **Amaç:** A’dan başlayıp **G** düğümüne ulaşmak.
- **Kaybetme koşulları:**
  - süre biterse
  - maliyet limiti aşılırsa
- Her hamlede maliyetler değişebildiği için rota planı dinamiktir.
- Mobilde **yatay mod** hedeflenmiştir.

---

## 📜 Lisans
MIT Lisansı (`LICENSE` dosyasına bakınız).