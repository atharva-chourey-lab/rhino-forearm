# Sources Map — Paper 6: The Forearm Splits the Rhinos

Author: Atharva Chourey
Affiliation: Atharva Chourey Lab (independent research lab)

*Manuscript in preparation — not yet peer-reviewed.*

This file maps every key number, verdict and reference in `paper.md` to the source file it was taken from. Nothing in the paper was taken from a source outside this list. Where a source gives a verdict without a number, the paper reports the verdict without a number.

## Primary sources

- `~/workspace/rhino-pair-first-computation/PREREGISTRATION.md` — pre-registration, committed to git (commit 28159eb) on 2026-11-17 BEFORE any data download or measurement. Question, data, ≥5-of-6 inclusion rule, exact metric definitions, tests (10,000 permutations, seed 42), signal/null criteria, declared limits.
- `~/workspace/rhino-pair-first-computation/NOVELTY.md` — novelty scrub for the pair study, done before measurement. What Mallet 2019 computed per bone; later Gravibone work (2020, 2022); the unclaimed contrast. **One statement in this file is superseded by SWEEP.md**: its "no CS value is ever tabulated" is wrong at species-mean level (Mallet 2019 Table 8); see `SWEEP.md` correction.
- `~/workspace/rhino-pair-first-computation/RESULTS.md` — pair study results as landed. Download provenance (Europe PMC route, zip sizes and MD5s, 314 `.pts` files), sample after the registered rule, primary test, full secondary table, honest limits.
- `~/workspace/rhino-pair-first-computation/outputs/secondary_tests.csv` — pair secondary tests at full precision (per-bone profile means by species, differences, Mann–Whitney and permutation p-values, per-metric n).
- `~/workspace/rhino-pair-first-computation/outputs/profiles.csv`, `outputs/centroid_sizes.csv`, `outputs/results.json` — pair computation outputs.
- `~/workspace/goldmine-hunter/gold/morpho-ct/epmc-rhino5/compute_rhino5.py` — the five-species computation script (seed 42, 10,000 permutations). Published copy: `~/workspace/github-code-publish/goldmine-hunter/gold/morpho-ct/epmc-rhino5/compute_rhino5.py` (identical).
- `~/workspace/goldmine-hunter/gold/morpho-ct/epmc-rhino5/rhino5_results.json` — five-species results (specimen counts; all 10 pairwise distances and full-precision p-values). MD5 `87effb42c3db42d68e58607daa1157f4`; identical to the published copy in the goldmine-hunter repository staging.
- `~/workspace/goldmine-hunter/gold/morpho-ct/epmc-rhino5/centroid_sizes_all5.csv` (MD5 `18cdffe0d792034556500954289139c5`), `profiles_all5_ge5.csv` (MD5 `24d7b481b43f116889181777ee31db83`), `profiles_all5_complete6.csv` (MD5 `7485ae120f85069c5feb108f5b3fa8fe`), `pairwise_profile_tests.csv` (MD5 `67e82c130a22fd48828b754720ddb42d`) — five-species outputs: per-file centroid sizes, ≥5-bone profiles, complete-6 profiles, pairwise tests.
- `~/workspace/github-code-publish/goldmine-hunter/fidelity-morpho-report.md` — Goldmine Hunter fidelity campaign report, Morpho-CT leg (2026-11-17). Access-route verification, completeness table, forearm ordering on the ≥5-bone set, declared caveat that the five-species extension was not separately pre-registered.
- `~/workspace/github-code-publish/goldmine-hunter/FIDELITY_CAMPAIGN_2026-11-17.md` — campaign shortlist; rhino-5 ranking and the same pre-registration caveat.
- `~/workspace/papers/p6-rhino-forearm/SWEEP.md` — this paper's binding novelty sweep (2026-11-17): live-web verification of Mallet 2019/2020/2022 and Etienne 2020, the Table 8 correction, Guérin (1980)/Groves (1983) prior art, verdicts (a)–(e) with surviving wordings, and the reproduction record.

## Reproduction record

