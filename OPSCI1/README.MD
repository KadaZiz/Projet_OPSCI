### Etudiant : Kada ZIZANI 28708212

Lien de la documentation ennoncé dans la vidéo: [Lien](https://sakv.notion.site/TD-Strapi-d1d79fa2b9654a1391eeba29735f5c3d)

## Containers utilisé dans ce projet:
#### Strapi:
- Container name : Strapi
- DATABASE_NAME: strapi
- DATABASE_USERNAME: strapi
- DATABASE_PASSWORD: strapi
- ports: 1337:1337
- networks:strapi
- depends_on:- strapiDB

#### StrapiDB
- container_name: strapiDB
- ports:5432:5432
- networks:strapi
- POSTGRES_USER: strapi
- POSTGRES_PASSWORD: strapi
- POSTGRES_DB: strapi

#### front end
- container_name: frontend
- ports:5173:5173
- depends_on:strapiDB,strapi,dump
- networks:strapi