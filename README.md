# ghost-template

This project aims to ease the deployment of easily managable micro-sites. It's main on-premises component is [Ghost](https://ghost.org), an open source opinionated CMS system like Wordpress. You don't only get an admin page but you can set a theme and your frontend is built by the software as well.

This project is part of a bigger strategy: to serve good-looking, self-managable and informative micro-sites for the Schönherz communities. The first prototype will be introduced with the dorm's main site: [sch.bme.hu](https://sch.bme.hu).

## Deployment

### Virtual machine

Set up environment variables by copying `.env.example` file and name it as `.env`. Change the values to the production system's values.

On virtual machine running Docker engine, you can easily deploy a Ghost site with the prepared `docker-compose.yml` file. Just run `docker compose up -d` to run the Docker stack in the background. The Ghost stack consists of the webapp and the MySQL database instance.

WIP: It would be recommended to integrate the database and storages with a back-up mechanism and save snapshots on a cloud service.

### K8s

WIP.

### Notes

Once you've run mysql, and changed env vars one time, the next time you run the mysql instance again, it won't let you access it. See discussion and solution here: <https://github.com/docker-library/ghost/issues/378>. Be aware, you'll need to dig deeper and back-up data, because the easy solution will remove the bind volume itself.
