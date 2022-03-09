## Snort

</br>

### ¿Qué es Snort?

</br>

És un IDS (Intrusion Detection system) capaz de analizar el tráfico de red en tiempo real y reaccionar a patrones detectado. Así puede percibir conexiones al exterior que no deberían producirse, ataques externos a la red o nuestra DMZ o detectar ataques de *buffer overflow*.

</br>

## Instalación y configuración

</br>

Actualizar paquetes de la distribución `sudo apt update`

Instalar Snort `sudo apt install snort` , seleccionar arranque de forma automatica

Comprobar el estado del servició `service snort status`

Las reglas de la configuración se encuentran en `/etc/snort/snort.conf`, donde esta dividico en secciones:

1. Variables de red
2. Decodificadores
3. Motor de detecciones
4. Modulos dinamicos
5. Preprocesadores
6. Modulos de salidas
7. Reglas personalizadas
8. Ajustes de preprocesadores
9. Ajustes de objetos compartidos

</br>

### Variables globales de Snort

</br>

**HOME-NET**: Define el rango de la red interna

**EXTERNAL_NET**: Define el rango fuera de la red interna

+ Para definir este rango se suele usar !HOME_NET que significa "cualquier red diferente a la definida en HOME_NET"

**SERVERS**: Lista de servicios que tiene nuestra red, definen donde están los servidores de diferentes servicios, por defecto tiene el mismo valor que HOME_NET.

+ Esta configuración es importante ya que impacta en algunas teglas que están diseñadas para servicios específicos, y para no crear falsos positivos, solo actúan sobre los servicios de los tangos definidos en la configuración.

</br>

#### Riesgos en redes no cifradas

</br>

**PORTS**: Lista de puertos que se usan en diversos servicios 
**Lista blanca**:Lista donde indicar dispositivos que están exluidos de la reglas
**Lista negra**:Lista dodne se definen hosts que cran una alerta sin son etectado en la red.

</br>

### Análisis de reglas

</br>

Cabecera:
- Acción
- Protocolo
- IP Origen
- Puerto Origen
- Dirección
- IP Destino
- Puerto Destino

</br>

Especificacines:
- Regla Opcional
- Parámetros de Regla Opcional
    + Identificador de regla (SID), donde las reglas propias usan un SID superior de 1000000

</br>

### Diferentes opciones que nos podemos encontrar en la cabecera

</br>

**Acción**

alert: Se envía una alerta y guarda la información en el archivo de log.

log: La regla se dispara pero solamente se guarda en el archivo de log esa información.

pass: Ignora el paquete.

drop: Si la regla se dispara se bloquea al paquete y se guarda la informaciñon en el log.

reject: Se bloquea el paquete y se fuerza el fallo de la comunciación.

sdrop: Se bloquea el paquete, pero no se deja 

</br>


## Como escribir reglas propias


## Uso de módulos dinámicos


## Revisión de las alertas

https://www.youtube.com/watch?v=IYaU8X0NKJE

3:50