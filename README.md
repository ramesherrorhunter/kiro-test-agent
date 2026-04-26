# test-agent

An intelligent Kiro CLI agent that auto-generates unit tests for uncovered functions by analyzing your codebase — no manual configuration needed.

---

## Purpose

Eliminate the manual effort of writing unit tests. The agent inspects your project, finds functions with no test coverage, and generates meaningful tests with edge cases and error handling using your existing test framework.

---

## Solutions Offered

| Problem | Solution |
|---|---|
| Writing tests from scratch | Auto-generates based on existing source code |
| Missing edge case coverage | Always includes happy path, edge cases, and error cases |
| Wrong test framework | Detects and uses your existing framework |
| Untested exported functions | Identifies and prioritizes uncovered public functions |
| Unmocked dependencies | Automatically mocks DB, HTTP, and filesystem calls |

---

## Benefits

- **Zero config** — infers everything from your project files
- **Framework-aware** — uses your existing test runner, never introduces a new one
- **Multi-language support** — Node.js, Python, Go, Java, Rust, Ruby
- **Thorough coverage** — happy path, edge cases, and error cases for every function
- **Consistent output** — follows the same best-practice sequence every time

---

## How It Works

The agent runs 3 skills in sequence:

```
analyze_project → find_untested_code → generate_tests
```

| Skill | What it does |
|---|---|
| `analyze_project` | Detects language, framework, and test runner |
| `find_untested_code` | Identifies functions and modules missing tests |
| `generate_tests` | Writes unit tests with mocks and edge cases |

---

## Installation

**1. Clone the repo**
```bash
git clone https://github.com/ramesherrorhunter/kiro-test-agent.git
```

**2. Copy the agent into your project**
```bash
cp -r kiro-test-agent/.kiro /path/to/your/project/
```

Or copy into the current directory:
```bash
cp -r kiro-test-agent/.kiro .
```

That's it — the agent and all skills are now available in your project.

---

## SOP — Standard Operating Procedure

### Prerequisites
- Kiro CLI installed
- Project directory accessible

### Steps

**1. Navigate to your project**
```bash
cd /path/to/your/project
```

**2. Start Kiro CLI**
```bash
kiro-cli
```

**3. Select the agent**

Type `/agent` and from the dropdown select `test-agent`

**4. Review generated test files**

Test files are placed alongside source files or in the existing test directory, following your project's naming convention.

### Supported Test Frameworks

| Language | Framework |
|---|---|
| Node.js | Jest, Vitest, Mocha |
| Python | Pytest, Unittest |
| Go | `testing` package |
| Java | JUnit 5 |
| Rust | Built-in `#[test]` |
| Ruby | RSpec, Minitest |

### Notes
- The agent never introduces a new test framework — it uses what's already in your project
- External dependencies (DB, HTTP, filesystem) are always mocked
- Re-run the agent after adding new functions or modules

## License

MIT
