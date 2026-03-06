# Maintainability & Documentation Checklist

## Naming Conventions
- [ ] Do variable names clearly express their purpose?
- [ ] Do function names describe what they do (verbs for actions)?
- [ ] Are boolean variables named as questions (isValid, hasPermission)?
- [ ] Are names pronounceable and searchable?
- [ ] Is naming consistent across the codebase?

## Code Readability
- [ ] Can the code be understood without extensive comments?
- [ ] Is the code formatted consistently?
- [ ] Is line length reasonable (<120 characters)?
- [ ] Is vertical spacing used to group related code?

## Comment Quality
- [ ] Do comments explain *why*, not *what*?
- [ ] Are complex algorithms explained?
- [ ] Are non-obvious decisions documented?
- [ ] Are there no commented-out code blocks?

## Documentation
- [ ] Are public APIs documented (parameters, returns, exceptions)?
- [ ] Does each module have a clear purpose statement?
- [ ] Is there a README with project overview?
- [ ] Are setup/build/test instructions provided?

## Test Coverage
- [ ] Are critical business logic paths tested?
- [ ] Are error handling paths tested?
- [ ] Are edge cases and boundary conditions tested?
- [ ] Can tests run in isolation and in any order?
- [ ] Are tests meaningful (verify behavior, not just exercise code)?

## Error Handling & Logging
- [ ] Are error messages clear and actionable?
- [ ] Do error messages include context?
- [ ] Are log levels used correctly (DEBUG, INFO, WARN, ERROR)?
- [ ] Are sensitive data excluded from logs?

## Configuration & Dependencies
- [ ] Is configuration externalized (not hardcoded)?
- [ ] Is sensitive configuration secured?
- [ ] Are dependencies documented and pinned?
- [ ] Are security vulnerabilities in dependencies addressed?

## Versioning & Compatibility
- [ ] Is semantic versioning used?
- [ ] Are breaking changes clearly marked?
- [ ] Is there a changelog?
- [ ] Are migration guides provided for breaking changes?
