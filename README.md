#### Software Architecture by Example



#### Architecture Decision Records
https://www.youtube.com/watch?v=7Gqn2dbt_JY

Change existing design and find something which makes your eyes raise.
Now you have two choices: 
1. Blindly accept the design and work around it
2. Blindly change the design and ignore the consequences

You would prefer to do neither and this is why we use Architecture Decision Records.
Most designs are badly documented. What is documented is how it is built but not Why it is built the way it is built.
In the most case you only have oral history and what started as clear becomes degraded.
Most designers don't like to write large documents and we don't like reading them before redesigning. 
Michael Nygard proposed of small documents to clarify the most important design decisions:
https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions

Whenever the team makes a decision. We write a small document:

### Title

### Status
What is the status, such as proposed, accepted, rejected, deprecated, superseded, etc.?

### Context
What is the issue that we're seeing that is motivating this decision or change?

### Decision
What is the change that we're proposing and/or doing?

### Consequences
What becomes easier or more difficult to do because of this change?

The decision is written in active voice and only the decision is written down:
- "The car uses a steering wheel"
- "The steering wheel changes the car's direction"
The active voice forces us to find the decision e.g.:
- "A microcontroller will be used in the steering wheel"
- "The microcontroller communicates the horn switch status to the engine controller"

### Recap 
- Not: "Hydrocoptic marzelvanes could be added to turbo encabulators"
- Rather: "The turbo encabulator uses hydrocoptic marzelvanes to prevent sidefumbling"

The decision is also the Title of the adr so we can see all decisions at a glance.
The title includes a number to show what decisions were taken in what order.

### Context
- High time pressure
- Many stakeholders giving input
- Design exploration rather than something reliable

### Consequences
- What alternatives were not chosen
- What does this mean for future developments
- Was it a good solution which no-one understands

#### Status
Each ADR has a status: 
- proposed
- accepted
- rejected
- deprecated
- superseded

After we agree on the decision the ADR is immutable. If we change our idea on the decision we 
write a new ADR with the current context and the new consequences. The old one gets the status superseded
by and the number of the new one.

Writing down the documents does not take a lot of time.
Why we are building, what we are building and the way we are building it.
This will lead to 10 to 100 decisions. The new hire on a design team will understand more
quickly the context for the project.

The most important part is not the tooling. The idea is the important point. If we document the most
important decisions it makes it easier for your future self and future colleagues to make useful changes.

