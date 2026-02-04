# CI Templates

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/lorislab)

A centralized repository of reusable CI/CD templates designed to standardize and streamline build, test, and release pipelines across Lorislab projects.

## Purpose

This repository provides modular, versioned workflow templates for **GitHub Actions** and **GitLab CI**. By centralizing pipeline logic, we ensure:
- **Standardization:** All projects follow consistent quality gates (e.g., SonarCloud, Checkstyle).
- **Reduced Boilerplate:** Developers can include complex logic with a single `uses` or `include` statement.
- **Easier Updates:** Security patches or tool upgrades (like moving to Java 21) can be managed in one place.

---

## Key Features

### Quality Gates
Pre-configured templates for **SonarCloud** and **JUnit** reporting. Our templates are designed to handle common static analysis edge cases, such as:
- Correct `Optional` handling in `@PostConstruct` methods.
- Standardized code coverage thresholds.

### Build & Package
- **Java/Quarkus:** Optimized Maven and Gradle build workflows.
- **Docker:** Multi-architecture builds using Buildx.
- **Helm:** Standardized linting and packaging for Kubernetes deployments.

### Continuous Delivery
- Automated semantic versioning and tagging.
- GitHub/GitLab release automation with changelog generation.

---

## Usage

### GitHub Actions
To use a template in your repository, reference it in your `.github/workflows` YAML:

```yaml
jobs:
  build:
    uses: lorislab/ci-templates/.github/workflows/maven-build.yml@main
    with:
      java-version: '25'
```
## Contributing
 
1. Fork the repository.
2. Create a feature branch (git checkout -b feat/new-workflow).
3. Ensure templates are generic (use inputs/variables instead of hardcoded project names).
4. Open a Pull Request.

## License

This project is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for details.