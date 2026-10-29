# Repository Instructions

- This repository defines reusable decision and control workflows for the AI-assisted software lifecycle, for adoption in other repositories.
- Define review perspectives, their assignments and required outputs directly in the relevant workflow; do not maintain separate role files.
- Keep only lifecycle-specific triggers, steps, decision rights, role assignments, exit conditions and delivery/evidence templates. Do not duplicate general programming knowledge or generic role curricula.
- Maintain each process rule in one place and reference it from related workflows and templates.
- Model every discipline through explicit scoped state transitions: source state, event, guard/question, evidence, action/authority, result, target state and next route. Use the shared lifecycle transition model; do not equate phase labels with proven completion.
- Write all text in this repository in English.
- Ensure every addition and change fits logically into the repository's overall purpose, structure and existing content.
- This repository contains process definitions, diagrams and reusable templates only. Implement software, tests, documentation builds, CI and deployment tooling in the adopting project when its task requires them; do not build reference runtimes here.
- Describe proposed target-project paths and commands as adaptation examples, not as existing repository capabilities.
