# School of Thinkers (Escola de Pensadores) - Data and codes

Private repository. Data, analysis code and reports of the School of Thinkers / Metodo SOFT evaluation in three municipal schools of Nova Mutum, MT, Brazil (O Semeador, Futuro Brilhante, Marton Lucca). Wave T1 (March-August 2026). Migrated from the Open Science Framework (osf.io/cxpt4 template).

## Structure

```
Original data and metadata/          T1 data exported from the platform on 2026-08-23, one row per response (= local Data/Official)
  EP_alunos_saude_emocional.csv                  students  - Inventario de Saude Emocional - Aluno (n = 748)
  EP_pais_saude_emocional_familia.csv            parents   - Inventario de Saude Emocional - Familia (n = 915)
  EP_professores_pratica_pedagogica.csv          teachers  - Inventario de Pratica Pedagogica e Perfil da Turma (n = 97)
  EP_professores_qualidade_vida_saude_mental.csv teachers  - Inventario de Qualidade de Vida e Saude Mental (n = 122)
  EP_codebook.csv                                variable dictionary: column_name, label, type, scale, options, dimension
Processing and analysis/
  Command files/
    DP - EP - School of Thinkers.ipynb           data preparation (R): cleaning, recoding, dyads -> ep.rds
    DA - School of Thinkers.ipynb                manuscript analyses (R): EFA/CFA, reliability, regressions, child-caregiver ICC, invariance
    DA - Professor Student.ipynb                 teacher variables predicting student self-report (R)
  Importable data/
    ep.rds                                       output of DP, input of DA: list of df_st (741), df_par (912), df_t (111), df_dy (406)
Results/
  Relatorio Parcial 1 - Linha de base - School of Thinkers.docx   baseline partial report
  Relatorio 2 - Dados ate agosto - School of Thinkers.docx        report with data up to August 2026
```

## Paths

DP reads `../Data/Official/<file>.csv` and writes `ep.rds`; DA notebooks read `../ep.rds`. Adjust the relative paths to this repository layout before running.
