#### Software Architecture by Example
https://www.youtube.com/watch?v=KWKrSw_wI3s

Neal Ford and Mark Richards - how do you become a software architect? This is the inspiration for
Fundamentals of Software Architecture. Software Architecture by Example O'Reilly learning platform. How do we practice architecture.
We need to practice to get better but designing opportunities are few and far between.


### Going...Going...Gone!
An auction company wants to take their auctions online to a nationwide scale--customers choose the auction to participate in, wait until the auction begins, then bid as if they were there in the room, with the auctioneer

- **Users**: scale up to hundreds of participants (per auction), potentially up to thousands of participants, and as many simultaneous auctions as possible
- **Requirements**:
  - bidders can see a live video stream of the auction and see all bids as they occur
  - auctions must be as real-time as possible
  - both online and live bids must be received in the order in which they are placed
  - bidders register with credit card; system automatically charges card if bidder wins
  - participants must be tracked via a reputation index
- **Additional Context**:
  - auction company is expanding aggressively by merging with smaller competitors
  - if nationwide auction is a success, replicate the model overseas
  - budget is not constrained -- this is a strategic direction
  - company just exited a lawsuit where they settled a suit alleging fraud

### Structural Design in Software Architecture
This is quite narrow but important part which is structural design. What is the starting point of the architectural style?
There are two activities to structural design which feed into the above question:
1. Architecture Characteristics
2. Logical design

### Architecture Characteristics
We have requirements for Going, Going, Gone. This is part of the structural design. We will do the logical architecture next.

![image](https://user-images.githubusercontent.com/27693622/225914730-2b7ad86a-9401-4cf7-bf8f-9c6372efe353.png)
These are often called non-functional, cross-cutting requirements. System quality attributes another term sounds like QA.

There are three parts to architecture characteristics
![image](https://user-images.githubusercontent.com/27693622/225916115-81716f0b-3cc2-4c8a-b4aa-dfb33f0527ce.png)

There can be more than one set of architecture characteristic which would lead to a distributed architecture.
The most important part of architecture characteristics is the part that is critical or important to application success.
For example, if we want to improve security we will impact performance because we have to do encryption, secrets hiding.
If we support more architecture characteristics it necessarily makes the architecture more complex. The advice is to embrace simple
design - the answer is support less stuff. The domain sits on top of the different characteristics. We shouldn't talk about the
best design but the least worst design.

![image](https://user-images.githubusercontent.com/27693622/225917687-df56555a-8be8-40bf-b770-cd46d5b7addb.png)

Operational architecture characteristics are important because in modern architectures like microservices these are where 
architecture and devops meet. These influence architecture. There are also quality and security.

![image](https://user-images.githubusercontent.com/27693622/225966326-6f089108-e47d-4806-a658-718a37a993f0.png)

![image](https://user-images.githubusercontent.com/27693622/225969865-151ba934-92ac-48e4-9c19-dc03b17d1156.png)

![image](https://user-images.githubusercontent.com/27693622/225972064-c7bfc9c0-9c49-44cf-bad9-5976e082924d.png)

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

