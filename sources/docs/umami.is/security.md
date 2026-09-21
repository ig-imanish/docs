# Source: https://umami.is/security

# Security at Umami

## Privacy starts with collecting less

Umami is designed to provide useful analytics without collecting unnecessary personal information. We combine privacy-first product design with technical and organizational safeguards intended to protect customer data and keep Umami Cloud reliable.

- [Read our DPA](https://umami.is/dpa)
- [Report a vulnerability](mailto:security@umami.is)

## Our approach

We base our security program on four principles:

**Data minimization** We limit the information collected and retained to what is necessary to provide the service.

**Least-privilege access** Access to production systems and customer data is restricted to authorized personnel who require it to operate or support the service.

**Defense in depth** We use multiple layers of protection across our application, infrastructure, development process, and service providers.

**Transparency** We describe our practices accurately and do not claim certifications or independent assessments that we have not completed.

The practices on this page apply primarily to Umami Cloud. Customers who self-host Umami control and are responsible for the security of their own infrastructure and deployment.

## Privacy by design

Security begins with reducing the amount of sensitive data that needs to be protected.

By default, Umami’s standard web analytics:

- Does not use cookies
- Does not track visitors across different websites
- Does not collect names, email addresses, or other directly identifying information
- Does not use analytics data for advertising
- Does not sell customer or visitor data

Umami anonymously groups activity into visits so customers can understand website traffic without creating persistent profiles of individual visitors.

Some optional features can collect additional information when a customer chooses to enable and configure them. These include Distinct IDs, custom event or session properties, revenue tracking, session replays, and heatmaps. Customers are responsible for ensuring that their use of these features is appropriate for their users, privacy policy, and legal obligations.

Session replays are disabled by default and require an additional recorder script. Input fields are masked by default, stricter masking can be enabled, and customers can exclude sensitive areas from recording.

[Learn more about Umami’s privacy stance](https://umami.is/privacy)

## Encryption and data protection

We use safeguards intended to protect data throughout its lifecycle.

### Data in transit

Connections to Umami Cloud are encrypted using HTTPS and industry-standard TLS. Communication between supported infrastructure components is encrypted where available.

### Data at rest

Customer data is stored using infrastructure and database providers that support encryption at rest. Backups and replicated data are protected using the security controls provided by the applicable infrastructure provider.

### Secrets and credentials

Production credentials, database credentials, API tokens, and other secrets are stored separately from application source code. Access is restricted to the systems and personnel that require them.

### Payment information

Payments for Umami Cloud are processed by Stripe. Umami does not directly store complete payment-card numbers or card security codes.

### Data isolation

Umami Cloud logically separates customer accounts, teams, websites, and analytics data. Application authorization controls are used to prevent one customer from accessing another customer’s resources.

## Access controls

Access to Umami’s production environment is limited to authorized team members with an operational need.

Our access practices include:

- Individual accounts rather than shared production credentials
- Least-privilege permissions
- Multi-factor authentication on critical services where supported
- Restricted administrative and production access
- Removal of access when it is no longer required
- Logging and monitoring provided by our infrastructure platforms

Customer access to Umami is controlled through authenticated accounts, teams, roles, and permissions. Customers are responsible for managing their users, protecting their credentials, and removing access that is no longer needed.

## Secure software development

Umami is developed using practices intended to identify security issues before and after code reaches production.

These practices include:

- Peer review of material code changes
- Automated testing
- Dependency and vulnerability monitoring
- Regular dependency and security updates
- Separation of development and production environments
- Restricted handling of production secrets
- Investigation of reported vulnerabilities and GitHub security advisories
- Monitoring of production errors and service health

Umami is open source under the MIT license. Our source code is publicly available for customers, researchers, and the community to inspect.

[View Umami on GitHub](https://github.com/umami-software/umami)

## Infrastructure and availability

Umami Cloud is operated using established infrastructure, hosting, database, networking, monitoring, and payment providers.

We use operational controls intended to maintain service availability, including:

- Infrastructure and application monitoring
- Error and performance monitoring
- Managed network protections
- Database backup and recovery mechanisms
- Deployment and rollback procedures
- Capacity and service-health monitoring
- Geographic data-region selection for Umami Cloud accounts

No online service can guarantee uninterrupted availability. When incidents occur, our objective is to identify the issue, reduce customer impact, restore service, and communicate material updates.

[View service status](https://umami.statuspage.io/)

## Incident response

We maintain a process for handling suspected security incidents.

Depending on the nature of an incident, our response may include:

1. Investigating and validating the report
2. Containing affected systems or credentials
3. Assessing the scope and customer impact
4. Remediating the underlying issue
5. Restoring normal operations
6. Preserving relevant evidence
7. Notifying affected customers when required
8. Reviewing the incident and improving our controls

When a confirmed incident affects customer data, we will notify affected customers without unreasonable delay and in accordance with applicable law and contractual requirements. Notifications may be delivered by email, through the Umami Cloud application, or through our service-status page.

## Data retention and deletion

Customers control the analytics data they submit to Umami within the capabilities of their plan and account.

Umami provides mechanisms for customers to:

- Remove websites and their associated analytics data
- Delete their Umami Cloud account
- Export supported analytics data
- Configure or disable optional collection features
- Manage team members and access
- Revoke and replace API credentials

When an account or dataset is deleted, it is removed from active systems according to our deletion process. Residual copies may remain temporarily in encrypted backups until those backups expire or are overwritten.

Additional processing, retention, and deletion terms are described in our Privacy Policy and Data Processing Agreement.

[Read our Privacy Policy](https://umami.is/privacy) [Read our Data Processing Agreement](https://umami.is/dpa)

## Compliance and independent assurance

Umami’s product and operating practices are designed to help customers meet their own privacy and security requirements.

| Area | Current status |
| --- | --- |
| Data Processing Agreement | Publicly available |
| GDPR and CCPA | Umami is designed to support compliant analytics use |
| Data-region selection | Available for Umami Cloud |
| Open-source review | Source code publicly available |
| SOC 2 | Not currently certified |
| ISO 27001 | Not currently certified |
| Independent penetration test | Not yet completed |
| Payment-card processing | Handled by Stripe |

We are evaluating formal compliance programs and an independent third-party penetration test as Umami Cloud and its enterprise customer base grow.

Security questionnaires and additional information may be provided during a legitimate customer procurement or security review.

[Contact us about a security review](mailto:security@umami.is)

## Responsible vulnerability disclosure

We welcome reports from security researchers and customers who believe they have discovered a vulnerability in Umami or Umami Cloud.

Please send reports to:

**[security@umami.is](mailto:security@umami.is)**

A useful report should include:

- The affected product, URL, API endpoint, or software version
- A description of the vulnerability and its potential impact
- Reproduction steps or a proof of concept
- Any relevant logs, screenshots, or request details
- Your preferred contact information

When performing security research, please:

- Do not access, modify, download, or delete customer data
- Do not disrupt Umami Cloud or degrade service availability
- Do not perform denial-of-service, spam, or social-engineering attacks
- Do not test against customer-controlled self-hosted installations without permission
- Use accounts and data that you own whenever possible
- Give us a reasonable opportunity to investigate and remediate an issue before public disclosure

We will review good-faith reports and keep the reporter informed as the issue is investigated.

**Umami does not currently operate a guaranteed paid bug-bounty program.**

## Self-hosted Umami

The self-hosted edition gives organizations complete control over where Umami runs and where its data is stored.

For self-hosted installations, the customer is responsible for:

- Securing the hosting environment and network
- Applying Umami and operating-system updates
- Configuring TLS
- Protecting database and application credentials
- Managing backups and disaster recovery
- Restricting administrative access
- Monitoring the installation
- Meeting applicable legal and regulatory requirements

We recommend keeping Umami and its dependencies current and following the deployment guidance in our documentation.

[Read the self-hosting documentation](https://docs.umami.is)

## Contact

For security questions, vulnerability reports, or customer security reviews:

**[security@umami.is](mailto:security@umami.is)**

For questions about personal data or our contractual privacy obligations:

**[privacy@umami.is](mailto:privacy@umami.is)**

For general product support:

**[support@umami.is](mailto:support@umami.is)**

Last updated July 29, 2026