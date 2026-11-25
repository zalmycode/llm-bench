Results folder
==============

Each CSV file is raw output from:

    llama-bench -m <model> -p 512 -n 128 -ngl 99 -o csv

Columns:
  model         - gguf file name
  size          - model size on disk
  params        - parameter count
  backend       - CUDA / Metal / ROCm / CPU
  n_gpu_layers  - number of layers offloaded to GPU (99 = all)
  test          - pp512 (prompt processing) or tg128 (generation)
  t/s           - speed in tokens per second

File naming: <gpu-name>.csv
Examples:
  rtx5090.csv
  rtx4090.csv
  rtx3060.csv
  rx7900xtx.csv
  m2-mac.csv

How to add a new file:
1. Run llama-bench with -o csv
2. Save output as results/<your-gpu>.csv
3. Add a row to the matching table in README.md
4. Open a pull request
