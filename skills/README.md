# Beceri kataloğu

Arch Studio becerileri tek bir düz katalog olarak birlikte kurulur. Aşağıdaki bağlantılar `/as:<beceri>` adlandırmasını kullanır; host'un keşfettiği gerçek giriş noktasını (gerekiyorsa eklenti ad alanıyla) kullanın. Gruplar becerilerin ne yaptığını anlatır; ayrı eklenti veya kurulum paketi değildir.

**Türkiye uyarlaması:** Türkiye'ye özel beceriler `-tr` ekiyle biter. Tüm diğer beceriler, kullanıcı Türkçe yazdığında veya arsa Türkiye'de olduğunda [Türkiye kuralını](../rules/turkiye.md) uygular (Türkçe çıktı, metrik birim, TL/KDV, Türk mevzuatı). `nyc-` ile başlayan beceriler yalnızca New York içindir.

[Oluşturulan yetenek kataloğu](../docs/capabilities.md), paylaşılan bileşen kaydından göreve göre keşif sağlar.

## Türkiye

| Beceri | Açıklama |
|-------|-------------|
| [`/as:mulk-raporu-tr`](./mulk-raporu-tr) | Parsel, imar, tescil, yapı kayıtları ve deprem tehlikesini birleştiren ön inceleme raporu |
| [`/as:imar-analizi-tr`](./imar-analizi-tr) | İmar durumu, emsal/KAKS, TAKS, Hmax, çekme mesafeleri, otopark ve plan notları |
| [`/as:parsel-sorgu-tr`](./parsel-sorgu-tr) | TKGM Parsel Sorgu ile ada/parsel kimliği, yüzölçümü, nitelik ve geometri |
| [`/as:tescil-kontrol-tr`](./tescil-kontrol-tr) | Tescilli kültür varlığı ve sit alanı kontrolü (2863, Koruma Bölge Kurulları) |
| [`/as:yapi-kayit-tr`](./yapi-kayit-tr) | Ruhsat, iskân, yapı denetim, yapı kayıt belgesi ve riskli yapı geçmişi |
| [`/as:mimarlik-bilgisi-tr`](./mimarlik-bilgisi-tr) | Türkiye mimarlık meslek pratiği: proje aşamaları, roller, Mimarlar Odası, yapı sınıfları |

## Ofis işleri

| Beceri | Açıklama |
|-------|-------------|
| [`/as:norma`](./norma) | Mimari niyeti, kapsamı ve devirleri mevcut beceriler üzerinden koordine eder |
| [`/as:norma-support`](./norma-support) | Arch Studio başlangıç, erişim, hafıza ve kanıta dayalı sorun giderme |
| [`/as:studio`](./studio) | Ofisi kurar ve inceler, projeleri kaydeder, genel istekleri Norma'ya iletir |
| [`/as:tool-catalog`](./tool-catalog) | Mevcut becerileri ve ajanları gösterir |
| [`/as:learn`](./learn) | Mimarlar için Codex ve Claude Code'a rehberli, devam ettirilebilir giriş (Codex'te `$learn`) |
| [`/as:skill-maker`](./skill-maker) | Yönetişimli ofis, proje veya katalog becerileri oluşturur ya da günceller |
| [`/as:studio-feedback`](./studio-feedback) | Otomatik gönderim olmadan gözden geçirilmiş hata raporu veya özellik isteği hazırlar |

## Proje yönetimi

### Proje kayıtları

Proje kayıtları düz dosyalardan oluşan bağlantılı bir yapıdır. `/as:project` kurulum ve hafıza arayüzüdür: `PROJECT.md` kaynaklı olguları, kayıtlı karar belgeleri kalıcı gerekçeleri tutar. Toplantı ve saha raporları kaynak bağlamını korur, proje veya ofis `TASKS.csv` aksiyon geçmişini tutar, iş planları bu kayıtları okur ve `TIME.csv` yalnızca kullanıcının onayladığı süreleri kaydeder.

