# Experiment Design

This document describes the experimental design used to evaluate a large language model (LLM) as a semantic compiler for floor plan representations. The experiments focus on translating floor plan information into the Generic Role–Entity-Based (GREB) thought language under different input conditions.

## Objective

The primary objective of the experiments is to assess whether an LLM can reliably generate a formal GREB representation of a floor plan when spatial information is provided:

1. Implicitly, through a raster floor plan image.
2. Explicitly, through a structured natural-language description.

The experiments are designed to isolate the role of perception versus language understanding in the generation of topologically correct GREB code.

## Scope and Constraints

- The experiments are limited to residential and institutional floor plans from Cairo, used as a controlled case study.
- Only symbolic topology (rooms, walls, doors, access, adjacency) is evaluated.
- No geometric measurements, scaling, or metric validation are performed.
- No external vision models, CAD tools, or geometric solvers are used.

## Model Configuration

All experiments were conducted using OpenAI’s ChatGPT large language model in a text-only interaction setting. The model was configured via a system prompt to act as a “GREB compiler,” constrained to output only syntactically valid GREB code following a predefined EBNF grammar.

The grammar and template used by the model are provided in the `greb/` directory.

## Experimental Setups

### Experiment 1: Image-Based Prompting (Image → Text → GREB)

In this setup, the LLM was provided directly with a floor plan image and instructed to first describe the layout and then generate GREB code based on that description.

This experiment evaluates the model’s ability to infer spatial structure from visual input and formalize it without explicit textual guidance.

### Experiment 2: Text-Based Prompting (Text → GREB)

In this setup, a detailed, manually authored textual description of the floor plan was provided as input. The description explicitly specifies rooms, walls, door locations, adjacencies, and circulation structure.

The LLM was then instructed to translate this description directly into GREB format.

This experiment evaluates the model’s performance as a semantic compiler under controlled, ambiguity-free input conditions.

## Evaluation Criteria

The generated GREB outputs are evaluated qualitatively using the following criteria:

- **Syntactic correctness**: Compliance with the GREB EBNF grammar.
- **Identifier consistency**: Stable and consistent naming of rooms, walls, and doors.
- **Topological fidelity**: Preservation of stated adjacencies and access paths.
- **Reproducibility**: Similar outputs across repeated runs with identical inputs.

Geometric accuracy is intentionally excluded, as GREB encodes symbolic topology rather than metric geometry.
