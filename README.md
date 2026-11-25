# Simple LLM Hardware Benchmarks

Hand-collected `llama-bench` results across consumer GPUs, Apple Silicon and server cards. Only generation speed (tg) and prompt processing (pp). No scripts, no CI — just raw text data.

[![Last update](https://img.shields.io/badge/last%20update-2026--02--15-blue)]() 
[![Benchmarks](https://img.shields.io/badge/benchmarks-47-green)]()
[![License](https://img.shields.io/badge/license-MIT-lightgrey)]()

## How to run a benchmark

1. Install [llama.cpp](https://github.com/ggerganov/llama.cpp)
2. Run this command and save the output into `results/`:

    llama-bench -m your-model.gguf -p 512 -n 128 -ngl 99 -o csv > results/your-gpu.csv

3. Add one row to the tables below and open a pull request.

## Leaderboard

### Qwen2.5-7B Q4_K_M

| Hardware | Backend | VRAM | tg128 (t/s) | pp512 (t/s) |
|---|---|---|---|---|
| RTX 5090 32GB | CUDA | 32 GB | 241.6 | 15380.2 |
| RTX 4090 24GB | CUDA | 24 GB | 179.8 | 11648.4 |
| RTX 4080 Super 16GB | CUDA | 16 GB | 132.4 | 8902.1 |
| RTX 4070 Ti 12GB | CUDA | 12 GB | 98.7 | 6710.5 |
| RTX 3090 24GB | CUDA | 24 GB | 121.3 | 7455.9 |
| RTX 3080 10GB | CUDA | 10 GB | 71.2 | 4980.3 |
| RTX 3060 12GB | CUDA | 12 GB | 49.0 | 3211.7 |
| RX 7900 XTX 24GB | ROCm | 24 GB | 88.5 | 5120.4 |
| RX 7800 XT 16GB | ROCm | 16 GB | 61.3 | 3980.8 |
| Apple M4 Max 40c | Metal | 48 GB | 74.2 | 4102.6 |
| Apple M3 Pro 18c | Metal | 18 GB | 41.8 | 2870.1 |
| Apple M2 Pro 16c | Metal | 16 GB | 29.4 | 2015.3 |
| Apple M1 8c | Metal | 8 GB | 14.1 | 980.6 |

### Llama-3.1-8B Q4_K_M

| Hardware | Backend | VRAM | tg128 (t/s) | pp512 (t/s) |
|---|---|---|---|---|
| RTX 5090 32GB | CUDA | 32 GB | 219.4 | 14002.7 |
| RTX 4090 24GB | CUDA | 24 GB | 163.2 | 10950.8 |
| RTX 4080 Super 16GB | CUDA | 16 GB | 118.9 | 8120.4 |
| RTX 4070 Ti 12GB | CUDA | 12 GB | 87.5 | 6011.2 |
| RTX 3090 24GB | CUDA | 24 GB | 110.1 | 6890.5 |
| RTX 3060 12GB | CUDA | 12 GB | 43.7 | 2980.9 |
| RX 7900 XTX 24GB | ROCm | 24 GB | 79.8 | 4770.1 |
| Apple M4 Max 40c | Metal | 48 GB | 66.9 | 3801.4 |
| Apple M3 Pro 18c | Metal | 18 GB | 37.2 | 2610.8 |
| Apple M1 8c | Metal | 8 GB | 12.4 | 890.2 |

### Mistral-7B-Instruct Q4_K_M

| Hardware | Backend | VRAM | tg128 (t/s) | pp512 (t/s) |
|---|---|---|---|---|
| RTX 5090 32GB | CUDA | 32 GB | 248.1 | 15901.3 |
| RTX 4090 24GB | CUDA | 24 GB | 184.5 | 11980.6 |
| RTX 4080 Super 16GB | CUDA | 16 GB | 136.7 | 9140.2 |
| RTX 3090 24GB | CUDA | 24 GB | 124.9 | 7620.8 |
| RTX 3060 12GB | CUDA | 12 GB | 50.2 | 3290.4 |
| RX 7900 XTX 24GB | ROCm | 24 GB | 90.6 | 5230.7 |
| Apple M4 Max 40c | Metal | 48 GB | 76.1 | 4210.5 |
| Apple M2 Pro 16c | Metal | 16 GB | 30.1 | 2060.9 |

### Gemma-2-9B Q4_K_M

| Hardware | Backend | VRAM | tg128 (t/s) | pp512 (t/s) |
|---|---|---|---|---|
| RTX 5090 32GB | CUDA | 32 GB | 198.3 | 12800.4 |
| RTX 4090 24GB | CUDA | 24 GB | 147.6 | 9880.1 |
| RTX 4080 Super 16GB | CUDA | 16 GB | 108.9 | 7410.6 |
| RTX 3090 24GB | CUDA | 24 GB | 99.4 | 6180.2 |
| RTX 3060 12GB | CUDA | 12 GB | 40.1 | 2710.5 |
| RX 7800 XT 16GB | ROCm | 16 GB | 50.8 | 3390.7 |
| Apple M4 Max 40c | Metal | 48 GB | 60.2 | 3450.9 |

### Llama-3.1-70B Q4_K_M (multi-GPU / large VRAM)

| Hardware | Backend | VRAM | tg128 (t/s) | pp512 (t/s) |
|---|---|---|---|---|
| 2x RTX 5090 | CUDA | 64 GB | 58.4 | 4210.7 |
| 2x RTX 4090 | CUDA | 48 GB | 44.1 | 3380.2 |
| RTX 6000 Ada 48GB | CUDA | 48 GB | 39.7 | 3010.5 |
| 2x RTX 3090 | CUDA | 48 GB | 31.2 | 2490.8 |
| Mac Studio M2 Ultra 192GB | Metal | 192 GB | 18.6 | 1420.3 |
| CPU only (Ryzen 9 7950X, 128GB DDR5) | CPU | 0 GB | 2.1 | 88.4 |

## Charts

![RTX 4090 llama-bench table](charts/rtx4090-table.png)
![RTX 3060 llama-bench table](charts/rtx3060-table.png)
![Apple M2 Pro llama-bench table](charts/m2-table.png)
![RTX 5090 llama-bench table](charts/rtx5090-table.png)
![RX 7900 XTX llama-bench table](charts/rx7900xtx-table.png)

## Rules

- Only the `t/s` column from `llama-bench` default output.
- Always use `-ngl 99` for GPU runs, otherwise speed is meaningless.
- Never mix quantizations in one table (Q4_0 vs Q4_K_M are different).
- Never compare different model sizes in one table (7B vs 14B).
- "not measured" in pp512 means the run was skipped.
- Multi-GPU rows assume tensor split across all cards.

## Raw data

See the `results/` folder. See `results/notes.txt` for caveats.

## Contributing

Run the command, drop the CSV into `results/`, add one row to the relevant table, open a PR. That's it.
