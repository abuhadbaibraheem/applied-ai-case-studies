# Multilingual banking NLU

**Context:** Arabic and English AI conversations · Model evaluation · Backend integration

## The problem

People do not speak to a banking assistant in one neat language or one complete sentence. A request can mix Arabic and English, include spelling variation, omit a key detail, or sound similar to a different intent. The system must understand the request, preserve conversation context, and avoid taking a consequential action from an uncertain prediction.

## My work

I have worked on multilingual intent and entity understanding, evaluation, conversation state, and the integration between AI services and product flows. This includes comparing a simple text-classification baseline with an Arabic-language model approach and examining where each fails.

## Design approach

1. **Separate intent from required details.** Predict the requested task and extract the fields needed to carry it out; ask for anything missing.
2. **Evaluate beyond the clean examples.** Include Arabic, English, mixed-language requests, spelling mistakes, paraphrases, and ambiguous utterances.
3. **Carry context across turns.** Store the conversation state needed for follow-up questions and corrections.
4. **Guard consequential steps.** Validate inputs and make the proposed action visible for user confirmation before execution.
5. **Define clear product contracts.** Keep model outputs, backend validation, and mobile presentation responsibilities explicit.

## Validation focus

I look at intent confusion, extraction errors, incomplete information, repeated requests, and recovery after a misunderstanding. Aggregate accuracy alone can hide these problems, so this case study intentionally avoids unsupported performance numbers. The implementation and customer data are private.

[Back to case studies](../README.md) · [LinkedIn](https://www.linkedin.com/in/ibraheem-abuhadba/)
