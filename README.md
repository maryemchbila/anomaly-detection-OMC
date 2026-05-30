# Anomaly Detection & Predictive Maintenance — LTE OMC Data

> P2M Project — SUP'COM 2025 | Mariem Chbila & Marwa Guiniche  
> Supervised by: Prof. Sami Tabbane & Prof. Houda Khedher

## Overview
End-to-end system for intelligent supervision of LTE mobile networks.  
From raw OMC counters to real-time operational decision support.

## Dataset
Raw OMC counters from a Senegalese LTE operator.  
📦 [Download on Kaggle](https://www.kaggle.com/datasets/maryemchbila/senegal-lte-kpi-dataset)

- 1,959,516 observations
- 20,250 unique LTE cells
- 10 KPIs: RRC_SR, ERAB_SR, DCR, HOSR, HOSR_InterFreq, HOSR_InterRAT, CSFB_SR, Thrp_DL, Thrp_UL, Cell_Availability

## Notebooks
| Notebook | Description |
|----------|-------------|
| `P2M_Finale.ipynb` | Anomaly detection & KPI prediction models |
| `Streamlit_P2M.ipynb` | Interactive dashboard (Streamlit + ngrok) |

## Models
- **Anomaly Detection** : Isolation Forest + LSTM Autoencoder
- **KPI Prediction** : XGBoost, LightGBM, N-HiTS (stacking)
- **Health Score** : Weighted aggregation 0–100 per cell

## Results
| Model | KPI | R² | MAE |
|-------|-----|----|-----|
| XGBoost + N-HiTS | Thrp_DL | 0.9984 | 0.076 Mbps |
| XGBoost + N-HiTS | Thrp_UL | 0.9902 | 0.037 Mbps |
| LightGBM | RRC_SR | 0.65 | 0.071% |
| XGBoost | DCR | — | 0.020% |

## How to Run
1. Open the notebook in Google Colab
2. Mount your Google Drive and update the dataset path
3. Add your ngrok token in Colab Secrets (`NGROK_TOKEN`)
4. Run all cells

## License
CC BY 4.0
