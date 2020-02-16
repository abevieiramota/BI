# Notes The DW toolkit

- Every stakeholder should be aware of the DW lifecycle
- "Implementing a data warehouse requires tightly integrated activities." p.331
- "Best-of-breed technologies won't salvage a data warehouse that fails to focus on the business." p.333

# High level
- 1.0 -> structure
- 2.0 -> goals -> aligned with business 
- 3.0, 4.0 -> which tools to use 
- 5.0, 6.0, 7.0 -> from operational sources to analytical bases
- 8.0, 9.0 -> user interfaces 
- 10.0 -> put everything together to production
- 11.0 -> suport and grow 
- 12.0 -> guarantee the structure 

# Detailed
- 1.0 - Project Planning
    - 1.1 - Assessing readiness
    
        factors that help predict the success of a project (! for critical):
        - !Strong business sponsor
            - good: {has a vision, leader}
            - bad: {lone sponsor, too much demand, missing in action}
        - !Strong business compelling motivation:
            - "dw needs to solve critical business problems in order to garner the resources required for a successful launch and healthy lifespan" p.335
            - ROI
            - SWAT matrix -> external x internal motivations
        - !Feasability:
            - data quality
            - technical resource feasability:
        - Relationship between Business and IT
            - do they understand and respect each other?
        - Data-driven culture:
            - "The businesspeople already immersed in numbers likely will be more receptive to a data warehouse." p.335
            - intuition/culture driven -> data-driven
    - 1.2 Scoping
        - when starting -> focus on data from single business process (cross-process projects for later)
        - define with business a scope both compelling and doable
        - avoid the law of too:
            - too firm of a commitment
            - too brief of a timeline
            - too many source systems
            - too many users
            - in too many locations
            - with too diverse analytic requirements
    - 1.3 Justification
        - estimation of costs x estimation of benefits
        - benefits -> look to {SWAP, problems, opportunities, deficiencies}
        - maximize benefits, minimizing costs -> cost x benefits quadrant
        - hard justification -> sign of wrong sponsor or wrong problem
    - 1.4 Staffing
        - roles + responsibilities
        - one person can fill more than one role
        
            roles in Business
            - Business Sponsor - ultimate client and advocate of the dw
            - Business Driver - delegated by the sponsor
            - Business Lead - ~Product Owner
            - Business Users - need to be involved early and often, beginning with the scope and requirements -> "Without business users, the dw is a technical exercise in futility." p.337
            
            tech+business
            - Business System Analyst - understand the business and translate into analytics
            - Business Subject Matter Expert - knows the business data very well
            - Analytic Application Developer - front
            - Data Warehouse Educator - education on data, apps and access tools

            technical
            - Project Manager - must be respected by business executives and technical analysts
            - Technical Architect - overall technical and security architecture -> plan that ties together the pieces of the technical solution
            - Technical Support Specialist - specialist in tools used in the project
            - Data Modeler - models the data that will feed the front
            - Database Administrator - DBA
            - Metadata Coordinator - ensures all metadata is collected, managed, and disseminated
            - Data Steward - responsible for enterprise agreement on the DW conformed dimensions and facts
            - Data Staging Designer - ETL
            - Data Warehouse Support - ongoing backroom and front room support -> often individuals that worked in the project
    - 1.5 Developing and Maintaining the Project Plan
        - estimation, communication
        - each role estimates their tasks
        - negotiation with business
        - Project Manager -> use communication matrix
            - business sponsor -> bimonthly face-to-face -> {issue resolution, expectation management, funding}
            - business community -> monthly with a website -> {requisite involvement, expectation management, critical dates}
            - project team -> weekly status meeting -> {progress, issue identification and resolution}
            - IT colleagues -> bimonthly IT staff meeting -> {expectation management, resource needs}
        - DW projects are vulnerable to scope creep! don't try to satisfy all user's needs
        - change -> {add time, resource or money; remove old scope items; say no}
