# p5_data — raw data transfer repo for P5 (drug sensitivity)

Compressed raw files only (gzip -9); no analysis. Originals are git-ignored. Files >90 MB are split into 90 MB parts (no Git LFS). `MANIFEST.csv` holds source URL, download date, bytes and MD5 of the ORIGINAL uncompressed file.

Reassemble (split files): `cat file.gz.part_* > file.gz && gunzip file.gz && md5sum file`  
Unsplit: `gunzip file.gz && md5sum file`

## Files

| path | original bytes | original md5 | stored as |
|---|---|---|---|
| raw/gdsc/GDSC2_fitted_dose_response_27Oct23.xlsx | 22112537 | 7303bf3b53a3cfb8f03e739f51cc810d | GDSC2_fitted_dose_response_27Oct23.xlsx.gz |
| raw/gdsc/screened_compounds_rel_8.5.csv | 46414 | 1f8a7c36e02f3298704063f104b5ff81 | screened_compounds_rel_8.5.csv.gz |
| raw/gdsc/model_list_latest.csv.gz | 145029 | 28f53085bf4db7b855bd8b251ca7d841 | model_list_latest.csv.gz |
| raw/prism/secondary-screen-dose-response-curve-parameters.csv | 264340589 | e629b9d505ad3d6bf65fde96f1c54bee | secondary-screen-dose-response-curve-parameters.csv.gz |
| raw/prism/secondary-screen-replicate-collapsed-treatment-info.csv | 3788355 | 54765b3639f91cede751378d694e3583 | secondary-screen-replicate-collapsed-treatment-info.csv.gz |
| raw/prism/secondary-screen-cell-line-info.csv | 40979 | 6737b4aa9fd85404fd2f0cf825b037e4 | secondary-screen-cell-line-info.csv.gz |
| raw/prism/secondary-screen-readme.txt | 7647 | 421d0bbadec381adc0d7981ee7e16bd7 | secondary-screen-readme.txt.gz |
| raw/genesets/h.all.v2026.2.Hs.symbols.gmt | 48694 | c945afd59d949398471c8768fe4d41b0 | h.all.v2026.2.Hs.symbols.gmt.gz |
| raw/beataml/beataml_wv1to4_clinical.xlsx | 488278 | e66c8e191b7446ab6cb47f648049230d | beataml_wv1to4_clinical.xlsx.gz |
| raw/beataml/beataml_waves1to4_norm_exp_dbgap.txt | 281337180 | da30e3483cf238b862fba926fcebfbe6 | beataml_waves1to4_norm_exp_dbgap.txt.gz.part_000, beataml_waves1to4_norm_exp_dbgap.txt.gz.part_001 |
| raw/beataml/beataml_probit_curve_fits_v4_dbgap.txt | 19047078 | e17bee701ee42b84e3e98d8a6b117ffd | beataml_probit_curve_fits_v4_dbgap.txt.gz |
| raw/beataml/beataml_wes_wv1to4_mutations_dbgap.txt | 3668996 | aed2e5a49914d73c8cb30c931a647604 | beataml_wes_wv1to4_mutations_dbgap.txt.gz |
| raw/beataml/beataml_drug_families.xlsx | 59330 | 8030f4a3800ba182007b680e1333d073 | beataml_drug_families.xlsx.gz |
| raw/beataml/LICENSE.txt | 18658 | 8c8ea597b5ac4c4bd0aa32ef4d8c63cc | LICENSE.txt.gz |
| raw/beataml/beataml2_portal_page.html | 8964 | eaf293f443cbd392f4791ec00acdaf69 | beataml2_portal_page.html.gz |
| raw/depmap/Model.csv | 789805 | a7423dbf345fcf5a822ab5fc7e854e5c | Model.csv.gz |
| raw/depmap/OmicsCNGeneWGS.csv | 661789195 | 8e5158c0b8c929cf7574f0ae7a7d922a | OmicsCNGeneWGS.csv.gz.part_000, OmicsCNGeneWGS.csv.gz.part_001, OmicsCNGeneWGS.csv.gz.part_002, OmicsCNGeneWGS.csv.gz.part_003 |
| raw/depmap/OmicsExpressionTPMLogp1HumanProteinCodingGenes.csv | 394997160 | b45585365eb9580bcf4618791ea87f76 | OmicsExpressionTPMLogp1HumanProteinCodingGenes.csv.gz.part_000, OmicsExpressionTPMLogp1HumanProteinCodingGenes.csv.gz.part_001 |
| raw/depmap/OmicsProfiles.csv | 882568 | 6a025f0c96c66e1cc49086ea9b2f7687 | OmicsProfiles.csv.gz |
| raw/depmap/OmicsSomaticMutations.csv | 642018258 | 24839b2c674ac449444ca2368bed05db | OmicsSomaticMutations.csv.gz.part_000, OmicsSomaticMutations.csv.gz.part_001 |

Note: `model_list_latest.csv.gz` is stored as downloaded (already gzip); its md5 is of the .gz.

## Licences

- **GDSC** (Sanger, release 8.5 / GDSC2 27Oct23): GDSC academic terms of use; cite Iorio 2016 / Yang 2013 and the Cell Model Passports. Check the Sanger terms before any commercial use.
- **DepMap**: licence is per file (mostly CC BY 4.0). DepMap files are in `raw/depmap/`.
- **PRISM Repurposing** (Figshare 9393293 v4): CC BY 4.0 (per Figshare record).
- **Beat AML** (waves 1-4, processed public files from github.com/biodev/beataml2.0_data): CC BY 4.0 (see `raw/beataml/LICENSE.txt.gz`); processed public data only, no dbGaP raw data.
- **MSigDB Hallmark** (2026.2.Hs): CC BY 4.0 (see gsea-msigdb.org licence page).

## Not included

- **DepMap**: files downloaded manually in a browser (Cloudflare blocks the file-list API). Release name was not recorded; CN file is `OmicsCNGeneWGS.csv`, expression is `OmicsExpressionTPMLogp1HumanProteinCodingGenes.csv`, mapping is `OmicsProfiles.csv`. Fill the release name in MANIFEST.csv.
- **GDSC Cell_Lines_Details.xlsx**: no longer published; cancerrxgene.org bulk page redirects to Cell Model Passports. `model_list_latest.csv.gz` (CMP) is the successor annotation.
- No separate README exists for GDSC/Beat AML repos; Beat AML portal page saved as `beataml2_portal_page.html.gz`.
