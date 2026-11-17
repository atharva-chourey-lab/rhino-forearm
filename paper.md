# The Forearm Splits the Rhinos: Within-Specimen Centroid-Size Profiles of the Six Long Bones Separate All Five Living Rhinoceros Species

Author: Atharva Chourey
Affiliation: Atharva Chourey Lab (independent research lab)

*Manuscript in preparation — not yet peer-reviewed.*

## Abstract

Mallet et al. (2019) published landmark configurations for the six limb long bones — humerus, radius, ulna, femur, tibia, fibula — of the five living rhinoceros species, and analysed the shape of each bone separately. Centroid size (CS) entered that work only as a per-bone covariate for shape, and although species-mean CS was tabulated, no comparison of relative bone size within a specimen was ever made. This paper makes that comparison. We form each specimen's within-specimen centroid-size profile — log₁₀ CS of each bone centred on that specimen's own mean log₁₀ CS across its bones — from the openly released landmark files (308 specimen-bone files; 38 specimens with all six bones). The profile metric and permutation test were pre-registered for a two-species study before any measurement; that study's primary result is reproduced here (*Ceratotherium simum* vs *Rhinoceros unicornis*: profile distance 0.0355 log₁₀ units, permutation p = 0.0001). Extending the frozen metric to all five species, all 10 pairwise mean-profile distances are significant (10,000 permutations; p ≤ 0.040, uncorrected; 8 of 10 survive Bonferroni correction), the largest between *Diceros bicornis* and *R. unicornis* (0.0566, p = 0.0014). The separation is carried by relative size, not absolute size: in the pre-registered pair the stylopods sit at identical relative sizes and the difference lies in the forelimb zeugopod, and across the five species the forearm (radius + ulna) profile runs from −0.0450 in *R. unicornis* to −0.0072 in *D. bicornis* — the two forearm extremes are the most separated pair.

*Keywords:* Rhinocerotidae; centroid size; geometric morphometrics; Gravibone; limb proportions; size allocation; pre-registration

## 1. Introduction: The Comparison Inside the Specimen That Was Never Made

The five living rhinoceros species are the surviving sample of a once-diverse superfamily, and their limb skeletons carry the signature of graviportal locomotion at body masses from roughly 775 kg (*Dicerorhinus sumatrensis*) to roughly 2,300 kg (*Ceratotherium simum*). The reference dataset for their limb morphology is the Gravibone sample analysed by Mallet, Cornette, Billet and Houssaye (2019): 62 dry skeletons spanning all five species, surface-scanned under one protocol, with three-dimensional landmark configurations for the six long bones — humerus, radius, ulna, femur, tibia and fibula — released openly as the paper's Supplemental Information 9.

What Mallet et al. (2019) computed from those configurations was, bone by bone, *shape*. For each of the six bones separately they ran generalised Procrustes analysis and principal components of shape, published species mean shapes, built neighbour-joining trees on the shape scores, and tested allometry as the correlation of shape with log centroid size and with species mean body mass. Centroid size — the standard scalar size of a landmark configuration — appears in that work in exactly two roles: as a covariate against which shape is regressed, and as a species-level summary, tabulated as mean ± standard deviation per bone per species (their Table 8). The Discussion compares those absolute sizes across species, noting for instance that *R. unicornis* carries the highest centroid sizes except at the radius and ulna, where it resembles *C. simum*.

What was never computed is the comparison *inside* the animal. A centroid-size table organised by bone and species cannot say how one specimen allocates size across its own limb: whether its forearm bones are large or small *for that animal*, relative to its own upper arm and hindlimb. Recovering that requires centring each bone's size on the same specimen's mean — a within-specimen profile — and per-specimen centroid sizes were never tabulated, so the profile cannot be reconstructed from anything in print. It has to be recomputed from the released landmark files. Later work from the same programme did not compute it either: Mallet et al. (2020) quantified cross-bone *shape* integration and covariation among the six bones; Mallet et al. (2022a, 2022b) extended per-bone shape analysis to 69 rhinocerotoid taxa against size and mass; Etienne et al. (2020) treated the tarsals. Cross-bone size allocation, as a scalar quantity, remained unmeasured.

