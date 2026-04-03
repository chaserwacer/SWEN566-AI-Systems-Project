# Phase 2 Onboarding Report Draft

## Course Project
**Movie Master — AI-Powered Film Intelligence Platform**

## 1. Technical Approach for AI Agent Team Member
Our team selected a **repository-native, provider-agnostic prompt architecture** so team members can use either GitHub Copilot workflows or alternative tooling (for example, Claude Code) while maintaining consistent behavior.

We created three specialized agent definitions:
1. **Prompting Agent** — converts issues/tasks into high-quality prompts and acceptance criteria.
2. **Coding Agent** — implements scoped, production-grade changes with maintainability and safety constraints.
3. **Code Reviewer Agent** — enforces quality gates for correctness, security/privacy, reliability, and test adequacy.

This approach emphasizes:
- **Portability:** prompts are tool-agnostic and can be used across AI coding platforms.
- **Consistency:** every task follows structured inputs, outputs, and definition-of-done checks.
- **Governance:** reviewer criteria standardize quality before human approval.

## 2. Training and Evaluation Process
We “trained” the AI team member by iterating on role-specific instructions and testing each role on realistic project tasks.

### Prompting Agent validation
- Input: rough task statements and issue-style descriptions.
- Expected behavior: produce clear, constrained prompts with assumptions and acceptance criteria.
- Result: improved task clarity and reduced back-and-forth before implementation.

### Coding Agent validation
- Input: implementation-ready prompts from the Prompting Agent.
- Expected behavior: minimal, focused changes aligned with architecture and style expectations.
- Result: stronger consistency in naming, documentation style, and error-path handling.

### Code Reviewer Agent validation
- Input: PR diffs and task context.
- Expected behavior: severity-tagged findings with concrete remediation steps.
- Result: more systematic quality checks, especially around edge cases and security/privacy concerns.

## 3. Team Interaction and Workflow So Far
Current workflow:
1. Team member creates or refines issue/task.
2. Prompting Agent produces implementation prompt + acceptance criteria.
3. Coding Agent drafts or implements the change.
4. Code Reviewer Agent evaluates output against quality checklist.
5. Human team member finalizes decisions and merges.

Observed collaboration impact:
- Faster initial implementation drafts.
- Better requirement traceability from issue → code → review.
- Improved accountability because criteria are explicit before coding starts.

## 4. What We Learned
- Specialized agents perform better than one general-purpose prompt for all tasks.
- Defining acceptance criteria up front significantly improves output quality.
- Tool-agnostic prompts reduce lock-in and let team members use preferred environments.
- Human review remains essential for final architecture and product decisions.

## 5. Challenges and Mitigations
- **Challenge:** ambiguity in issue descriptions.
  - **Mitigation:** Prompting Agent explicitly captures assumptions and open questions.
- **Challenge:** inconsistent code quality across generated outputs.
  - **Mitigation:** Coding standards embedded in Coding Agent + Reviewer gate.
- **Challenge:** risk of over-trusting AI output.
  - **Mitigation:** mandatory human review and explicit severity-based findings.

## 6. Next Steps
- Add a Test/Validation Agent for standardized test matrix generation.
- Integrate reviewer checklist into pull request templates/checklists.
- Measure cycle-time and defect-rate impact over upcoming sprints.
- Continue refining agent prompts using observed failure patterns.

## 7. Conclusion
The Phase 2 onboarding approach established a practical AI teammate model with clear role boundaries, shared quality expectations, and portable prompts. The team can now collaborate with AI more consistently while preserving human ownership of product and engineering decisions.
