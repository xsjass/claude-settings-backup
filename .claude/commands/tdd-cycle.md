# TDD Cycle - Complete Test-Driven Development Workflow

Execute a full Red-Green-Refactor TDD cycle for the specified feature or component.

## Instructions

You are a TDD expert. Guide the developer through a complete Red-Green-Refactor cycle for: $ARGUMENTS

Follow these three phases strictly in order:

---

## Phase 1: RED - Write Failing Tests

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

5. **Test Categories**
   - **Unit Tests**: Isolated component behavior
   - **Integration Tests**: Component interaction scenarios
   - **Contract Tests**: API and interface contracts
   - **Property Tests**: Invariants and mathematical properties

6. **Test Quality Checklist**
   - Tests are readable and self-documenting
   - Failure messages clearly indicate what went wrong
   - Tests follow DRY principle with appropriate abstractions
   - Coverage includes positive, negative, and edge cases
   - No implementation details leaked into tests

---

## Phase 2: GREEN - Minimal Implementation

### Implementation Strategy
1. **Pre-Implementation Analysis**
   - Review all failing tests and their error messages
   - Identify the simplest path to make tests pass
   - Map test requirements to minimal implementation needs
   - Avoid premature optimization or over-engineering

2. **Implementation Techniques**
   - **Fake It**: Return hard-coded values when appropriate
   - **Obvious Implementation**: When solution is trivial and clear
   - **Triangulation**: Generalize only when multiple tests require it
   - Start with the simplest test and work incrementally
   - One test at a time - don't try to pass all at once

3. **Code Guidelines**
   - Write the minimal code that could possibly work
   - Avoid adding functionality not required by tests
   - Use simple data structures initially
   - Defer architectural decisions until refactor phase
   - Don't add error handling unless tests require it

4. **Progressive Implementation**
   - Make first test pass with simplest possible code
   - Run tests after each change to verify progress
   - Add just enough code for next failing test
   - Resist urge to implement beyond test requirements
   - Keep track of technical debt for refactor phase

5. **Success Criteria**
   - All tests pass (green)
   - No extra functionality beyond test requirements
   - Code is readable even if not optimal
   - No broken existing functionality

---

## Phase 3: REFACTOR - Improve with Confidence

### Refactoring Process
1. **Pre-Refactoring Assessment**
   - Analyze current code structure and identify code smells
   - Review test coverage to ensure safety net is comprehensive
   - Identify refactoring opportunities and prioritize by impact
   - Run all tests to establish green baseline

2. **Code Smell Detection and Fixes**
   - **Duplicated Code**: Extract methods, pull up to base classes
   - **Long Methods**: Decompose into smaller, focused functions
   - **Large Classes**: Split responsibilities, extract classes
   - **Long Parameter Lists**: Introduce parameter objects
   - **Feature Envy**: Move methods to appropriate classes
   - **Primitive Obsession**: Replace with value objects
   - **Dead Code**: Remove unused code paths

3. **SOLID Principles Enforcement**
   - **Single Responsibility**: One reason to change per class
   - **Open/Closed**: Open for extension, closed for modification
   - **Liskov Substitution**: Subtypes must be substitutable
   - **Interface Segregation**: Small, focused interfaces
   - **Dependency Inversion**: Depend on abstractions

4. **Incremental Refactoring Steps**
   - Make small, atomic changes
   - Run tests after each modification
   - Commit after each successful refactoring
   - Keep refactoring separate from behavior changes

5. **Quality Metrics**
   - Cyclomatic Complexity: Reduce decision points
   - Code Coverage: Maintain or improve percentage
   - Coupling: Decrease interdependencies
   - Cohesion: Increase related functionality grouping

---

## Workflow Summary

For each iteration:
1. Write ONE failing test (RED)
2. Write MINIMAL code to pass it (GREEN)
3. REFACTOR while keeping tests green
4. Repeat

## Output Format

For each phase, provide:
- The actual code (tests or implementation)
- Commands to run tests
- Current test pass/fail status
- Notes on decisions made
- Next steps for the following phase

Target feature: $ARGUMENTS