One older literature did compare limb proportions across the five species, and it must be credited precisely. Guérin (1980), as summarised by Groves (1983), discussed long-bone *length* proportions, reporting that the proximal segments remain primitively long in the African species while in the Asian forms the radius is nearly always under 85% of the humerus length, with distal segments elongated. That is a length comparison, from calliper-era data, not a centroid-size comparison; it is not centred within specimens and was not tested as a profile. The claim of this paper is correspondingly scoped, and we state it in its surviving form: this is the first within-specimen, centroid-size-based relative-size (allocation) comparison — log₁₀ CS of each long bone centred on that specimen's mean log₁₀ CS across its bones — across all five living rhino species, and the first within-specimen centroid-size profile analysis of the Gravibone data. Forearm differentiation between rhino species, in size or in shape, is not claimed as new; what is new is where the forearm sits inside a centred size profile, and that the profile itself separates the species.

The analysis proceeds in the order it was actually done. A two-species study — *R. unicornis* against *C. simum*, the two largest species on two continents — was pre-registered on 2026-11-17, before any data were downloaded or measured, with the profile metric, an inclusion rule, and a permutation test fixed in advance, on the basis of a novelty scrub of the Mallet programme. Its primary test returned a clear signal, localised to the forearm. The present paper extends the identical, frozen metric to all five species. That extension was not itself separately pre-registered, and we flag its status wherever it matters: the metric and the pair test are pre-registered and confirmatory; the five-species pairwise tests are tests under that pre-registered metric, reported with their post-hoc extension status declared, not silently upgraded.

Section 2 describes the data and the profile construction. Section 3 reports the reproduced pair result, the five-species pairwise tests, the mean profiles, and the forearm decomposition. Section 4 discusses what a centred profile adds beyond the published size table, its relation to the length-proportion and shape-integration literatures, and the analysis's limits.

## 2. Methods

### 2.1 Data: Mallet et al. 2019, Supplemental Information 9

The data are the raw landmark coordinate files released as Supplemental Information 9 of Mallet et al. (2019, *PeerJ* 7:e7647; article and supplements CC-BY; supplement DOI 10.7717/peerj.7647/supp-9). The files were obtained barrier-free through the Europe PMC supplementary-files route for article PMC6766374 — the full supplement zip (51,043,042 bytes, MD5 `f07575f66b1af99ea0c1123613c2edd6`) and within it the Supplemental Information 9 bundle (3,057,122 bytes, MD5 `0cae2df77ef81f06ea9e5b68076fc30c`). No MorphoSource account was created or needed; the Gravibone surface scans themselves were not used — this computation runs entirely on the released landmark coordinates. The dataset was located and flagged for exactly this kind of re-use by Goldmine Hunter, the lab's stranded-data prospecting tool, which scans project and publisher surfaces for published-but-unintegrated data deposits; the Europe PMC supplement route is what the tool's fidelity campaign verified and used.

Supplemental Information 9 contains 314 `.pts` files. Six of them are `LM_surface` template files (one per bone, for a single *C. simum* specimen), not specimen configurations; excluding them leaves **308 specimen-bone files**, every one of which parsed with its header landmark count asserted in code. The six bones are humerus, radius, ulna (forelimb) and femur, tibia, fibula (hindlimb). Landmark configurations are identical within each bone across all species and specimens — verified point counts: humerus 674, femur 639, radius 416, tibia 408, ulna 364, fibula 281 — comprising the anatomical and curve landmarks together with the sliding surface semi-landmarks as released. Mirrored (`miroir`) files were included as separate specimens' bones where so named; reflection does not change centroid size. Specimen and species identities come from the file names, which follow the convention of Mallet et al.'s specimen list.

Specimens represented in the parsed files, by species: *Ceratotherium simum* 16, *Dicerorhinus sumatrensis* 14, *Diceros bicornis* 14, *Rhinoceros unicornis* 11, *Rhinoceros sondaicus* 8. (Mallet et al. describe their sample as 62 dry skeletons, 37 of them complete; counts here are as parsed from the released files and are the denominators for everything that follows.)

### 2.2 Centroid size and the within-specimen profile

For a landmark configuration of $n$ points $x_k$ in three dimensions, centroid size is

$$\mathrm{CS} = \sqrt{\sum_k \| x_k - \bar{x} \|^2},$$

computed here directly from each `.pts` file's coordinates, in the units as digitised. For specimen $i$ and bone $b$, the profile value is

