# EHR-Rel
**EHR-RelB** is a **benchmark dataset** for biomedical concept relatedness, 
consisting of 3630 concept pairs sampled from electronic health records (EHRs).
**EHR-RelA** is a smaller dataset of 111 concept pairs, which are mainly unrelated.

**If you use one of the datasets in your research, please cite**

```
@inproceedings{
SchulzEtAl2020COLING,
title={Biomedical Concept Relatedness – A large EHR-based benchmark},
author={Schulz, Claudia and Levy-Kramer, Josh and Van Assel,Camille and Kepes, Miklos and Hammerla, Nils},
booktitle={Proceedings of the 28th Internatinal Conference on Computational Linguistics},
year={2020},
pages={to appear}
}
```
You can also access the paper on [Arxiv](https://arxiv.org/abs/2010.16218).

**Contact:** 
* [Claudia Schulz](clauschulz1812@gmail.com)
* [Josh Levy-Kramer](josh@levykramer.co.uk)
* [Camille Van Assel](camille.vanassel@babylonhealth.com)
* [Miklos Kepes](kepes.miklos@gmail.com)
* Nils Hammerla


## Dataset Details
* Each concept is given in terms of its **SNOMED ID** and SNOMED (UK) **preferred term**. 
Most concepts furthermore have a **UMLS CUI**.
* For each concept pair, the ratings of the 3 (EHR-RelB) or 5 (EHR-RelA) doctors is given.
* For each concept pair, the **relatedness score** is given as the mean of the doctors' ratings.

#### Concept Pairs
Concepts are sampled from IQVIA Medical Research Data (IMRD) incorporating data from The Health Improvement Network
(THIN, a Cegedim database), which consists of anonymised primary care EHRs, covering 5% of the UK
population.
For each patient in IMRD, all distinct concepts that are symptoms, diagnoses, or presenting complaints occurring
 in the patient’s EHR are paired, resulting in a total of 1,345,193 unique pairs made from
34,794 unique concepts.
1) **EHR-RelA:** 111 randomly selected concept pairs, each annotated by 5 doctors
2) **EHR-RelB:** the 3630 most frequently occurring concept pairs, each annotated by 3 doctors

The concepts in IMRD are given as Read Version 2 codes. 
To ensure international compatibility, we map all concepts in
the extracted concept pairs to SNOMED IDs using the mappings provided by 
[NHS Digital](https://isd.digital.nhs.uk/trud3/user/guest/group/0/pack/8/subpack/9/releases).
Only the SNOMED IDs are given in the benchmark datasets.


#### UMLS CUIs
Where possible, SNOMED IDs are mapped to UMLS CUIs using the
[UMLS REST API](https://documentation.uts.nlm.nih.gov/rest/home.html).
For a given SNOMED ID `id`, all CUIs that `id` is associated with are obtained. 
For each of the obtained CUIs `cui`, the SNOMED IDs which are preferred terms of `cui` are retrieved.
If `id` is one of them, then `cui` is considered as representing `id`.

Note that we only provide a UMLS CUI for a SNOMED ID if the mapping is unambiguous.
That is, if there is more than one `cui` considered as representing `id`, we do not provide either of them.
Note also that some SNOMED IDs are from the SNOMED UK release and are thus not part of UMLS.
These SNOMED IDs also have no UMLS CUI in EHR-Rel. 

## About Babylon
At Babylon we believe it’s possible to put an accessible and affordable 
health service in the hands of every person on earth.
 The technology we use is at the heart and soul of that mission. 
 Babylon is a Healthcare Platform, currently providing online consultations via in-app video and phone calls,
  AI-assisted Triage and Predictive Health Assistance.

If you are interested in helping us build the future of healthcare, please find our open roles 
[here](https://jobs.lever.co/babylonhealth?lever-via=LLeodZVvTU).

Follow us on Twitter @Babylon_Eng or go to [babylonhealth.com](https://www.babylonhealth.com/) 
for more information
