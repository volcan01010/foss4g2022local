## Benefits to BGS of using open source software for large scientific data projects

> The following text is a slimmed-down version of a report written by Dr John A Stevenson with contributions from Jo Walsh and Dr Rosa Filgueira, December 2017.
> Since then there has been a significant increase in containerisation, automated testing and use of PostgreSQL for publication of data.
> All opinions are our own!


### Better for building quality software

The most significant advantage of open source is its **portability**.
Software can be easily downloaded, installed and deployed whenever or wherever required.
Even if licence costs were not an issue, the technical hurdles of dealing with licence keys or servers mean that this is not practical with proprietary software.
Portable software can easily be put through a continuous integration system (CI - see [continuous integration, explained](https://www.atlassian.com/continuous-delivery/continuous-integration-intro) for details), where it is automatically tested, deployed and scaled.
Developing with automated testing results in better software products.

Best-practice software development uses disposable environments, often [within virtual or cloud servers](https://www.gov.uk/guidance/use-cloud-first), which are defined by code.
This makes them reproducible.
Identical software can be downloaded, installed and configured automatically in a matter of minutes on a developer's laptop, a test server or in a production environment.
Developers can work quickly and freely in their local environment, safe in the knowledge that they are not affecting anyone else.
Database schema definitions are stored in version control alongside the code.
This freedom is lost when developing against a single, central database with fixed schema and contents.

Developers can write tests to ensure that their code performs as expected, and these tests can be run automatically by a CI system to reject broken code.
[Container technology](https://www.docker.com/what-container), such as Docker, is becoming the standard way to deploy software within the cloud.
This would let a developer _spin-up_ the entire software stack (including data loaders, a database, the data access APIs and the front-end web pages) on their laptop in a couple of minutes, allowing complete end-to-end testing.

The [GDS guidelines recommend Agile development](https://www.gov.uk/service-manual/agile-delivery/agile-government-services-introduction).
Agile projects proceed by frequent delivery of small increments.
Progress can be monitored and specifications amended as users provide feedback on the working product.
The portability of open source code makes Agile development easier because the deployment step can be automated.
The continuous integration pipeline can be configured to deploy tested code out to the production server whenever it is tagged for release.
Meanwhile, the developers can concentrate on writing code.
New features are quickly made available to the end-user for feedback, which ensures that software products to what their users need.

Portable software can also be scaled. If there is a newsworthy event, e.g. a large earthquake, it is expected that there will be a surge of users trying to access data.
If this puts great demand on the system, new database or web servers can be automatically created and the load can be balanced between them.
In extreme cases, Docker-based services could even be temporarily deployed on external hardware e.g. Jasmin or even AWS.
This is not practical with proprietary tools where each instance needs to be licensed and paid for.


### Better for BGS science

In addition, our own data processing and publication code should be released to the public under open source licenses.
The GDA describes many [advantages of coding in the open](https://gds.blog.gov.uk/2017/09/04/the-benefits-of-coding-in-the-open/).
Two of these are increased transparency and involvement from external users.
These are particularly relevant to BGS.

There is a growing movement towards [open science](https://en.wikipedia.org/wiki/Open_science) and the professionalisation of scientific code development by [Research Software Engineers](https://society-rse.org/).
Authors make both the data and the code used to produce it available when they publish a paper.
The aim is that anyone else should be able to use them to recreate the results.
Transparent code is crucial here.
Proprietary software hinders open science because the internal workings of algorithms (e.g. in ArcGIS) cannot be inspected and because you cannot recreate the results without paying for the software.
If any data processing takes place within the BGS infrastructure e.g. interpolation between missing data points, then it should be reproducible by others.

Open science is particularly important in the context of [UKGEOS](https://ukgeos.ac.uk/) and the controversies around shale gas exploitation.
If the code is available, and running on open source components, then anyone can verify the results that are presented via the BGS.

If the code is open, then it can also be used and contributed to by external users.
Other agencies that work with time series data at home or abroad e.g. BAS, CEH, USGS have lots in common with BGS.
If they can use our software libraries with their sensor networks, this is of major benefit to them.
This is great for the reputation of the BGS as well as a great source of _impact_.
Users may even contribute back e.g. by contributing plugins or new features to data analysis tools.
This is only possible if code is shared openly. 

### Better for BGS as an organisation

Developers want to work with the best and most cutting-edge tools.
A BGS with a reputation for using these to advance the frontiers of science would be very attractive to them.
Open source developers work within a large international community, where experience and advice are shared.
Making open source contributions would increase visibility of the BGS in this domain.

Overseas Development Agency (ODA) work is important to the BGS but proprietary software licence fees are too expensive for these projects.
Open source is already seen as a solution to this and the best way develop the skills to implement it for others is to use it ourselves.
We should [eat our own dogfood](https://en.wikipedia.org/wiki/Eating_your_own_dog_food).
In the same way a developer could run the an geodata stack on her laptop, a Docker-based data-management system could be spun up on an overseas geological survey's server in just a couple of minutes, too.
The better we understand the tools, the easier it will be to use them in ODA projects.
