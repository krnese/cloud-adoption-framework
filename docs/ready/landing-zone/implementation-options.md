---
title: Landing zone deployment options
description: Which landing zone deployment option best fits your requirements
author: BrianBlanchard
ms.author: brblanch
ms.date: 06/15/2020
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: ready
---

# Landing zone implementation options

The objective of [Azure landing zones](./index.md) is to provide cloud adoption teams with a well-managed environment for their workloads. To reach that objective, the Microsoft recommendation is to follow the [landing zone design areas](./design-areas.md) discussed in the prior article.

Each of the following implementation options is built for a specific set of operating model dependencies to support your specific non-functional requirements. Each implementation option includes distinct automation approaches. When available, reference architectures and reference implementations are also included to accelerate your cloud adoption journey. While each is mapped to a different operating model, they all share the same design areas. The difference is how you choose to implement them.

## Platform development velocity

In addition to the recommended design areas, platform development velocity (how fast your platform team can develop the required skills) is a key factor in choosing the best deployment option. There are two primary modes to consider:

**Start with enterprise scale:** When business requirements necessitate a rich initial implementation of landing zones, with fully integrated governance, security, and operations from the start, Microsoft suggests the enterprise scale approach. This approach can use the Azure Portal or infrastructure-as-code to setup and configure your environment. It is also possible to transition between portal and infrastructure-as-code (recommended) when your organization is ready. As with any other Azure Infrastructure-as-code approaches, you will require skills in Azure Resource Manager Templates and GitHub.

**Start small and scale:** If it is more important to develop these skills and commit to your own decisions as you learn more about the cloud, then a more modular approach may be beneficial. In this approach, the landing zones will only focus on implementing the basic landing zones considerations required to start cloud adoption. As adoption scales, modules in the Govern and Manage methodologies will build on top of your initial landing zones. The design principles of any Azure landing zones' design will outline the specific design areas which will need to be refactored over time.

## Implementation options

The following grid captures some of the landing zones' implementation options and variables that may drive the decision.

| Implementation option | Description | Deployment velocity | Deeper design principles | Deployment instructions |
|---------|---------|---------|---------|---------|---------|---------|---------|
| [CAF Migrate](./migrate-landing-zone.md) | Deploys the basic foundation for migrating low risk assets | Start small | [Design principles](./migrate-landing-zone.md#design-principles) | [Deploy](./migrate-landing-zone.md) |
| [CAF Foundation](./foundation-blueprint.md) | Adds the minimum tools need to begin developing a governance strategy | Start small | [Design principles](./foundation-blueprint.md#design-principles) | [Deploy](./foundation-blueprint.md) |
| [CAF Enterprise-scale](./enterprise-scale.md) | Deploys an enterprise ready platform foundation with all the necessary shared services to support the full IT portfolio. | Enterprise-scale | [Design principles](../enterprise-scale/design-principles.md) | [Deploy](https://github.com/Azure/Enterprise-Scale/blob/master/docs/reference/contoso/Readme.md) |
| [CAF Terraform](./terraform-landing-zone.md) | Third-party path for multi-cloud operating models. This path can limit Azure-first operating models. | Start small | [Design principles](./terraform-landing-zone.md#design-decisions) | [Deploy](./terraform-landing-zone.md#customize-and-deploy-your-first-landing-zone) |

The following table looks at the same implementation options from a slightly different perspective to guide more technical decision processes.

| Implementation option | Hub | Spoke | Deployment technology | Deployment instructions |
|---|---|---|---|---|
| [CAF Enterprise-scale](./enterprise-scale.md) | Included                              | Included | Azure Resource Manager templates, Azure portal, Azure Policy and GitHub | [Deploy](../enterprise-scale/implementation-guidelines.md) |
| [CAF Migrate](./migrate-landing-zone.md)      | Refactor required                     | Included | Azure Resource Manager templates, Azure portal, and Azure Blueprint | [Deploy](./migrate-landing-zone.md) |
| [CAF Terraform](./terraform-landing-zone.md)  | Included in Virtual Datacenter module | Included | Terraform | [Deploy](terraform-landing-zone.md#customize-and-deploy-your-first-landing-zone) |

## Next steps

To proceed, choose one of the implementation options above. Each option includes a link to deployment instructions and the specific design principles that will guide implementation.
