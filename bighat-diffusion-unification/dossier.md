# Source dossier — A Unification of Discrete, Gaussian, and Simplicial Diffusion

## 서지와 범위

- 실제 읽은 원문: `/Users/minsung.choi/bioeu/protein/papers/bighat-diffusion-unification.pdf`, 41 pages. 본문 pp.1–10, 참고문헌 pp.10–13, 부록 pp.14–41.
- Authors: Nuria Alina Chandra, Yucen Lily Li, Alan N. Amin (equal contribution), Alex Ali, Joshua Rollins, Sebastian W. Ober, Aniruddh Raghu, Andrew Gordon Wilson.
- Affiliations: NYU, CUNY, BigHat Biosciences. BigHat authors: Ober, Raghu. Company participation is not proof that every described capability is a deployed commercial platform.
- arXiv 2512.15923: first submitted 17 December 2025; v2 18 April 2026. [arXiv record](https://arxiv.org/abs/2512.15923)
- PDF repeated header says “Published as a conference paper at ICLR 2025”. This conflicts with chronology and [BigHat official publications list](https://www.bighatbio.com/publications), which says ICLR 2026. Script reports preprint/revision dates and official-company listing while disclosing mismatch. Do not silently call this an ICLR 2025 paper.
- Scope: mathematical/statistical unification of discrete sequence diffusion. Main empirical settings DNA accessibility, general protein sequences, language. Appendix computational VHH optimization, MNIST. No new prospective antibody wet-lab measurements, animal experiments, clinical results, or de novo epitope binding results in this work.

## Actual section map and narration order

1. Abstract + Introduction pp.1–2: three discrete-data diffusion paradigms and practical comparison problems.
2. Related work pp.2–3 (+Appendix A/B pp.14–15): forward-process unification precedents; why argmax of Gaussian trajectories is not generally Markov; stable simplex alternatives.
3. Background and Motivation pp.3–4: Markov forward/reverse models, time dilation, negative ELBO, likelihood/hyperparameter comparison issues.
4. Unifying Discrete and Gaussian Diffusion pp.5–6: ζ copied letters, normalized counts, large population + rescaling/time change; dominant eigenspace; hollow parameterization; induced amino-acid embeddings.
5. Unifying Simplicial Diffusion pp.7–8: add reproduction; Wright–Fisher limit; ELBO convergence; exact marginal sampler + low-time approximation; DNA evaluation.
6. Practical Unified Diffusion Models pp.8–10: sufficient statistic parameterization, common evidence space, alternating domains; protein/language comparisons.
7. Conclusion p.10: omissions, intermediate population models, possible future hyperparameter/domain sharing.
8. After main conclusion, Appendix G pp.39–41: computational antibody optimization and MNIST supplemental validation. Script chapter10 explicitly identifies appendix material.

## Critical facts and interpretation guardrails

- ζ=1 corresponds to discrete mutation; ζ→∞ without reproduction yields Gaussian limit under proper time change and local rescaling; ζ→∞ with scaled reproduction yields Wright–Fisher/simplex diffusion. Population copies are mathematical auxiliary states, not real cultured cells.
- Gaussian correspondence is not simply “many copies means Gaussian”; dominant non-stationary eigenspace controls retained initial-state information. Other eigendirections lose useful x0 information in the limit.
- Comparability concerns discrete-data likelihood/ELBO with appropriate parameterization, not arbitrary continuous density scores. Negative ELBO minimized in algorithms; ordinary ELBO has opposite sign. Script uses negative-ELBO wording for 8/1.39/1.30 comparison.
- Hollow predictor incorporates known local evidence and predicts context separately. No mandatory architecture change; neural net must learn to disregard direct position in context prediction.
- Every embedding can be induced only under construction allowing additional dummy tokens (Appendix E.4 pp.28–29). Script flags auxiliary-state qualification.
- Simplex coordinates are nonnegative and sum1; simplex geometry couples coordinates. Score means ∇log-density, not test-set score.
- New sampler uses ancestral count m then Dirichlet(ψπ+m x0). Exact marginal algorithm is from mathematical genetics, but implementation uses low-time Gaussian/Griffiths approximation; do not call all-time implementation exact.
- Main threshold τ<0.05 uses low-time approximations. Figure9a benchmark uses switching threshold0.1, distinct from main prescribed0.05; script does not conflate figure9a threshold with main method.
- High precision recomputation used selectively when alternating-series cancellation is detected. Main summation kmax80 for τ≥0.05 vs previous1000. Source p17 has a likely explanatory typo about cancellation denominator becoming “very large”; correct conceptual explanation is small residual / high condition number. Script uses correct conceptual description, not typo.
- SSP input φ_b∝p(x_t|x0=b,t) normalized overb. This is relative likelihood evidence, not full posterior with learned sequence prior. F optimal depends on fixed target data distribution; does not unify arbitrary unrelated datasets.
- Time invariance means no separate explicit time input to F; preprocessing and reverse simulation still depend on time.

## Benchmarks / exact numbers

### DNA pp.8,37–38
- B=4, D=500. FlyBrain enhancer training data. Small CNN about3M parameters, same base architecture/optimizer lineage as DDSM/Dirichlet flow matching.
- Training11h A10080GB,700epochs. Precomputes/caches noisy states/series where useful. Cross-hardware comparisons not strict identical-speed claims.
- Accessibility predictor bpAITAC CNN, trained on Drosophila embryonic16–20h data; chr2L held-out. Predicts central250bp count profile; figure displays central150positions.
- Reported prior negativeELBO8 nats/position (12.7 before training), uniform baseline1.39, proposed1.30.
- Conditional profiles measured by predictor RMSE, no newly measured cell-based accessibility.
- **Internal inconsistency**: Fig5 caption1000targets×10samples, AppendixF.1 says100targets×10samples (top100peaks). Script openly flags and avoids selecting one.
- Figure5 bars visually ~random50, previous43, flow29, ours10; script deliberately gives ranking without spurious precise values.

### Protein pp.9,38
- All begin ESM2 150M pretrained weights; UniRef50; lr1e-5; A10080GB48h, about3Msequences; single shared SSP alternates3domains.
-1000generated sequences length200;100grid points,4corrector steps; OmegaFold onecycle pLDDT.
- Fig7 single models ordered simplicial/discrete/Gaussian: NLL2.46/2.41/2.29; pLDDT41.1/40.7/44.4.
- Unified same order: NLL2.47/2.41/2.30; pLDDT40.7/41.8/43.8.
- Referenced DPLM values NLL2.36, foldability45.2. Not all models beat comparator; pLDDT is computational confidence/proxy, not physical foldability assay.

### Language pp.9–10,39
- Simplicial omitted for scaling challenge B≈3×10^4. Only discrete/Gaussian/unified2domain.
-12layers,12heads,dim768, fourA10080GB,40–50hours;33billion tokens fromlm1b and33epochs inmaincaption. lr3e-4,EMA.9999. BERT embeddings×8 forGaussian.
- Single discrete/Gaussian NLL3.46/4.57; GPT2-large generative perplexity100.7/144.8.
- Unified discrete/Gaussian NLL3.55/4.18; genperplexity122.8/105.5.
- Unified worsens discrete and improves Gaussian in these metrics; avoid “wins all settings”. Language effective batch differs (single512,shared1024); no blanket3×compute saving.

### Appendix antibody pp.39–40
- Perturb parentalVHH,128denoisingsteps; noise sweep t∈{.01,.02,.05,.1,.2,.5}, prefer diversity with≤5mutations; then rejection sample single/doublepoint variants.
- G.1 text50unique variants perrepeat,100repeats, bestoracle sequence eachrepeat. **Figure10 caption librarysize100 conflicts**. Script reports textandflagscaption.
- Proprietary10CARP/ByteNet regressor ensemble: pretraining≈537k phagedisplay/NGSsequences,9556 NanoDSF Tm datapoints; testcrossvalidated Spearman.72.
- Figure10 predictedΔTm, not new measuredΔTm. No exactboxquantiles fabricated. Oracle-selectedbest candidate can exploitmodelerror; scriptlabels inference/limit.

### MNIST pp.39–41
-28×28pixels,8uniformquantizationlevels; U-Net128embedding,4down/upblocks,20epochs.
- Fig11 independent discrete/simplex/Gaussian NLL.22/.22/.25; unified.18/.22/.23.
-64unconditionalsamples/model,1000steps. Fig12 qualitative comparable digitquality, not fullimagebenchmark.

## Figure inspection anchors

Rendered and visually inspected full pages:2,6,8,9,18,40,41; PNGs in `figures/`.

|Figure|PDF page|Audio description|
|---|---:|---|
|1|2|Six-member copying/mutation population; population size and reproduction-rate map; discreteζ1 vs two large-population limits|
|2|6|ζ1000 triangle trajectory; near-equilibrium zoom to Gaussian cloud|
|3|6|ζ300 random vs hollow reversepaths; plausible deterministicreturn|
|4|6|BLOSUM-derived amino-acid embedding chemically similar groups; no affinity claim|
|5|8|central150positions targetdashed vs generatedblue curves; RMSEbars rankedoursbest|
|6|9|different domainrepresentations map to normalizedevidencevector|
|7|9|protein NLL/pLDDT andlanguage NLL/perplexity; exactnumbersabove|
|8|15|argmaxGaussian vs discrete paths can differ despite similar marginals; readcaption/text|
|9|18|sampling runtime, simplex corner densityerror, relativeerrorvsseries terms|
|10|40|predictedΔTm boxplots greyindividual/blueunified; broadoverlap; in silico|
|11|40|MNISTNLLbarsexactabove|
|12|41|sixgridsofgeneratedhandwrittendigits; noobviousqualitydrop|

## Primary background sources consulted

- [Ho, Jain, Abbeel, Denoising Diffusion Probabilistic Models](https://arxiv.org/abs/2006.11239): basic denoising/variational-objective context; no imagebenchmarks imported into biological claims.
- [Avdeyev etal., Dirichlet Diffusion Score Model for Biological Sequence Generation](https://arxiv.org/abs/2305.10699): predecessor on probabilitysimplex, ICML2023. Predecessor’s own biological tasks not ascribed to currentwork.
- [Jenkins and Spanò, Exact simulation of the Wright-Fisher diffusion](https://arxiv.org/abs/1506.06998):2015preprint,2017AnnalsAppliedProbability; exactmarginal samplingsource. Only briefhistoricalcontextused.
- [Authorcode](https://github.com/yucenli/unify-diffusion): provenance/support; code not executed and findings not independently reproduced.

## Final QC

-73narratorparagraphs, each206–255Hangul syllables. Spoken section includingchapterheadings17,666Hangul; prose-only count is reported separately by checker ifneeded. No dialogue or production directions in spoken body.
- Main-source claims checked against actualPDF; allnumeric values above retained or intentionally omitted when unclear. Script does not claim clinical validation or prospective wetlabtesting.
- Audio/render/publishing deliberately left to parentagent.
