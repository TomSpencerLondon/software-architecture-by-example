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

### Neal Ford Fundamentals of Software Architecture: Chapter 19 - Architecture Decisions
- Architecture decisions involve the structure of the applicatoin or system, but can involve technology deicisions
- Good architecture decision helps guide development teams to make the right technical choices
- Making architecture decisions involves gathering enough relevant information, justifying the decision, and effectively
communicating the decision to the right stakeholders

#### Architecture Decision Anti-Patterns
- Anti-pattern = something that seems to be a good idea when you begin but leads to trouble
- Anti-pattern = repeatable process that produces negative results
- 3 main architecture anti patterns:
  - Covering your assets
  - Groundhog Day
  - Email driven Architecture
- They are progressive
  - Covering your assets = overcoming => Groundhog Day = overcoming => Email-Driven Architecture
- Making effective and accurate architecture decisions requires architect to overcome all three anti-patterns

#### Covering your assets Anti-Pattern
- Architect avoids or defers making an architecture decision out of fear of making the wrong choice
- Two ways to overcome:
1. Wait until last responsible moment to make an important architecture decision
   - wait until have enough information to justify and validate the decision
   - Not wait too long to fall into Analysis Paralysis 
2. Continually collaborate with development teams to ensure that the decision you made can be implemented as expected
  - Close collaboration enables the architect to respond quickly to change in architecture decision

#### Groundhog Day Anti-Pattern
- People don't know why a decision was made so it keeps getting discussed over and over and over
- Comes about because architect has failed to provide a justification for the decision
- Four most common business justifications include cost, time to market, user satisfaction and strategic positioning

#### Email-Driven Architecture Anti-Pattern
- People lose, forget or don't even know an architecture decision has been made and cannot implement the decision
- Email is good tool for communication but poor document repository system
- Don't include architecture decision in the body of the email
- Often important details including justification are left out of the email => groundhog day anti-pattern
- Better mention only the nature and context of the decision in the body of the email and provide link to single system of record
- only notify people who really care about the architecture decision:
  - "Hi Sandra, I've made an important decision regarding communication between services that directly impacts you. Please see the
decision using the following link..."
  - important decision regarding communication between services (context)
  - directly impacts you (impact for person)
  - Single system of record for the decision

#### Architecturally significant
- Architecturally significant = decisions that affect the structure, nonfunctional characteristics, dependencies, interfaces or construction
techniques
- structure refers to decisions that impact patterns or styles of architecture being used
- nonfunctional characteristics = ilities
- dependencies = coupling points between components and / or services in the sysetm => affect scalability, modularity, 
agility, testability, reliability and so on
- Interfaces = how services and components are accessed and orchestrated - through gateway, integration hub, service bus or API proxy.
  - defining contracts including versioning and deprecation of the contracts
- construction techniques = decisions on platforms, frameworks, tools and processes that impasct some aspect of the architecture

#### Architecture Decision Records
https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions
https://www.thoughtworks.com/radar/techniques/lightweight-architecture-decision-records
- short text file (one to two pages) describing a specific architecture decision
- markdown or asciidoc
- Nat Pryce ADR-tools
- Micha Kops:  https://www.hascode.com/2018/05/managing-architecture-decision-records-with-adr-tools/
  - The Agile Manifesto states that “Working software over comprehensive documentation” but this does not mean that there should be no documentation at all.
  - a good facility on adr-tools is adr list:
```bash
$ adr list
doc/architecture/decisions/0001-record-architecture-decisions.md
doc/architecture/decisions/0002-use-hystrix-to-stabilize-integration-points.md
doc/architecture/decisions/0003-use-thrift-for-data-serialization-between-system-a-and-system-b.md
```
- adr-tools also has a tool for superseding a decision
```bash
 adr generate graph
digraph {
  node [shape=plaintext];
  _1 [label="1. Record architecture decisions"; URL="0001-record-architecture-decisions.html"]
  _2 [label="2. Use Hystrix to stabilize integration points"; URL="0002-use-hystrix-to-stabilize-integration-points.html"]
  _1 -> _2 [style="dotted"];
  _3 [label="3. Use Thrift for data serialization between system a and system b"; URL="0003-use-thrift-for-data-serialization-between-system-a-and-system-b.html"]
  _2 -> _3 [style="dotted"];
  _3 -> _4 [label="Superceded by"]
  _4 [label="4. Use Avro for data serialization between system a and system b"; URL="0004-use-avro-for-data-serialization-between-system-a-and-system-b.html"]
  _3 -> _4 [style="dotted"];
  _4 -> _3 [label="Supercedes"]
}
```

<img width="392" alt="image" src="https://user-images.githubusercontent.com/27693622/226395520-9f7b7272-0432-42a1-b82a-595915bcdca2.png">
- When ADRs are linked somehow we want to document this and adr link eases this for us. Let’s use an example where ADR #4 amends ADR #2 so that we could link both with the following command:
```bash
$ adr link 4 Amends 2 "Amended by"
```

#### ADRs and request for comments (RFC)
- Request for Comments status - specify deadline for when review would be complete

#### Compliance
- Neal Ford suggests Compliance section - forces the architect to think how the architecture decision will be measured and governed
from compliance perspective
- Possible to automate the decision with a fitness function
- ArchUnit - measure interaction of business and services layer

<img width="362" alt="image" src="https://user-images.githubusercontent.com/27693622/226397857-e2e62098-3db9-4ae0-b6db-4bebeaeb5754.png">

- Measured by using ArchUnit
```java
class ArchUnit {

  @Test
  public void shared_services_should_reside_in_services_layer() {
      classes().that().areAnnotatedWith(SharedService.class)
              .should()
              .resideInAPackage("..services..")
              .because(
                      "All shared services classes used by business " + 
                      "objects in the business layer should reside in the services " +
                      "layer to isolate and contain shared logic" +
              ).check(myClasses);
  }
}
```

### Notes
Neal Ford also advises using a notes section:
- original author
- approval date
- approved by
- superseded date
- last modified date
- modified by
- last modification

### Storage
- Large applicatoins not stored in code
- store in a wiki or in a shared directory on a shared file server 
which can be accessed easily by a wiki or other document rendering software
- Example directory structure:
<img width="352" alt="image" src="https://user-images.githubusercontent.com/27693622/226399463-bacb909e-a013-48fc-8bbe-2152943160e5.png">

- application = decisions specific to application context
  - common = apply all applications
    - e.g. "All framework related classes will contain an annotation identifying the class as belonging to the underlying framework code"
  - others specific application context
- integration = ADRs involving communication between application, systems / services
- enterprise = global architecture decisions impacting all systems and applicatoins
  - e.g. "All access to a sysetm database will only be from the owning sysetm"
- Each ADR in wiki sysetm is single wiki page within each navigational landing page
  (Application, Integration or Enterprise)
- ADRs are standard for documenting software architecture
- ADRs can also be used for standards
  - forces the architect to justify the standard

### Example - Going Going Gone
- Use of event-driven microservices
- Splitting up the bidder and auctioneer user interfaces
- Use of Real time Transport Protocol for video capture
- Use of single aPI layer
- Use of publish-and-subscribe messaging

"Every architecture decision made in a system no matter how obvious should be documented and justified"
<img width="433" alt="image" src="https://user-images.githubusercontent.com/27693622/226401346-be33faa3-285f-4132-beab-0b22247b4441.png">

<img width="248" alt="image" src="https://user-images.githubusercontent.com/27693622/226401429-c53f859c-d431-4d94-9942-e8decc0bd9a2.png">


