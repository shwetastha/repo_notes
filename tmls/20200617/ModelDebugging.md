# Real-World Strategies for Model Debugging
Presenter: Patrick Hall
https://towardsdatascience.com/strategies-for-model-debugging-aa822f1097ce

## Practical Model Debugging
- Sensitivity Analysis:
	- ICE: Partial dependence and individual conditional expectation
	- Adversarial example searches-> Github:
		- Looking for adversarial rows
	- Random attacks
	- Simulating different scenarios to see how the model behaves
- Residual Analysis:
	- By feature
	- Residual vs. SHAP
	- What features are drving the model 
	- Disparate accuracy, error, and impact analysis
	- surrogate models
- Benchmark Models:
	- simple model vs complex model; if its too different then we should see what is wrong
- Security Audits:
	- Checking for known ML attacks
	
## Fixing Models
- Practical Model Debugging:
	- Data Augmentation
	- Interpretable ML
	- Model Editing
	- Model Assertions
	- Discrimination Remediation
	- Model Monitoring
	- Anomaly Detection

## AI Anomaly in the Real World
- AI Incident: Any behaviour by the model with the potential to cause harm, expected or not
	- Characterized by : Materiality and Preparedness
- 1200 Incidents of AI fail in real world

## Sample AI Incident Response Checklis


## Reources:
- Course on Responsible Machine Learning: https://jphall663.github.io/GWU_rml/
- Sample AI Incident Checklist: https://bnh-ai.github.io/resources/
- Github Examples: https://github.com/jphall663/interpretable_machine_learning_with_python

## Eaxmple of ML Attack:
- Stolen Model
