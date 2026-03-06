# Code Health Indicators Checklist

## Dead Code Detection
- [ ] Are there unused functions or methods?
- [ ] Are there unused variables or parameters?
- [ ] Are there unused imports or dependencies?
- [ ] Are there unreachable code paths?
- [ ] Are there commented-out code blocks that should be removed?

## Stale Code
- [ ] Are there outdated implementations that should be modernized?
- [ ] Are deprecated APIs or libraries still in use?
- [ ] Are there TODO comments from months/years ago?
- [ ] Are there workarounds for bugs that have been fixed?

## Code Smells Summary
| Dimension | Key Checks |
|-----------|------------|
| **Method/Function** | Functions >50 lines, >4 parameters, >3 nesting levels |
| **Class Level** | Classes >300 lines, >7 variables, God classes, low cohesion |
| **Naming** | Vague names, misleading names, inconsistent naming |
| **Duplication** | Repeated logic, copy-pasted code |
| **Complexity** | Complex booleans, nested ternaries, switch chains |
| **Dependencies** | Circular dependencies, tight coupling |
| **Data** | Primitive obsession, magic numbers, mutable globals |
| **Control Flow** | Multiple returns, control coupling |

## Performance Red Flags
- [ ] Are there N+1 query problems?
- [ ] Is there unnecessary work in loops?
- [ ] Are there inefficient algorithms (O(n²) where better works)?
- [ ] Is there excessive object creation in hot paths?

## Security Red Flags
- [ ] Is user input used without validation or sanitization?
- [ ] Are there SQL injection vulnerabilities?
- [ ] Are there hardcoded credentials or secrets?
- [ ] Is cryptography used incorrectly?

## Refactoring Opportunities
### High Priority (Before Merge)
- [ ] Security vulnerabilities requiring immediate fix
- [ ] Functions/classes too large to maintain safely
- [ ] Missing error handling in critical paths

### Medium Priority (Near Term)
- [ ] Violations of Single Responsibility Principle
- [ ] Tight coupling that makes changes risky
- [ ] Duplication that creates maintenance burden

### Quick Wins (High Value, Low Effort)
- [ ] Remove dead code
- [ ] Fix naming inconsistencies
- [ ] Extract obvious duplicated code
- [ ] Replace magic numbers with constants
