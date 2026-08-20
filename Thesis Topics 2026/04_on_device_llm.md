# Bachelor Thesis Topic 4

## Performance Evaluation of On-Device Small Language Models for Offline Aviation Scenario Processing

## Background

The long-term AviaReason concept requires its core language-processing functions to operate locally without continuous cloud access. On-device deployment may improve data localisation and offline availability, but small language models have limitations in quality, memory use, storage, latency, power consumption and structured-output reliability.

This thesis is part of the proposed **AviaReason** research project. It investigates which bounded language tasks can be performed successfully by a small model on a laptop, mobile device or other edge platform.

## Aim

The aim is to implement and compare selected on-device small language models for two or three clearly defined aviation scenario-processing tasks.

The project evaluates engineering feasibility. It does not attempt to build the complete AviaReason application or validate operational cockpit use.

## Candidate Tasks

The student should select a manageable subset, for example:

- scenario classification;
- aviation entity extraction;
- fact and assumption separation;
- threat identification;
- structured JSON generation;
- clarification-question generation;
- summarisation of retrieved passages.

## Possible Research Questions

1. Which on-device model offers the best balance between task quality and resource consumption?
2. How does quantisation affect structured-output accuracy?
3. Can a local model achieve acceptable response latency for an interactive application?
4. How does local inference compare with a larger reference model on the same dataset?
5. Which AviaReason language tasks are feasible on-device?
6. Which tasks should remain deterministic rather than model-generated?

The student should refine the questions according to the selected hardware and tasks.

## Proposed Prototype

The prototype should:

- load a small or quantised language model locally;
- operate without internet access during inference;
- accept a synthetic pilot scenario;
- perform the selected bounded tasks;
- produce constrained output;
- record latency and resource usage;
- store test results for comparison.

## Possible Model and Runtime Categories

The student may investigate:

- compact open-source instruct models;
- quantised GGUF models;
- llama.cpp or a comparable local runtime;
- ONNX Runtime;
- mobile or edge inference frameworks;
- CPU, GPU or neural-processing-unit execution, depending on available hardware.

The final selection should be justified by licensing, hardware compatibility and thesis scope.

## Research Method

An experimental benchmarking approach is suitable.

Suggested stages:

1. Review research on small language models, edge AI and model compression.
2. Select two or more candidate models or quantisation configurations.
3. Define two or three bounded language tasks.
4. Create a fixed synthetic scenario dataset and reference outputs.
5. Implement a local inference test application.
6. Compare model quality and resource use.
7. Analyse failure modes and recommend a deployment configuration.

## Evaluation

Possible measures include:

- task accuracy, precision, recall or F1;
- JSON-validity rate;
- schema-completion rate;
- unsupported-output rate;
- response latency;
- time to first token;
- tokens per second;
- peak memory use;
- model storage size;
- CPU or GPU utilisation;
- energy or battery consumption, if reliably measurable;
- offline completion rate;
- crash or failure rate.

## Expected Deliverables

- literature review;
- documented hardware and software setup;
- local inference prototype;
- synthetic test dataset;
- comparison of selected models or quantisation levels;
- performance and quality results;
- failure analysis;
- source code and deployment instructions;
- recommendation for the AviaReason on-device architecture.

## Scope and Limitations

- Limit the project to two or three language tasks.
- Use synthetic or authorised research data.
- Do not connect the prototype to aircraft systems.
- Do not claim operational cockpit suitability.
- Do not assume that local processing alone makes a system safe.
- Check and document the licences of all models and frameworks used.

## Expected Contribution to AviaReason

This thesis will identify the **feasible on-device model, runtime and bounded language functions** for a future offline prototype. It should also identify tasks for which local models are not sufficiently reliable.

## Suitable Student Profile

This topic is suitable for a student interested in:

- machine learning engineering;
- mobile or edge computing;
- open-source language models;
- performance benchmarking;
- model quantisation;
- systems programming or application development.
