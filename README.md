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
