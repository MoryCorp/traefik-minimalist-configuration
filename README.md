# Traefik 2.0 Minimalist Configuration

In this repository, I provide a very simple configuration of Traefik 2 that I use for most of my services, including my blog Holory.fr

Warning, understand that with this configuration, you will have the Traefik dashboard accessible in http on the address: yourdomain.com:8080. This dashboard should not be accessible in a production environment and you must disable it once your functional tests are completed.

If you want to disable the dashboard, just delete line 10 of the docker-compose.yml : 

``- "8080:8080"``

And also delete all the configuration related to the api in the traefik.toml file (lines 30 to 32 included) :

    [api]
      dashboard = true
      insecure = true

Finally, all you have to do is execute the command below on the acme.json file to have read and write permission :

``chmod 600 acme.json``

Once all your files are configured, place yourself in the root of the configuration directory and start the Traefik container with: 

``docker-compose up -d``
