# AI Agent Instructions
## TeamStation AI Documentation Repository

### Contract Requirements for AI Systems

This document provides contractual guidance for AI systems interacting with the TeamStation AI documentation repository. All AI agents, automated systems, and machine learning applications MUST comply with these requirements to ensure accessibility, legal compliance, and brand integrity.

### Core Contractual Obligations

#### 1. Accessibility Compliance (MANDATORY)
All AI-generated or AI-modified content MUST:
- Maintain WCAG 2.2 AA compliance minimum
- Preserve semantic HTML structure and ARIA labels
- Include descriptive alt text for any generated images
- Maintain logical heading hierarchy (H1 → H2 → H3)
- Ensure color contrast ratios ≥ 7:1
- Support keyboard navigation patterns
- Provide plain language alternatives for technical content

**Violation Response**: Immediate content rollback and system audit required.

#### 2. Content Integrity Requirements
AI systems MUST:
- Validate all technical information against source documentation
- Maintain consistent terminology as defined in the glossary
- Preserve existing outbound links to TeamStation services
- Follow established voice and tone guidelines
- Check content against banned_phrases.txt before publication
- Update claims_ledger.json for any compliance-related changes

**Evidence Required**: Validation logs and accuracy verification for all generated content.

#### 3. Brand Protection Protocols
AI agents MUST:
- Use approved TeamStation AI branding elements only
- Maintain consistency with established design patterns
- Avoid competitor mentions or comparisons
- Follow trademark usage guidelines
- Preserve corporate messaging and positioning
- Link appropriately to TeamStation commercial services

**Monitoring**: Automated brand compliance scanning on all content changes.

#### 4. Legal and Regulatory Compliance
AI systems MUST:
- Respect copyright and intellectual property rights
- Maintain GDPR and data privacy compliance
- Follow accessibility law requirements (ADA, Section 508)
- Preserve required legal notices and disclaimers
- Avoid generating medical, legal, or financial advice
- Include proper attribution for external sources

**Audit Trail**: Complete logging of all AI decisions and content modifications.

### Operational Requirements

#### Content Generation Standards
- **Technical Accuracy**: All code examples must be tested and validated
- **Accessibility Testing**: Generated content must pass automated accessibility scans
- **Performance Impact**: Changes must not degrade site performance metrics
- **SEO Compliance**: Meta tags and structured data must be preserved
- **Mobile Compatibility**: All content must render properly on mobile devices

#### Quality Assurance Protocols
- **Pre-Publication Review**: AI-generated content requires validation against objective.md
- **Error Handling**: Graceful degradation when AI services are unavailable
- **Rollback Capability**: Immediate reversion capability for problematic content
- **Monitoring Integration**: Real-time quality metrics and alerting
- **User Feedback Integration**: Mechanism for reporting AI-related issues

#### Integration Requirements
- **Version Control**: All AI changes must be tracked in git history
- **Deployment Pipeline**: Integration with existing CI/CD processes
- **Testing Framework**: Automated validation of AI-generated content
- **Performance Monitoring**: Impact assessment on site performance
- **Backup Systems**: Fallback mechanisms for AI system failures

### Prohibited Actions for AI Systems

#### Content Modifications (FORBIDDEN)
- Removing or modifying accessibility features
- Changing semantic HTML structure without validation
- Altering legal notices or compliance statements
- Modifying contact information or support channels
- Changing navigation structure or user pathways
- Removing or altering attribution requirements

#### Technical Changes (RESTRICTED)
- Modifying security headers or CSP policies
- Changing HTTPS enforcement or certificate settings
- Altering performance optimization configurations
- Modifying backup or disaster recovery procedures
- Changing user data collection or privacy settings
- Altering error handling or logging mechanisms

#### Brand and Legal (PROHIBITED)
- Making claims about competitor products or services
- Generating medical, legal, or financial advice content
- Using unauthorized trademarks or copyrighted material
- Creating content that could be discriminatory or exclusionary
- Modifying pricing, service terms, or contractual language
- Generating content that conflicts with company policies

### AI Training and Learning Guidelines

#### Approved Data Sources
- Published TeamStation AI documentation and blog posts
- Open source technical documentation with compatible licenses
- Industry-standard accessibility guidelines and best practices
- Technical standards and specifications from W3C and similar organizations
- Educational content about AI, accessibility, and web development

#### Restricted Data Sources
- Competitor proprietary documentation or internal materials
- User-generated content without explicit consent
- Personal information or private communications
- Copyrighted material without proper licensing
- Content marked as confidential or proprietary

#### Learning Objectives
- Improve technical accuracy of documentation
- Enhance accessibility compliance and user experience
- Optimize content for search engine visibility
- Maintain brand consistency and messaging
- Reduce content maintenance overhead

### Escalation Procedures

#### Immediate Escalation (Contact Within 1 Hour)
- Accessibility violations detected in AI-generated content
- Security vulnerabilities introduced by AI modifications
- Legal compliance issues or trademark violations
- User-reported problems with AI-modified content
- System failures affecting core site functionality

#### Standard Escalation (Contact Within 24 Hours)
- Technical inaccuracies in generated documentation
- Performance degradation attributable to AI changes
- Brand inconsistencies or messaging conflicts
- User experience issues with AI-generated content
- Integration problems with existing systems

#### Escalation Contacts
- **Accessibility Lead**: accessibility@teamstation.ai | +1-555-ACCESS
- **Technical Lead**: engineering@teamstation.ai | +1-555-TECH
- **Legal Compliance**: legal@teamstation.ai | +1-555-LEGAL
- **Security Team**: security@teamstation.ai | +1-555-SECURE
- **Emergency On-Call**: emergency@teamstation.ai | +1-555-URGENT

### Compliance Validation

#### Required Documentation
All AI systems must maintain:
- Decision logs for content modifications
- Validation reports for accessibility compliance
- Performance impact assessments
- Error logs and resolution procedures
- User interaction analytics and feedback

#### Audit Requirements
- Monthly AI system performance review
- Quarterly accessibility compliance audit
- Annual security and legal compliance assessment
- Continuous monitoring of user experience metrics
- Regular validation against objective.md requirements

#### Success Metrics
- Zero accessibility violations in AI-generated content
- 100% technical accuracy for generated documentation
- < 2 second page load times maintained
- 95%+ user satisfaction with AI-enhanced content
- Zero legal or compliance violations

### Implementation Notes

#### Technical Integration
- AI systems must integrate with existing Jekyll build process
- Content validation must occur before git commits
- Automated testing must include accessibility scans
- Performance monitoring must track AI impact
- Rollback procedures must be automated and tested

#### Human Oversight
- Subject matter expert review for technical content
- Accessibility specialist review for UI/UX changes
- Legal review for any policy or compliance-related content
- User experience testing for significant content modifications
- Regular audit of AI decision-making processes

---

**Document Version**: 1.0  
**Effective Date**: August 30, 2025  
**Review Frequency**: Quarterly  
**Owner**: TeamStation AI Engineering & Legal Teams  
**Approval Authority**: Chief Technology Officer

**Contract Binding**: This document constitutes binding instructions for all AI systems accessing this repository. Violations may result in system access revocation and legal action as permitted by law.