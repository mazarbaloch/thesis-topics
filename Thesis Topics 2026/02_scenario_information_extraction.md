# Bachelor Thesis Topic 2

## Structured Extraction of Threats, Constraints and Decision Conditions from Natural-Language Aviation Scenarios

## Background

A pilot may describe an operational situation in unstructured language. Before a decision-support system can use that description, it must convert the input into a structured and machine-readable representation.

This thesis is part of the proposed **AviaReason** research project. AviaReason is envisioned as an on-device application that receives a pilot-entered scenario, identifies the most relevant information and produces a grounded, concise and structured recommendation.

A central research challenge is determining whether a language model can reliably distinguish between reported facts, assumptions, threats, constraints, missing information, current plans and decision conditions.

## Aim

The aim is to design, implement and evaluate an LLM-based information-extraction component that converts natural-language aviation scenarios into validated structured output, such as JSON.

The emphasis is scenario understanding and structured extraction. The prototype will not make operational decisions.

## Possible Research Questions

1. How accurately can a language model identify facts, assumptions, threats, constraints and missing information in aviation scenarios?
2. Which prompting approach produces the most reliable structured output?
3. Does few-shot prompting perform better than zero-shot prompting?
4. How reliably can the model distinguish pilot-reported information from verified information?
5. Can the model recognise ambiguous input and request clarification instead of guessing?
6. How do different open-source language models compare on this task?

The student may narrow or refine these questions with the supervisor.

## Proposed Information Schema

The student should design and justify a schema similar to the following:

```json
{
  "flight_phase": "cruise",
  "reported_facts": [],
  "verified_facts": [],
  "assumptions": [],
  "threats": [],
  "constraints": [],
  "missing_information": [],
  "current_plan": "",
  "decision_condition": "",
  "available_alternative": "",
  "clarification_required": false
}
```

Each extracted item should ideally include its source text and verification status.

## Example Input

> Frankfurt visibility is deteriorating. We expect another 20 minutes of holding. Düsseldorf may also become congested. Our current plan is to continue until the next weather update.

## Example Output

```json
{
  "reported_facts": [
    {
      "claim": "Frankfurt visibility is deteriorating",
      "status": "pilot_reported"
    },
    {
      "claim": "Expected holding time is 20 minutes",
      "status": "pilot_reported"
    }
  ],
  "assumptions": [
    "Düsseldorf remains available"
  ],
  "threats": [
    "Destination availability may deteriorate",
    "Additional holding may reduce available options"
  ],
  "missing_information": [
    "Current destination weather",
    "Applicable operational limit",
    "Verified alternate availability"
  ],
  "current_plan": "Continue until the next weather update",
  "clarification_required": true
}
```

## Suggested Technical Areas

- Python
- structured prompting
- JSON Schema or Pydantic validation
- open-source LLMs
- constrained decoding
- function calling or tool calling
- prompt templates
- few-shot learning
- local inference frameworks
- optional speech-to-text input

## Research Method

A design-science and experimental evaluation approach is suitable.

Suggested stages:

1. Review research on information extraction, structured LLM output and aviation decision-making concepts.
2. Define a clear annotation scheme.
3. Create a small set of synthetic aviation scenarios.
4. Have the scenarios manually annotated to create reference answers.
5. Implement and compare two or more extraction approaches.
6. Evaluate output quality and analyse common failure types.

## Evaluation

Possible measures include:

- precision, recall and F1 score for extracted fields;
- JSON-validity rate;
- schema-completion rate;
- incorrect or unsupported field rate;
- ambiguity-detection rate;
- clarification quality;
- consistency across repeated runs;
- processing latency.

A qualitative error analysis should identify cases such as:

- facts incorrectly classified as assumptions;
- assumptions incorrectly classified as verified facts;
- missing threats;
- invented values;
- incorrect units;
- failure to ask for clarification.

## Expected Deliverables

- literature review;
- structured aviation scenario schema;
- annotated test dataset;
- working scenario-extraction prototype;
- comparison of prompting or model alternatives;
- quantitative evaluation and error analysis;
- source code and instructions;
- recommendations for integration into AviaReason.

## Scope and Limitations

- Use synthetic or properly authorised scenarios.
- Do not infer a pilot's internal thoughts, emotions or intentions.
- Analyse only what is explicitly present in the input.
- Do not generate operational values that were not provided.
- Do not connect the system to aircraft or live operational systems.
- Treat all output as research and training material.

## Expected Contribution to AviaReason

This thesis will provide the **scenario-understanding and structured-input component**. Its output should be suitable for later use by RAG, deterministic decision rules and the structured recommendation interface.

## Suitable Student Profile

This topic is suitable for a student interested in:

- natural language processing;
- prompt engineering;
- structured data;
- open-source LLMs;
- software testing;
- dataset annotation and evaluation.
