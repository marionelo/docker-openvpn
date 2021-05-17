## Proyecto para poder levantar un VPN 

Para poder levantar un servidor VPN con docker es ejecutar

```
    $ docker-compose up -d
```

Una vez creado el servicio para garantizar que todo esta correcto, ejecutar 

```
    $ docker logs -f openvpn-as
```

El resultado de que el servidor se ha levantado en su totalidad es, llegar a este mensaje

```
    [cont-init.d] done.
    [services.d] starting services
    [services.d] done.
```

El servidor ahora tiene como usuario y contraseña ( admin, password )

Para poder entrar al servidor a su administración basta con colocar https://ip_server:943/admin

Colocar el usuario y contraseña y despues ir a la sección de **CONFIGURATION**

* En **Network settings** en la parte de **Hostname or IP Address**, colocar la IP pública del servidor y dar en guardar
* **En VPN Settings**, activar **Have clients use specific DNS servers** y colocar 
```
    Primary DNS Server: 8.8.8.8
    Secondary DNS Server: 8.8.8.4
```
Dar en guardar.

Finalmente conectar al servidor con los datos el mismo.