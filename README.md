# LeWitt-Bench

Instruction-based art offers a rare opportunity to test models’ ability to follow explicit, rule-based instructions—a core but often overlooked aspect of visual reasoning. We build upon [Maximal Margin’s](https://github.com/infoxiao/lewitt_instructions) 2023 study to explore how faithfully models execute instructions in the domain of visual art and reveal whether technical progress has led to genuine compositional improvement. 

The resulting [LeWitt-Bench](https://www.designarena.ai/leaderboard/lewitt-bench) is a crowdsourced, subjective benchmark that collects human consensus—a noisy but critical vector of measuring what makes “good art”. A post-analysis will be conducted comparing live, subjective results against the verifiable domain of prompt adherence, marking a structured attempt to evaluate a non-verifiable task. Our motivation to create this benchmark can be found [here](https://notes.designarena.ai/the-prompt-is-not-the-picture/).

<img width="4532" height="2146" alt="image" src="https://github.com/user-attachments/assets/c04a392c-1f23-47fa-beb6-b18f440688b3" />

The following code generates a dataset created by text-to-image models on Sol LeWitt's instruction-based art (75 instruction-image pairs). Data source: a subset of [Sol LeWitt: A Wall Drawing Retrospective](https://massmoca.org/sol-lewitt/) at MASS MoCA, spanning 1969 to 2007.

## Quick Start

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Set up API keys in `.env`:
```bash
OPENAI_API_KEY=your_key
GOOGLE_API_KEY=your_key
BLACK_FOREST_LABS_API_KEY=your_key
RECRAFT_API_KEY=your_key
IDEOGRAM_API_KEY=your_key
FAL_API_KEY=your_key
```

3. Run the notebook:
```bash
jupyter notebook get_images.ipynb
```

## Supported Models

| Model                                                    | Company / Organization                       |
| -------------------------------------------------------- | -------------------------------------------- |
| GPT-Image-1                                              | OpenAI                                       |
| Imagen 4 Ultra / Imagen 4                                | Google / DeepMind    |
| Imagen 4 Generate Preview                                | Google / DeepMind |
| Imagen 3 Generate 002                                    | Google / DeepMind                            |
| FLUX.1 Kontext Max / FLUX.1 Kontext Pro / FLUX.1 Kontext | Black Forest Labs                     |
| Recraft V3                                               | Recraft                               |
| Ideogram 3.0                                             | Ideogram AI                                  |
| Qwen Image                                               | Alibaba                          |


## Usage

Test a single instruction:
```python
# Cell 18 in notebook - tests all providers with first instruction
```

Batch process all instructions:
```python
# Cell 19 in notebook - uncomment and configure providers
```

Parallel generation (Imagen models):
```python
# Cell 20 in notebook - generates all images in parallel
```

---

## About Instruction-Based Art

"Influenced by his time working in an architect's office, LeWitt would use assistants to produce three-dimensional works he called "structures." He wrote: "An architect doesn't go off with a shovel and dig his foundation and lay every brick. He's still an artist." Instead of executing the works of art himself, LeWitt comes up with an idea or plan for his art, usually a set of simple instructions—sometimes with line drawings. He then hands over the written plan to his assistants, and they construct the work. LeWitt's instructions are both specific and open-ended so that the resulting work of art varies according to the interpretation made by the draftsperson producing the work of art." — [Sol LeWitt's Concepts and Structures](https://www.nga.gov/learn/teachers/lessons-activities/new-angles/sol-lewitt.html)

## Attribution

This project was inspired by and initially based on [lewitt_instructions](https://github.com/infoxiao/lewitt_instructions) by Maximal Margin. 

We're grateful to Maximal Margin for her invitation to build on her foundational work. The original project is available under MIT License [here](https://github.com/infoxiao/lewitt_instructions).

## Updates

### Oct 5, 2025
Added support for the following image generation providers:

| Model                                                    | Company / Organization                       |
| -------------------------------------------------------- | -------------------------------------------- |
| GPT-Image-1                                              | OpenAI                                       |
| Imagen 4 Ultra / Imagen 4                                | Google / DeepMind    |
| Imagen 4 Generate Preview                                | Google / DeepMind |
| Imagen 3 Generate 002                                    | Google / DeepMind                            |
| FLUX.1 Kontext Max / FLUX.1 Kontext Pro / FLUX.1 Kontext | Black Forest Labs                     |
| Recraft V3                                               | Recraft                               |
| Ideogram 3.0                                             | Ideogram AI                                  |
| Qwen Image                                               | Alibaba                          |



### Oct 15, 2023
Added manual evaluation results of DALL·E 3, Midjourney, and [Stable Diffusion 2.1](https://huggingface.co/spaces/stabilityai/stable-diffusion). Folder `20231015_eval` contains the generated images and associated DALL·E 3 prompts.
