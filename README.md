# hello-cicd

Proyecto de la **Guía 3.1.2 – Actividad DevSecOps**: pipeline CI/CD en Jenkins con Docker.

## Probar localmente
```bash
npm run build
npm test
npm start      # http://localhost:3000
```

## Levantar Jenkins
```bash
docker compose up -d --build
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```
Abrir http://localhost:8080, pegar la clave e instalar los plugins sugeridos.

## Crear el pipeline
1. Subir este repositorio a GitHub/GitLab (o usar una ruta accesible desde el contenedor).
2. Nuevo item -> **Pipeline** -> Definition: **Pipeline script from SCM** -> SCM: Git.
3. Indicar la URL del repositorio, credenciales y rama; Script Path: `Jenkinsfile`.
4. **Build Now**. Etapas: Build -> Test -> Deploy (app en http://localhost:3000).
