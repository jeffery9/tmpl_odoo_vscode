# vscode project tempalte for odoo that run and debug in docker

**welcome to improve this.**

## Dirctory structure

```
.
├── .devcontainer
│   ├── .DS_Store
│   ├── Dockerfile
│   ├── addons
│   ├── config
│   │   └── odoo.conf
│   ├── devcontainer.json
│   ├── docker-compose.yml
│   ├── odoo
│   ├── pip.conf
│   └── translate.py
├── .vscode
│   └── settings.json
├── README.md
├── requirements.txt
├── addons
│   ├── README.rst
│   ├── __init__.py
│   ├── __manifest__.py
│   ├── controllers
│   │   ├── __init__.py
│   │   └── main.py
│   ├── data
│   │   ├── data_1.xml
│   │   └── data_2.xml
│   ├── i18n
│   │   ├── en_US.po
│   │   ├── addons.pot
│   │   └── zh_CN.po
│   ├── controllers
│   │   └── __init__.pys
│   ├── models
│   │   └── __init__.py_
│   ├── report
│   │   └── __init__.py
│   ├── security
│   │   └── ir.model.access.csv
│   ├── static
│   │   └── description
│   │       └── icon.png
│   ├── tests
│   │   └── __init__.py
│   └── views
│       ├── view_1.xml
│       └── view_2.xml
└── other_addons_name


```

## Run project

Press shift+cmd+p or click menu view and select Command Palatte, choose `Remote-Containers: Open in Container`

vscode should build docker image for project, and then run odoo in project.


## Debug project

When the odoo project is runing, use vscode debug tools attach to container.

## Customise odoo docker image.

edit `.devcontainer/Dockerfile`, change the base image to other odoo offical image, or install additional tools or package for the project.
