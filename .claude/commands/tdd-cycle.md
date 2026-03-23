# TDD Cycle - Complete Test-Driven Development Workflow

Guide the full Red-Green-Refactor TDD cycle for: $ARGUMENTS

## Overview

This command orchestrates the complete TDD workflow through three disciplined phases. Follow each phase in order, never skipping ahead.

---

## Phase 1: RED - Write Failing Tests

Write comprehensive failing tests that define the expected behavior.

### Test Generation Process

1. **Test Structure Setup**
   - Choose appropriate testing framework for the language/stack
   - Set up test fixtures and necessary imports
   - Configure test runners and assertion libraries
   - Establish test naming conventions (should_X_when_Y format)

2. **Behavior Definition**
   - Define clear expected behaviors from requirements
   - Cover happy path scenarios thoroughly
   - Include edge cases and boundary conditions
   - Add error handling and exception scenarios
   - Consider null/undefined/empty input cases

3. **Test Implementation**
   - Write descriptive test names that document intent
   - Keep tests focused on single behaviors (one assertion per test when possible)
   - Use Arrange-Act-Assert (AAA) pattern consistently
   - Implement test data builders for complex objects
   - Avoid test interdependencies - each test must be isolated

4. **Failure Verification**
   - Ensure tests actually fail when run
   - Verify failure messages are meaningful and diagnostic
   - Confirm tests fail for the RIGHT reasons (not syntax/import errors)
   - Validate test isolation - no cascading failures

5. **Test Categories to Cover**
   - **Unit Tests**: Isolated component behavior
   - **Integration Tests**: Component interaction scenarios
   - **Contract Tests**: API and interface contracts
   - **Property Tests**: Invariants and mathematical properties
   - **Acceptance Tests**: User story validation

### Red Phase Checklist
- [ ] Tests are readable and self-documenting
- [ ] Failure messages clearly indicate what went wrong
- [ ] Coverage includes positive, negative, and edge cases
- [ ] No implementation details leaked into tests
- [ ] Tests use meaningful test data

---

## Phase 2: GREEN - Minimal Implementation

Implement the minimum code necessary to make all tests pass.

### Implementation Strategy

1. **Approach Selection**
   - **Fake It**: Return hard-coded values when appropriate
   - **Obvious Implementation**: When solution is trivial and clear
   - **Triangulation**: Generalize only when multiple tests require it

2. **Implementation Rules**
   - Write the minimal code that could possibly work
   - Avoid adding functionality not required by tests
   - One test at a time - don't try to pass all at once
   - Defer architectural decisions until refactor phase
   - Don't add error handling unless tests require it

3. **Progressive Implementation**
   - Make first test pass with simplest possible code
   - Run tests after each change to verify progress
   - Add just enough code for next failing test
   - Keep track of technical debt for refactor phase
   - Document assumptions and shortcuts taken

### Green Phase Checklist
- [ ] All tests pass (green)
- [ ] No extra functionality beyond test requirements
- [ ] Code is readable even if not optimal
- [ ] No broken existing functionality
- [ ] Technical debt documented for refactor phase

---

## Phase 3: REFACTOR - Improve Code Quality

Improve the code while keeping all tests green.

### Refactoring Process

1. **Code Smell Detection**
   - Duplicated Code: Extract methods, pull up to base classes
   - Long Methods: Decompose into smaller, focused functions
   - Large Classes: Split responsibilities, extract classes
   - Long Parameter Lists: Introduce parameter objects
   - Primitive Obsession: Replace with value objects
   - Dead Code: Remove unused code paths

2. **SOLID Principles Enforcement**
   - Single Responsibility: One reason to change per class
   - Open/Closed: Open for extension, closed for modification
   - Liskov Substitution: Subtypes must be substitutable
   - Interface Segregation: Small, focused interfaces
   - Dependency Inversion: Depend on abstractions

3. **Incremental Refactoring Steps**
   - Make small, atomic changes
   - Run tests after each modification
   - Commit after each successful refactoring
   - Keep refactoring separate from behavior changes

4. **Quality Improvements**
   - Clear, intentional, domain-specific naming
   - Remove obvious comments, add "why" comments
   - Consistent formatting throughout
   - Strengthen type safety where possible
   - Strategic error handling and logging

### Refactor Phase Checklist
- [ ] All tests still pass (100% green)
- [ ] No functionality regression
- [ ] Code coverage maintained or improved
- [ ] Code smells addressed
- [ ] Documentation updated

---

## Cycle Completion

After completing all three phases:

1. **Review the cycle** - Did each phase stay disciplined?
2. **Run full test suite** - Confirm everything passes
3. **Measure metrics** - Coverage, complexity, coupling
4. **Plan next cycle** - Identify next behavior to implement
5. **Commit** - Clean, atomic commit with descriptive message

## Anti-Patterns to Avoid

- Writing tests and implementation simultaneously
- Skipping the red phase (writing tests after code)
- Over-engineering in the green phase
- Mixing refactoring with new feature work
- Ignoring failing tests to move forward
- Writing too many tests before any implementation

## Best Practices

- Start with the simplest failing test
- One behavior change at a time
- Tests should tell a story of the feature
- Prefer many small tests over few large ones
- Make it work, then make it right, then make it fast
- Keep test code as clean as production code
- Commit after each completed phase
