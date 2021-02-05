# Portainer Templates Manual

- [Portainer Templates Manual](#portainer-templates-manual)
  - [Template writing manual](#template-writing-manual)
    - [Template types](#template-types)
  - [Standalone container](#standalone-container)
  - [Swarm stack](#swarm-stack)
  - [Compose stack](#compose-stack)
  - [Template usage](#template-usage)
  - [External Resources](#external-resources)
## Template writing manual
### Template types

Values are corresponding to:
- `1` : Standalone Container
- `2` : Swarm Stack
- `3` : Compose stack

## Standalone container


Example:
```
{
  "title": "<AppTitle>",
  "name": "<AppName>",
  "description": "Service description",
  "note": "Some useful additional informations",
  "categories": [
    "<category1>"
    "<category2>"
  ],
  "platform": "<os_platform>", #ie: linux
  "logo": "<logo_url>",
  "image": "<docker_repo>/<docker_image>:<image_tag>",
  "env": [{
      "name": "<var_1>", # Name to the environment variable to set
      "set": "true" # Value to set into the environment variable
    },
    {
      "name": "<var_2>", # Name to the environment variable to set
      "set": "true" # Value to set into the environment variable
    },
  ],
  "ports": [
    "<host_port1>:<container_port1>/<l4_protocol>", # ie: 80:80/tcp
    "<host_port2>:<container_port2>/<l4_protocol>", # ie: 443:443/tcp
  ],
  "volumes": [
    {
      "container": "<container_path_volume_1>"
    },
    {
      "container": "<container_path_volume_2>"
    }
  ]
  "command": "<shell_command>" # ie. if needed
},
```
## Swarm stack

`<TODO>`
## Compose stack

Example:
```
{
  "type": 3,
  "title": "<AppTitle>",
  "name": "<AppName>",
  "description": "Service description",
  "note": "Some useful additional informations",
  "categories": [
    "<category1>"
    "<category2>"
  ],
  "platform": "<os_platform>", // ie: linux
  "logo": "<logo_url>",
  "repository": {
    "url": "git_repo_url", // ie: https://github.com/portainer/templates
    "stackfile": "docker-compose.yml"
  }
  "env": [{
  "name": "MYSQL_DATABASE_PASSWORD", // environment var from which to get the value
  "label": "Database root password", // label in which tu put the value
  "description": "Password used by the MySQL root user." // the long description of the label contained value
  }]
},
```

## Template usage

## External Resources
  - [Official portainer templates github repository](https://github.com/portainer/templates)