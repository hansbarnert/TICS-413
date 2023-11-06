# Repaso prueba 2

## Vulnerabilidad
"Es una falla en un sistema informatico que puede ser explotada para acceder a elevaciones de privilegios con fines maliciosos."

Se dividen en:
- Sistema operativo
- Mala configuracion
- Credencales debiles o predeterminadas
- Logica de inplementacion
- Factor humano

## Vectores
Los vectores son medios o metodos por los cuales se consiguen atacar las vulnerabilidades. Los 10 mas comunes son:

- [FH] Correo electronico y mensajeria instantanea
- [MC] Navegacion web
- [MC] Endpoints
- [MC] Apps web
- [MC] Software de redes
- [CDP] Credenciales de usuario comprometidas
- [CDP][LA] Credenciales predecibles o por defecto
- [FH] Insiders
- [LA] Carencia de cifrado
- [LA] Carencia en proveedores tecnologicos

## Payload
Es el fragmento de codigo que hace la infeccon propiamente tal, encriptando informacion, instalando malware en el dispositivo, etc.

Entonces por ejemplo si una persona que se encuentra descontenta con su empresa y un desconocido le dijo que con un usb podia atacar a la empresa este se tentara en usarlo, al hacerlo se instalara un malware de tipo ransomware encriptando la computadora a la que fue introducido el dispositivo usb. En este caso el vector seria de un insider y el payload seria el ransomware instalado en el equipo.

## Version disclojure

Existen varias bases de datos que documentan las distintas vulnerabilidades, entre ellos se encuentran MITRE.

- Un exploit es una accion o comportamiento que utiliza una vulnerabilidad en un sistema o aplicacion.
- Una PoC es una tecnica o herramienta que a menudo demuestra la explotacion de una vulnerabilidad.

---
---
---

# Tecnicas de mitigacion 
## Minimizar superficie de ataque
- Realizar como minimo un sistema cliente-servidor.
- Transitar de APIs publicas a privadas.
- Usar bibliotecas y drivers que esten parchados (evitar inventar la rueda).
- Hacer un correcto despliegue y operaciones con proveedores de confianza.
- Habilitar configuracion de administracion remota.

## Minimizar exposicion de datos
- Limitar eltiempo que los datos residen en memoria **priorizando la s llaves de encriptacion y credenciales**.
- Aplicar a almacenamiento de datos tambien, marcar para borrar.

## Politica y control de acceso
Agentes que necesitan acceder a registros de clientes **Limitar la cantidad de registros que pueden consultar diariamente??????????.**

# Zero trust

Estrategia establecida por Microsoft en la que se asume la violacion y verifica cada solicitud como si se origina en una red abierta
- Nunca se confia, siempre se verifica.
- Toda solicitud de acceso esta autenticad, autorizada y cifrada antes de conceder el acceso.
- Se debe detectar y responder a las anomalias en tiempo real.
- Se deben aplicar los principios de microsegmentacion y acceso para minimizar el movimiento lateral.

## Decisiones
Se debe armar un protocolo de toma de decisiones estatico que indique claramente que decision se tomara en cada escenario y como reaccionara el sistema

# SSH Secure Shell
- Paso 1: El cliente inicializa la coneccion contactando el server
- Paso 2: El server envia la llave publica
- Paso 3: Se negocian los parametros de permisos y se abre un canal seguro
- Paso 4: El cliente se registra al sistema operativo del servidor