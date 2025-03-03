# Entorn de Desenvolupament Ubuntu amb VNC i VS Code

## 🛠️ Instal·lació i Ús

### 1. Construir la imatge Docker
```bash
docker build -t dev-ubuntu-vnc -f Dockerfile.txt .
```

**Paràmetres opcionals** (modifica el Dockerfile abans de construir):

- `ENV VNC_PASSWORD`: Canvia la contrasenya predeterminada ('password')
    
- `ENV RESOLUTION`: Resolució de pantalla (per defecte: 1280x720)
    
- `ENV COLOR_DEPTH`: Profunditat de color (per defecte: 24)

### 2. Executar un nou contenidor

```bash
docker run -d \
  --name my-dev-env \
  -p 5901:5901 \
  -p 2222:22 \
  dev-ubuntu-vnc
```

**Opcions addicionals**:

- `-e RESOLUTION=1920x1080`: Canvia la resolució
    
- `-v /ruta/local:/home/developer`: Monta un directori local
    
- `--shm-size 2g`: Augmenta la memòria compartida

### 3. Connectar-se via VNC

1. Obre el teu client VNC
    
2. Connecta't a:
```shell
Adreça: localhost:5901
Contrasenya: password
```

### 4. Accés alternatiu via SSH
```bash
ssh developer@localhost -p 2222
Contrasenya: password
```
## 🌐 URL Pública a Docker Hub

La imatge preconstruïda està disponible a [docker hub]: https://hub.docker.com/r/ianditb/dev_ubuntu , o:  
`docker pull ianditb/dev_ubuntu:latest`
