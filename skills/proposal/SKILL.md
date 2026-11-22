---
name: proposal
description: "Proje tekliflerini hazırlar ve kaydeder (Mimarlar Odası en az bedel esasları, yapı sınıfı ve Yapı Yaklaşık Birim Maliyetleri dikkate alınarak), verilmiş koşulları korur ve açıkça belgelenen ticari değişiklikleri kaydeder. Mesaj göndermek ayrı yetki gerektirir."
allowed-tools:
  - Read
  - Write
  - Edit
  - Glob
  - Grep
  - Bash
  - AskUserQuestion
---

# /as:proposal

Before acting, read the [host contract](../../docs/host-harness-contract.md), this component's [declaration](host-contract.json) (`skill:proposal`), and applicable [workspace semantics](../../docs/workspace-model.md). Load only the required modes from the [shared catalog](../../corpus/host-contracts.json).

<!-- architecture-studio:harness-compatibility -->
Use the [host adapter](../../docs/host-adapters.md) and available native tools or ordinary task-specific code. Operation names identify the semantic work in the [workspace model](../../docs/workspace-model.md), not installed functions or a script API. Resolve canonical context before durable work. No Arch Studio runner, package installation or executable reconstruction is required. Existing exact authorization persists; ask only for material missing information or missing permission.

Own documents of kind `proposal`. Resolve the project; never create a global proposal register. Use the [proposal template](templates/proposal.md), keeping exactly one nonempty `issued-terms` marker block. Capture normal-case title, date, explicit local revision, scope/fees/exclusions and user-selected terms. Unknowns remain TO CONFIRM; their presence is context, not an invented workflow gate. Use human `Rev. NN` and a safe received/authored filename; confirmed lineage uses `supersedes`.

## Before changing records

Before persistent changes, follow the [native mutation sequence](../../docs/workspace-model.md#native-mutation-sequence): **Inspect → Prepare → Verify preparation → Apply → Verify result → Complete**. Inspect pending work first. Finish and verify preparation before the first canonical write: separately reread every saved original and prepared file, check its complete actual bytes, establish durable saving, and inspect actual permissions, ownership and ACLs. Merely writing recovery files does not finish verification. Apply only that verified set. Mark complete only after fresh readback validates the entire affected result and its relationships. Read-only requests and inline drafts need no publication sequence.

For proposal creation, prepare the complete proposal and DOCUMENTS.csv together, including destination absence. Lifecycle changes affect DOCUMENTS.csv; the proposal's actual raw bytes and issued-terms seal are read guards. Additional rendered outputs are separate registered documents with their own complete affected set. Do not publish a proposal first and prepare its register afterward.

The harness prepares the terms from authorized inputs and current applicable originals, then `proposal.create` registers the authored source under confirmed coordinates. Do not copy external clause libraries or portray local summaries as current legal authority. Assembled terms include: “These clauses are drafting guidance, not legal advice; have a licensed attorney review before signing.”

`proposal.list/status/verify` read the actual registered record and protected terms. `proposal.send` only records supplied send date/evidence and seals the exact issued terms; it never emails or uploads. `proposal.set-status` records accepted/declined/superseded with explicit evidence/date. Acceptance may seal a draft directly when an earlier send was not recorded; no mandatory proposal→agreement→invoice sequence is imposed. Never infer acceptance, payment or project status from activity.

Once sealed, changed terms require a new registered revision, not replacement of the stored checksum. Lifecycle evidence stays in registry history outside the issued block. Preserve malformed input and checksum failures without guessing repair. HTML letters may use a confirmed firm template or bundled proposal-letter template, but the registered Markdown terms remain canonical; register additional outputs as documents.

Agreement promotion cites the accepted proposal ID and protected checksum without copying it. Tasks/time/invoices and project facts retain their owners. Fresh readback and actual inspection support completion; a recorded send event does not prove that any message was actually sent.

## Türkiye

Türkiye'de teklif hazırlarken hizmet kapsamını Mimarlar Odası **Mimarlık Hizmetleri Şartnamesi** aşamalarına göre tanımla (ön proje, avan proje, uygulama projesi, detay, şantiye denetimi vb.; `source:tr-mimarlar-odasi`). Ücret, kullanıcı isterse en az bedel esasına göre hesaplanabilir: yapı sınıfı/grubu ve ilgili yılın **Yapı Yaklaşık Birim Maliyetleri Tebliği** (`source:tr-yapi-yaklasik-birim-maliyetleri`) kullanılır; hangi yılın tebliğini kullandığını yaz, katsayıları her seferinde güncel kaynaktan doğrula. Tutarları TL ve KDV hariç/dahil belirterek ver. Kamu işlerinde 4734 sayılı Kanun ve EKAP süreçleri ayrıdır.

Kullanıcı Türkçe yazıyorsa veya proje/arsa Türkiye'deyse [Türkiye kuralını](../../rules/turkiye.md) uygula: yanıtlar ve raporlar Türkçe, metrik birimler, Türk sayı biçimi (1.234,56), GG.AA.YYYY tarih biçimi; tutarlar TL ve KDV hariç/dahil belirtilerek. Kişisel verilerde KVKK'ya uy.
