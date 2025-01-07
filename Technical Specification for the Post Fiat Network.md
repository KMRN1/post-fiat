Technical Specification Document for Post Fiat Network

Use Case: Decentralized Freelance Marketplace

Overview

The Post Fiat network facilitates a decentralized freelance marketplace where users can post tasks, verifiers ensure the tasks are completed as required, and rewards are distributed fairly based on contributions and validation. This document outlines the technical workflow, task verification mechanisms, reward distribution logic, and the interactions between the system’s key components.

Key Components

Users (Task Creators):

Submit tasks to the network with specific requirements.

Deposit rewards in escrow upon task creation.

Workers:

Accept tasks and submit completed work for validation.

Verifiers:

Validate submitted tasks based on predefined criteria.

Reach consensus using a decentralized validation mechanism.

Post Fiat Network:

Acts as the orchestrator for task creation, verification, and reward distribution.

Workflow

1. Task Creation

A user creates a task specifying:

Task description.

Requirements for completion.

Reward amount (deposited in escrow).

Deadline for submission.

2. Task Submission

Workers select tasks from the marketplace and submit their completed work.

3. Verification Process

Verifiers review the submitted work against the requirements.

Verifiers vote on the validity of the submission (e.g., valid, invalid, or requires changes).

The network applies a consensus mechanism (e.g., majority voting or weighted scoring) to finalize the verification outcome.

4. Reward Distribution

If the submission is verified as valid:

The worker receives the reward.

Verifiers receive a share of the escrow as compensation for their work.

If the submission is invalid:

The reward is refunded to the task creator.

Verifiers are compensated for their effort.

A small network fee is deducted for operational costs.

Verification Mechanism

Consensus Protocol

Verifiers are randomly selected or stake tokens to participate.

Each verifier reviews the submission and casts their vote.

A threshold consensus (e.g., 70% majority) determines the final outcome.

Dispute Resolution

In case of disagreements, a higher-tier validation group or arbitration mechanism resolves disputes.

Sequence Diagrams

Diagram 1: Task Creation

graph TD;
    User -->|Create Task| Network;
    Network -->|Escrow Reward| Escrow;
    Network -->|Publish Task| Marketplace;

Diagram 2: Task Submission and Verification

graph TD;
    Worker -->|Submit Work| Network;
    Network -->|Notify Verifiers| Verifiers;
    Verifiers -->|Validate Submission| Network;
    Network -->|Consensus Reached| Result;

Diagram 3: Reward Distribution

graph TD;
    Result -->|Valid| Worker;
    Worker -->|Receive Reward| Wallet;
    Result -->|Compensate| Verifiers;
    Verifiers -->|Receive Payment| Wallets;

Reward Distribution Logic

Worker Rewards:

Full reward upon successful task verification.

Verifier Rewards:

A percentage of the escrow based on their contribution to the validation process.

Network Fees:

Deducted from the escrow before distribution.

Publishing and Repository

This document and associated diagrams are published in a public repository for transparency and collaboration:

Repository URL: https://github.com/postfiat/documentation

File Structure:

/specifications: Contains detailed technical specifications.

/diagrams: Includes sequence diagrams in .png and .mermaid formats.

/README.md: High-level overview of the repository.
