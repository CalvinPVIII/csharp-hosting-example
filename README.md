# Easy Hosting for C# ASP.NET Applications

This guide will aims walk you through hosting a database backed ASP.NET web app/api.

In order to setup our ASP.NET app with a database, there are two things we will need to configure: the database and the website itself. For the website, we will use a service called Render, along with a Dockerfile. For the database we have a few options. Below are a list of options this guide covers:

- TiDB: Built on AWS infrastructure. Scales up/down as needed. Provides 25 bg of row and column storage. [More information can be found here](https://www.pingcap.com/pricing/)
- Railway: Easy to setup and provision a MySQL database. **No longer provides a free tier, but is still a solid option for easy hosting** [More information can be found here](https://railway.app/pricing)
- Planetscale: Advanced MySQL database. **As it does not support foreign key constraints, it can be a bit of a pain to setup.** [More information can be found here](https://planetscale.com/pricing)
- Supabase: Widely supported and simple to setup database provider. **Does not support MySQL, but the guide does cover switching to PostgreSQL** [More information can be found here](https://planetscale.com/pricing)

Overall, I would recommend using TiDB or Supabase. TiDB is simple to setup, and while Supabase does require switching from MySQL to PostgreSQL, it is the most widely supported of all the providers.

You can also check out other free options that are listed in [this Github repo](https://github.com/cloudcommunity/Free-Hosting#databases-dbaas) that has a list of free database providers and other hosting options.

As with all free hosting options, it is only recommend to deploy demo or personal projects, and more research and consideration should go into finding a provider for a full scale production app.

**You only need to follow the setup for one database provider.**

### Quick Links:

[Hosting the MySQL database with TiDB](./Guides/TiDB.md)

[Hosting the MySQL database with Railway](./Guides/Railway.md)

[Hosting the MySQL database with Planetscale](./Guides/Planetscale.md)

[Converting to a PostgreSQL database, and hosting with Supabase]("./Guides/PSQL.md)

[Hosting the website with Render](./Guides/SiteHosting.md)

_Disclaimer: service providers will often change their pricing and plan options, depending on when you view this guide, some steps may be different, and some providers may not offer the same plans. This guide was last updated in October of 2023. Feel free to submit an issue on Github if any of these providers change, or if the guides become outdated._
