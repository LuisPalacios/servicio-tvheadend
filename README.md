# Introducción

Este repositorio contiene un ejemplo del fichero de configuración [fig](http://www.fig.sh/index.html) para instanciar tvheadend. Está basado en el contenedor Docker [luispa/base-tvheadend](https://registry.hub.docker.com/u/luispa/base-tvheadend/) (GitHub [base-tvheadend](https://github.com/LuisPalacios/base-tvheadend)).

Consulta este [apunte técnico sobre varios servicios en contenedores Docker](http://www.luispa.com/?p=172) para ver más ejemplos de uso. 


## Ejecución con "fig"

Para automatizar con el programa [fig](http://www.fig.sh/index.html) y que arranquen el contenedor: descarga y renombra el fichero fig-template.yml y después ejecuta el programa fig: 

    $ git clone https://github.com/LuisPalacios/servicio-db-log.git
    :
    $ mv fig-template.yml fig.yml   (edita a tu gusto)
    :
    $ fig up -d


### Volumen

Directorio persistente para configurar el Timezone. Crear el directorio /Apps/data/tz y dentro de él crear el fichero timezone. Luego montarlo con -v o con fig.yml

    Montar:
       "/Apps/data/tz:/config/tz"  
    Preparar: 
       $ echo "Europe/Madrid" > /config/tz/timezone
