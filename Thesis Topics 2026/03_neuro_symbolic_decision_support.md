# Bachelor Thesis Topic 3

## A Neuro-Symbolic Decision-Support Architecture for Grounded Aviation Scenario Recommendations

## Background

A general-purpose language model may generate fluent recommendations, but it is not a reliable calculation or rule-execution engine. A safer research direction is to combine language models with deterministic rules and grounded information.

This thesis is part of the proposed **AviaReason** research project. AviaReason is envisioned as a pilot-controlled application that receives a scenario and provides one concise, grounded and traceable recommendation.

The proposed architecture separates responsibilities:

- the LLM interprets and explains language;
- the RAG component retrieves supporting evidence;
- the rule engine evaluates explicit decision conditions;
- the user remains responsible for the final decision.

## Aim

The aim is to design, implement and evaluate a small neuro-symbolic Decision Support System that combines structured scenario data, retrieved evidence, deterministic rules and an LLM-generated explanation.

The study should examine whether this hybrid architecture is more consistent and traceable than an LLM-only approach.

## Possible Research Questions

1. Does a hybrid LLM and rule-based architecture produce more consistent results than an LLM-only system?
2. Can deterministic rules reduce unsupported recommendations?
3. How should the system behave when information is incomplete, conflicting or outdated?
4. How can each recommendation be linked to the facts, rules and sources supporting it?
5. Which conditions should require the system to abstain?
6. Does RAG improve explanation grounding when the decision itself is produced by rules?

The student should select a manageable subset of these questions.

## Proposed Architecture

```text
Natural-language scenario
          |
          v
Structured scenario data
          |
          +-------------------+
          |                   |
          v                   v
Retrieved evidence      Deterministic rules
          |                   |
          +---------+---------+
                    |
                    v
          Validated decision state
                    |
                    v
          LLM-generated explanation
```

## Example Synthetic Rule

```text
IF destination_condition = outside_configured_boundary
AND protected_scenario_limit = reached
AND alternate_suitability = verified
THEN recommendation_state = protective_action
ELSE recommendation_state = verification_required
```

This rule is a synthetic research example, not an approved operational aviation rule.

## Proposed Prototype

The prototype should:

- receive structured scenario data;
- retrieve or receive relevant grounded evidence;
- evaluate a small set of transparent deterministic rules;
- produce a recommendation state;
- generate a short explanation that cannot contradict the rule result;
- show the supporting facts, rules and sources;
- abstain when essential information is missing.

## Comparative Experiment

A useful comparison would include:

1. LLM only;
2. RAG plus LLM;
3. structured scenario plus RAG plus deterministic rules plus LLM explanation.

All configurations should be tested against the same synthetic scenario set.

## Suggested Technical Areas

- Python
- rule engines or a custom rules layer
- JSON Schema or Pydantic
- finite-state machines
- decision tables
- RAG
- open-source LLMs
- explanation generation
- provenance and audit logging
- automated testing

## Research Method

A design-science and comparative experimental approach is suitable.

Suggested stages:

1. Review literature on Decision Support Systems, neuro-symbolic AI and grounded LLMs.
2. Define a small synthetic decision domain.
3. Design the architecture and rule representation.
4. Create a scenario and reference-decision dataset.
5. Implement the comparison configurations.
6. Measure consistency, grounding and abstention behaviour.
7. Analyse failure cases and architectural trade-offs.

## Evaluation

Possible measures include:

- agreement with reference decision states;
- consistency across repeated runs;
- unsupported recommendation rate;
- rule-application accuracy;
- explanation-to-rule consistency;
- traceability completeness;
- correct abstention rate;
- false acceptance and false rejection rates;
- processing latency.

## Expected Deliverables

- literature review;
- documented system architecture;
- small synthetic rule and scenario set;
- working Decision Support System prototype;
- comparison with simpler LLM configurations;
- evaluation results and failure analysis;
- source code and installation instructions;
- recommendations for future AviaReason integration.

## Scope and Limitations

- Use synthetic decision rules and training scenarios.
- Do not claim that the rules are approved for cockpit operations.
- Do not reproduce proprietary manufacturer or operator procedures.
- Do not perform real aircraft performance, fuel or mass-and-balance calculations.
- Do not connect to aircraft systems.
- The prototype is for research and training only.

## Expected Contribution to AviaReason

This thesis will provide the **decision engine and assurance boundary**. It should demonstrate how a recommendation can be generated by transparent rules while an LLM is limited to interpretation and explanation.

## Suitable Student Profile

This topic is suitable for a student interested in:

- software architecture;
- Decision Support Systems;
- rule engines;
- neuro-symbolic AI;
- backend development;
- testing and system reliability.
