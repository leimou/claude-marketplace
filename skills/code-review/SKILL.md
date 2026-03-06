---
name: code-review
description: Conduct comprehensive code reviews of uncommitted/staged changes or commits, analyzing design, code quality, maintainability, performance, and architectural soundness. Use this skill when users ask to review code, check changes, analyze commits, evaluate code quality, assess architecture, or want feedback on their code changes. Trigger for phrases like "review my code", "check these changes", "analyze this commit", "code quality check", "review PR", or "evaluate my changes".
---

# Code Review Skill

Perform thorough, language-agnostic code reviews focusing on design principles, code quality, maintainability, performance, and architectural soundness.

## Workflow

### Step 1: Identify Review Scope

Start by determining what needs to be reviewed:

1. Check for uncommitted/staged changes: `git status` and `git diff --cached`
2. Check for unstaged changes: `git diff`
3. If reviewing commits, identify the range: `git log --oneline -n 10`

**Confirm with the user** if the scope is unclear:
- Are we reviewing uncommitted changes, staged changes, or specific commits?
- Should we review a specific commit range (e.g., `HEAD~3..HEAD`)?
- Are there specific files or modules to focus on?

### Step 2: Analyze Changes by Functional Units

Group changes by functional units or modules rather than reviewing file-by-file. This provides better context for understanding the impact of changes. Use `git diff` with appropriate flags to see the changes, then organize your review around:

- Feature additions or modifications
- Bug fixes
- Refactoring efforts
- Infrastructure or configuration changes
- Test additions or modifications

### Step 3: Conduct Multi-Dimensional Review

Review the code across all five dimensions below. For each dimension, perform the 5 key checks listed. When deeper analysis is needed for a specific dimension, consult the corresponding reference checklist in `references/`.

---

## Review Dimensions

### 1. Architecture & Design Analysis

**Key Checks:**

1. **Component Boundaries**: Are responsibilities clearly separated? Do components have well-defined interfaces and single purposes?

2. **Design Pattern Appropriateness**: Are design patterns used correctly and appropriately for the problem? Avoid pattern overuse or misapplication.

3. **Coupling Assessment**: Are dependencies between modules minimized? Can components be modified independently without cascading changes?

4. **Scalability Evaluation**: Will this design handle increased load, data volume, or user growth? Identify potential bottlenecks early.

5. **Abstraction Levels**: Are abstractions at the right level? Avoid leaky abstractions that expose implementation details or over-abstraction that obscures intent.

**For detailed analysis**, read `references/architecture_checklist.md`

### 2. Code Quality Assessment (SOLID Principles)

**Key Checks:**

1. **Single Responsibility Principle**: Does each class have only one reason to change? Look for classes that handle multiple concerns like data access, business logic, and presentation simultaneously.

2. **Open/Closed Principle**: Can behavior be extended without modifying existing code? Check for hardcoded logic that should be abstracted, and ensure new features can be added via extension rather than modification.

3. **Liskov Substitution Principle**: Can derived classes be used anywhere their base class is expected? Verify that subclasses honor parent contracts and don't violate expected behavior.

4. **Interface Segregation Principle**: Are interfaces focused and cohesive? Clients shouldn't be forced to depend on methods they don't use—prefer many small interfaces over one large one.

5. **Dependency Inversion Principle**: Do high-level modules depend on abstractions rather than concrete implementations? This enables flexibility, testability, and independent module evolution.

**For detailed analysis**, read `references/code_quality_checklist.md`

### 3. Code Health, Performance & Security

**Key Checks:**

1. **Dead Code Detection**: Are there unused functions, variables, imports, or unreachable code paths? These add maintenance burden and confusion.

2. **Code Duplication**: Is logic repeated across multiple locations? Identify opportunities for extraction and reuse.

3. **Method/Function Length**: Are functions too long (>50 lines is a yellow flag)? Long functions usually do too much and are hard to test and understand.

4. **Performance Issues**: Are there N+1 query problems, inefficient algorithms, or unnecessary work in loops? Identify performance bottlenecks early.

5. **Security Vulnerabilities**: Is user input validated? Are there SQL injection risks, hardcoded secrets, or improper cryptography usage?

**For detailed analysis**, read `references/code_health_checklist.md`

### 4. Maintainability, Testing & Documentation

**Key Checks:**

1. **Naming Clarity**: Do names clearly express intent? Variables, functions, and classes should be self-documenting.

2. **Test Coverage**: Are critical paths tested? Do tests verify behavior (not just exercise code)? Can tests run independently?

3. **Code Organization**: Is related code grouped together? Is the file/module structure logical and easy to navigate?

4. **Comment & API Documentation**: Do comments explain *why*, not *what*? Are public interfaces documented with expected inputs, outputs, and side effects?

5. **Consistency**: Does the code follow existing project conventions for style, naming, and structure? Inconsistency creates cognitive load.

**For detailed analysis**, read `references/maintainability_checklist.md`

---

## Output Format

Structure your review as follows:

### Executive Summary
- High-level assessment (2-3 sentences)
- Critical issues requiring immediate attention
- Overall code quality rating (if appropriate)

### Detailed Findings

For each dimension where issues are found, provide:

**[Dimension Name]**
- **Issue**: Brief description with file:line_number references
- **Severity**: Critical / High / Medium / Low
- **Impact**: Why this matters
- **Recommendation**: Specific, actionable suggestion

### Code Examples

When illustrating issues, show:
- Current problematic code (with file:line_number)
- Explanation of the problem
- Suggested improvement (when helpful)

### Improvement Roadmap

Prioritize recommendations:

**High Priority** (address before merge/deploy)
- [List critical items]

**Medium Priority** (address in near term)
- [List important items]

**Low Priority** (consider for future refactoring)
- [List nice-to-have improvements]

### Metrics Summary

Provide quantifiable observations:
- Files changed: X
- Lines added/removed: +X / -X
- Complexity hotspots: [list files with high complexity]
- Test coverage impact: [if measurable]

---

## Principles

**Be constructive**: Frame feedback as opportunities for improvement, not criticism. The goal is to help the code and the developer get better.

**Be specific**: Vague feedback like "this could be better" isn't helpful. Point to specific lines and explain exactly what and why.

**Explain the why**: Don't just say what's wrong—explain why it matters. Help the developer understand the principles behind your feedback.

**Balance thoroughness with pragmatism**: Not every issue needs to be fixed immediately. Help prioritize based on impact and risk.

**Recognize good work**: Call out well-designed solutions and improvements. Positive reinforcement matters.

**Consider context**: A quick prototype has different standards than production code. Adjust your review rigor accordingly.
