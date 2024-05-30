# Statics

## Another heading

## Diagrams

``` mermaid
flowchart TD
    A["dev-statics.softteco.tools | 165.22.194.166"]-->C
    B["test-statics.softteco.tools | 206.189.63.133"]-->C
    C["statics_frontend | node:18.12.1 ---> NGINX:1.17-1-alpine | routing logic"]-->D
    D["statics_backend | Maven:3.8-openjdk-11 ---> tomcat:9-jdk11-temurin-focal"]
    DB1[statics-redis 
    redis:latest]
    DB2[statics-postgres
    postgres:15.2
    ]
	D --- DB1
	D --- DB2
```

more text
