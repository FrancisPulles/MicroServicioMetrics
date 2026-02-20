PASOS PARA LEVANTAR:
1- LEVANTAR EL SERVICIO DE MONGODB DEL DOCKER-COMPOSE

2- EJECUTAR LAS SIGUIENTES LINEAS DE CÓDIGO EN POWERSHELL
docker ps

docker exec -it mongodb-metrics mongosh -u root_admin -p root_password

use metrics_db

db.createUser({
  user: "metrics_user",
  pwd: "secure_password",
  roles: [
    {      role: "readWrite",
      db: "metrics_db"
    }
  ]
})

3- LEVANTAR EL SERVICIO metrics-service

4-REVISAR QUE FUNCIONE

ESTE CÓDIGO TIENE LOS MÉTODOS DEL FEIGN PERO SOLO SON DECORATIVOS PORQUE AÚN NO HAY CONEXIÓN ENTRE MICROSERVICIOS.
TODO ESTÁ COMO LOCALHOST, UTILIZANDO PUERTOS "8083:8083" PARA EL SERVICIO Y "27017:27017" PARA MONGO
