# BigHat masked-LM protein engineering — source dossier

## Source and evidence boundary
- Actual 27-page supplied PDF fully read through extracted text including references and appendix A.1–A.11.
- Title: *How to make the most of your masked language model for protein engineering*.
- Authors on first page: Calvin McCarter, Nick Bhattacharya, Sebastian W. Ober, Hunter Elliott. BigHat Biosciences; McCarter footnote work at BigHat, now Aureka Biotechnologies.
- Actual PDF first page: arXiv:2603.10302v4 [cs.LG], 1 Nov 2026; footer “40th Conference on Neural Information Processing Systems (NeurIPS 2026)”. Do not substitute ICLR 2026 from external company listing, or independently assert acceptance/peer review beyond supplied document.
- Article order retained: abstract/introduction; related work; Methods 2.1–2.3; Experiments 3.1, 3.2, 3.3; Conclusion; supplemental caveats after conclusion.
- This is candidate-seeded iterative engineering, not a de novo zero-shot target-binder discovery success study.

## Numerical anchors
- Table 1, p5: Trastuzumab 190 one-edit H3 variants; approximate vs exact PLL Pearson ESM2 .964, AbLang2 .869, ProteinMPNN .944, AbMPNN .927; correlation is model-score agreement, not biological binding prediction.
- §3.1, pp5–6: ESM2 at six realized edits mean oracle predicted p(binder) ~.95 beam, ~.43 denoising, ~.44 Gibbs. Strong oracle trained on367k, AUROC.995; separate Mason guidance on34k, AUROC.914.
- Table8 p21: fraction p(binder)>.5 at6edits: ESM2Beam.98,Gibbs.44,BeamMason.92,BeamMasonOASis.98; AbLang2Beam.26,Gibbs.40,BeamMason.99,BeamMasonOASis.64. These are surrogate thresholds, NOT wet-lab hit rates. Mean score and pass fraction explicitly distinct in speech.
- §3.2: ten seeds; exactly3 substitutions; real scFv program with surrogate property evaluation. Predicted PQ model trained6038 samples, mean test AUROC.9057. Tm predictor lineage test Spearman.7693; other-lineage1111 test.8486.
- §3.3: fresh Fab program, single seed; for most methods2/3 designed4CDR edits,1/3 designed3anywhere; DiffAb+4CDR only.
- Guided methods use729 labeled samples;60/20/20 split;5classifier ensemble; test meanAUROC.9342±.0101. Filtering p_success>.6; ranking p_success; NDS and STS generation guidance followed by ranking. Beam width5 vs guided20, temperature1.5. Not perfectly identical search budgets.
- Main text reports289samples/14methods AND at least21each; internally inconsistent since14×21=294. Script says289/14 as reported, does not repeat >=21 each. Do not infer exact per-method sample sizes from graphic.
- STS observed100% production+bindingQC success for tested batch; NOT100% future success, drug efficacy, clinical success. Error intervals are binomial inversion95%CIs.
- Seed p27: KD7.83nM, -log10KD8.11;yield42.8ng/µLCFPS;OASis16%;pI6.14. Source uses rounded values.
- BLI1:1model; upstream failures concentration<50ng/µL orA260/A280outside.5–.85. Nonbinder max signal<.05nm at highest analyte concentration. Signal unit nm not physical interaction distance. CFPS yield/unit input and assayed sample concentration differ.
- Before lab: pI<=9 and exclusions for newly introduced liabilities. Thus lab success pertains post-filter selected batches.

## Core figures inspected visually
Rendered/inspected actual PDF images p6,p8,p9,p24, local inspect_p*.png.
- Fig1 p6: edits vs oracle meanp(binding);OASis×predictedbinding3/6edits;conditionalhumannessbinmean;quality-filtered pairwise diversity. Beamhigherpredictedbinding;guidedMOOcantrade diversity for reliability. Not in vitro.
- Fig2 p8: predictedPQ probability,predictedTm,inter-seed distance,intra-seed distance, ridgeline plots. BeamimprovesPQ butnotclearTm; internaldiversity lower whileinter-seed lessaffected.
- Fig3 p9: observedcombinedproduction+bindingQC rate, -log10KD(successesonly), CFPSyield(productionsuccessesonly).Magenta star seed baseline. Cannot compare successful-only affinity distribution as overall success.
- Fig4 p9: OASis,pI,germlinefrequencydelta;success/fail split. Guided success improves whilehumanness can worsen.
- Fig5 p9:CDRmutationcount,VHmutationcount,pairwisediversity;guided methodsretainCDRmutations, favorVLmore,reducedsingle-seed diversity.
- Table2–6pp16–18:7antibody approximation study;AbLang2near-UCAframework exception; authorsattribute sharpPLLcliffstogermlinememorization usingCDR-only andDASMcomparison. Biological interpretation is author inference, notdirectwetvalidation.
- Fig6p21,Fig7p22,Fig8p23/Table8:AbLang2andMPNNsurrogate results,antigenpresent(holo)/absent(apo).
- Fig9p24:parameter sweeps,qualityvsdiversity forbeamwidth/temp. Fig10p24:wallclockseconds A10G,7editTrastuzumab;actualobservedruntime differsfromtheory;fixed200returnedvariants;beamhasadditional3800scoredneighbors available withcaveats.
- Fig11p25:predictedPQinitialAbLang2samplercomparison. Fig12p26:in silicohumanness,germlinebias,pI,CDRmutations.

## Limitations to retain
1. Only one wet-lab campaign/one seed. No broad target or modality generalization.
2. Guided Gibbs not tested wet-lab, so guided beam not proved superior to all guided samplers experimentally.
3. Oraclepredictions versus real BLI/QC are repeatedly distinguished.
4. OASis percentile is repertoire-based humanness metric against therapeutic reference, not direct clinical immunogenicity.
5. ESM2 is useful in specific tasks, not proof structure irrelevant or antibody-specialized models useless.
6. No cells,animals,clinicalefficacyvalidation inreportedexperimentalbenchmark.
7. Guidance can reducehumannessanddiversity;rewardedmetricsnotallqualities.
8. “ExactPLL”exactcomputationofmodelscore,notbiologicaltruth.
9. Main text p6 “Appendix TODO” not propagated; real runtime data AppendixA.7/Fig10.

## Primary background sources verified online
- Salazar etal., ACL2020, *Masked Language Model Scoring*: https://aclanthology.org/2020.acl-main.240/ (PLL for masked models; this is background, not new proteinresults.)
- Lin etal., Science2023, *Evolutionary-scale prediction of atomic-level protein structure with a language model*: https://pubmed.ncbi.nlm.nih.gov/36927031/ ;authorcode https://github.com/facebookresearch/esm (generalproteinlanguage-model context.)
- Prihoda etal., mAbs2022, *BioPhi*: https://pubmed.ncbi.nlm.nih.gov/35133949/ ; DOI https://doi.org/10.1080/19420862.2021.2020203 (Sapiens/OASis;humannessnotclinicalimmunogenicity.)
- Mainarticle https://arxiv.org/abs/2603.10302 ;code https://github.com/calvinmccarter/mlm4proteins . Source PDF versions govern narration.

## Script QA
- Main spoken section before appendix: 74 narrator paragraphs; 15,752 Hangul syllables before final cosmetic adjustments,22,377characters. Actual count recomputed on delivery.
- No dialogue, no invented clinical claims, no company platform positioning; complete solo paper lecture.