| Beceri | Açıklama |
|-------|-------------|
| [`/as:project`](./project) | Proje başlatır, kaynaklı olguları tutar ve kalıcı kararları yönetir |
| [`/as:receive`](./receive) | Gelen ve üretilen belgeleri doğrulanmış kimlik ve geçmişle DOCUMENTS.csv'ye kaydeder |
| [`/as:workplan`](./workplan) | İşe başlamadan önce depo, operasyon veya yapı işlerini planlar |
| [`/as:meeting-minutes`](./meeting-minutes) | Kaynak bağlantılı toplantı tutanakları |
| [`/as:site-visit-report`](./site-visit-report) | Saha gözlemleri, beyanlar, sınırlamalar ve takip adayları |
| [`/as:tasklist`](./tasklist) | Proje görevleri veya ofis portföy kaydı |
| [`/as:timetracker`](./timetracker) | Etkinliği yeniden oluşturur ve yalnızca onaylanan süreyi ekler |
| [`/as:proposal`](./proposal) | Korumalı verilmiş koşullarla proje teklifleri (Mimarlar Odası en az bedel, TL/KDV) |
| [`/as:agreement`](./agreement) | Kaynaklı sözleşme bağlamı ve işin kapsamla karşılaştırılması |
| [`/as:invoice`](./invoice) | Kullanıcı talimatıyla fatura kaydı, tavan uyarıları ve boşluk tespiti (TL, e-Fatura) |

### Mesleki pratik bilgisi

| Beceri | Açıklama |
|-------|-------------|
| [`/as:architecture-knowledge`](./architecture-knowledge) | ABD pratiği terimleri (CD set, AIA, CSI); Türkiye için `mimarlik-bilgisi-tr` |

## Pratik ve tasarım

### Ön inceleme — New York (yalnızca NYC)

| Beceri | Açıklama |
|-------|-------------|
| [`/as:nyc-landmarks`](./nyc-landmarks) | LPC landmark ve tarihî bölge kontrolü |
| [`/as:nyc-dob-permits`](./nyc-dob-permits) | DOB ruhsat ve başvuru geçmişi |
| [`/as:nyc-dob-violations`](./nyc-dob-violations) | DOB ve ECB ihlalleri |
| [`/as:nyc-acris`](./nyc-acris) | ACRIS mülk işlem kayıtları |
| [`/as:nyc-hpd`](./nyc-hpd) | HPD ihlalleri, şikâyetler ve kayıt |
| [`/as:nyc-bsa`](./nyc-bsa) | BSA muafiyetleri ve özel izinler |
| [`/as:nyc-property-report`](./nyc-property-report) | Birleşik NYC mülk raporu |

### Arsa ve imar

| Beceri | Açıklama |
|-------|-------------|
| [`/as:environmental-analysis`](./environmental-analysis) | İklim, rüzgâr, güneş, sel, deprem (AFAD) ve zemin araştırması |
| [`/as:mobility-analysis`](./mobility-analysis) | Toplu taşıma, yürünebilirlik, bisiklet ve yaya altyapısı |
| [`/as:demographics-analysis`](./demographics-analysis) | Nüfus, gelir, yaş, konut ve istihdam (TÜİK) |
| [`/as:site-history`](./site-history) | Mahalle bağlamı, tescilli yapılar, hareketlilik ve planlanan gelişmeler |
| [`/as:zoning-analysis-nyc`](./zoning-analysis-nyc) | NYC FAR, yükseklik, setback ve kullanım analizi (Türkiye için `imar-analizi-tr`) |
| [`/as:zoning-envelope`](./zoning-envelope) | Bağımsız etkileşimli 3B imar zarfı (Türkiye ve NYC) |

### Programlama ve şartnameler

| Beceri | Açıklama |
|-------|-------------|
| [`/as:workplace-programmer`](./workplace-programmer) | Personel sayısı ve çalışma biçiminden ofis alan programı |
| [`/as:occupancy-calculator`](./occupancy-calculator) | Kullanıcı yükü, kaçış ve çıkışlar (Türkiye: Yangın Yönetmeliği; ABD: IBC) |
| [`/as:spec-writer`](./spec-writer) | Mahal listesi ve teknik şartname bölümleri, inceleme işaretleriyle (TS/TS EN veya CSI) |

### Sürdürülebilirlik

| Beceri | Açıklama |
|-------|-------------|
| [`/as:epd-parser`](./epd-parser) | EPD PDF'lerinden çevresel veri çıkarır |
| [`/as:epd-research`](./epd-research) | Malzeme veya kategoriye göre EPD kayıtlarını araştırır (EPD Türkiye dahil) |
| [`/as:epd-compare`](./epd-compare) | Çevresel etkileri ve LEED uygunluğunu karşılaştırır |
| [`/as:epd-to-spec`](./epd-to-spec) | Şartname için EPD teslim gereklilikleri ve kaynaklı GWP sınırları |

### FF&E ve malzemeler

