# Akış Şeması Uygulaması

Eğitsel amaçlı, etkileşimli akış şeması tasarlama uygulaması. **Yapay Zeka Destekli** - Metinden otomatik akış şeması üretimi!

## Özellikler

### 🎨 Temel Özellikler
- Sürükle-bırak ile kolay düzenleme
- Otomatik Mermaid kod senkronizasyonu
- Geri al/İleri al desteği (Ctrl+Z/Ctrl+Y)
- 10+ düğüm tipi (Terminal, İşlem, Karar, Döngü, vb.)
- Hazır şablonlar (ATM, Rutin, Döngü, Okula Gidiş vb.)
- Proje kaydet/yükle (.mmd formatı)
- PNG/SVG/PDF olarak dışa aktarma
- Tam Türkçe arayüz

### 🤖 AI Asistanı (Groq API)
- **Metinden Akış Şeması Üretimi**: Sadece tanım yazın, AI gerçekçi bir akış şeması oluştursun
- **2 Mod**: 
  - **Akış Şeması**: Bağlantılı, profesyonel akış şemaları (8-12 düğüm)
  - **Bağımsız Düğümler**: 9 adet bağımsız düğüm (brainstorming için)
- **Akıllı Etiketleme**: Karar düğümleri için otomatik "Evet/Hayır" etiketleri
- **Hata Yönetimi**: Rate limit hataları 5 saniye ekranda kalır
- **Örnek Kullanım**: "okula gidiş", "ATM para çekme", "kahvaltı hazırlama" gibi tanımlar yazın

### 🎯 Gelişmiş Özellikler
- **Akıllı Düğüm Ekleme**: Seçili düğümün altına otomatik bağlantılı ekleme
- **Yeni Şemaya Geç**: Seçimi iptal edip bağımsız düğüm ekleme modu
- **Çoklu Karar Dalları**: Bir karar düğümünden 3+ dal çıkarabilme
- **Otomatik Yerleşim**: Düğümler akıllıca konumlandırılır
- **Doğrulama**: Akış şeması hataları anlık kontrol edilir

## Kurulum

```bash
# Gerekli paketleri yükle
pip install -r requirements.txt
```

**Not**: AI asistanı için [Groq API anahtarı](https://console.groq.com/keys) gereklidir (ücretsiz).

## Çalıştırma

```bash
streamlit run app_end.py
```

Uygulama varsayılan olarak `http://localhost:8501` adresinde açılacaktır.

## Gereksinimler

- Python 3.8+
- Streamlit 1.30.0+
- streamlit-flow-component 1.6.1+
- groq 0.4.0+ (AI asistanı için)
- reportlab 4.0.0+ (PDF export için)

## Kullanım

### 1. Manuel Akış Şeması Oluşturma
1. Sol panelden şablon seçin veya sıfırdan başlayın
2. Üst paletten düğüm türü seçin
3. Seçili düğümün altına yeni düğüm eklemek için düğüme tıklayıp palette'ten seçim yapın
4. "Yeni Şemaya Geç" ile bağımsız düğüm ekleme moduna geçin
5. Düğümleri sürükleyerek konumlandırın
6. Sağ panelden düğüm/bağlantı özelliklerini düzenleyin

### 2. AI ile Akış Şeması Üretimi
1. Sol sidebar'dan "AI Asistanı (Metinden Şemaya)" bölümünü açın
2. [console.groq.com/keys](https://console.groq.com/keys) adresinden API key alın
3. API key'i girin
4. "Akış Tanımı" kutusuna ne yapmak istediğinizi yazın
   - Örnek: "okula gidiş"
   - Örnek: "ATM'den para çekme"
   - Örnek: "kahvaltı hazırlama"
5. Mod seçin:
   - **Akış Şeması**: Bağlantılı, profesyonel akış (önerilen)
   - **Bağımsız Düğümler**: 9 adet bağımsız kutu
6. "⚡ AI Üret" butonuna tıklayın
7. AI otomatik olarak akış şemasını oluşturacak ve ekrana yansıtacak

### 3. Dışa Aktarma
- **PNG/SVG**: "Grafik Dışa Aktar" butonuyla görsel olarak kaydedin
- **PDF**: "PDF Dışa Aktar" ile profesyonel doküman oluşturun
- **Mermaid**: "Kodu Kopyala" ile Mermaid kodunu paylaşın
- **Proje**: ".mmd" formatında kaydedip tekrar yükleyin

## Ekran Görüntüleri

- Etkileşimli düğüm paleti ile hızlı şema oluşturma
- AI asistanı ile metinden otomatik şema üretimi
- Gerçek zamanlı Mermaid kod senkronizasyonu
- Profesyonel PDF/PNG/SVG export

## Sık Sorulan Sorular

**S: AI asistanı çalışmıyor, ne yapmalıyım?**
A: 1) Groq API key'inizin doğru olduğundan emin olun. 2) İnternet bağlantınızı kontrol edin. 3) Rate limit hatası alıyorsanız 5 saniye bekleyin.

**S: Karar düğümünden 3'ten fazla dal çıkarabilir miyim?**
A: Evet! İlk 2 dal otomatik "Evet/Hayır" etiketli olur, 3. ve sonraki dallar boş bırakılır (manuel etiket ekleyebilirsiniz).

**S: "Yeni Şemaya Geç" butonu ne işe yarar?**
A: Seçili düğümü iptal eder, böylece sonraki düğümler bağımsız (bağlantısız) eklenir.

## Güncellemeler

### v2.0 (Şubat 2026)
- ✨ **AI Asistanı eklendi** (Groq API entegrasyonu)
- 🎯 Metinden akış şeması üretimi
- 🔀 Çoklu karar dalları desteği (3+ dal)
- 🎨 Gelişmiş düğüm ekleme mantığı
- ⚡ Rate limit hata yönetimi
- 🐛 Bug düzeltmeleri ve performans iyileştirmeleri

## Teknolojiler

- **Frontend**: Streamlit, streamlit-flow-component
- **AI**: Groq API (llama-3.3-70b-versatile modeli)
- **Export**: ReportLab (PDF), Pillow (PNG)
- **Format**: Mermaid.js flowchart syntax

## Katkıda Bulunma

Pull request'ler kabul edilir. Büyük değişiklikler için önce issue açarak tartışalım.

## Yazar

**Hüseyin SIHAT** - Eğitsel faaliyetler için hazırlanmıştır.

GitHub: [@huseyinsihat](https://github.com/huseyinsihat)

## Lisans

Eğitim amaçlı kullanım için geliştirilmiştir.
