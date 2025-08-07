# FinInsights – A Simple LLM-Powered Financial Assistant

This project demonstrates how to use OpenAI’s large language models (LLMs) to generate natural language insights from portfolio data. The goal is to explore how models like GPT-4 can assist with common investment-related tasks by interpreting structured datasets and answering questions in plain English.

## What It Does

The notebook sends tabular data (e.g. portfolio holdings, fundamentals, business descriptions) to the OpenAI API and asks natural language questions like:
- Which sectors have the highest allocations in the portfolio?
- What are the top 3 performing companies?
- What companies are most similar to Alibaba based on their business description?
- Are there any patterns among the strong performers?

The model responds with a concise summary based solely on the data provided.

## How It Works

- The `ask_fininsights()` function formats the DataFrame and prompt.
- A request is made to the OpenAI API via `requests.post()` using the Chat Completions endpoint.
- Proxy support is included for use behind a firewall.

## Example Output

> **Q:** What are top 3 performing companies (with their YTD Performance)?  
> **A:** The top three performing companies based on the Year-to-Date (YTD) performance are:
>
> 1. Delta Electronics, Inc. with a YTD Performance of 0.595656
> 2. SK hynix Inc. with a YTD Performance of 0.587134
> 3. Xiaomi Corporation Class B with a YTD Performance of 0.548867

> **Q:** What are the 3 most similar companies to Alibaba based on business description?  
> **A:** Based on the business description, the three most similar companies to Alibaba Group Holding Limited are:
>
> 1. Tencent Holdings Ltd - Similar to Alibaba, Tencent provides a range of online and mobile services, including fintech and business services. Both companies are heavily involved in the technology sector and are based in China.
> 2. JD.com, Inc. Class A - JD.com is also a technology-driven E-commerce company, similar to Alibaba. Both companies are involved in the sale of various products and services online, and are based in China.
> 3. Meituan Class B - Meituan, like Alibaba, provides a technology platform that connects consumers and merchants. It operates in similar segments such as food delivery, in-store, hotel, and travel. This company is also based in China.

## Limitations

- The model can sometimes only "see" a subset of the data (due to token limits), which may bias the results.
- Numerical calculations are sometimes inaccurate or overly simplified.
- The model doesn’t access real-time market data or news — it only uses the input table.
- Business descriptions with long text fields may cause token overflow.

## Future Improvements

- Embed pre-calculated metrics to guide the LLM.
- Use vector similarity for more rigorous comparisons.
- Combine structured data with scraped news or earnings commentary.
- Use OpenAI's function-calling or retrieval features for dynamic question answering.

Author: Richard Fairbairn 
Last updated: August 2025