Açıkça benimsenen FF&E (mobilya, donatı, ekipman) listeleri değişmez kalem/liste kayıtları kullanır; Excel çalışma kitapları sabitlenmiş görünümlerdir. İsteğe bağlı yeniden kullanılabilir kütüphane `product-library.csv`, isteğe bağlı EPD kaydı `epd-library.csv` dosyasıdır. Bkz. [kayıt sahipliği](../studio/ffe/README.md) ve [`schema/`](../schema).

| Beceri | Açıklama |
|-------|-------------|
| [`/as:master-schedule`](./master-schedule) | Listeleri benimser/revize eder/uzlaştırır; kütüphane bakımı product-library'de kalır |
| [`/as:product-library`](./product-library) | Önizleme, korumalı kayıt ve yeniden deneme kurtarmasıyla CSV ürün kütüphanesi |
| [`/as:product-url-clip`](./product-url-clip) | Verilen URL kanıtını saklar ve kayıt geçmişini inceler; ürün benimsemez |
| [`/as:product-research`](./product-research) | Tasarım brifinden ürün bulur |
| [`/as:product-spec-bulk-fetch`](./product-spec-bulk-fetch) | Ürün URL'lerinden toplu teknik özellik çıkarır |
| [`/as:product-spec-pdf-parser`](./product-spec-pdf-parser) | Katalog, fiyat listesi ve föylerden teknik özellik çıkarır |
| [`/as:drawing-quantity-extract`](./drawing-quantity-extract) | Çizimlerden konum kanıtlı adet sayımı ve kapsam boşlukları |
| [`/as:schedule-quantity-reconcile`](./schedule-quantity-reconcile) | Eşleşen kapsamlarda kaynaklı adetleri kayıt değiştirmeden karşılaştırır |
| [`/as:lighting-report-extract`](./lighting-report-extract) | Aydınlatma raporu sonuçlarını kesin yüzey ve sayfa kimlikleriyle çıkarır |
| [`/as:product-data-cleanup`](./product-data-cleanup) | Ürün kategorisi, ölçü, malzeme ve dili normalize eder |
| [`/as:product-data-import`](./product-data-import) | Ürün listelerini biçimli FF&E listelerine dönüştürür |
| [`/as:product-enrich`](./product-enrich) | Ürünleri kategori, renk, malzeme ve stil ile etiketler |
| [`/as:product-match`](./product-match) | Görsel, ad veya tanımdan benzer ürün bulur |
| [`/as:product-pair`](./product-pair) | Tamamlayıcı ürün önerir |
| [`/as:product-image-processor`](./product-image-processor) | Ürün görsellerini indirir, boyutlandırır ve arka planını kaldırır |
| [`/as:product-audit`](./product-audit) | Ürün kanıtını, tutarsızlıkları ve bilinmeyenleri denetler |
| [`/as:product-cut-sheet`](./product-cut-sheet) | Kaynağa sadık tek ürün föyü veya FF&E girdisi |
| [`/as:ffe-spec-book`](./ffe-spec-book) | Kalem kalem teslim kaydıyla sıralı FF&E şartname kitabı |
| [`/as:csv-to-sif`](./csv-to-sif) | Kanonik ürün CSV'sini SIF'e dönüştürür |
| [`/as:sif-to-csv`](./sif-to-csv) | SIF'i kanonik ürün CSV şemasına dönüştürür |

### Sunumlar

| Beceri | Açıklama |
|-------|-------------|
| [`/as:slide-deck-generator`](./slide-deck-generator) | Bağımsız HTML sunumlar |
| [`/as:color-palette-generator`](./color-palette-generator) | WCAG kontrast kontrollü renk paletleri |
| [`/as:resize-images`](./resize-images) | Web, sosyal medya, sunum ve baskı için görsel boyutlandırma |

## Tek tek beceri belgeleri

Her klasör yetkili bir `SKILL.md`, gerekirse kullanıcıya yönelik bir rehber ve kendi prosedür, betik, şema veya şablonlarını içerir; dış bilgi kaynak kataloğu üzerinden yönlendirilir. Ofis veya proje becerisi oluşturmak/güncellemek için `/as:skill-maker` kullanın; yerleşik beceriye katkı için [CONTRIBUTING.md](../CONTRIBUTING.md) dosyasını okuyun.

Pratik keşfi, [on bakımlı küme manifestinden](../docs/practice-clusters.md) üretilir.
Paylaşılan sahiplik için [kategori yazım sözleşmesine](../docs/category-authoring.md) bakın;
genel beceri adları ve çağırma sözdizimi değişmeden kalır.
