# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0-alpha.1] - 2025-11-26
## [0.1.0] - 2025-11-26

### Changes
- fix(ci): add contents:write permission for auto version bump

The GITHUB_TOKEN needs explicit write permission to push commits
and tags back to the repository.


### Added

#### SDK-Based Evaluation Framework
- Complete test execution framework using OpenCode SDK
- Support for openagent and opencoder testing
- Real agent testing with session management
- Smart timeout system with activity monitoring
- Multi-turn conversation support

#### Modular Architecture
- Refactored test-runner.ts (884 lines → 4 focused modules):
  - `test-runner.ts` (411 lines): Thin orchestrator
  - `test-executor.ts` (392 lines): Core execution logic
  - `result-validator.ts` (253 lines): Validation logic
  - `event-logger.ts` (128 lines): Logging utilities
- Improved Single Responsibility Principle compliance
- Enhanced testability through dependency injection

#### Test Infrastructure
- 20+ test cases across multiple categories:
  - OpenAgent: Developer (12), Context Loading (5), Business (2), Edge Cases (3)
  - OpenCoder: Developer (4)
- BehaviorEvaluator for validating expected agent actions
- Comprehensive evaluators: approval-gate, context-loading, delegation, tool-usage

#### Interactive Results Dashboard
- Real-time test results visualization
- Filtering by agent, category, status
- Detailed violation tracking
- CSV export functionality
- Historical results tracking
- One-command deployment (`./serve.sh`)

#### Documentation
- ARCHITECTURE.md: Comprehensive system review (456 lines)
- GETTING_STARTED.md: Quick start guide (435 lines)
- SDK_EVAL_README.md: Complete SDK guide (298 lines)
- Test design guide and architecture overview
- Documentation cleanup (removed 3 outdated files)

#### Script Organization
- Organized 12 scripts into logical directories:
  - `scripts/debug/`: Session debugging tools (4 files)
  - `scripts/test/`: Test execution scripts (6 files)
  - `scripts/utils/`: Utility scripts (2 files)
- Comprehensive scripts/README.md with usage examples

#### Monorepo Structure
- Root package.json with convenient npm scripts
- Easy agent selection (openagent, opencoder)
- Easy model selection (grok, claude, gpt-4)
- Quick dashboard access from root
- No folder navigation required

#### CI/CD
- GitHub Actions workflow for automated testing
- Pre-merge validation for agent changes
- Fast smoke tests for both agents
- Automated test result reporting

#### Agent Improvements
- Enhanced openagent with better context loading
- New opencoder agent with test suite
- Improved subagent invocation patterns
- Ultra-compact context index system

### Changed
- Reorganized evaluation framework structure
- Improved test case schema with behavior expectations
- Enhanced context loading detection

### Removed
- Outdated documentation files (TESTING_CONFIDENCE.md, TEST_REVIEW.md, SESSION_STORAGE_FIX.md)
- Redundant test files

### Fixed
- Context loading evaluator detection accuracy
- Multi-turn prompt handling
- Test artifact cleanup

---

## Version Format

```
v0.1.0-alpha.1
│ │ │  │      │
│ │ │  │      └─ Build/Iteration number
│ │ │  └──────── Release stage (alpha, beta, rc)
│ │ └─────────── Patch version
│ └───────────── Minor version
└─────────────── Major version (0 = pre-release)
```

### Version Progression

- **Alpha** (`v0.x.0-alpha.N`): Early development, unstable
- **Beta** (`v0.x.0-beta.N`): Feature complete, testing
- **RC** (`v0.x.0-rc.N`): Release candidate, stable
- **Stable** (`v1.x.x`): Production ready

[0.1.0-alpha.1]: https://github.com/darrenhinde/OpenAgents/releases/tag/v0.1.0-alpha.1