$$P(i,b) = \log_{10} \mathrm{CS}(i,b) \;-\; \frac{1}{|B_i|} \sum_{b' \in B_i} \log_{10} \mathrm{CS}(i,b'),$$

where $B_i$ is the set of bones available for that specimen. The profile is therefore each bone's size relative to the same animal's own mean long-bone size: a pure allocation quantity, from which the specimen's overall size has been removed by construction. A profile difference of 0.02 log₁₀ units corresponds to a factor of about 1.047 — roughly a 4.7% difference in relative centroid size.

Because the landmark configuration is identical within each bone, CS values are comparable across specimens and species *within* a bone, and the profile is internally consistent. Absolute CS values are used only through the centred profile; they are not compared against Mallet et al.'s Table 8 values in any test, and no cross-study absolute-size claim is made.

### 2.3 Inclusion rules

The inclusion rule is the pre-registered one, unchanged: a specimen enters the profile analysis only if it has at least 5 of the 6 bones present. That rule yields 44 specimens (*C. simum* 12, *D. sumatrensis* 9, *R. unicornis* 9, *D. bicornis* 7, *R. sondaicus* 7). The primary pairwise tests use the stricter complete-6 set — specimens with all six bones, so that every profile is centred on the same six-bone mean — yielding 38 specimens (*C. simum* 10, *D. sumatrensis* 9, *R. sondaicus* 7, *R. unicornis* 7, *D. bicornis* 5). The *D. bicornis* complete-6 cell, n = 5, is the weakest in the design and is declared as such wherever its pairs are discussed. The forearm summary of §3.4 uses the ≥5-bone set, matching the pair study's registered profile set.

### 2.4 Tests

For each pair of species, the test statistic is the Euclidean distance between the species' mean profile vectors over the six bones, computed on complete-6 specimens. Significance is by permutation of species labels: 10,000 permutations, seed 42, two-sided, with $p = (\text{count} + 1)/(\text{permutations} + 1)$, so the minimum reportable value is approximately 0.0001. This is the pair study's pre-registered primary test, applied unchanged to all 10 pairs. Pairwise p-values are reported **uncorrected**; because 10 tests are run, we also report how many survive Bonferroni correction at family-wise 0.05 (per-test α = 0.005). The forearm summary is descriptive: for each specimen in the ≥5-bone set, the mean of its radius and ulna profile values (the available value alone, for the rare specimen missing one of the two), averaged by species.

For the pre-registered pair alone, the registration also fixed secondary, exploratory analyses — per-bone Mann–Whitney U tests and permutation tests on individual profile values and on fore:hind and stylopod:zeugopod ratios — explicitly labelled exploratory and uncorrected in the registration. Those pair-level secondary values are reported in §3.4 as registered, and no equivalent per-bone testing was added for the other pairs, to avoid manufacturing confirmatory language around an unregistered extension.

### 2.5 Pre-registration status

The novelty scrub, metric, inclusion rule, tests and signal/null criteria for the two-species study were committed to version control on 2026-11-17 (commit 28159eb) **before** any data download or measurement. The registered signal criterion was: primary permutation p < 0.05 **and** at least one profile value or ratio differing by ≥ 0.02 log₁₀ units between species means; the registered null — "size allocation is conserved between the pair" — would have been reported as-is had it occurred. The five-species extension applies the metric, inclusion rule and test exactly as registered, but the extension itself was not separately pre-registered. We regard the pair result as confirmatory and the five-species results as strong tests under a frozen, pre-registered metric whose family-wise status is declared in §2.4 and §4.4 — not as a pre-registered five-species hypothesis.

## 3. Results

### 3.1 The pre-registered pair, reproduced

Inside the five-species run, the pre-registered primary test reproduces exactly. On complete-6 specimens (*C. simum* n = 10, *R. unicornis* n = 7), the mean-profile distance between the white rhinoceros and the greater one-horned rhinoceros is **0.0355 log₁₀ units, permutation p = 0.0001** — the minimum reportable value at 10,000 permutations. Both registered signal criteria were met several times over in the original study (largest single profile difference 0.0293 log₁₀ units, at the radius). The two species allocate long-bone size differently. That was the confirmatory result; everything in §3.2 is its extension.

### 3.2 All five species: every pair separates

Table 1 gives all 10 pairwise tests on complete-6 specimens.

