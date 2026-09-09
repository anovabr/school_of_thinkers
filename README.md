# School of Thinkers (Escola de Pensadores) - Data and codes

Data, analysis code and reports of the School of Thinkers / Metodo SOFT evaluation in three municipal schools of Nova Mutum, MT, Brazil (O Semeador, Futuro Brilhante, Marton Lucca). Wave T1 (March-August 2026). Migrated from the Open Science Framework; same folder template.

## Structure

```
Original files/                      T1 data exported from the platform on 2026-08-23, one row per response
  EP_alunos_saude_emocional.csv                  students  - Inventario de Saude Emocional - Aluno (n = 748)
  EP_pais_saude_emocional_familia.csv            parents   - Inventario de Saude Emocional - Familia (n = 915)
  EP_professores_pratica_pedagogica.csv          teachers  - Inventario de Pratica Pedagogica e Perfil da Turma (n = 91)
  EP_professores_qualidade_vida_saude_mental.csv teachers  - Inventario de Qualidade de Vida e Saude Mental (n = 111)
  EP_codebook.csv                                variable dictionary: column_name, label, type, scale, options, dimension
Processing and analysis/
  Command files/
    DP - EP - School of Thinkers.ipynb           data preparation (R): cleaning, recoding, dyads -> ep.rds
    DA - School of Thinkers.ipynb                manuscript analyses (R): EFA/CFA, reliability, regressions, child-caregiver ICC, invariance
    DA - Professor Student.ipynb                 teacher variables predicting student self-report (R)
  Importable data/                               output of the DP notebook; input of the DA notebooks
    ep.rds                                       list of 4 data frames: df_st, df_par, df_t, df_dy
    ep_st.csv                                    students (n = 741), recoded items as *_num
    ep_par.csv                                   caregivers (n = 912)
    ep_t.csv                                     teachers (n = 111), both inventories joined by respondent_id
    ep_dy.csv                                    student-caregiver dyads (n = 406), suffixes _aluno / _familia
Results/
  Relatorio Parcial 1 - Linha de base - School of Thinkers.docx   baseline partial report
  Relatorio 2 - Dados ate agosto - School of Thinkers.docx        report with data up to August 2026
```

## De-identification

Public files exclude direct identifiers present in the private originals: respondent names, caregiver names, birth dates and contacts. Respondent, class and school IDs are kept; `respondent_id` links a student row to the caregiver row about the same child (dyads). The test-row and birth-year exclusions of the DP notebook were applied before publishing (teachers: 97 -> 91 and 122 -> 111 rows), so the notebooks reproduce the reported samples. DA section 6 (caregiver sex inferred from first name) requires the private file.

## Paths

DP reads `../Data/Official/<file>.csv` and writes `ep.rds`; DA notebooks read `../ep.rds`. Adjust the relative paths to this repository layout before running.
