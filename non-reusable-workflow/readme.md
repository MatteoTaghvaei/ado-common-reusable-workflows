# Non-Reusable Pipeline Example

This folder shows how the Terraform Plan + Apply pipeline would look
**without using reusable templates**.

Why keep this?
- To document the “long form” that templates are abstracting away.
- To help new contributors understand what the templates are doing under the hood.
- To provide a fallback in case template usage is not possible.

---

## Reusable vs Non-Reusable

### Using reusable templates (short & clean)

```yaml
stages:
  - stage: Terraform
    jobs:
      - template: reusable-workflow/terraform/terraform-plan.yaml@ado-common-reusable-workflows 
        parameters:
          ENVIRONMENT: Environment
          SERVICE_CONNECTION: SERVICE_CONNECTION

     