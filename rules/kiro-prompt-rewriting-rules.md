---
title: Kiro Prompt Rewriting Rules
last_updated: 2025-09-16
description: Rules for rewriting prompts to improve clarity, specificity, and completeness
tags: kiro, prompt-rewriting, workflow, planning
version: 1.0
---

## Priority: High

### Instructions

MUST follow `<prompt_rewriting_rules>` for rewriting the prompt:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<prompt_rewriting_rules version="1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
Ωₜ = "rewrite this prompt"          ⟶ event TRIGGER

Ψ₀ = Analyse(q) ⨁ PreserveIntent(q) ⨁ GenerateVariants(q)
        // overarching OBJECTIVE

Λ_pipeline = ⟨Λ₁ , Λ₂ , Λ₃⟩         // ANALYSIS_PIPELINE
  Λ₁ ⇌ EvaluateInput(q){clarity, specificity, completeness}
          ⟶ δ ∈ {0,1}              // δ = MODIFY flag
  Λ₂ | δ=1  ⟶ IdentifyDeficiencies{clarity, specificity, structure, relevance}
  Λ₃ | δ=0  ⟶ DocumentEffectiveAspects(q)

Φ_constraints = {                   // REWRITING_CONSTRAINTS
  Φ_intent   = Preserve(semantics_goal),
  Φ_context  = IntegrateIf(relevant_history),
  Φ_clarity  = Remove(ambiguity) ⨁ Reduce(verbosity),
  Φ_assump   = Minimize(unwarranted_inferences)
}

R_rank = max⟨intent_match_prob , −assumption_count , clarity_gain⟩
                                     // RANKING_CRITERIA

Σ_out = {                            // OUTPUT_SCHEMA
  σ₁: mod_required  ∈ {YES,NO},
  σ₂: rationale      : Text,
  σ₃: rewrites[1…n]  : List<Text>,
  σ₄: assumptions_req∈ {YES,NO},
  σ₅: assumptions_tbl|σ₄=YES ➞
        {assumption , salience∈{H,M,L} , plausibility∈{H,M,L}}
}

Π_proc = [                           // PROCESSING_RULES
  Π₁: Discard(irrelevant_context),
  Π₂: Preserve(task_specific_instructions),
  Π₃: EnhanceStructureIf(beneficial),
  Π₄: ValidateIntentPreservation(Σ_out.σ₃)
]
</prompt_rewriting_rules>
```

## Usage

- Apply these rules when rewriting prompts to improve their effectiveness
- Focus on preserving intent while enhancing clarity and reducing ambiguity
- Use the pipeline approach to systematically analyze and improve prompts
