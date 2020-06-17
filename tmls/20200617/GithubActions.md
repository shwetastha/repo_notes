# GitHub Actions
Presenter: Jon Peck

## Resources:
- Github Code: https://github.com/peckjon/coreml_ghactions
- Slide: https://docs.google.com/presentation/d/1aIwxTMPF8rm2sY3VAJypB5x7paYeCVMlpwYsSHrUl_E/edit#slide=id.p

## Modern Development Workflow
- Version Control -> PR -> CI/CD Process
- Classic Uses CI/CD:
	- Trigger on change to monitored branch
	- Build codebase
	- Run test
	- Check for compliance
	- Configure infra
	- deploy
## Github Actions
- Setting up CI/CD 
- Converting SkLearn Model to CoreMl Model that will run on IOS or OSX.
- .github/workflows/train.yml -> for CI/CD config
- 1 YAML = 1 Workflow
	- <on>: When to trigger
	- <push>: as many 
- With the yml config, multiple env cane set up and parallel workflow can run
- Appropriate for Adhoc singular predictions

