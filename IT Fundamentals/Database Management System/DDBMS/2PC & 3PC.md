## **Two-Phase Commit (2PC)**

- **Two-Phase Commit (2PC)** is a protocol used to coordinate all participants in a distributed transaction to ensure *atomicity*
- either all nodes commit the transaction or all abort, even across failures.

## **# Phases of 2PC**

1. **Prepare (Voting) Phase:**
    - The coordinator sends a *Prepare* message to all participants.
    - Each participant votes by replying with:
        - **Yes/Prepared:** if it can successfully commit.
        - **No/Abort:** if it cannot.
    - Participants log their decision.
2. **Commit Phase:**
    - **If all vote “Yes”:** The coordinator instructs all to commit; participants commit and log the outcome.
    - **If any vote “No”:** The coordinator instructs all to abort; participants abort and log the outcome.
    - The coordinator notifies all participants of the decision, which they then execute.

## **# Characteristics**

- Provides **atomic commit** over multiple nodes.
- **Drawback:** Can cause *blocking -* participants must wait indefinitely for the coordinator if it crashes at certain points, resulting in potential unavailability.

## **Three-Phase Commit (3PC)**

- **Three-Phase Commit (3PC)** improves upon 2PC by dividing the commit process into three distinct phases, reducing the likelihood of blocking and increasing fault tolerance in the face of coordinator failures.

## **# Phases of 3PC**

1. **CanCommit (Prepare) Phase:**
    - The coordinator asks if participants are ready to commit.
    - Votes are returned just like in 2PC; if any say “No”, the protocol aborts immediately
2. **PreCommit Phase:**
    - If all agree, the coordinator sends a *PreCommit* message.
    - Participants acknowledge and enter a state in which they can safely commit, but do not commit yet.
    - This phase allows the protocol to time out and handle failures without indefinite blocking
3. **DoCommit (Commit) Phase:**
    - The coordinator tells participants to commit.
    - All commit and finalize the transaction.

## **# Characteristics**

- **Non-blocking:** If the coordinator fails during certain stages, participants can autonomously decide to commit or abort after a timeout.
- **Extra safety:** The additional phase ensures that no participant commits unless all are known to be ready, avoiding inconsistent outcomes and reducing the risk of indefinite waiting found in 2PC.

## **2PC vs. 3PC: Summary Table**

| Feature | 2PC | 3PC |
| --- | --- | --- |
| Phases | 2: Prepare, Commit | 3: CanCommit, PreCommit, DoCommit |
| Blocking Issues | Can block indefinitely on failures | Designed to avoid blocking |
| Fault Tolerance | Limited (blocking possible) | Higher (better recovery from coordinator failure) |
| Complexity | Simpler | More complex (extra phase, messages) |
| Usage | Standard in many databases, applications | Used in scenarios demanding higher availability |