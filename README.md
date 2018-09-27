# Colonial project archive
Static generated files from http://colonialrevival.lib.virginia.edu

## Process of creating the static archive
- Scraping the old site was done with this command:
  - `wget --mirror -P static-content -nH -np -p -k -E http://colonialrevival.lib.virginia.edu/`
- All files were archived in a bzip2.tar file using this command:
  - `tar -jcf colonial.bzip2.tar /usr/local/projects/colonialrevival/releases/20120820144256`
- To recreate the site
  - Put the contents of the 'static-content' folder on a web server. It is just static HTML files.
  - Or use Docker to build an nginx container with the folder 'static-content' linked to the folder /usr/share/nginx/html in the container.
    - The docker-compose.yml file needs to have the static-content folder on the same level as itself.
    - The docker-compose.yml file requires Traefik to be running and a 'thenetwork' docker network to be created. See here: https://github.com/scholarslab/traefik

## File Structure
```
.
├── README.md
├── colonial.bzip2.tar
├── docker-compose.yml
└── static-content
    ├── gsearch.html
    ├── images
    │   ├── banner.gif
    │   └── banner2.jpg
    ├── index.html
    ├── texts
    │   ├── ColRevBi.html
    │   ├── ColRevBii.html
    │   ├── ColRevBiii.html
    │   ├── ColRevBiv.html
    │   ├── ColRevBv.html
    │   ├── ColRevBvi.html
    │   └── ColRevBvii.html
    └── www
        └── colonial.css

```

