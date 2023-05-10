## Easy Hosting for C# ASP.net Applications

### Setting Up the Database

- Two options for hosting the database portion: Planetscale and Railway, both have pros and cons.

### Railway:

Pros:

- Easy to setup
- No extra configuration required

Cons:

- Limited to 500 hours of uptime, or $5 of free credit, per month
- Limits are shared across all databases
- Database will shutdown when limits are reached

### Planetscale:

Pros:

- Only sleeps after 7 days of inactivity

Cons:

- More difficult to setup
- Has some specific restrictions on your schema
