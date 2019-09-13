# 1. Gradated Access – overview of explore (discovery) phase

TNA's digital strategy sets out a vision and roadmap for our evolution into the disruptive digital archive of the future. One innovation identified by the strategy is a requirement for a nuanced and _gradated_ approach to providing access to records:

>We will gradate access to open records to manage presentation risks. Opening a record and publishing a record are very different acts. The new presentation system needs to gradate access to help manage presentation risks (like intellectual property rights issues). We need to be able to flexibly decide what is available to index by search engines, what is on the web, what is adapted, what is only available on site.<sup>[1](#myfootnote1)</sup>

The proposed Gradated Access Service will give the digital archive increased control over access to digital records and data. The vision is of a very fine-grained level of control, but we don't yet understand what degree of gradation we can practically achieve and manage. The Service may be regarded as a decision engine that combines a range of factors to reach a decision on whether a user may access a specified resource. Factors may include: the user's identity and location, the sensitivity of the records, how recently the records were created or released, the volume of information requested and the purpose and timing of the request.

# 2. Current access policies

There are several reasons for restricting access to records. If FOI exemption(s)2 are applied, there can be no access at all for the general public, however, our staff or the original creators of the records may still need access. Records containing 3rd
 party copyright or potentially distressing or defamatory content can be made available for consultation but cannot be published online. There may be additional restrictions on copying. We may wish to release new records gradually, initially making them available in TNA's reading room or other trusted locations and progressing to online access over time. Some non-sensitive material is not published because it is available elsewhere or because it is not, itself, a Public Record (e.g., high resolution digital images of paper records). These access conditions are complex than simply _open_ or _closed_ and can apply to documents (or other digital objects) and the data and metadata we hold about them.

# 3. Business requirements

## 3a. Initial requirements

We require robust, secure, fine-grained control over who has access to what.

We envisage that a user will make a request for a resource over http. The gradated access service will receive information such as the identity of the user (which might be a public or anonymous user) and the identity of the resource being requested (which may be a single resource or an aggregation of resources).

Users and resources will have associated attributes. For a user, this may include role(s) such as: Archivist at TNA, FOI reviewer at TNA, Records Officer at a specific department, journalist, registered public user, anonymous user. For a resource, the attributes may describe different types of sensitivity: FOI exemption(s) and their dates, copyright, date of release, creator.

Based on these attributes and a set of business rules which map user and resource attributes to access conditions, the gradated access service will make a decision on whether the user can access the resource that has been requested. Requests may be for a single resource, but will more usually be for complex resources or aggregations of resources, potentially with different access conditions.

Approximately 20 initial scenarios for gradated access have been identified.

Examples:

- As a member of the public, I want to be able to access resources (records, metadata, surrogates...) without needing to register or log in, so that I can do my research readily, flexibly and without unnecessary barriers.
- As a journalist, I want to see closed 'press pack' records before they are released to the public, so that I can create news stories in time for publication or broadcast while they are still 'news'.
- As a member of staff in a record-creating department, I don't want staff from other departments without a clear business need to have access to closed records or metadata from my own department, so that I can be sure that we are complying with information security policies and managing risks correctly.

## 3b. Additional properties

The initial model dealt with users and resources. Additional properties which may affect access decisions are Location, Volume, Type of use, Time.

|Property|Description|
|--------|-----------|
|Time|Records may have limited access when they are first released, with full access over a period of time. Users may wish to 'play back' access decisions to understand what records were available at a particular point in time.|
|Volume|We may not wish (or be able) to deliver very large volumes online.|
|Location|For users viewing restricted content, we may wish to limit access to staff areas or other trusted locations. Some content may be available on-site in our reading room that cannot be made available online (for example, records containing 3rd  party copyright…).|
|Type of use|We may wish to make a distinction between viewing, downloading or indexing content.|

## 3c. Generous responses

The gradated access service will make a decision on whether access can be allowed. However, for TNA's services as a whole, it is not necessarily helpful to simply decline a particular request. It would be preferable to suggest alternative resources or access routes.

Examples:

- For a public request for a closed record – return the appropriate http response (403) but additionally suggest an open (redacted) version of the resource and/or direct users to submit an FOI request for the records.
- For a remote or mobile request for a huge volume of data – return the appropriate http response (413) but additionally suggest a compressed version and/or return just the first few records and/or offer an alternative method for accessing the data.

## 3d.        Other security considerations

The Gradated Access service will be just one of a number of measures that will control access to records. Additional security measures are outside the scope of this work.

# 4. Previous work

A small product team, working in a 'time box' looked at business rules for gradated access, carried out some initial architectural design and developed a small-scale prototype service to demonstrate the ideas behind the service.

For this initial investigation, business rules were expressed in the form of a small matrix with limited dimensions and attribute values. The further assumption was made that all requests were for a single resource.

An Attribute Based Access Control (ABAC) model was chosen for investigation. This makes access decisions on the basis of a combination of attributes of the user, resource, action and environment.

# 5. Project brief 

We would like to undertake rapid investigation, modelling and prototyping of a Gradated Access service. We are looking for a **Senior Developer** to join a small team (Data Analyst, Technical Architect, Developer, UX researcher) based at TNA. Project management will be provided by TNA.

## 5.1 Aims

The aims of this work are:

1. To create, test, evaluate and iterate different approaches so that we can learn more about the feasibility of our requirements for the Gradated Access service and understand how much of the proposed scope is manageable in practice
1. Communicate and demonstrate the features of a Gradated Access service to users and stakeholders
1. Make firm design decisions and choices about appropriate technology or frameworks for a future implementation of the service.

There is no expectation or requirement that this project will create production code or components to be deployed as part of a live service.

## 5.2 Deliverables

1. Prototype and demonstrate the features described in section 3a – 3c above ('initial requirements', 'additional properties', 'generous responses').
1. Create a supporting data model for the access conditions and related properties and attributes.
1. Propose a draft technical architecture which is consistent with the overall architecture and security requirements for the Digital Archive.

# Notes
- <a name="myfootnote1">1</a>: [The National Archives' Digital Strategy 2017-19](http://www.nationalarchives.gov.uk/documents/the-national-archives-digital-strategy-2017-19.pdf)
- <a name="myfootnote2">2</a>: [Exemptions under the Freedom of Information Act, 2000](http://www.legislation.gov.uk/ukpga/2000/36/part/II)
