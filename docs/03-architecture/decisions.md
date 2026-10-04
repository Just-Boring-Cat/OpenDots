# Architecture And Product Decisions

Decision states: `accepted` means the owner selected the direction;
`provisional` means a working boundary is being used; `open` means do not
implement as a settled choice.

| ID | State | Decision | Reason / follow-up |
| --- | --- | --- | --- |
| D-001 | accepted | Start from the public `CopilotKit/OpenDots` repository as a fork. | Owner requested a separate repository and product. Base commit is recorded in `docs/00-start-here.md`. |
| D-002 | accepted | Keep this product separate from Agent Harllens and Agent Context Kit. | Avoid mixing product identity, runtime, data, and roadmap. |
| D-003 | accepted | Context Kit is optional for product users. | Standalone operation must remain possible. Product integration contract is open. |
| D-004 | accepted | The private Context Kit checkout is local-only and ignored in this public repo. | A private submodule URL/pointer must not be published. The operator requested local project context. |
| D-005 | provisional | Keep the repository name `OpenDots` while product naming is undecided. | Do not claim a new product brand yet. |
| D-006 | accepted | Start discovery with a single-owner proof, while treating multi-user isolation as a non-negotiable future release gate. | The upstream template is single-owner; it is not ready for multiple users as-is. |
| D-007 | open | Provider, identity, persistence, device-control, and hosting implementations. | Resolve through DOT-003 to DOT-007 before product implementation. |
| D-008 | open | Whether CopilotKit Intelligence remains the durable conversation service. | Compare portability, security, operating cost, and user data requirements in DOT-004. |

Update this table when the owner makes a decision. Link larger choices to
separate ADRs rather than expanding this table into a design document.
