# Bachelor Thesis Topic 5

## Design and Evaluation of Structured, Source-Traceable LLM Outputs for Safety-Critical Decision Support

## Background

A decision-support system may retrieve correct information and apply valid rules but still fail if its output is too long, ambiguous or difficult to interpret. A pilot-facing application should present one clear recommendation, a short rationale, the critical checks, the supporting evidence and the reassessment condition.

This thesis is part of the proposed **AviaReason** research project. It focuses on the design, validation and usability of structured recommendations rather than on determining the operationally correct aviation action.

## Aim

The aim is to design and evaluate a structured output schema and user interface for concise, grounded and traceable decision-support responses.

The project should investigate how constrained output and evidence linking can improve clarity, consistency and recognition of uncertainty.

## Possible Research Questions

1. Which output structure best supports rapid and accurate comprehension?
2. Can constrained generation and schema validation prevent malformed or incomplete responses?
3. How can every stated reason be linked to retrieved evidence or a deterministic rule?
4. How should confidence, uncertainty and abstention be displayed?
5. Does a single prioritised recommendation improve comprehension compared with an unprioritised option list?
6. How do concise and expanded views affect task completion time and perceived workload?

The student may choose a technical, user-interface or mixed emphasis.

## Proposed Response Schema

```json
{
  "response_state": "red",
  "recommendation": "Divert to the verified suitable alternate",
  "reasons": [
    {
      "text": "Destination condition is outside the configured scenario boundary",
      "evidence_id": "evidence-01"
    },
    {
      "text": "Additional delay exceeds the protected scenario limit",
      "rule_id": "rule-02"
    }
  ],
  "critical_checks": [
    "Confirm that alternate information remains current",
    "Cross-check the applicable value using the approved source"
  ],
  "confidence": "high",
  "reassess_when": "Alternate suitability changes",
  "sources": [],
  "limitations": "Training scenario only"
}
```

## Proposed Response States

### Green: Supported continuation

A clearly supported continuation recommendation with a defined review point.

### Amber: Verification required

The system cannot produce a supported operational recommendation because information is missing, inconsistent, ambiguous or stale.

### Red: Protective recommendation

A configured scenario boundary has been reached and the available grounded information supports a protective response.

These colours and labels are research design proposals and are not approved aviation alerting standards.

## Proposed Prototype

The prototype should include:

- a schema-validated recommendation object;
- concise and expanded output views;
- one prioritised recommendation;
- a maximum of a few decisive reasons;
- evidence and rule links;
- critical verification actions;
- a reassessment condition;
- a visible uncertainty or abstention state;
- validation that required fields cannot be silently omitted.

## Suggested Technical Areas

- frontend application development;
- JSON Schema or Pydantic;
- constrained structured generation;
- UI/UX prototyping;
- explainable AI;
- evidence highlighting;
- usability testing;
- accessibility;
- auditability and provenance.

## Research Method

A design-science approach combined with a usability study is suitable.

Suggested stages:

1. Review research on explainable AI, decision-support interfaces and structured LLM output.
2. Define the output schema and information hierarchy.
3. Design at least two interface alternatives.
4. Use synthetic scenario recommendations with predetermined reference content.
5. Conduct a small user study or expert review.
6. Compare clarity, comprehension, time and recognition of uncertainty.
7. Refine the design based on the findings.

## Evaluation

Possible measures include:

- time to identify the recommendation;
- comprehension accuracy;
- source-location success;
- recognition of uncertainty or abstention;
- perceived clarity;
- perceived workload;
- user preference;
- schema-validity rate;
- missing-field rate;
- unsupported-reason rate;
- consistency between concise and expanded views.

If pilots are not available, the student may conduct the first usability study with general users while clearly documenting that this does not validate cockpit usability.

## Expected Deliverables

- literature review;
- structured recommendation schema;
- interface requirements;
- working UI prototype;
- synthetic scenario and response set;
- usability or expert-evaluation results;
- source code and design documentation;
- recommendations for future pilot-centred testing and AviaReason integration.

## Scope and Limitations

- The thesis evaluates communication, structure and interface design.
- It does not establish whether an aviation recommendation is operationally correct.
- Use synthetic, public or properly authorised content.
- Do not present the interface as approved cockpit software.
- Do not connect to aircraft systems or live operational data.
- Treat all outputs as research or training examples.

## Expected Contribution to AviaReason

This thesis will provide the **structured output contract and pilot-facing recommendation interface**. It should ensure that later RAG and decision modules can produce concise, traceable and consistently rendered responses.

## Suitable Student Profile

This topic is suitable for a student interested in:

- full-stack or frontend development;
- user experience design;
- explainable AI;
- structured LLM output;
- usability research;
- data visualisation and interface evaluation.
