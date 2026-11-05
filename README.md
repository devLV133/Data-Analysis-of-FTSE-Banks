# Bank Price Comparison Pilot

A Python notebook that retrieves adjusted daily prices, aligns trading dates across selected UK-listed banks and produces a comparison table and chart. An optional Gradio chat explains the supplied price evidence using OpenAI.

## What it does

- Covers Barclays, HSBC, Lloyds, NatWest, Standard Chartered, Investec and Lion Finance Group.
- Cleans missing, invalid, non-positive and non-finite prices, normalises trading dates and removes duplicate dates.
- Uses the same overlapping dates for every bank in a comparison.
- Shows adjusted-close returns, observation counts, actual start/end dates and source links.
- Plots each bank's adjusted-close performance with a common starting value of 100.
- Provides optional AI explanations with selected-bank and period controls and recent conversation context.

## Run

1. Open [AI_Banking_Research_Mini (1).ipynb](AI_Banking_Research_Mini%20%281%29.ipynb) in Google Colab or Jupyter.
2. Run the setup cell to install pandas, matplotlib, yfinance, openai and Gradio.
3. Run the configuration cell. Press Enter at the API-key prompt for data-only use, or supply a runtime key for AI chat. Never save the key in the notebook.
4. Run **Public market data**, then **Example comparison**. Defaults are Barclays and HSBC over three months. Supported periods are `1mo`, `3mo`, `6mo` and `1y`.
5. To use chat, run **Basic AI response** and **Chat interface**. Set `OPENAI_MODEL` to a model available to your OpenAI account before running configuration. The notebook's model default is not an availability check.
6. In Colab, choose a password when prompted and open the generated link using username `researcher`. Keep the runtime running. Local Jupyter displays the interface locally.

Change the bank/period controls to change comparison scope and clear the chat afterwards. Typing different banks or dates in a question does not change those controls. Each AI question retrieves fresh price evidence and may incur OpenAI API charges.

## Calculations and scope

Return is `(last adjusted close / first adjusted close - 1) × 100`, using shared trading dates. Adjusted closes already account for splits and dividends. The comparison stops with an explanation if a selected bank has no usable data or fewer than two shared dates remain.

This repository contains the price-comparison pilot. It does not implement news retrieval, sentiment analysis, portfolio allocation, fundamental analysis, index/currency context or the full dissertation research workflow. AI explanations are not independently verified.

## Troubleshooting

- Missing packages or functions: run preceding cells in order.
- No usable data: check the connection, retry later or select another bank/period.
- AI request fails: check your model selection, API access and connection.
- Embedded chat does not open: use the generated Gradio link.

Python in Jupyter/Colab and internet access are required. No GPU is needed. Clear outputs before sharing a run containing private questions or session links.


