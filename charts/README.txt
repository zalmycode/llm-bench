Charts folder
=============

Put terminal screenshots of llama-bench output here:

- rtx5090-table.png    -> screenshot of llama-bench markdown table on RTX 5090
- rtx4090-table.png    -> screenshot of llama-bench markdown table on RTX 4090
- rtx3060-table.png    -> screenshot of llama-bench markdown table on RTX 3060
- rx7900xtx-table.png  -> screenshot of llama-bench markdown table on RX 7900 XTX
- m2-table.png         -> screenshot of llama-bench markdown table on Apple M2 Pro

How to get a screenshot:
1. Run: llama-bench -m your-model.gguf -p 512 -n 128 -ngl 99
2. llama-bench prints a markdown table in the terminal.
3. Take a screenshot of that table and save it here.
4. Reference it in README.md as:
   ![RTX 4090 table](charts/rtx4090-table.png)
