# Contexto del Proyecto — MedCaseReasoning

## Descripción
Pipeline y benchmark open-access para evaluar y mejorar el razonamiento diagnóstico clínico en LLMs.

- **Dataset**: [`zou-lab/MedCaseReasoning`](https://huggingface.co/datasets/zou-lab/MedCaseReasoning)
- **Paper**: https://arxiv.org/abs/2505.11733
- **Licencias**: Código MIT | Dataset CC-BY 4.0

## Dataset
| Split | Casos | Uso |
|-------|------:|-----|
| train | 13,092 | Fine-tuning supervisado |
| test  |    897 | Evaluación agnóstica al modelo |

Cada ejemplo contiene: `case_prompt`, `diagnostic_reasoning`, `final_diagnosis`.

---

## Estructura del repo

| Archivo | Estado | Rol |
|---------|--------|-----|
| `download_pmc.py` | presente | Descarga bulk XML de PMC OA |
| `get_case_report_pmcids.py` | presente | Obtiene PMCIDs de case reports |
| `process_pmc.py` | presente | Extracción paralela de XML candidatos |
| `extract_metadata.py` | presente | Metadatos estructurados |
| `extract_text.py` | presente | Limpieza XML → texto |
| `requirements.txt` | presente | Dependencias Python |
| `prompts.py` | **faltante** | Templates de prompts usados en el paper |
| `stitch_reasoning.py` | **faltante** | Bullets → reasoning trace fluido |
| `evaluate.py` | **faltante** | Runner de evaluación (accuracy + reasoning recall) |
| `finetune/` | **faltante** | Recipe SFT + configs |

## Dependencias principales
- `pandas`, `numpy`, `beautifulsoup4`, `lxml`, `tqdm`, `biopython`, `pyarrow`, `requests`, `multiprocess`

---

## Pipeline de reproducción del dataset

```
1. download_pmc.py          → descarga XMLs
2. get_case_report_pmcids.py → filtra case reports
3. process_pmc.py            → extrae XMLs relevantes
4. extract_metadata.py       → metadatos
5. extract_text.py           → texto limpio
6. stitch_reasoning.py       → reasoning trace (FALTANTE)
```

---

## Sesiones de trabajo
<!-- Registrar aquí sesiones, decisiones y avances -->

### 2026-03-09
- Exploración inicial del repositorio.
- Creada carpeta `docs/` para contexto y sesiones.
- Identificados archivos faltantes: `prompts.py`, `stitch_reasoning.py`, `evaluate.py`, `finetune/`.