**Table 1. Pairwise mean-profile distances (log₁₀ units) and permutation p-values, complete-6 specimens, 10,000 permutations, seed 42, uncorrected.**

| Pair | n₁ / n₂ | Distance | p |
|---|---|---|---|
| *Diceros bicornis* – *Rhinoceros unicornis* | 5 / 7 | **0.0566** | 0.0014 |
| *Diceros bicornis* – *Rhinoceros sondaicus* | 5 / 7 | 0.0556 | 0.0017 |
| *Ceratotherium simum* – *Rhinoceros sondaicus* | 10 / 7 | 0.0469 | 0.0002 |
| *Rhinoceros sondaicus* – *Rhinoceros unicornis* | 7 / 7 | 0.0458 | 0.0011 |
| *Dicerorhinus sumatrensis* – *Diceros bicornis* | 9 / 5 | 0.0376 | 0.0009 |
| *Ceratotherium simum* – *Rhinoceros unicornis* | 10 / 7 | 0.0355 | 0.0001 |
| *Dicerorhinus sumatrensis* – *Rhinoceros sondaicus* | 9 / 7 | 0.0276 | 0.0002 |
| *Dicerorhinus sumatrensis* – *Rhinoceros unicornis* | 9 / 7 | 0.0263 | 0.0002 |
| *Ceratotherium simum* – *Diceros bicornis* | 10 / 5 | 0.0232 | 0.0400 |
| *Ceratotherium simum* – *Dicerorhinus sumatrensis* | 10 / 9 | 0.0223 | 0.0092 |

In the surviving, scoped wording: **all 10 pairwise species comparisons differ significantly in mean within-specimen centroid-size profile (permutation test on centred log₁₀ CS profile distances)**, at uncorrected p ≤ 0.040. Eight of the ten survive Bonferroni correction at family-wise 0.05; the two that do not are *C. simum* – *D. bicornis* (p = 0.040) and *C. simum* – *D. sumatrensis* (p = 0.0092), both involving the smallest distances in the table (0.0232 and 0.0223).

Three features of the table carry the interpretation. First, the largest separation in the family is a pair nobody had computed in any form: *D. bicornis* against *R. unicornis*, 0.0566 log₁₀ units — the black rhinoceros and the greater one-horned rhinoceros are the two extremes of size allocation among living rhinos. Second, the two *Rhinoceros* species separate strongly from each other (0.0458, p = 0.0011): same genus, same continent, different habitat and mass — the profile is not a genus label. Third, the pre-registered pair (0.0355) sits mid-table: the original signal was not the family's outlier but a typical member of it.

### 3.3 Mean profiles

**Table 2. Mean within-specimen CS profiles (log₁₀, centred per specimen), complete-6 specimens.**

| Species | Humerus | Radius | Ulna | Femur | Tibia | Fibula |
|---|---|---|---|---|---|---|
| *Ceratotherium simum* | +0.1190 | +0.0127 | −0.0457 | +0.1681 | −0.0298 | −0.2243 |
| *Dicerorhinus sumatrensis* | +0.1353 | +0.0053 | −0.0538 | +0.1723 | −0.0259 | −0.2332 |
| *Diceros bicornis* | +0.1180 | +0.0257 | −0.0361 | +0.1531 | −0.0293 | −0.2315 |
| *Rhinoceros sondaicus* | +0.1586 | +0.0017 | −0.0533 | +0.1724 | −0.0347 | −0.2447 |
| *Rhinoceros unicornis* | +0.1296 | −0.0085 | −0.0651 | +0.1811 | −0.0185 | −0.2187 |

The shared architecture is visible in every row: femur and humerus sit well above the specimen mean, the fibula far below it, and the species differ in the middle of the profile — the zeugopod bones and the humerus — rather than in the gross pattern. *R. sondaicus* has the most top-heavy profile (humerus +0.1586, the highest of any species, with the lowest fibula, −0.2447); *D. bicornis* has the flattest stylopod end (femur +0.1531, the lowest) and the heaviest forearm, to which we now turn.

### 3.4 The forearm carries the split

