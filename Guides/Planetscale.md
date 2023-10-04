## Planetscale Setup

_Last updated July 2023_

- Go to [Planetscale.com](https://planetscale.com) and create an account
- On the dashboard, click on `create`
  ![Planetscale create](../images/Planetscale1.png)
- Give it a name and set the region
- Wait for the database to initialize
- On the right hand side, click `Connect`
  ![Planetscale create](../images/Planetscale2.png)
- Click `Create password`
- Under the `Connect with` drop down, select `.NET` and copy the appsettings.json
  ![Planetscale create](../images/Planetscale5.png)
  - **You may need to change the connection string from `Default` to `DefaultConnection`, depending on how your app is setup**
- You will also want to save your username and password for later
- Open up MySQL workbench and click on the plus button next to `MySQL Connections`
  ![Planetscale create](../images/Planetscale6.png)
- Set a connection name, and set the method to `Standard (TCP/IP)`
- Hostname should be `aws.connect.psdb.cloud`, port is `3306`. `Username` and `Password` are the ones you copied earlier from the Planetscale setup page
  ![Planetscale create](../images/Planetscale7.png)
- Test the connection to make sure it works, then click `Ok`.
- Before going into the Planetscale database, click the home icon in the top left, then click on your local instance
  ![Planetscale create](../images/Planetscale10.png)
- Due to how Planetscale works, we need to delete our foreign key constraints in our tables. This shouldn't effect the basic functionality of the site, but could lead to some unexpected behaviors. Planetscale won't let us import our database if we have these, so we have to get rid of them to use their service
- Expand your schema, and go to a table that has a foreign key
- Right click, alter table
  ![Planetscale create](../images/Planetscale12.png)
- At the bottom, click `Foreign Keys`
  ![Planetscale create](../images/Planetscale13.png)
- On the left panel, right click and delete all foreign key constraints - do this for every item listed
  ![Planetscale create](../images/Planetscale14.png)
- Click apply at the bottom
- **You will need to do that for every table that has foreign keys**
- Once there are no tables that have foreign key constraints to the `administration tab` and click `Data export`
  ![Planetscale create](../images/Planetscale8.png)
- Under the left panel, click on your schema, and then under the right panel, click on `Select Tables`
  ![Planetscale create](../images/Planetscale9.png)
- At the bottom, click on `Export to self contained file` and pick a path
- Then click start export
- Once that is done, click on the `Home` button in the top left, then click on your Planetscale instance
- Click on administration tab, then data import/restore

- Click on `Import from Self-Contained File` and pick your file
- Under `Default Target Schema` pick the database you specified when creating the database on Planetscale earlier, then click start import
  ![Planetscale create](../images/Planetscale16.png)
- Once that is done, go back to Planetscale and click the branches tab
- Click on `main` and double check that all your tables have been created properly
- If all your tables look good, you can move on to [hosting the app on Render](./SiteHosting.md)
