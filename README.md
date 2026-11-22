<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/brand/arch-studio-typemark-white.png">
  <img src="assets/brand/arch-studio-typemark.png" alt="Arch Studio" width="650">
</picture>
<br>
<br>
<br>

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Claude Code: plugin](https://img.shields.io/badge/Claude_Code-plugin-blue)](https://code.claude.com/docs)
[![Codex: plugin](https://img.shields.io/badge/Codex-plugin-blue)](https://developers.openai.com/codex/)
[![beceri: 67](https://img.shields.io/badge/beceri-67-blue)](./skills/README.md)
[![Türkiye](https://img.shields.io/badge/uyarlama-T%C3%BCrkiye-red)](./rules/turkiye.md)

**Sürüm: 1.5.3 tabanlı Türkiye uyarlaması**

</div>

# Arch Studio — Türkiye

Bu depo, ALPA'nın açık kaynak (MIT) [Arch Studio / skills-for-architects](https://github.com/AlpacaLabsLLC/skills-for-architects) eklentisinin **Türkiye'deki mimarlık ofisleri için uyarlanmış** bir çatalıdır (fork). Arch Studio, bir mimarlık ofisinin kendi yapay zekâ pratiğini kurmasına yardım eder: yapay zekânın nasıl yönetileceğine, hangi pratik alanlarını kapsayacağına, neyi hatırlayacağına ve hangi araçları kullanacağına karar verirsiniz; bu kararlar [Claude Code](https://code.claude.com/docs) veya [Codex](https://developers.openai.com/codex/) içinde uygulanır.

> Bu çatal ALPA tarafından yayımlanmamış ve desteklenmemektedir. Orijinal proje ve tüm hakları için [LICENSE](LICENSE) dosyasına bakın.

## İçindekiler

- [Türkiye uyarlamasında neler var](#türkiye-uyarlamasında-neler-var)
- [Kurulum](#kurulum)
- [Temel iş akışı](#temel-iş-akışı)
- [İçerik](#i̇çerik)
- [Önemli sınırlamalar](#önemli-sınırlamalar)
- [Veri, gizlilik ve telemetri](#veri-gizlilik-ve-telemetri)
- [Lisans](#lisans)

## Türkiye uyarlamasında neler var

- **6 yeni Türkiye becerisi:** imar analizi (emsal/KAKS, TAKS, Hmax, çekme mesafeleri, plan notları), TKGM parsel sorgu, tescil ve sit alanı kontrolü, yapı kayıtları (ruhsat, iskân, yapı denetim, yapı kayıt belgesi, riskli yapı), birleşik mülk ön inceleme raporu ve Türkiye mimarlık meslek bilgisi.
- **Yeni ajan:** `turkiye-imar-uzmani` — Türkiye'deki taşınmazlar için parsel, imar, tescil ve yapı kaydı araştırmasını koordine eder.
- **Türkiye yargı bölgesi ve 27 resmî kaynak:** Mevzuat Bilgi Sistemi, Resmî Gazete, 3194 sayılı İmar Kanunu, Planlı Alanlar İmar Yönetmeliği, Binaların Yangından Korunması Hakkında Yönetmelik, Türkiye Bina Deprem Yönetmeliği, Otopark Yönetmeliği, 2863, 4708, 6306 ve 4734 sayılı kanunlar, TKGM, e-Plan, e-Devlet, AFAD Deprem Tehlike Haritası, MTA, Koruma Bölge Kurulları, TÜİK, MGM, Mimarlar Odası, Yapı Yaklaşık Birim Maliyetleri, TSE, GİB, EKAP ve İBB Açık Veri.
- **Tüm 61 mevcut beceri uyarlandı:** açıklamalar Türkçe; her beceride Türkiye talimatları var. Örnekler: kullanıcı yükü hesabı Yangın Yönetmeliği'ne göre, deprem tehlikesi AFAD'dan, nüfus TÜİK'ten, teklifler Mimarlar Odası en az bedel esasına göre, faturalar TL/KDV/e-Fatura ile, şartnameler mahal listesi ve TS/TS EN atıflarıyla.
- **[Türkiye kuralı](rules/turkiye.md):** Türkçe çıktı, metrik birimler, Türk sayı ve tarih biçimi, TL ve KDV, KVKK ilkeleri.
- **Türkçe sorumluluk reddi:** Mevzuat içeren çıktılar Türkçe kanonik blokla biter; kontrol hook'u Türkçe bloğu da tanır.

## Kurulum

Bu çatalın marketplace adı, orijinaliyle aynıdır (`skills-for-architects`). **Orijinal eklentiyi kurduysanız önce onu kaldırın:**

```bash
claude plugin uninstall as@skills-for-architects
```

```bash
claude plugin marketplace remove skills-for-architects
```

### Claude Code

`<github-kullanici>/<depo>` yerine bu deponun GitHub adresini yazın:

```bash
claude plugin marketplace add <github-kullanici>/<depo>
```

```bash
claude plugin install as@skills-for-architects
```

Ardından yeni bir oturum başlatın:

```bash
claude
```

### Codex

```bash
codex plugin marketplace add <github-kullanici>/<depo>
```

```bash
codex plugin add as@skills-for-architects
```

### Çalıştığını kontrol edin

Claude Code'da `/as:studio`, Codex'te `$studio` yazın. Türkiye becerilerini görmek için `/as:tool-catalog` yazın veya doğrudan deneyin:

- `/as:imar-analizi-tr İstanbul Kadıköy Moda Mahallesi 123 ada 45 parsel`
- `/as:occupancy-calculator 450 m² restoran, İzmir`
- `/as:mimarlik-bilgisi-tr Uygulama projesi ile avan proje arasındaki fark nedir?`

## Temel iş akışı

1. **studio** — `/as:studio` ile ofis politikanızı, adlandırma kurallarınızı, birimleri (metrik), yargı bölgesini (Türkiye) ve proje aşamalarını kaydedin ya da kurulum yapmadan doğrudan bir işe başlayın.
2. **norma** — İhtiyacınızı düz Türkçeyle anlatın. Norma uygun becerileri seçer; büyük işler için önce bir iş planı gösterir.
3. **Araştırma becerileri** — Arsa, imar, taşınmaz, ürün ve EPD becerileri asıl kaynaklara gider ve kaynak gösterir. Örneğin **mulk-raporu-tr**, parsel, imar, tescil, yapı kayıtları ve deprem tehlikesini tek raporda birleştirir.
4. **Şartname ve sunum becerileri** — **spec-writer**, **epd-to-spec**, **product-cut-sheet**, **slide-deck-generator** araştırmadan belge hazırlar. Mevzuat içeren her çıktı mesleki inceleme için işaretlenir.
5. **Kayıt becerileri** — **project**, **receive**, **meeting-minutes**, **tasklist** ve **timetracker** olguları, belgeleri, kararları, görevleri ve zamanı proje klasörünüzde tutar.
6. **skill-maker** — Ofisinizde tekrarlanan bir prosedürü `/as:skill-maker` ile ofis veya proje becerisine dönüştürün.

## İçerik

67 beceri (6'sı Türkiye'ye özel), 9 ajan, 9 kural ve 4 hook; hepsi birlikte kurulur. English summary: 67 skills, 9 agents, 9 rules, and 4 hooks. Tam katalog: [skills/README.md](./skills/README.md).

### Ajanlar (Claude Code)

| Ajan | Ne yapar |
|-------|--------------|
| [turkiye-imar-uzmani](./agents/turkiye-imar-uzmani.md) | Türkiye'de parsel, imar, tescil ve yapı kaydı araştırması ile imar zarfı |
| [site-planner](./agents/site-planner.md) | Çevre, ulaşım, demografi ve tarihçe araştırmasını birleştirir |
| [nyc-zoning-expert](./agents/nyc-zoning-expert.md) | Yalnızca New York: mülk araştırması ve imar analizi |
| [workplace-strategist](./agents/workplace-strategist.md) | Personel sayısı ve çalışma biçiminden alan programı |
| [product-and-materials-researcher](./agents/product-and-materials-researcher.md) | Ürün bulur, özellik çıkarır, muadil önerir |
| [ffe-designer](./agents/ffe-designer.md) | FF&E listeleri ve oda paketleri hazırlar, kontrol eder |
| [sustainability-specialist](./agents/sustainability-specialist.md) | EPD araştırır, karşılaştırır, şartname sınırları hazırlar |
| [brand-manager](./agents/brand-manager.md) | Sunum ve paletler hazırlar, teslimleri kontrol eder |
| [norma](./agents/norma.md) | Onaylanmış bir görevi yürüten isteğe bağlı çalışan |

### Kurallar

Ayrıntılar için [kurallar dizinine](./rules/README.md) bakın. Türkiye'ye özgü kural: [turkiye](./rules/turkiye.md). Diğerleri: units-and-measurements, code-citations, professional-disclaimer, csi-formatting, terminology, output-formatting, transparency, moments.

### Hook'lar

| Hook | Host | Ne zaman | Ne yapar |
|------|------|------|--------------|
| [session-start-welcome](./hooks/session-start-welcome.sh) | Claude Code | Oturum başlangıcı | Becerilerin hazır olduğunu bildirir |
| [version-check](./hooks/version-check.sh) | Claude Code | Günde en fazla bir kez | **Orijinal** projenin yeni sürümünü kontrol eder (aşağıya bakın) |
| [post-write-disclaimer-check](./hooks/post-write-disclaimer-check.sh) | Claude Code | Write/Edit sonrası | Sorumluluk reddi eksik mevzuat çıktısını işaretler (Türkçe veya İngilizce) |
| [session-start-ambient](./hooks/session-start-ambient.sh) | Codex | Oturum başlangıcı | Kısa yönlendirme bağlamı ekler |

### Nasıl düzenlenmiştir

Arch Studio dört bölümden oluşur (çerçeve terimleri orijinal adlarıyla):

| Pillar | Responsibility |
|---|---|
| Governance | Account and access, Configuration, Standards and Assurance |
| Tooling | Skills, specialist profiles, tools and integrations; the host performs execution |
| Knowledge | Access to applicable authoritative original sources and their provenance |
| Memory | Accepted studio/project facts, decisions, preferences, records and evidence |

Yönetişim (kim neyi onaylar), araçlar (beceriler ve ajanlar), bilgi (asıl kaynaklara erişim) ve hafıza (ofis/proje olguları ve kararları). Ayrıntılar: [mimari](docs/architecture.md), [çalışma alanı modeli](docs/workspace-model.md) (hangi dosya kime ait), [host sözleşmesi](docs/host-harness-contract.md) ve [PATTERNS](PATTERNS.md).

Kendi becerilerinizi `/as:skill-maker` ile ofis (`studio/.claude/skills/`) veya proje klasörünüzde oluşturabilirsiniz; eklenti güncellemeleri bunların üzerine yazmaz. Belediyenize özel bir imar prosedürü, ofis şartname şablonunuz veya teklif formatınız için idealdir.

## Önemli sınırlamalar

- **Mesleki onay değildir.** Tüm imar, yangın, deprem ve şartname çıktıları ön planlama amaçlıdır; yetkili mimar/mühendis tarafından doğrulanmalı ve belediyeden resmî imar durum belgesi alınmalıdır.
- **Rakam gömülü değildir.** Beceriler emsal, kullanıcı yükü katsayısı, KDV oranı veya birim maliyet gibi değerleri içermez; her görevde asıl kaynaktan doğrulanması gerekir. Kaynağa erişilemezse sonuç "çözümlenmemiş" kalır.
- **Erişim.** Bazı resmî siteler (e-Devlet, Web Tapu, belediye e-İmar) kimlik doğrulama ister veya otomatik erişimi engeller; bu durumda beceriler sizin sağladığınız belgelerle çalışır.
- **Belediyeye özgü kurallar.** Her belediyenin imar yönetmeliği ve plan notları farklıdır; beceriler bunları ayrıca kontrol etmenizi ister.
- **İç belgeler.** `docs/`, `schema/` ve test dosyaları gibi iç yönetişim belgeleri İngilizce bırakılmıştır; bunlar Claude'un okuduğu teknik sözleşmelerdir ve kullanımı etkilemez.

## Veri, gizlilik ve telemetri

Arch Studio kendi Claude Code veya Codex oturumunuzda çalışır. Ofis ve proje kayıtlarınız yerel klasörlerinizde kalır; eklenti bunları hiçbir yere yüklemez. Araştırma becerileri, çalıştırdığınızda belgelerinde adı geçen kamu kaynaklarına bağlanır. Tapu ve kişisel verilerde KVKK ilkelerine uyulur ([Türkiye kuralı](rules/turkiye.md)).

**Telemetri (yalnızca Claude Code).** Orijinal projeden gelen version-check hook'u günde en fazla bir kez `version.alpa.llc` adresine istek gönderir: orijinal ALPA sürümünü kontrol eder ve anonim bir kullanım sinyali (rastgele kurulum kimliği ve sürüm) içerir. Bu çatalda "yeni sürüm" bildirimi orijinal projeye aittir; o sürüm Türkiye uyarlamasını içermez. Kapatmak için:

- Kullanım sinyalini kapatın: `AS_TELEMETRY_DISABLED=1`
- Güncelleme kontrolünü kapatın: `AS_UPDATE_CHECK_DISABLED=1`

English summary: The open-source plugin does not upload or store studio, project or module records on Arch Studio servers. Hosted record-holding modules use the separate boundaries in the [data-governance documentation](./docs/data-governance.md).

Ayrıntılar: [veri yönetişimi belgeleri](./docs/data-governance.md).

## Lisans

MIT. Bkz. [LICENSE](LICENSE). Orijinal eser: Copyright © 2026 Alpaca Labs, LLC. Orijinali Federico Negro oluşturdu ve [ALPA](https://alpa.llc) geliştirdi. Türkiye uyarlaması aynı MIT lisansıyla dağıtılır.