In the pre-registered pair, the localisation was exact. The stylopods sat at identical relative sizes (humerus profile +0.1233 vs +0.1185, Δ = +0.0048, Mann–Whitney p = 0.21; femur +0.1642 vs +0.1656, Δ = −0.0015, p = 0.21), and the entire registered difference lived in the forelimb zeugopod: radius profile −0.0170 in *R. unicornis* against +0.0123 in *C. simum* (Δ = −0.0293, p = 0.00014) and ulna −0.0731 against −0.0456 (Δ = −0.0276, p = 0.00020), with the fore:hind balance differing by −0.0419 and the fore stylopod:zeugopod ratio by +0.0356. Same upper arms; different forearms. (Pair secondary values are on the registered ≥5-bone profile set, exploratory and uncorrected per the registration; the hind stylopod:zeugopod ratio and the tibia and fibula profiles did not differ.)

Across all five species, the forearm summary (mean of radius and ulna profile values, ≥5-bone set) orders the family:

| Species | n (≥5 bones) | Forearm (radius + ulna) profile |
|---|---|---|
| *Rhinoceros unicornis* | 9 | −0.0450 |
| *Rhinoceros sondaicus* | 7 | −0.0258 |
| *Dicerorhinus sumatrensis* | 9 | −0.0243 |
| *Ceratotherium simum* | 12 | −0.0143 |
| *Diceros bicornis* | 7 | −0.0072 |

*R. unicornis* is the distal-light extreme — its forearm bones are the smallest, relative to its own limb, of any living rhino — and *D. bicornis* is the distal-heavy extreme. The spread between them is 0.0378 log₁₀ units (≈ 9% in relative CS terms), and the two forearm extremes are precisely the pair with the largest overall profile distance in Table 1. In the scoped wording of the novelty sweep: in a within-specimen centred log-centroid-size profile, the forelimb zeugopod (radius + ulna relative CS) is the principal contributor to species separation in relative bone size.

One honest exception keeps the headline from over-running the data. The strong *R. sondaicus* – *R. unicornis* separation (0.0458) is driven largely by the humerus, not the forearm: *R. sondaicus*'s humerus profile (+0.1586) is the family's highest, against +0.1296 in *R. unicornis*, while their forearm summaries are the family's two lowest and closest in spirit (−0.0258 vs −0.0450). The forearm is the principal axis of separation across the family and the whole story of the pre-registered pair; it is not the mechanism of every pair, and the humerus carries the same-genus contrast.

## 4. Discussion

### 4.1 What a centred profile adds

Mallet et al.'s Table 8 already established that the species differ in absolute bone size — unsurprising, in animals spanning a threefold mass range, and dominated by overall size. The centred profile asks a different question of the same numbers: given the animal's own size, where is the bone size placed? That quantity is not a re-presentation of Table 8. It cannot be computed from species means at all, because the specimens contributing to one bone's mean are not the specimens contributing to another's, and centring is defined per animal. The result — that all five species differ in allocation, that the extremes are *D. bicornis* and *R. unicornis*, and that the forearm is the principal axis — is therefore a genuinely additional fact about the Gravibone sample, obtained from data that have been openly downloadable since 2019 without the quantity ever being extracted. This is the pattern the lab's prospecting tool exists to find: the deposit was never hidden; the comparison was simply never run.

### 4.2 Relation to the length-proportion literature

Guérin (1980, via Groves 1983) reported the radius at under 85% of humerus length in the Asian species, against primitively long proximal segments in the African species. Our forearm result is directionally consonant for *R. unicornis* — the Asian extreme of a distal-light forearm — but the two measurements are not the same quantity: length ratios from external measurements against a three-dimensional centroid-size profile centred within specimens, and *D. bicornis* (African) as our distal-heavy extreme does not map onto a simple continental reading of the older claim. We cite the older work as what it is — the prior art on cross-species limb proportions — and claim only the CS-profile quantity as new.

### 4.3 Relation to the shape programme

Nothing here revises Mallet et al.'s shape results, and the profile should be read alongside them, not against them. The 2020 integration study found the appendicular skeleton strongly integrated in shape, with radius–ulna shape covariation particularly associated with body mass; the 2022 forelimb study found radius and ulna *shape* linked more strongly to body-mass repartition than to absolute mass. That the same bone pair carries the scalar size-allocation signal is a convergence worth noting: the forearm is where these animals' limbs differ, in shape covariation and now in relative size. A joint shape-and-allocation analysis is the obvious next step and is not attempted here.

### 4.4 Limitations

