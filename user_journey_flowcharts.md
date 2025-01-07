# User Journey Flowcharts for Freelancer and Client Personas

This document presents detailed flowcharts for the user journeys of freelancers and clients on the Post Fiat platform, created using Mermaid syntax. The flows cover account creation, task interaction, payment settlement, error handling, and dispute resolution.

## Freelancer Journey Flow

```mermaid
graph TD
    A[Start: Freelancer Signs Up] --> B[Create Profile]
    B --> C[Browse Available Tasks]
    C --> D[Submit Proposal]
    D -->|Proposal Accepted| E[Work on Task]
    D -->|Proposal Rejected| F[Receive Feedback]
    E --> G[Submit Completed Task]
    G -->|Client Approves| H[Payment Released]
    G -->|Client Requests Changes| I[Revise and Resubmit]
    G -->|Dispute Raised| J[Dispute Resolution]
    J -->|Freelancer Wins| H
    J -->|Freelancer Loses| K[No Payment]
    K --> L[End: Feedback for Freelancer]
    H --> L
    F --> C


Key Interaction Touchpoints for Freelancers:

Profile Creation: Enter skills, portfolio, and rates.

Proposal Submission: Tailor responses to tasks with competitive bids.

Task Completion: Deliver quality work and communicate revisions.

Dispute Resolution: Participate in mediation when disputes arise.


Client Journey Flow
graph TD
    A[Start: Client Signs Up] --> B[Post a Task]
    B --> C[Receive Proposals]
    C --> D[Evaluate and Accept Proposal]
    C --> E[Reject Proposals]
    D --> F[Funds Held in Escrow]
    F --> G[Monitor Task Progress]
    G --> H[Approve Completed Task]
    H --> I[Release Payment to Freelancer]
    G --> J[Request Revisions]
    G --> K[Raise Dispute]
    K -->|Client Wins| L[Funds Returned]
    K -->|Client Loses| I
    E --> M[Revise Task Details]
    M --> B
    L --> N[End: Task Feedback]
    I --> N




Key Interaction Touchpoints for Clients:

Task Posting: Clearly define task requirements and budgets.

Proposal Evaluation: Assess freelancer reputation and bids.

Payment and Feedback: Approve deliverables and provide ratings.



Error States and Resolution Paths
Freelancer Errors:
Incomplete Profile: Prompt to fill missing details before task browsing.

Proposal Rejected: Provide actionable feedback to improve submissions.

Client Errors:
Ambiguous Task Description: Suggest edits for clarity.

No Suitable Proposals: Recommend reposting or adjusting task parameters.

Shared Errors:
Payment Failures: Notify users of payment issues and guide them to retry.

Dispute Mismanagement: Offer guided steps for submitting evidence in disputes.

Dispute Resolution Flow (Applicable to Both)
graph TD
    A[Dispute Raised] --> B[Collect Evidence]
    B --> C[Submit Evidence to Arbitrators]
    C --> D[Arbitrators Evaluate Case]
    D -->|Ruling in Favor of Freelancer| E[Release Payment to Freelancer]
    D -->|Ruling in Favor of Client| F[Refund Payment to Client]
    E --> G[Feedback Submitted]
    F --> G
    G --> H[End of Dispute]