`compute_rhino5.py` was re-run end-to-end on 2026-11-17 (system Python 3.12.3; numpy 1.26.4, pandas 2.1.4, scipy 1.11.4) before this paper was written. All five output files were **byte-identical** to the pre-existing outputs (diffed against a pre-run backup); all 10 pairwise distances and full-precision p-values match `rhino5_results.json` exactly; forearm means, mean profiles, specimen counts and per-bone landmark counts all match; source zip MD5s match (Supp. 9 bundle `0cae2df77ef81f06ea9e5b68076fc30c`; Europe PMC full zip `f07575f66b1af99ea0c1123613c2edd6`). The 314-vs-308 file count is explained in §2.1 of the paper: 314 `.pts` files in Supplemental Information 9 minus 6 `LM_surface` template files = 308 specimen-bone files.

## Key numbers and their sources

| Claim in paper | Value | Source file |
|---|---|---|
| Mallet et al. sample as published | 62 dry skeletons; 37 complete; per-bone counts 53 humeri, 49 radii, 46 ulnae, 56 femora, 52 tibiae, 50 fibulae | rhino-pair NOVELTY.md (from Mallet 2019 full text); SWEEP.md §1 |
| Mallet Table 8 humerus CS means (example) | *C. simum* 723 ± 34; *D. sumatrensis* 626 ± 24; *D. bicornis* 660 ± 49; *R. sondaicus* 749 ± 39; *R. unicornis* 812 ± 26 | SWEEP.md §2 (live check of PMC6766374 full text) |
| Europe PMC full supplement zip | 51,043,042 bytes; MD5 `f07575f66b1af99ea0c1123613c2edd6` | rhino-pair RESULTS.md; MD5 re-verified 2026-11-17 |
| Supp. 9 bundle | 3,057,122 bytes; MD5 `0cae2df77ef81f06ea9e5b68076fc30c`; 314 `.pts` files | rhino-pair RESULTS.md; MD5 re-verified 2026-11-17 |
| Specimen-bone files parsed | 308 (314 − 6 `LM_surface` templates) | compute_rhino5.py (filename filter); reproduction record (SWEEP.md) |
| Landmark point counts per bone | Humerus 674, Femur 639, Radius 416, Tibia 408, Ulna 364, Fibula 281 (constant within bone) | rhino-pair RESULTS.md; centroid_sizes_all5.csv (reproduction: single unique count per bone) |
| Specimens per species (any bone) | *C. simum* 16, *D. sumatrensis* 14, *D. bicornis* 14, *R. unicornis* 11, *R. sondaicus* 8 | fidelity-morpho-report.md §2 table; centroid_sizes_all5.csv groupby (reproduction) |
| ≥5-bone specimens | 44 total: 12 / 9 / 9 / 7 / 7 (*simum / sumatrensis / unicornis / bicornis / sondaicus*) | rhino5_results.json (`ge5`); fidelity-morpho-report.md §2 |
| Complete-6 specimens | 38 total: 10 / 9 / 7 / 7 / 5 (*simum / sumatrensis / sondaicus / unicornis / bicornis*) | rhino5_results.json (`complete6`) |
| Pre-registered pair primary test | distance 0.0355 log₁₀; permutation p = 0.0001 (10,000 perms, seed 42); complete-6 n = 7 vs 10 | rhino-pair RESULTS.md; rhino5_results.json (pair row, p = 9.999e-05) |
| Registered signal criterion | primary p < 0.05 AND ≥ 1 profile/ratio difference ≥ 0.02 log₁₀ (≈ 4.7% CS) | rhino-pair PREREGISTRATION.md |
| Largest pair difference in pair study | radius Δ = −0.0293 log₁₀ | rhino-pair RESULTS.md; secondary_tests.csv (diff −0.029287) |
| All 10 pairwise distances + p-values (Table 1) | largest *D. bicornis* – *R. unicornis* 0.0566, p = 0.0014; smallest *C. simum* – *D. sumatrensis* 0.0223, p = 0.0092; max p = 0.0400 (*C. simum* – *D. bicornis*) | rhino5_results.json (`pairwise`); pairwise_profile_tests.csv; byte-identical on re-run |
| Bonferroni count | 8 of 10 survive at family-wise 0.05 (failures: p = 0.0400, p = 0.0092) | computed from rhino5_results.json p-values (this paper's count, stated as such) |
| Mean profiles, complete-6 (Table 2) | 5 × 6 table | profiles_all5_complete6.csv group means (reproduction record) |
| Pair secondary: humerus | *R. unicornis* +0.1233 vs *C. simum* +0.1185; Δ +0.0048; MWU p = 0.21 | secondary_tests.csv (0.123326 / 0.118510 / 0.004815 / 0.213621) |
| Pair secondary: femur | +0.1642 vs +0.1656; Δ −0.0015; MWU p = 0.21 | secondary_tests.csv (0.164160 / 0.165620 / −0.001461 / 0.213621) |
| Pair secondary: radius | −0.0170 vs +0.0123; Δ −0.0293; MWU p = 0.00014 | secondary_tests.csv (−0.016958 / 0.012329 / −0.029287 / 0.000143) |
| Pair secondary: ulna | −0.0731 vs −0.0456; Δ −0.0276; MWU p = 0.00020 | secondary_tests.csv (−0.073134 / −0.045578 / −0.027556 / 0.000197; per-metric n = 9 vs 11) |
| Pair secondary: fore − hind | Δ −0.0419 | secondary_tests.csv (−0.041854) |
| Pair secondary: stylopod − zeugopod, fore | Δ +0.0356 | secondary_tests.csv (0.035602) |
| Forearm (radius + ulna) profile, ≥5-bone set | *R. unicornis* −0.0450 (n=9); *R. sondaicus* −0.0258 (n=7); *D. sumatrensis* −0.0243 (n=9); *C. simum* −0.0143 (n=12); *D. bicornis* −0.0072 (n=7) | fidelity-morpho-report.md §2; recomputed from profiles_all5_ge5.csv (reproduction record) |
| Forearm spread, extremes | 0.0378 log₁₀ (≈ 9% relative CS: 10^0.0378 ≈ 1.091) | computed from the forearm values above (this paper's arithmetic, stated as such) |
| Humerus contrast, same-genus pair | *R. sondaicus* +0.1586 vs *R. unicornis* +0.1296 (complete-6 means) | profiles_all5_complete6.csv group means; fidelity-morpho-report.md §2 |
| Species body masses (context, §1) | *C. simum* ~2,300 kg; *D. sumatrensis* ~775 kg | fidelity-morpho-report.md §2 comparable-set list |
| Guérin/Groves length proportions | radius nearly always < 85% of humerus length in Asian forms; proximal segments primitively long in African forms; distal segments elongated in Asian forms | SWEEP.md §4 (Groves 1983 summary of Guérin 1980, RRC PDF) |
| Pre-registration commit | 28159eb, 2026-11-17, before download/measurement | rhino-pair RESULTS.md; PREREGISTRATION.md |
| Five-species extension registration status | NOT separately pre-registered; frozen pre-registered metric applied unchanged | fidelity-morpho-report.md §2 caveats; FIDELITY_CAMPAIGN_2026-11-17.md §1 |

## References and their sources

| Reference in paper | Source |
|---|---|
| Mallet, Cornette, Billet & Houssaye (2019), *PeerJ* 7:e7647, DOI 10.7717/peerj.7647; PMCID PMC6766374 | SWEEP.md §1 (publisher/PMC page, live) |
| Mallet, Billet, Houssaye & Cornette (2020), *J Anat* 237(4):704–726, DOI 10.1111/joa.13232 | SWEEP.md §3 |
| Mallet, Houssaye, Cornette & Billet (2022a), *Zool J Linn Soc* 196(3):1201–1234, DOI 10.1093/zoolinnean/zlab095 | SWEEP.md §3 |
| Mallet, Billet, Cornette & Houssaye (2022b), *Zool J Linn Soc* 196(3):1235–1271, DOI 10.1093/zoolinnean/zlac007 | SWEEP.md §3 |
| Etienne, Mallet, Cornette & Houssaye (2020), *Biol J Linn Soc* 129(4):950–974, DOI 10.1093/biolinnean/blaa005 | SWEEP.md §3 |
| Groves (1983), "Phylogeny of the living species of Rhinoceros" | SWEEP.md §4 (RRC PDF). Journal/pages not present in source files; omitted in the paper rather than supplied. |
| Guérin (1980) | Known only as summarised in Groves (1983); cited in the paper in exactly that form, full details flagged as not in the lab's source files. |

## Novelty claims — SWEEP-ADOPTED

Novelty wording in the paper follows `SWEEP.md` verdicts (a)–(e) verbatim in scope: claim (a) HOLD as stated; claims (b), (c), (d) in their narrowed wordings only (every "first" carries *within-specimen, centred, centroid-size*); claim (e) scoped to the Supplemental Information 9 landmark files. Killed wording — "first CS comparison", unqualified "first size-allocation comparison", forearm differentiation as new, and any extension of open-availability to the MorphoSource scans — appears nowhere in `paper.md`.
