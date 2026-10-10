# \# databricks-aws-platform

# 

# A hands-on project to build and automate a Databricks platform on AWS using Terraform, Databricks Asset Bundles (DABs) and GitHub Actions.

# 

# > \*\*Status:\*\* work in progress (started 9 Oct 2026). See the progress table below.

# 

# \## Why this project

# 

# <!-- TODO: 2-3 sentences in your own words. Example prompts:

# &#x20;    - What problem does this project solve?

# &#x20;    - Why Databricks on AWS?

# &#x20;    - What do you want to prove you can do? -->

# 

# TODO

# 

# \## Planned architecture

# 

# ```

# GitHub (code, PRs)

# &#x20;  |

# &#x20;  v

# GitHub Actions (validate, scan, plan, deploy)

# &#x20;  |                          |

# &#x20;  v                          v

# Terraform                 Databricks Asset Bundles

# (platform)                (workloads)

# &#x20;  |                          |

# &#x20;  v                          v

# AWS: VPC, IAM, S3        Databricks: jobs, notebooks

# Databricks workspace     per environment (dev / prod)

# Unity Catalog

# ```

# 

# \- \*\*Terraform\*\* owns the platform: network, IAM, storage, workspace, Unity Catalog and permissions.

# \- \*\*Databricks Asset Bundles\*\* own the workloads: jobs, notebooks and their per-environment settings.

# \- \*\*GitHub Actions\*\* validates, scans and deploys both, with approval before prod.

# 

# <!-- TODO: replace the diagram with a real one in docs/ once you have drawn it -->

# 

# \## Repository structure

# 

# ```

# databricks-aws-platform/

# &#x20; terraform/

# &#x20;   modules/          network, iam, workspace, unity-catalog

# &#x20;   envs/             dev, prod

# &#x20; bundles/

# &#x20;   sales\_etl/        Databricks Asset Bundle (databricks.yml, src/, resources/)

# &#x20; .github/workflows/  CI/CD pipelines

# &#x20; policies/           Policy as Code rules

# &#x20; docs/               notes and architecture diagrams

# ```

# 

# \## Progress

# 

# | Area | Status |

# |---|---|

# | Local tools (Terraform, AWS CLI, Databricks CLI, Python, Checkov, Git) | Done |

# | Databricks Free Edition: notebook, job, schedule, run | Done |

# | Unity Catalog basics: catalog, schema, table | Done |

# | Concept notes (`docs/concepts.md`) | In progress |

# | AWS account and safety setup | TODO |

# | Terraform: network, IAM, workspace | TODO |

# | Terraform: Unity Catalog and grants | TODO |

# | Databricks Asset Bundle with dev and prod targets | TODO |

# | GitHub Actions: Terraform pipeline | TODO |

# | GitHub Actions: bundle deployment pipeline | TODO |

# | Policy as Code (Checkov, OPA or Kyverno) | TODO |

# | Git branching strategy and PR checks | TODO |

# 

# <!-- Update this table as you finish each item. Only mark "Done" for things you have actually built and tested. -->

# 

# \## Tools

# 

# \- Terraform

# \- AWS CLI v2

# \- Databricks CLI (new CLI, v0.205 or higher)

# \- Python 3.12

# \- Checkov

# \- Git and GitHub

# 

# \## Getting started

# 

# <!-- TODO: fill in once the Terraform and bundle code exists. Suggested outline:

# 1\. Prerequisites (AWS account, Databricks account, tools above)

# 2\. Configure AWS credentials and the Databricks CLI profile

# 3\. Deploy the platform: terraform init / plan / apply in terraform/envs/dev

# 4\. Deploy the bundle: databricks bundle validate / deploy -t dev

# 5\. Tear down: terraform destroy

# \-->

# 

# TODO

# 

# \## Security notes

# 

# \- No credentials, tokens or state files are committed. `.gitignore` excludes `\*.tfstate`, `\*.tfvars`, `.terraform/`, `.databricks/` and `.env`.

# \- CI/CD is planned to use OIDC and a Databricks service principal, not long-lived personal tokens.

# 

# \## Cost notes

# 

# <!-- TODO: add what you learn, for example which resources cost money (NAT gateway, running clusters)

# &#x20;    and how you clean up (terraform destroy after each session). -->

# 

# TODO

# 

# \## What I learned

# 

# See \[`docs/concepts.md`](docs/concepts.md) for my notes on notebooks, jobs, runs, Unity Catalog and troubleshooting.

# 

# \## Roadmap

# 

# \- Week 1: Databricks and Unity Catalog fundamentals

# \- Week 2: Terraform for Databricks on AWS

# \- Week 3: Asset Bundles, CI/CD, Git governance and policy checks

