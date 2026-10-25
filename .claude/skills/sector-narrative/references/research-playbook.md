# Research playbook

## Search discipline

- Use WebSearch `standard` for routine checks. Use `extended` for the week's or month's broad sector sweeps and anything less than about 10 days old.
- Put a date in queries ("October 2026", "this week") to avoid stale results.
- Every fact you keep needs an outlet and a date.
  - Aggregator, blog or vendor figures get "(secondary)" until a primary source confirms them.
  - Conflicting figures: report the range and name the sources.
- Wikipedia may be unreachable via WebFetch. Search results that summarise it are acceptable as secondary.

## Sweeps

Run each sweep every time.

1. **Broad sector sweeps** (catch what the ledger doesn't know):
   - "semiconductor industry news {period}"
   - "AI data center infrastructure news {period}"
   - "oil gas LNG energy markets news {period}"
   - "power utilities electricity grid news {period}"
   - "nuclear energy news {period}"
2. **Policy sweeps:**
   - "White House executive order {period} energy OR semiconductors OR AI"
   - "Commerce BIS export controls {period}"
   - "Section 232 tariff proclamation {period}"
   - "OFAC sanctions oil {period}"
   - "FERC order {period} large load OR data center"
   - "NRC approval {period}"
   - "Federal Reserve {period} decision OR minutes OR speech"
   - "state legislature data center {period}"
   - "China MOFCOM export control {period}"
3. **Story signposts:** for each Active/Escalating story, one search built from its Confirm/Break signposts.
4. **Catalyst calendar:** results of every event dated within the window.
5. **Predictions due:** one targeted search per prediction whose check-by date falls in the window.
6. **Deals and capital markets.** Big M&A, IPOs and mega-financings reshape sectors, and thematic searches miss them. The baseline missed NextEra–Dominion and the SpaceX IPO this way.
   - "largest acquisitions {sector} {period}" for semiconductors, AI, utilities/power and oil & gas
   - "biggest IPO {period}"
   - "{sector} merger announced {period}"
   - "private credit data center financing {period}"
   - Then check the status of every deal already in the ledger (votes, regulatory orders, closings).

## Primary sources (prefer these)

| Area | Sources |
|---|---|
| Executive actions | whitehouse.gov/presidential-actions, federalregister.gov |
| Trade | USTR, CBP CSMS messages, Commerce/ITA, Court of International Trade, CAFC |
| Export controls | BIS (bis.gov) rules and press releases |
| Sanctions | Treasury OFAC recent actions |
| Monetary | federalreserve.gov (statements, minutes, SEP), BLS CPI/PPI, BEA PCE |
| Energy data | EIA (STEO, weekly petroleum status), IEA Oil Market Report, OPEC MOMR |
| Power | FERC, PJM/ERCOT/MISO releases, state PUCs |
| Nuclear | NRC, DOE Office of Nuclear Energy |
| Companies | SEC EDGAR (8-K, 10-Q, 10-K), company IR earnings releases and transcripts |
| China | MOFCOM announcements (via reputable wires) |

## Company universe (starting set; extend as stories require)

**Semis — compute and design:**
- Nvidia (NVDA), AMD, Broadcom (AVGO), Marvell (MRVL), Intel (INTC), Qualcomm (QCOM), Arm (ARM)
- Alchip (3661.TW), GUC (3443.TW)

**Semis — foundry and memory:**
- TSMC (TSM), Samsung (005930.KS), GlobalFoundries (GFS)
- Micron (MU), SK Hynix (000660.KS), SanDisk (SNDK), Western Digital (WDC), Seagate (STX)

**Semis — equipment and materials:**
- ASML, Applied Materials (AMAT), Lam Research (LRCX), KLA (KLAC), Tokyo Electron (8035.T)
- Linde (LIN), Air Products (APD), Entegris (ENTG), MP Materials (MP)

**Networking and optics:** Arista (ANET), Coherent (COHR), Lumentum (LITE), Credo (CRDO), Ciena (CIEN)

**AI platforms and clouds:**
- Microsoft (MSFT), Alphabet (GOOGL), Amazon (AMZN), Meta (META), Oracle (ORCL)
- CoreWeave (CRWV), Nebius (NBIS), IREN
- Private: OpenAI, Anthropic, xAI/SpaceX

**Data-center physical layer:**
- Vertiv (VRT), Eaton (ETN), Schneider (SU.PA), Quanta (PWR), Hubbell (HUBB)
- Equinix (EQIX), Digital Realty (DLR), Super Micro (SMCI), Dell (DELL)

**Power generation and equipment:**
- GE Vernova (GEV), Siemens Energy (ENR.DE), Mitsubishi Heavy (7011.T), Caterpillar (CAT), Cummins (CMI), Bloom Energy (BE)
- Constellation (CEG), Vistra (VST), Talen (TLN), NRG
- Dominion (D), AEP, Entergy (ETR), Southern (SO), NextEra (NEE)

**Nuclear and fuel:** Cameco (CCJ), Centrus (LEU), BWX Technologies (BWXT), Oklo (OKLO), NuScale (SMR), NANO Nuclear (NNE)

**Oil, gas and LNG:**
- Majors: Exxon (XOM), Chevron (CVX)
- Shale: ConocoPhillips (COP), EOG, Diamondback (FANG), Devon (DVN), Occidental (OXY)
- Gas: EQT, Expand Energy (EXE), Antero (AR)
- LNG: Cheniere (LNG), Venture Global (VG), NextDecade (NEXT)
- Refiners: Valero (VLO), Marathon Petroleum (MPC), Phillips 66 (PSX), PBF, HF Sinclair (DINO)
- Services: SLB, Halliburton (HAL), Baker Hughes (BKR)
- Pipelines: Williams (WMB), Kinder Morgan (KMI)
- Tankers: Frontline (FRO), Scorpio Tankers (STNG)

**Renewables and storage:** First Solar (FSLR), Enphase (ENPH), Sunrun (RUN), Fluence (FLNC), Tesla (TSLA), Ørsted (ORSTED.CO)

**Software exposed to AI disruption:** Salesforce (CRM), ServiceNow (NOW), Intuit (INTU), Adobe (ADBE), Thomson Reuters (TRI)

Verify a ticker before first use in a report if it hasn't appeared before; companies get renamed and merged.
