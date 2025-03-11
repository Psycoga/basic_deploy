1. Creamos el repositorio local

```bash
git init
git add 
git commit -m "build"
```
2. Subimos el repo a github

```bash
gh repo create
```
3. Creamos una app para desplegar
```bash
npm i express
npm install express
```

4. Creamos un archivo server.js
```javascript
const express = require('express');
const app = express();
app.get('/', (req, res) => {
    res.send('Hola mundo');
    });

app.listen(3000, () => {
    console.log('Server is running on http://localhost:3000');
    });
```

5. Añadimos node_modules a .gitignore


6. Testeamos si la app funciona
```bash
node server.js
curl localhost:3000
```
7. Lanzamos nuestro vps, y lanzamos los secretos de github

```
SSH_HOST=ip
SSH_USER=usuario
SSH_PASSWORD=contraseña
```
8. Clonamos el repo en el vps
```bash
git clone <URL>
```
9. Actualizamos el vps y descargamos las dependecias
```bash
apt update
apt install nodejs npm -y
npm install -g pm2
```
9. Instalamos dependecias de npm y probamos a lanzar la app

```bash
cd <repo>
npm install
node server.js
curl <ip>:3000
```

10. Usamos pm2 para lanzar la app en segundo plano
```bash
pm2 start server.js --name <nombre>
```
11. Comenzamos a crear el deploy, creamos la carpeta .github/workflows y dentro un archivo llamado deploy.yml
```bash
.github
└── workflows
    └── deploy.yml
```
