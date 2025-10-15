# LLM Summary Internal vs External

This repository implements a controlled experiment comparing Large Language Models' ability to recall book plots from parametric memory (internal knowledge) versus their ability to summarize provided text (external knowledge).

## Overview

The experiment tests whether LLMs can accurately recall complete book plots from their training data, or if they require the actual text to produce high-quality summaries. Two experimental conditions are applied to 25 classic literary works:

- **Internal Knowledge**: Provides only book title + author name
- **External Knowledge**: Provides full book text

Each condition generates 5 independent runs across 2 models (GPT-4.1 and Gemini-2.5-Flash) and two temperature (0.4 and 0.9); the resulting summaries are then evaluated by both models.

## Repository Structure

```
books/                          # Source texts (25 classic works)
├── {title}-{author}.txt

Results_internal/               # Internal knowledge summaries
├── books_summaries_generator_gpt-4.1_temperature_0.9_{1-5}.csv
├── books_summaries_generator_gemini-2.5-flash_temperature_0.9_{1-5}.csv
└── Evaluated/                  # With quality scores

Results_external/               # External knowledge summaries  
├── books_summaries_generator_gpt-4.1_temperature_0.4_{1-5}.csv
├── books_summaries_generator_gemini-2.5-flash_temperature_0.4_{1-5}.csv
└── Evaluated/                  # With quality scores

Call_openai_internal.ipynb      # GPT internal generation
Call_openai.ipynb               # GPT external generation
Call_google_internal.ipynb      # Gemini internal generation
Call_google.ipynb               # Gemini external generation
Evaluation.ipynb                # Evaluate summaries
Extract_results.ipynb           # Extract the scores using gpt-4o-mini
Plot.ipynb                      # Generate figures
```

