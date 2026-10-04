# Hosting And Inference Options

Status: evaluation framework. No cloud account, provider, region, or monthly
budget has been selected or provisioned.

## Deployment Shapes To Compare

| Shape | Fit | Main risks / questions |
| --- | --- | --- |
| Local application | Fastest private prototype; user data and local tools stay on one machine. | Availability, updates, backups, mobile access, and remote device pairing. |
| Private single-owner cloud | Always-on jobs and cross-device access without inviting other users yet. | Protecting personal data, hosted-provider terms, credential custody, and ongoing cost. |
| Multi-tenant hosted service | Future product for invited users or customers. | Tenant isolation, data protection obligations, abuse, support, incident response, and provider approval. |
| Hybrid control plane plus local companion | Hosted scheduling/chat with scoped access to the user's actual computer. | Local agent pairing, updates, offline behavior, network relay, revocation, and host compromise. |

## AWS Candidate For Evaluation

A plausible AWS design to price and validate later is a containerized web/API
control plane on ECS, managed PostgreSQL on RDS, object storage for user files,
and cloud key management/secrets services. Keep computer workers in a separate
isolated pool. Evaluate GPU-backed inference separately: AWS documents GPU
workloads on ECS GPU-capable container instances, which is operationally
different from ordinary CPU application containers. Do not assume a GPU worker
is economical while idle or required for the initial prototype.

AWS references:

- [ECS persistent storage options](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/using_data_volumes.html)
- [ECS GPU workloads](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-gpu.html)
- [RDS for PostgreSQL capabilities](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_PostgreSQL.html)
- [RDS encryption](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html)

This is a candidate pattern, not a recommendation to purchase or deploy AWS
resources now. The first app prototype should be local or on the smallest
reversible environment that tests the selected workflow.

## Evaluation Criteria

- EU region/data location and the ability to explain where prompts, files,
  logs, credentials, and backups go.
- Isolated task/computer workers with short-lived scoped credentials and
  network egress controls.
- Separate durable database/object storage from disposable execution
  containers.
- GPU availability, queueing, scale-to-zero/idle costs, model loading time,
  throughput, and capacity quotas.
- Outbound connectivity to a user-installed desktop companion without opening
  inbound ports on the user's home network.
- Tenant-level cost attribution, budget caps, and kill switches.
- Backup/restore, account deletion, operational alerts, deployment rollback,
  and recovery objectives.
- Engineering effort, portability, exit strategy, and monthly cost under
  measured low, expected, and peak usage.

## Decision Gate

DOT-007 should compare AWS with at least one managed-container alternative
after DOT-002 defines the first workflow and DOT-004/DOT-006 define storage and
tenant boundaries. No cloud deployment or GPU purchase is authorized by this
planning document.
