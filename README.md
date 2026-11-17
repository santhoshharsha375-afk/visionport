# VisionPort

A GPU-trained, GPU-served vision system for Indian traffic.

## Current version

v0.1 - pretrained YOLOv8n demo, FastAPI gateway, request trace

## Codebase tour

| Part | Location | Will contain |
|---|---|---|
| Data pipeline | `data/`, `train/dataset.py` | Loading COCO-format images and annotations, collate function |
| Training loop | `train/train.py` | Forward, loss, backward, optimiser step, scheduler, checkpointing |
| Architecture file | `train/model.py` | YOLO-style backbone, neck and head |
| Evaluation harness | `eval/` | mAP@0.5, latency and throughput measurement |
| Optimisation script | `optimise/` | ONNX export, TensorRT build, INT8 calibration |
| Triton config | `serve/triton/` | Model repository and `config.pbtxt` |

## Environment

Pinned package versions are in `requirements.txt`. Recreate with:

```
pip install -r requirements.txt
```

## How to run

```
uvicorn serve.gateway:app --reload
uvicorn serve.gateway_trace:app --reload
```

Then open `http://127.0.0.1:8000/docs`. The Streamlit demo is `app.py`.

## Known limitations

- Pretrained on COCO, not on Indian traffic. No auto-rickshaw class.