Five limits are declared. **(1) Registration scope.** The metric and pair test were pre-registered; the five-species extension was not separately pre-registered. The pairwise p-values are uncorrected, and two of the ten do not survive Bonferroni correction (§3.2); the family's claim should be quoted with that count attached. **(2) Sample size.** Complete-6 n ranges from 5 (*D. bicornis*) to 10 (*C. simum*); the two largest distances both involve the n = 5 cell, and while permutation p-values account for cell size, the *D. bicornis* mean profile is the least precisely estimated in the study. **(3) Sex.** Sex is unknown for roughly half the museum sample (a limitation inherited from the source data, noted by Mallet et al.); no sex term is fitted, and sexual dimorphism, if present in allocation, is folded into within-species variance. **(4) The ruler.** CS is computed from the released landmark configurations, which include the sliding surface semi-landmarks as published; the configuration is identical within each bone, so profiles and ratios are internally valid, but absolute CS values from these files should not be pooled with sizes measured from meshes or specimens by other protocols. **(5) Phylogeny and ecology.** Five species cannot support a phylogenetic comparative test, and none is attempted: the profile differences are reported as species differences. The same-genus separation (*R. sondaicus* – *R. unicornis*) shows the profile is not a simple genus or continent split, but with two African and three Asian species, no ecological attribution is made.

### 4.5 Conclusion

A quantity that costs nothing to compute — each bone's size relative to its own animal's mean — was left unextracted in an open dataset for six years, and it separates all five living rhinoceros species, most sharply along the forearm. The finding is modest in machinery and, we think, instructive in kind: the published record's uncomputed comparisons are a research surface in their own right, and a pre-registered metric is what turns one of them from a pattern noticed into a result stated.

## Data and Code Availability

Source data: Mallet et al. (2019), Supplemental Information 9 (raw `.pts` landmark files), DOI 10.7717/peerj.7647/supp-9, obtained via the Europe PMC supplementary-files route for PMC6766374 (zip MD5s in §2.1); article and supplements CC-BY. Analysis code and full outputs for the five-species computation — `compute_rhino5.py`, `centroid_sizes_all5.csv`, `profiles_all5_ge5.csv`, `profiles_all5_complete6.csv`, `pairwise_profile_tests.csv`, `rhino5_results.json` — are published in the lab's Goldmine Hunter repository under `gold/morpho-ct/epmc-rhino5/` (github.com/atharva-chourey-lab/goldmine-hunter). The two-species pre-registration (2026-11-17, commit 28159eb, committed before any download or measurement) and the pair computation's outputs are held in the lab's project records. No new specimens were measured and no restricted data were accessed.

## References

- Etienne, C., Mallet, C., Cornette, R., & Houssaye, A. (2020). Influence of mass on tarsus shape variation. *Biological Journal of the Linnean Society*, 129(4), 950–974. https://doi.org/10.1093/biolinnean/blaa005
- Groves, C. P. (1983). Phylogeny of the living species of Rhinoceros. [Source for the summary of Guérin (1980) on long-bone length proportions quoted in §1 and §4.2.]
- Guérin, C. (1980). [Long-bone proportion comparisons across the living rhinoceros species; as summarised in Groves (1983). Full bibliographic details not present in the lab's source files and not supplied here.]
- Mallet, C., Cornette, R., Billet, G., & Houssaye, A. (2019). Interspecific variation in the limb long bones among modern rhinoceroses — extent and drivers. *PeerJ*, 7, e7647. https://doi.org/10.7717/peerj.7647
- Mallet, C., Billet, G., Houssaye, A., & Cornette, R. (2020). A first glimpse at the influence of body mass in the morphological integration of the limb long bones: an investigation in modern rhinoceroses. *Journal of Anatomy*, 237(4), 704–726. https://doi.org/10.1111/joa.13232
- Mallet, C., Houssaye, A., Cornette, R., & Billet, G. (2022a). Long bone shape variation in the forelimb of Rhinocerotoidea: relation with size, body mass and body proportions. *Zoological Journal of the Linnean Society*, 196(3), 1201–1234. https://doi.org/10.1093/zoolinnean/zlab095
- Mallet, C., Billet, G., Cornette, R., & Houssaye, A. (2022b). Adaptation to graviportality in Rhinocerotoidea? An investigation through the long bone shape variation in their hindlimb. *Zoological Journal of the Linnean Society*, 196(3), 1235–1271. https://doi.org/10.1093/zoolinnean/zlac007
