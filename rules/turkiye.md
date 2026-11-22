# Türkiye

This rule adapts Arch Studio outputs to architectural practice in Türkiye. It applies whenever the user writes in Turkish, the studio or project is registered in Türkiye, or the selected site resolves to `jurisdiction:tr` (or a province such as `jurisdiction:tr-34`). It never resolves a site by itself: a Turkish-speaking user may still ask about a site abroad, and a site's jurisdiction still needs evidence per [geographic applicability](../docs/geographic-applicability.md).

## Language

- Respond and write reports in **Turkish** when the user writes in Turkish, unless they ask for another language. Keep official names exactly as published (e.g. "Planlı Alanlar İmar Yönetmeliği", "Türkiye Bina Deprem Yönetmeliği").
- Use Turkish professional terms: *imar durumu, emsal (KAKS), TAKS, Hmax, çekme mesafesi, ada/parsel, tapu, ruhsat, iskân (yapı kullanma izin belgesi), yapı denetim, proje müellifi, şantiye şefi, avan proje, uygulama projesi, metraj, keşif, hakediş, birim fiyat, mahal listesi, teknik şartname*.
- When a skill's source material is US-specific (IBC, CSI MasterFormat, AIA, ADA), name the Turkish counterpart where one exists and say when none is equivalent. Do not present a US value as a Turkish rule.

## Units and formats

- Metric only: m, cm, mm, m², m³; kN, kg. Area types: *brüt alan, net alan, emsal alanı, emsal harici alan, satılabilir alan*. Do not convert to imperial unless asked.
- Numbers: Turkish format — thousands with dot, decimals with comma (`1.234,56`). In CSV/JSON data files keep machine format (`1234.56`) and state it.
- Dates: `GG.AA.YYYY` in prose; ISO `YYYY-MM-DD` in data files.
- Currency: Turkish lira, written `₺` or `TL` (e.g. `125.000,00 TL`). State whether amounts are **KDV hariç** or **KDV dahil**, and the rate actually verified for the task date; never assume a VAT rate from memory.

## Regulatory sources

Primary navigation entries are the `jurisdiction:tr` records in [the source catalog](../corpus/sources/catalog.json): Mevzuat Bilgi Sistemi, Resmî Gazete, TKGM, e-Plan, e-Devlet, AFAD, MTA, Koruma Bölge Kurulları, TÜİK, MGM, Mimarlar Odası, TSE, GİB, EKAP and İBB Açık Veri. Hierarchy reminder for zoning work: municipal *imar durum belgesi* and approved plan notes → local imar yönetmeliği → Planlı Alanlar İmar Yönetmeliği → 3194 sayılı İmar Kanunu. Always verify the consolidated current text and amendment dates for the analysis date; yearly instruments (Yapı Yaklaşık Birim Maliyetleri, Mimarlar Odası en az bedel) must cite the year used.

## Personal data (KVKK)

Tapu records, TC kimlik numbers, owner names and similar personal data are protected under 6698 sayılı KVKK. Use only what the user supplies, include it in outputs only when needed and requested, and never collect it from third-party sites.

## Disclaimer

Regulatory output in Turkish uses the Turkish canonical block from [professional-disclaimer](professional-disclaimer.md).