- 2.0 Business Requirements Definition
    - 2.1 Requirements Preplanning
        - choose the forum {interview - easier to schedule; facilitated session -->> reunião indivual ou em grupo}
            - extract from business {what they do, why, how they make decisions}
            - extract from IT {data availability and quality}
            - organizational therapy
            - don't survey -> {flat/closed, to create bond between people and respondent is one of the goals of gathering requirements, and survey is bad with that}
        - Identify and prepare the requirements team
            - roles {lead interviewer -> explores, interview scribe(s) -> take valuable notes/preprocess answers}
            - before interviews, learn a little about the matters
            - prepare the questions beforehand (#TODO - see 2.2, prepare for each interviewee profile), but as a fallback and not as a script
        - Select, schedule, and prepare business representatives
            - you should talk to people that represent horizontal matters across the org -> business process driven
            - 3~4 interviews/day, 1~1.5 hour per interview, 0.5 hour interval between interviews
            - before interviews, conduct a project launch meeting with the users + business sponsor, stressing his commitment and importance of everyone's participation + show business ownership of the project ~> maybe by e-mail, if in person is difficulty
            - highlight the topics to be covered in interviews and ask interviwees to bring copies of their key reports and analysis
        - keys to dw project planning and management p.340:
            - having a solid business sponsor;
            - balancing high value and doability to define the scope;
            - working with the best team possible to develop a detailed project plan;
            - being an excellent project manager by motivating, managing, and communicating up, down, and across the organization
    - 2.2 Collecting the Business Requirements
        - launch - define who will introduce the interview; focus on project, its goals and the interview goals -> make a script prior; don't talk about technology
        - interview flow - goal: understand what users do and why -> ask about their responsibilities and organizational fit; then about their key performance metrics, how they track success and progress -> this translates to dimensional model
        - questions like 'how do you distinguish between students' or 'how do you categorize them' help identify dimension attributes and hierarchies
        - if the interviewees are more analytical -> ask about their analysis; ask for samples of reports; understand -> that will become input to design application tools
        - if the interviewees are business executives -> ask about their vision to leveraging information -> that become input to the project's goals
        - ask about expected benefits -> manage expectations, capture more potential
        - ground rules for effective interview p.344:
            - remember your interview role; listen and absorb like a sponge;
            - strive for a conversational flow; don't dive too quickly (or pull out a copy of a potential data elements);
            - verify communication and capture terminology precisely because most organizations use terminology inconsistently;
            - establish a peer basis with the interviwee; use his vocabulary
        - wrap-up
            - ask users about success criterias -> make it measurable! touchable, objective
            - make clear that this is a collection of requirements, not the goal of the first phase of the project
            - manage expectations
        - conducting data-centric interviews
            - the goal is to assess data availability and its quality, with the data gurus
            - "we're trying to learn enough at this point to manage organization's expectations appropriately."
    - 2.3 Postcollection documentation and follow-up
        - after interview -> interview debriefing -> ensure the team are on the same page; review notes
        - two levels of documentation can be made:
            - 'ata' - it should make sense to someone who wasn't in the interview
            - consolidated findings - organized by business process, list findings related to them
                
                structure:
                - 1. Executive summary
                - 2. Project overview - participants and process used
                - 3. Requirements findings - for each business process discussed {why users want to analyze them, what capabilities they desire, their current limitations, potential benefits and impacts, sample of questions that could be answered post project, feasability}
                - 4. Matrix of business processes x groups/functions that have opportunities to work better with analytic support for those processes
        - prioritization and consensus -> prioritization meeting:
            - show a overview of the findings, make everyone know the big view; 
            - develop a prioritization quadrant -> try to come to a consensus on a feasibility x business impact matrix:
                - feasible and high impact -> DW now
                - not feasible and high impact -> work to make it feasible
        
- 3.0 Technical Architecture Design
    - "the architecture plan serves as an organizing framework to support the integration of technologies." and as a comunication tool {architect, team, management, vendors}
    - "allows us to catch problems on paper", to order the activities, reuse
    - 3.1 Eight-Step process for creating the technical architecture
        - care with under architected and over architected
        - 'every dw has a technical architecture. The question is whether yours is planned and explicit or merely implicit.' p.349

            eight steps to develop the architecture plan
            - 1. establish an architecture task force {technical architect, staging designer, analytic app developer} {they should plan its activities, and educate the rest of the team}
            - 2. collect architecture-related requirements {business requirements, timing, availability, peformance needs, technology standards, nonnegotiable boundaries, prior experiences, willingness to accomodate operational change on behalf of the dw} -> architecture-related requirements
            - 3. document architecture requirements -> table with business requirements, and findings of the previous task, and their implications in the architecture
            - 4. develop a high-level architecture model -> from the requirements, start defining the components {data staging, data access, metadata, infrastructure}
            - 5. design and specify the subsystems -> refine the model, design the components -> for each component, list requisites capabilities; consider the security requirements and physical infrastructure/configuration -> try to leverage enterprise-level resources
            - 6. determine architecture implementation phases -> define the phases of development
            - 7. document the technical architecture -> "the technical architecture plan document should include adequate detail so that skilled professionals can proceed with construction of the framework, much like carpenters frame a house based on the blueprint." p.351
            - 8. review and finalize the technical architecture -> {review, communicate, educate, manage expectations}

- 4.0 Product Selection & Installation
    - 4.1 Understand the corporate purchasing process
    - 4.2 Develop a product evaluation matrix -> product x evaluation criteria
    - 4.3 Conduct market research
    - 4.4 Narrow options to a short list and perform detailed evaluations -> if the product will serve business users, involve them; share relevant architectural information with vendors, so they can show how their tools satisfy our requirements, and not on the 'products bells and whistles'; talk with vendor references, both the ones they suggest, and the ones you discover; try to talk with references with similar requirements/size of installations
    - 4.5 coduct prototype, if necessary -> if there is a winner, ok; else, choose best two and prototype {observe venders developing, manage expectations}
    - 4.6 select product, install on trial, and negotiate -> don't buy in a hurry -> trial and evaluate

- 5.0 Dimensional Modeling
    - "immediately following the business requirements definition, we should draft (or revisit) the data warehouse bus matrix" p.353 dimensions x business processes
    - select the first business process to work on
    - now is the time to analyse {granularity, historical consistency, valid values, attribute availability, inconsistencies, challenges} -> {business subject matter experts, power analysts}
    - conduct design workshops with {business system analyst, business subject matter expert, business power analyst, data modeler} -> make someone responsible for logging and documenting issues and resolutions; evaluate if the model can support the key needs and questions of the business requirements! don't let the modeler work alone!
    - when the model is stable, communicate and validate -> first with the IT and DW team, then with the business
    - communicate the model to the users -> simplify the model
    - documentation -> {tables, columns, definitions, calculation rules, slowly changing dimensions}
    - adopt standard naming conventions for the data elements early in the process!

- 6.0 Physical Design
    - physical design and performance tuning, partitioning, file layouts
    - some of the techniques, like indexing and aggregation, should evolve as the dw is being used
    - indexing -> btree to high cardinality, bitmap to medium/low cardinality; composity index -> date FK first, because dates are the most used
    - partitioning -> good for query performance, data loading/deleting, index
    - implement usage monitoring system as early as possible!

- 7.0 Data Staging Design & Development
    - "while the iceberg looks formidable from the ship's helm, we often don't gain a full appreciation of its magnitude until we collide with it and discover the mass that's lurking beneath the water's surface." p.358
    - much of the heavy lifting occurs in the transform step {combine data, deal with quality issues, identify updated data, manage surrogate keys, build aggregates, handle errors}
    - 7.1 Dimensional table staging
        - take care, because dimensions should be shared with others data mart (integration) -> "the dimension authority is responsible for defining, maintaining, and publishing a particular dimension for the appropriate data marts." p.358
        - dimensions can be processed concurrently -> but they must be processed before the fact tables
        - 1. extract dimensional data from operational source systems -> audit statistics;
        - 2. cleanse attribute values -> parse, inconsistent descriptive values, invalid data, missing data; 
        - 3. manage surrogate key assignments; 
        - 4. slowly changing dimensions; 
        - 5. build dimension row and publish revised dimensions
    - 7.2 Fact table staging
        - 1. extract fact data from operational source systems
        - 2. receive updated dimensions from the dimension authorities
        - 3. separate the fdact data by granularity as required
        - 4. transform the fact data as required
        - 5. replace operational source keys with surrogate keys
        - 6. add aditional keys for known context
        - 7. quality-assure the fact table data
        - 8. construct or update aggregation fact tables
        - 9. bulk load the data
        - 10. alert the users

- 8.0 Analytic Application Specification
    - don't assume all users will need a high flexible environment -> part (maybe a large percentage) of them will be satisfied with parameter-driven analytic applications
    - start with a set of 10~15 analytic applications (each one is like a question in metabase)
    - define and follow standards/conventions
    - define their locations -> paths/organizations on the portal
    
- 9.0 Analytic Application Development 
    - follow standards for naming conventions, calculations, libraries, and coding
    - invest in tool training/education
    - start app dev in parallel with staging dev -> interactively consume staged data, dev app, give feedback {errors, performance, etc}
    - plan time to that feedback loop!

- 10.0 Deployment 
    - educate prior deployment!
    - develop education materials (estimate 1~2 days to develop 1 hour of educational materials)
    - consider the following for an effective education program:
        - understand your target audience; don't overwhelm;
        - don't train the business community early prior to the availability of data and analytic applications;
        - postpone the education (and deployment) if the dw is not ready to be released;
        - gain the sponsor's commitment to a 'no education, no access' policy
    - define support resources and procedures
    - plan app maintenance and release plan
    - dev -> alpha test (team) -> beta test (business users) -> release

- 11.0 Maintenance and Growth
    - support -> the support team should be working proactively with the users, after the education; they must be easily accessible
    - education -> continuing education program; curriculum {formal refresher, advanced courses, introductory courses (repeated)}
    - technical support -> SLA, monitor performance and system capacity trends. "We don't want to rely on the business community to tell us that performance has degraded." p.366
    - program support -> continuous assessment of the use of the dw -> "We need to market our success." p.366
    - if good work -> more will be demanded! {new users, new data, new app, enhancements} -> prioritization -> program management -> project planning
- 12.0 Project Management

---

# Common dw mistakes to avoid

- don't talk to the business users; rather, rely on consultants or internal experts to give you their interpretation of the user's dw requirements; -> "Nothing substitutes for direct interaction with the users."
- agree to deliver a high-profile customer-centric data mart, ideally customer profitability or customer satisfaction, as your first deliverable; -> too complex, unfeasible, challanging etc to a first interaction
- encourage the business users to give you continuous feedback throughout the development cycle about new data sources and key performance metrics they would like to access, and make sure to include these requirements in the in-process release; -> care with scope creep
- don't bother the senior executives of your organization with the dw until you have implemented it and can point to a significant success; -> the senior management must support the project from the beginning
- before implementing the dw, do a comprehensive analysis describing all possible data assets of the enterprise and all intended uses of information, and avoid the seductive illusion of iterative development, which is only an excuse for not getting it right the first time; -> start small, focused and dealing with the most feasible and important business process -> increment interactively
- assume that business users naturally will gravitate toward robust data and develop their own killer analytic applications; -> be flexible, but not at the point it becomes another barrier to users
- train every user on every feature of the data access tool in the first training class, defer data content education because the class uses dummy data (the real data won't be ready for another couple of months), and declare success at the completion of the first training class because the dw has been rolled out to business users; -> train with real data, with short and focused sessions
- make sure the dw support personnel have nice offices in the IT building, which is only a short drive from the business users, and set up a dw support number with lots of touch-tone options; -> give easy access suppport to users
- after the dw has been rolled out, set up a planning meeting to discuss communication with the business users, if the budget allows; -> before the rollout -> {newsletters, training sessions, ongoing personal support}
- accept the premise that those responsible for the enterprise's major source systems are too important and busy to spend time with the dw team. Certainly, they cannot alter their operational procedures significantly for passing data to or from the dw; -> involve the responsible for the operations
