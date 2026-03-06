# Code Quality Assessment Checklist

## Single Responsibility Principle (SRP)

- [ ] Does each class have only one reason to change?
- [ ] Does each function/method do one thing well?
- [ ] Are there "God classes" that do too much?
- [ ] Can you describe each class's responsibility in one sentence?
- [ ] Are responsibilities clearly separated between methods?

## Open/Closed Principle (OCP)

- [ ] Can new functionality be added without modifying existing code?
- [ ] Are extension points provided for anticipated changes?
- [ ] Is behavior extended through abstraction rather than modification?
- [ ] Are switch/if-else on type used instead of polymorphism?
- [ ] Can new features be added via configuration or plugins?

## Liskov Substitution Principle (LSP)

- [ ] Can derived classes be used anywhere their base class is expected?
- [ ] Do subclasses honor the contracts of their parent classes?
- [ ] Are there subclasses that violate parent behavior expectations?
- [ ] Do overrides maintain the original method's invariants?
- [ ] Are preconditions weakened and postconditions strengthened appropriately?

## Interface Segregation Principle (ISP)

- [ ] Are interfaces focused and cohesive?
- [ ] Do clients depend only on methods they use?
- [ ] Are there "fat" interfaces with methods some clients don't need?
- [ ] Should large interfaces be split into smaller, specific ones?
- [ ] Are there interface implementations that throw "not supported" exceptions?

## Dependency Inversion Principle (DIP)

- [ ] Do high-level modules depend on abstractions, not concretions?
- [ ] Are dependencies injected rather than instantiated internally?
- [ ] Can implementations be swapped without changing high-level code?
- [ ] Is there excessive coupling to concrete implementations?
- [ ] Are there unnecessary dependencies between unrelated modules?

## YAGNI (You Aren't Gonna Need It)

- [ ] Is there code for features that aren't currently needed?
- [ ] Are there abstractions built for hypothetical future requirements?
- [ ] Is functionality over-engineered for current use cases?
- [ ] Are there configuration options that will never be used?
- [ ] Is code more complex than the current requirements justify?

## KISS (Keep It Simple)

- [ ] Is the solution as simple as possible while still being correct?
- [ ] Could a simpler approach achieve the same result?
- [ ] Are there unnecessary layers of indirection?
- [ ] Is the code easy to understand on first reading?
- [ ] Are clever tricks making the code harder to maintain?

## DRY (Don't Repeat Yourself)

- [ ] Is logic duplicated across multiple locations?
- [ ] Are similar code blocks candidates for extraction?
- [ ] Is knowledge represented in one place (single source of truth)?
- [ ] Are copy-paste modifications a sign of missed abstraction?
- [ ] Are constants or magic values repeated?
