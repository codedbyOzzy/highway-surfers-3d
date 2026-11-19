# 🏎️ Highway Surfers: 5-Şerit Turbo (Roblox Luau & 3D Web)

**Highway Surfers**, klasik *Subway Surfers* sonsuz koşu (endless runner) mekaniklerini **5 şeritli yüksek hızlı bir otoyol ve araba yarışı** atmosferine taşıyan sıfırdan tasarlanmış bir Roblox Luau ve 3D Web oyun projesidir.

---

## ✨ Temel Özellikler

1. **5 Şeritli Geniş Otoban & Makas (Near Miss) Sistemi**
   - 5 şerit (`-28`, `-14`, `0`, `14`, `28` Studs) arasında yüksek hızda şerit değiştirme (`A / D` veya `Sol / Sağ Ok`).
   - **Rampalardan Zıplama (`W / Space`)**: Alçak bariyerlerin, trafik araçlarının üstünden atlama veya rampa kamyonlarından (`RampTruck`) uçuşa geçme.
   - **Drift / Alçalma (`S / Aşağı Ok`)**: Yüksek lazer bariyerlerin (`HighBarrier`) altından drift yaparak kayma ve havadayken hızlı yere iniş (*Fast-Drop*).
   - **Makas Bonusu**: Akan trafiğin yanından teğet geçildiğinde ekstra kombo puanı kazanma.

2. **Polis Takibi (Interceptor Chase)**
   - Subway Surfers'taki bekçi mekaniği gibi koşu başında ve engellere yandan sürtüldüğünde (*Stumble*) sirenleri çalan polis aracı arkadan tampona yaklaşır.
   - Polis yakın takipteyken ikinci kez sürterseniz **Polise Yakalanırsınız (Busted!)**. Temiz sürüş yaptığınızda polis tekrar geriye düşer.

3. **5 Güçlendirme (Power-Ups)**
   - 🔥 **Nitro Turbo**: Süper hız ve çarpışma koruması (öndeki araçları fırlatır).
   - 🧲 **Altın Mıknatısı**: 5 şeritteki tüm altınları arabaya otomatik çeker.
   - 🛡️ **Enerji Kalkanı**: Tek bir ölümcül kazayı tamamen absorbe eder.
   - ✖️ **2X Skor & Kombo**: Kazanılan tüm skor ve makas puanlarını ikiye katlar.
   - ✈️ **Hava Otobanı (AeroWing Jet)**: Trafiğin üstünde uçarak gökyüzü altınlarını toplar.

4. **4 Dinamik Biyom Geçişi**
   - İlerlenen mesafeye göre gökyüzü, sis, asfalt ve çevre mimarisi otomatik değişir:
     1. **Metro Otobanı** (Neon Gökdelenler)
     2. **Yeraltı Tüneli** (Kehribar Kemerler)
     3. **Boğaz Köprüsü** (Kızıl Gün Batımı & Köprü Kuleleri)
     4. **Siber Gece Çölü** (Cyberpunk Neon Sütunlar)

5. **Garaj & Modifiye Mağazası (`DataStoreService` Kayıtlı)**
   - **5 Farklı Araç Sınıfı**: *Apex GT-86*, *Ronin Drift S15*, *Titan V8 Charger*, *Valkyrie X-2077*, *Solaris Phantom* (dahili kalkanla başlar).
   - **Gövde Boyası & Alt Neon (Underglow)** özelleştirme.
   - **Güçlendirme Yükseltmeleri**: Her güçlendirmenin süresini 5. seviyeye kadar kalıcı olarak artırma.

---

## 📁 Proje Mimari Yapısı

```text
├── default.project.json               # Rojo proje yapılandırması
├── src/
│   ├── shared/
│   │   ├── GameConfig.lua             # 5 şerit, araçlar, biyomlar, polis ve güçlendirme ayarları
│   │   └── VehicleBuilder.lua         # Kodla sıfırdan 3D Araba, Polis, TIR, Rampa üretici
│   ├── server/
│   │   └── GameServer.server.lua      # DataStore kayıt, Garaj mağazası ve Leaderstats yönetimi
│   └── client/
│       ├── HUDManager.lua             # Canlı HUD, Polis siren uyarısı, dokunmatik butonlar ve Garaj UI
│       └── RunnerController.client.lua# 60 FPS sürüş fiziği, dünya üretimi, çarpışma ve kamera sistemi
└── web-preview/
    └── index.html                     # Tarayıcıda doğrudan oynanabilir 3D WebGL/Canvas sürümü
```

---

## 🚀 Kurulum ve Çalıştırma

### Roblox Studio (Rojo ile)
1. [Rojo](https://rojo.space/) eklentisini kullanarak `default.project.json` dosyasını Roblox Studio'ya senkronize edin veya `src/` altındaki dosyaları ilgili servislere (`ReplicatedStorage.Shared`, `ServerScriptService.Server`, `StarterPlayerScripts.Client`) yerleştirin.
2. Harici hiçbir 3D model gerekmez; [`VehicleBuilder.lua`](src/shared/VehicleBuilder.lua) ve [`RunnerController.client.lua`](src/client/RunnerController.client.lua) tüm 3D otobanı ve araçları kodla otomatik inşa eder.

### 3D Web Tarayıcı Önizlemesi
- [`web-preview/index.html`](web-preview/index.html) dosyasını herhangi bir modern tarayıcıda açarak oyunu anında test edebilirsiniz.
