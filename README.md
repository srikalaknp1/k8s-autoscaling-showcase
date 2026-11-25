# AI-Based Kubernetes Auto-Scaling Optimizer

MCA project by Srikala Kodchwadkar.

A predictive auto-scaler for Kubernetes. It forecasts CPU load about 1 minute ahead using a Random Forest model and adds pods before the load arrives. I compared it with the standard reactive Kubernetes HPA.

## Results (cycles 2 and 3 of each run)

| Measure | HPA | Predictive |
|---|---|---|
| Average pods | 2.34 | 1.81 |
| Seconds to 2 pods | +15 (after load) | -30 (before load) |
| Overloaded steps | 3 | 5 |

- 22.6% fewer pods on average.
- Pods were added about 45 seconds earlier than HPA.
- Limitation: more overloaded steps (5 vs 3). A safety margin or a better forecast is future work.

## What I built
- Local Kubernetes cluster (kind) with Docker
- Random Forest forecasting model (Python, scikit-learn)
- Predictive scaler and comparison script
- FastAPI backend with live dashboard

## Tech
Python, Kubernetes, Docker, FastAPI, scikit-learn, pandas

Source code is available on request.
