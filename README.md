# labs
Section Name	Description	Key Steps	Best Practices
Pipeline Management	Overview of our CI/CD pipelines (Pie1, Did2, Ow3).	1. Define pipeline stages
2. Automate build & testing
3. Deploy using IaC
4. Implement rollback strategies	- Use version control (Git)
- Keep pipelines modular
- Ensure rollback plans are in place
Infrastructure as Code (IaC)	Managing infrastructure using code for consistency & automation.	1. Define infra using Terraform/CloudFormation
2. Use parameterized templates
3. Automate deployments
4. Implement state management	- Store IaC in Git
- Enforce code reviews
- Follow least privilege access control
Monitoring & Observability	Ensuring system health & performance through logging and alerts.	1. Set up metrics & logging (CloudWatch, Prometheus, Grafana)
2. Implement alerts for failures
3. Automate response actions
4. Regularly review dashboards	- Use centralized logging
- Define SLIs, SLOs & SLAs
- Test alerting mechanisms
Security & Compliance	Enforcing security best practices in deployments.	1. Implement IAM roles & policies
2. Automate security scans (SAST/DAST)
3. Encrypt data in transit & at rest
4. Conduct regular audits	- Follow least privilege model
- Enforce MFA
- Regularly update dependencies


