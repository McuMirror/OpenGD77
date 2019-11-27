---
OpenGD77  Guía del usuario 
---

![](media/OpenGD77-logo.svg)

# OpenGD77 Guía del usuario
(19 de noviembre de 2019)

## Introducción

Esta guía del usuario es un trabajo en progreso al igual que el firmware Open GD77. Si encuentra algún error u omisión, avíseme para que puedan corregirse.

Este manual cubre tanto la versión original de Nivel 1 / Fase uno, que incluye el modo Hotspot, como las versiones Alpha de Nivel 2 que no incluyen el modo Hotspot, sino que tiene otras características nuevas.

Debido al rápido ritmo de desarrollo, algunas fotos de pantallas ahora están desactualizadas, porque el DMR TS y CC ahora se muestran en todas las pantallas DMR.

Las fotos se actualizarán cuando el firmware no cambie tan rápidamente.

La intención del proyecto OpenGD77 es crear un firmware no comercial con todas las funciones que reemplace por completo el firmware de fábrica de Radioddity GD-77. Este firmware está diseñado específicamente para uso ** ** Radio Amateur **, y tiene características no disponibles en el firmware oficial.

**Nota.**
** El firmware aún está en desarrollo y hay algunas áreas clave de funcionalidad que aún no se han escrito. **

1. Actualmente, el firmware estable solo funciona en DMR con puntos de acceso simplex o en otras radios DMR para contactos simplex. Esto se debe a que el firmware actualmente no es totalmente compatible con DMR Tier 2 requerido para la mayoría de los sistemas comerciales y de repetidores MMDVM.

   Sin embargo, el modo DMR se puede usar con un punto de acceso simplex y para la operación DMR simplex.

   Existe una versión de prelanzamiento (Alpha 2) que admite la operación de punto de acceso Tier2, repetidor y dúplex, pero actualmente tiene algunos problemas menores.

   *Nota. La versión de Nivel 2 actualmente no es compatible con el modo Hotspot *

1. La transmisión FM Rx y Tx funciona.

   Esto incluye la operación del repetidor usando CTCSS en Tx y Rx.

1. En DMR, solo son posibles las "llamadas" de Talk Group y las llamadas privadas

   Los mensajes de texto y otras funciones similares no son compatibles actualmente, pero están en la lista de tareas pendientes.

   Para obtener una lista completa de los errores actuales y las mejoras propuestas, consulte
   https://github.com/rogerclarkmelbourne/opengd77/issues

El firmware está diseñado para el uso de Radioaficionados, especialmente en DMR, y tiene una serie de características para el uso de Radioaficionados que normalmente no están disponibles en radios DMR comerciales.

Estos incluyen la entrada numérica directa de los números de DMR TalkGroup y el uso de la lista Rx Group para controlar los TG seleccionables para cada "canal" DMR

Además, en la medida de lo posible, el firmware es de código abierto. Esto permite que cualquiera pueda modificar el firmware para satisfacer sus propias necesidades individuales, y también para la revisión por pares y la mejora del código fuente del firmware

#### Créditos:

El proyecto fue concebido por Kai DG4KLU, quien desarrolló el marco inicial y toda la funcionalidad FM y DMR Tx y Rx (Nivel 1).

Kai dejó de participar activamente en el proyecto en junio de 2019 y, al momento de escribir este artículo, Roger VK3KYY es el desarrollador principal y único.

Roger VK3KYY desarrolló la funcionalidad de nivel 2, la interfaz de usuario, el controlador de pantalla, la API Codeplug, la API de memoria EEPROM, la API de memoria Flash, el modo Hotspot y muchas otras características.

Múltiples correcciones de errores y adiciones de Alex DL4LEX, incluidas la pantalla de bloqueo y las funciones DTMF y Tone burst

Mejoras gráficas y otras de Daniel F1RMB

Adiciones de Colin G4EML, incluyendo FM CTCSS y funcionalidad de zona "Todos los canales"

Esta guía del usuario fue escrita por Roger VK3KYY basada en el trabajo de Alister G0NEF

Gracias a todos los Beta Testers que proporcionan informes detallados de errores y comentarios de los usuarios, especialmente VK7ZCR, W1RHS y G4TSN

#### Descargar enlaces y otros recursos

** Código fuente de firmware y binarios: **

Versión estable: (Modo Tier 1 + Hotspot)
https://github.com/rogerclarkmelbourne/OpenGD77/raw/master/firmware_binaries/OpenGD77.sgl

Versión de nivel 2 "Alpha 2" (no incluye el modo Hotspot)
https://github.com/rogerclarkmelbourne/OpenGD77/raw/Tier2/firmware_binaries/daily_builds/OpenGD77_Tier2_Alpha_2.sgl

** GD-77 Community CPS con soporte para OpenGD77: **
https://github.com/rogerclarkmelbourne/radioddity_gd-77_cps/raw/master/installer/RadioddityGD77CPS31XCommunityEditionInstaller.exe

## Instalación

El firmware se puede instalar en el GD-77 utilizando la herramienta de actualización de firmware provista por Radioddity con sus paquetes oficiales de actualización de firmware. Esto se puede descargar del sitio web de Radioddity [radioddity.com] (https://radioddity.com/). Consulte la documentación de Radioddity sobre cómo usar su herramienta de actualización de firmware.

Las versiones más recientes de Community CPS también tienen una función en el menú Extras para cargar el firmware en la radio.

El firmware OpenGD77 (archivo .sgl) se puede descargar desde Github, utilizando cualquiera de los enlaces que se enumeran en la sección 1.1 de esta guía.

La instalación del firmware OpenGD77 se realiza bajo el riesgo del propietario, pero el firmware oficial generalmente se puede volver a cargar en el GD-77 si el usuario tiene problemas con el firmware OpenGD77.

Nota. El software oficial para PC Radioddity GD-77 CPS no es compatible con el firmware OpenGD77, y en su lugar se debe utilizar el "Community CPS". Esto se puede descargar desde el enlace que se muestra en la sección 1.1 de esta guía

## Pantallas principales (pantallas VFO y Channel)

El firmware OpenGD77 tiene 2 pantallas principales. La pantalla VFO y la pantalla del canal. Estos son similares a las pantallas de canal y VFO en el firmware oficial, excepto que tienen una funcionalidad adicional.

Inicialmente después de instalar el firmware OpenGD77, se mostrará la pantalla VFO.

![](media/vfo-screen.jpg)

La frecuencia utilizada en el VFO para Tx y Rx se leerá en la configuración "VFO A" del codeplug.

En las pantallas VFO y Channel, el modo (DMR o FM) se muestra en la esquina superior izquierda de la pantalla y el porcentaje de voltaje de la batería se muestra en la esquina superior derecha de la pantalla.

En modo DMR, el TimeSlot actual se muestra a la derecha del texto "DMR", por ejemplo, TimeSlot 2 "TS2
y el Código de color, p. Se muestra "C1" a la izquierda del porcentaje de batería.

La potencia de transmisión actual se muestra en el medio de la parte superior de la pantalla. P.ej. 750mW

En la pantalla VFO, se muestran las frecuencias Tx y Rx, así como el TalkGroup cuando está en modo DMR.

La flecha a la izquierda de la R (frecuencia de recepción) indica que las flechas hacia arriba y hacia abajo del teclado y las teclas de entrada de número controlarán la frecuencia de Rx.

La pantalla del canal muestra la misma información en la fila superior, pero muestra el nombre del canal (en este ejemplo, “VK3RGL D”), así como la zona (“VK3 DMR”) y en modo DMR también se mostrará el TalkGroup

![](media/dmr-screen.jpg)

En las pantallas VFO y Channel:

Presione el botón de menú ** Rojo ** para alternar entre las pantallas VFO y Canal

Presione la tecla de menú ** Verde ** para ingresar al sistema de menús

Al presionar ** Función + Verde ** se accede rápidamente a la pantalla de detalles del Canal, a la que también se puede acceder a través del sistema de menús.
*Nota.*
El VFO es en realidad un tipo especial de canal; por lo tanto, la pantalla Detalles del canal también funciona para el VFO.

#### Cambio de canal VFO <->

Presione la tecla ** Función + Estrella (*) ** para alternar entre los modos FM y DMR en las pantallas VFO o Canal.

#### Cambio de intervalo de tiempo en modo DMR
En modo DMR, al presionar la tecla ** Estrella (*) ** se alterna entre Timeslot 1 y Timeslot 2

#### Control de la potencia de transmisión

Presione ** Función + Derecha ** para aumentar la potencia, Presione ** Función + Izquierda ** para disminuir la potencia. La potencia se puede configurar en 250mW, 500mW, 750mW, 1W, 2W, 3W, 4W y 5W.
Nota. La potencia de salida solo será correcta después de que el operador haya calibrado su propia radio, ya que el GD-77 no parece tener una calibración de potencia muy precisa aplicada en la fábrica por TYT

#### Gráfico de barras de intensidad de señal

En los modos FM y DMR, la intensidad de la señal recibida se muestra como un gráfico de barras con el ancho de la pantalla. El gráfico de barras del 100% es aproximadamente S9 +40 dB.

En modo DMR, el medidor de señal solo estará activo cuando el hardware DMR detecte una señal DMR.

En modo FM, el medidor de señal debe funcionar todo el tiempo.

![](media/signal-meter.jpg)

### Funcionalidad específica de la pantalla del canal
La pantalla del canal muestra el número del canal actual, así como la zona actual.

![](media/channel-and-zone.jpg)

#### Cambio de canales dentro de la zona actual

Al presionar las teclas ** Arriba ** o ** Abajo **, el canal cambia en la zona actual, y el número de canal en la zona se mostrará en lugar del nombre de la zona.

#### Cambio de zonas

Presionando ** Función + Flecha arriba ** o ** Función + Flecha izquierda ** cambia a la zona siguiente o anterior

![](media/changing-zones.jpg)

#### Pantalla del canal Menú rápido

Al presionar el botón ** Naranja ** en la parte superior de la radio en el modo Canal, aparece el menú Rápido para la pantalla Canal.

##### Copiando un canal a VFO

##### Lee el VFO en el canal actual

Presione la tecla ** Verde ** para confirmar y guardar el canal actualizado en la memoria de codeplug ** Tecla ** roja para cancelar.

![](media/channel-quick-menu.jpg)

#### Menú rápido de VFO

Al presionar el botón ** Naranja ** en la parte superior de la radio en modo VFO, se muestra el menú Rápido para la pantalla VFO. Actualmente esto tiene tres opciones

##### Copie la frecuencia Tx a la frecuencia Rx

##### Intercambia las frecuencias Tx y Rx

##### Copie la frecuencia Rx a la frecuencia Tx

Presione la tecla ** Verde ** para confirmar la copia o la tecla ** Roja ** para cancelar.

![](media/vfo-quick-menu.jpg)

**Nota.**

Escuchar la entrada de un repetidor solo funcionará en modo DMR si la frecuencia Tx y la frecuencia Rx son las mismas. Esto se debe a que la mayoría de las radios DMR no ofrecen la opción de seleccionar el modo pasivo Tier2 o pasivo Tier 2, y en su lugar suponen que si las frecuencias Tx y Rx son las mismas, la radio debe estar en modo activo, donde la radio es el maestro DMR . Mientras que si las frecuencias Tx y Rx son las mismas, la radio asume que necesita operar en modo pasivo de nivel 2, donde la señal del repetidor controla la sincronización del intervalo de tiempo DMR.

Sin embargo, para escuchar la entrada de un repetidor, la señal que se recibe no contiene la información de sincronización, por lo tanto, la radio debe ponerse en modo DMR activo para recibir la señal.

No estoy seguro de si el firmware oficial puede recibir en la entrada de un repetidor si se configuró un canal con las frecuencias Tx y Rx intercambiadas, pero debido a la forma en que el firmware OpenGD77 realmente monitorea ambos TimeSlots simultáneamente, pero solo decodifica el TG / ID y audio para el TS seleccionado.

### Funcionalidad específica de DMR (pantallas VFO y Channel)

#### Selección de intervalo de tiempo

La tecla ** Estrella (*) ** alterna entre Timeslot 1 y Timeslot 2 (versión de Nivel 2)

Nota. El número de intervalo de tiempo no se muestra en esta foto, pero aparece a la derecha del "DMR", también se muestra el Código de color a la izquierda del porcentaje de batería

#### DMR ID indicativo de llamada y visualización de nombre

Cuando se recibe una señal DMR que usa el mismo código de color seleccionado para el VFO o el canal, la pantalla de la radio mostrará el grupo de conversación de la estación y la ID DMR

![](media/talkgroup-and-dmr-id.jpg)

Si la ID de DMR está en la base de datos de ID de DMR cargada previamente en la radio, se mostrará el indicativo y el nombre.

![](media/callsign-and-name.jpg)

#### Pantalla de alias de hablador

En la red Brandmeister, si la ID de DMR de la estación no está en la base de datos de ID de DMR, la pantalla mostrará la información de Alias ​​Talker enviada por Brandmeister.

![](media/talker-alias.jpg)

El indicativo se mostrará en el centro de la pantalla y se mostrará información adicional en la parte inferior de la pantalla. La información adicional tendrá como valor predeterminado el texto "ID de DMR:" seguido del número de ID de DMR de la estación.

Si la estación ha ingresado algún dato en la sección APRS de su página Brandmeister "Self care", ese texto se mostrará en lugar del número de ID de DMR.

![](media/talker-alias-data.jpg)

Nota. A medida que los datos de Talker Alias ​​se envían lentamente a medida que se incrustan dentro de los marcos de datos de audio DMR, el indicativo aparecerá primero y aproximadamente medio segundo después, la ID DMR u otro texto llegará a través de los datos DMR y se mostrará.

#### Selección de grupo de conversación de la lista de grupos Rx

Presione las teclas ** Izquierda ** o ** Flecha derecha ** para recorrer los Grupos de conversación en el Grupo Rx asignado al VFO o Canal en el CPS.
Este TalkGroup se aplicará tanto a Rx como a Tx.

#### Asignación de Timeslot a Digital Contact TalkGroup

Una nueva característica introducida en Community CPS permite que se aplique un TimeSlot a cada grupo de conversación de contacto digital

De manera predeterminada, la anulación del canal TS está deshabilitada. Esto significa que si se presionan las flechas ** Izquierda ** o ** Derecha ** para seleccionar este TG dentro de la lista Grupo Rx, el intervalo de tiempo asignado al Canal (en el CPS) o se cambia manualmente usando la ** Estrella ** la llave no cambiará

Sin embargo, si el contacto digital tiene un TS de anulación asignado. P.ej. TS 1.
Cuando este contacto digital TG se selecciona presionando las flechas derecha o izquierda, el intervalo de tiempo se establecerá en el intervalo de tiempo asignado al contacto digital TG

#### TalkGroup se muestra en video inverso

Si se muestra un Talkgroup en video inverso durante la recepción de una señal DMR, esto indica que el Tx TalkGroup actual no coincide con el TalkGroup recibido, por lo tanto, presionar el PTT no transmitirá a la estación en el mismo TalkGroup.

Si desea transmitir en el mismo TalkGroup que la señal recibida actualmente, presione el botón ** Función ** (azul) en el costado de la radio mientras el TalkGroup se muestra en video inverso y Tx TalkGroup se configurará en Rx TalkGroup

![](media/talkgroup-inverse-video.jpg)

#### Entrada manual del número de TalkGroup

Presione el botón ** Hash (#) ** para ingresar el número de TalkGroup. Seguido por la tecla ** Verde ** para confirmar

![](media/talkgroup-entry.jpg)

#### Entrada de número de llamada privada

Presione el ** Hash (#) ** nuevamente para ingresar un número de ID de DMR de llamada privada.

![](media/private-call-entry.jpg)

En todas las pantallas de entrada numérica, al presionar la tecla de menú roja se vuelve a la pantalla anterior, ya sea la pantalla VFO o Channel

#### Selección de contacto digital

Presione ** Hash (#) ** nuevamente para acceder a los contactos digitales definidos en el CPS

![](media/contact-selection.jpg)

El nombre del contacto se muestra en el medio de la pantalla, p. "TG 505 TS2" y el número de TalkGroup o PC se muestran en un texto más pequeño en la parte inferior de la pantalla

Presione las flechas ** Arriba ** o ** Abajo ** para recorrer la lista de Contactos digitales

Presione ** Verde ** para seleccionar o ** Rojo ** para cancelar.

Las llamadas privadas también se pueden seleccionar.

![](media/private-call-selection.jpg)

#### Entrada del número de ID de DMR de la estación

En el modo de selección de contacto, presione la tecla ** Función + Hash (#) **, y se puede ingresar una ID de DMR alternativa, para propósitos de prueba, para anular temporalmente su número de ID de DMR normal que se cargó del codeplug.

Esta ID de DMR se usará para la transmisión * hasta que * la radio se reinicie o ingrese otra ID de DMR a través de la misma pantalla.

Para que el cambio sea permanente, de modo que se regrese al codeplug Presione ** Función + Verde ** en lugar de ** Verde ** para ingresar el número.

![](media/user-dmr-id.jpg)

### Funcionalidad específica de FM (pantallas VFO y Channel)

#### FM / FM Estrecho

** Para FM con banda de 25 kHz con el texto "FM" se muestra en la esquina superior izquierda de la pantalla.
Para banda estrecha / 12.5kHz se muestra el texto "FMN" **

#### tono CTCSS

Esto se puede configurar para el canal o VFO, las letras ** CT ** ** CR ** o ** CTR ** se mostrarán junto a la indicación de FM en la parte superior de la pantalla.

** CT ** significa solo tono CTCSS Tx. ** CR ** significa solo tono CTCSS Rx. ** CTR ** significa tonos CTCSS Tx y Rx.

![](media/ctcss-tone.jpg)

#### Silenciador

Al presionar las teclas ** Izquierda ** o ** Derecha **, se activa el control de silenciador FM

![](media/squelch.jpg)

Una vez en el modo de control de silenciamiento, presionar ** Derecha ** más el silenciador, ** Izquierda ** abre más el silenciador.

El VFO y cada canal tienen configuraciones de silenciador individuales

El silenciador variable se puede configurar en diferentes valores para cada canal y para el VFO utilizando una nueva función en Community CPS, donde el silenciador se puede configurar en cualquier lugar entre Abierto y Cerrado en pasos de 5%.

En este ejemplo, el silenciador en el VFO se establece en 20%


Si se cambia el silenciador en el VFO, el valor se recordará incluso si la radio se apaga y enciende. Sin embargo, si se cambia el silenciador en un canal, el valor es solo una anulación temporal.

Para hacer que el cambio de silenciamiento sea permanente a un canal, presione ** Función + Verde ** para ingresar a la pantalla Detalles del canal, y luego presione ** Verde ** nuevamente para guardar los datos del canal en el código.

Nota.
Si Rx CTCSS está habilitado, esto tiene prioridad sobre el control del silenciador, y bajar el umbral del silenciador no hará que se abra el silenciador.

#### 1750Hz Tono para operación repetidora

Al presionar el botón ** Función ** durante la transmisión de FM, se envía el tono de 1750Hz requerido para alguna operación del repetidor.

#### Transmisión de tonos DTMF

Al presionar cualquier tecla del teclado, excepto las teclas de menú Verde y Rojo, se transmitirán los tonos DTMF para esa tecla.

El tono también será audible a través del altavoz.

### Funcionalidad específica de VFO

![](media/vfo-screen.jpg)

El VFO muestra la frecuencia Tx y Rx en todo momento.

Cuando la frecuencia seleccionada actualmente es la frecuencia ** Rx **, se muestra una flecha a la izquierda de “** R **”, los cambios en la frecuencia ajustarán las frecuencias Tx y Rx.

#### Cambio de frecuencia paso arriba / abajo

Al presionar las flechas ** Arriba ** o ** Abajo **, cambiará la frecuencia por el valor definido en la frecuencia Valor de paso definido para el VFO en el CPS.

El paso se puede ajustar presionando ** Función + Verde ** para ingresar al modo Detalles de canal y luego ajustar la configuración de "Paso"

#### Entrada de frecuencia numérica

Al presionar cualquiera de las teclas numéricas se permite la entrada directa de la frecuencia.

![](media/frequency-entry.jpg)

Cuando se han ingresado todos los dígitos, se reproducen los pitidos de aceptación y la pantalla vuelve a la pantalla de VFO.

Si se ingresa una frecuencia no válida, se reproducen los pitidos de error.

Al ingresar una frecuencia:

Al presionar la tecla ** Rojo ** se cancela la entrada

Al presionar ** Flecha izquierda ** se eliminan los dígitos uno por uno.

#### Para ajustar la frecuencia Tx, independiente de la frecuencia Rx.

Presione el botón ** Función (Azul) ** en el costado de la radio y la flecha ** Abajo **.

Esto cambiará la frecuencia seleccionada actualmente a la frecuencia Tx, y la flecha se moverá a la izquierda de “** T **” en lugar de “** R **”

Para cambiar la frecuencia Rx nuevamente, presione ** Función + Flecha arriba **.

Cuando se cambia la frecuencia Tx, la frecuencia Rx no se cambiará.

Use este método para establecer diferentes frecuencias Tx y Rx, p. Esto puede ser útil para la operación satelital ya que permite la operación de banda cruzada, así como la operación simple de frecuencia dividida en la misma banda.

**Nota**

Si se configuran diferentes frecuencias Tx y Rx, y la entrada seleccionada actualmente se configura en Rx. Cambiar la frecuencia Rx también cambiará la frecuencia Tx, y la diferencia entre la frecuencia Rx y Tx se mantendrá si es posible.

El único caso en el que no se mantendrá la diferencia de frecuencia es si la frecuencia Tx se sale del rango de frecuencias admitidas por el hardware de radio.

## Transmitiendo

Durante la transmisión, el temporizador de conversación cuenta hacia arriba o hacia abajo dependiendo de si el canal tiene un tiempo de espera definido.

Si se define un tiempo de espera en el CPS, o se ajusta en la pantalla Detalles del canal, el temporizador de conversación contará hacia atrás y cuando se alcance el período de tiempo de espera se escuchará un pitido y el Tx se detendrá.

En DMR Tier2, el temporizador no comenzará a contar hasta que el repetidor se active.

Durante DMR Tx, se muestra un medidor VU que muestra el nivel del micrófono de entrada, en forma de gráfico de barras en la parte superior de la pantalla.

![](media/dmr-mic-level.jpg)

##### Pitido de advertencia de tiempo de espera

Se puede configurar una advertencia de tiempo de espera en el menú Utilidades. La radio emitirá un pitido cada 5 segundos cuando el tiempo de llamada restante sea inferior al tiempo de advertencia de Tiempo de espera que ha configurado en la pantalla Opciones

##### TOT

Si TOT está configurado para el canal actual o VFO, cuando el temporizador haga la cuenta regresiva a cero, la transmisión se detendrá, se escuchará un pitido de advertencia y la radio dejará de transmitir

![](media/timeout.jpg)

## Otras pantallas

#### Bloquear pantalla

![](media/lock-screen.jpg)

A la cerradura el teclado.

En la pantalla VFO o Channel, presione la tecla de menú ** Verde ** para mostrar el menú Principal, luego presione la tecla ** Estrella (*) **

Para desbloquear el teclado

Presione y mantenga presionado el botón ** Función (Azul) ** y presione la tecla ** Estrella (*) **

## Las teclas y botones de control

![](media/keys-and-buttons-NEW.png)

## El sistema de menús

Al presionar la tecla ** VERDE ** se ingresa al sistema de menús, presione nuevamente para ingresar a una subsección del menú o para salir del menú.

Presione la tecla ** ROJO ** para retroceder un nivel o para salir del sistema de menús.

Las teclas de flecha ** ARRIBA ** y ** ABAJO ** suben y bajan por las distintas páginas del sistema de menús.

Las teclas de flecha ** IZQUIERDA ** y ** DERECHA ** cambiarán los elementos individuales en el sistema de menús donde se pueden cambiar.

El botón ** AZUL ** en el costado de la radio, conocido como SK2, se usa como “** Función **”. Se accede a varias funciones manteniendo presionada la tecla "función" cuando se presiona un botón en el teclado.

## Menú principal

![](media/main-menu.jpg)

### Zona

Este menú se usa para seleccionar qué grupos de canales, llamados Zona, se usan en la pantalla del Canal y funcionan de la misma manera que el firmware oficial de Radioddity, excepto con una adición.

![](media/zones.jpg)

Además de las zonas que se definen en el CPS y se cargan en el GD-77 utilizando el Community CPS. El firmware crea una zona especial llamada todos los canales

![](media/all-canales.jpg)

Cuando se selecciona la zona Todos los canales, la pantalla del canal muestra el número del canal en lugar del nombre de la zona, p. CH 1

![](media/all-canales-channel-screen.jpg)

Al presionar las flechas ** Arriba ** y ** Abajo ** se recorrerán todos los canales en todas las zonas

Al presionar cualquiera de las teclas numéricas en el teclado, ingresa "Pasar al modo de número de canal"

![](media/goto-channel-number.jpg)

En este modo, puede ingresar varios dígitos y luego presionar la tecla verde para confirmar, o la tecla roja para cancelar.

### RSSI

Muestra un indicador de intensidad de señal que muestra el valor numérico de RSSI en dBm, junto con un gráfico de barras de la Unidad S.

![](media/rssi.jpg)

* Notas *

Tanto el RSSI como el medidor S no están calibrados y variarán un poco entre diferentes radios en su precisión

Las señales DMR por su naturaleza, debido a que son transmisiones de pulso, no proporcionarán valores RSSI precisos.

El número en la parte superior derecha de la pantalla es para fines de depuración y es el número informado por el hardware del receptor.

### Batería

Muestra el voltaje actual de la batería.

![](media/battery.jpg)

### Última escucha

Muestra un registro de las últimas 16 estaciones DMR que ha recibido la radio.

![](media/last-hear.jpg)

Al presionar las flechas ** Arriba ** o ** Abajo ** se recorre la lista para mostrar las estaciones que se han escuchado.

La radio almacena datos de las últimas 16 estaciones que se escucharon

### Información de firmware

![](media/firmware-info.jpg)

Muestra la fecha y hora en que se creó el firmware, y también el código de confirmación de Github entre paréntesis.

Para ver detalles sobre Github, agregue el código a
https://github.com/rogerclarkmelbourne/OpenGD77/commit/

p.ej.
https://github.com/rogerclarkmelbourne/OpenGD77/commit/a0ebbc7

### Opciones

La pantalla ** Opciones ** es el nuevo nombre para el menú ** Utilidades **.

![](media/menu-options.jpg)

Este menú controla varias configuraciones específicas del firmware OpenGD77

![](media/options-screen.jpg)

#### DMR mic

Esto controla la ganancia de audio del sistema de entrada de micrófono DMR, en relación con el valor predeterminado.

Esto solo ajusta la ganancia en DMR y no afecta la ganancia del micrófono FM.
La configuración se realiza en pasos de 3dB, siendo 0dB la configuración predeterminada normal, que es lo mismo que el firmware oficial.

#### Volumen del pitido

Esto controla el volumen del pitido y otros tonos, y se puede configurar del 100% al 10%

#### Pitido de tiempo de espera

Esta configuración controla si la radio emite pitidos de advertencia de tiempo de espera durante la transmisión cuando el tiempo de espera está por expirar y la transmisión finalizará.

#### Restablecimiento de hechos

Restablece la radio a la configuración predeterminada y lee los valores de CPS VFO A del codeplug en la pantalla VFO.

** La radio también se puede establecer en la configuración predeterminada manteniendo presionada la tecla azul (Función) mientras se enciende la radio. **

#### Calibración

Activa / desactiva la función de calibración (valor predeterminado).

Algunas radios parecen tener datos de calibración no válidos, posiblemente porque el firmware oficial ha dañado los parámetros de calibración en la memoria Flash.

Si la radio no parece transmitir o recibir correctamente. Intente deshabilitar la calibración y reiniciar la radio, ya que los parámetros de calibración nominales utilizados por el firmware OpenGD77 normalmente funcionan casi tan bien como los datos de calibración correctos.

#### Límites de banda

Activa / desactiva la función de límite de banda de transmisión que impide la transmisión fuera de las bandas de radioaficionados. (Predeterminado activado).

### Opciones de pantalla

![](media/display-options.jpg)

Modo de color
: Esta opción permite la visualización en color normal o inversa. Normal es el fondo blanco con píxeles negros; Inverso es fondo negro con píxeles blancos.
: Nota. Esto no replica completamente la versión de hardware de la pantalla "Negro" GD-77, porque esa radio usa un panel LCD diferente que físicamente tiene un fondo posterior, mientras que el GD-77 normal tiene un panel LCD con fondo blanco.

Brillo
: El firmware OpenGD77 permite controlar el brillo de la retroiluminación de la pantalla del 100% al 0%, en pasos del 10% entre 10% y 100% y por debajo del 10%, el brillo se controla en pasos del 1%.
: El brillo predeterminado de la luz de fondo (predeterminado 100%).
: Use las teclas de flecha derecha e izquierda para ajustar el brillo.

Contraste
: El firmware OpenGD77 permite controlar el contraste de la pantalla.
: Los valores son el número enviado al controlador del panel LCD, con un rango utilizable de 12 a 30. Los valores más altos producen más contraste, pero también aumentan la oscuridad del fondo.
: El firmware oficial usa un valor de 12, sin embargo, este no parecía ser el valor óptimo, por lo que el firmware OpenGD77 usa 18 como valor predeterminado.

Se acabó el tiempo
: Establece el tiempo antes de que se apague la luz de fondo de la pantalla (predeterminado 5 segundos).
: Establecer este valor en cero evita que la luz de fondo se apague.

### Detalles del canal

![](media/channel-details.jpg)

Paso
: Selecciona el tamaño de paso de frecuencia VFO / Canal.

Codigo de color
: Establece el código de color cuando el VFO / Canal está configurado en DMR

Intervalo de tiempo
: Selecciona DMR Timeslot 1 o 2 cuando el VFO / Canal está configurado en DMR.

Tx CTCSS
: Establece el tono de transmisión CTCSS cuando el VFO / Canal está configurado en FM

RX CTCSS
: Establece el tono de recepción CTCSS cuando el VFO / Canal está configurado en FM

Ancho de banda
: Establece el ancho de banda Rx y Tx en modo FM en 25Khz o 12.5Khz

Al presionar la tecla de menú ** Verde ** se confirman los cambios y se guardan las configuraciones en el codeplug, o en el caso del VFO, los cambios se guardan en las configuraciones no volátiles.
Al presionar la tecla de menú ** Rojo ** se cierra el menú sin realizar ningún cambio en el canal.

### Créditos

![](media/Créditos.jpg)

Detalles de los creadores del firmware OpenGD77.

Si otros desarrolladores contribuyen al esfuerzo de desarrollo, se agregarán a esta pantalla, y los detalles de la adición se verán presionando la ** flecha hacia abajo ** para desplazar el texto

## Realización y recepción de llamadas privadas DMR

### Para hacer una llamada privada

En modo DMR, ya sea en el VFO o en la pantalla del canal ...

* Presione la tecla # dos veces para ingresar la ID de DMR de llamada privada

* La parte superior de la pantalla ahora mostrará "Entrada de PC"

* Ingrese la ID DMR de la estación, p. Ej. 5053238

* Presione la tecla de menú verde para conformar, o la tecla de menú roja para salir.

Nota.

Si comete un error al ingresar el número, presione la tecla de flecha ** Izquierda ** para borrar los dígitos uno por uno.

Si la ID de PC que ingresó está en la base de datos de ID de DMR, la había subido previamente a la radio, el indicativo y el nombre de la estación ahora se mostrarán en la pantalla.

Si la ID no está en la base de datos de ID de DMR, se mostrará el texto "ID:" seguido del número

** La radio ahora está en modo de llamada privada. **

Para volver a la operación normal de Talkgroup, hay 3 métodos

1. Presione la tecla de menú ** Función + Rojo **

2. Presione la tecla de flecha ** Izquierda o Derecha ** que cargará el siguiente TG en la lista de Grupo Rx asignado al VFO o al Canal

3. Presione la tecla ** Hash (#) **, luego ingrese un número TG y presione la tecla de menú ** Verde **.


*Nota*

Cuando esté en el modo de llamada privada, al cambiar del modo de VFO al modo de canal y viceversa, a través de la tecla de menú roja no cambiará volver al modo de grupo de conversación

### Para recibir una llamada privada

Al recibir una llamada privada, la radio mostrará esta pantalla

![](media/accept-call.jpg)

Con el indicativo de llamada y el nombre (o ID) que se muestran en la parte superior de este texto en la pantalla.

Para aceptar la llamada y configurar la radio para que devuelva la llamada privada a la estación que llama, presione el botón de menú ** Verde **, para SÍ. De lo contrario, presione la tecla de menú ** Rojo **, para No, o ignore el mensaje y continúe usando la radio normalmente.

Si acepta la llamada privada, la radio cambiará al modo de llamada privada, lista para la transmisión. Para que se muestre la identificación o el nombre de la persona que llama, p.

![](media/private-call.jpg)

Una vez que se complete la llamada privada, puede regresar al grupo de conversación en el que estaba antes de aceptar la llamada privada, presionando la tecla de menú ** Función + Rojo **. (o por cualquiera de los métodos descritos en la sección sobre cómo hacer una llamada privada)

## Modo de punto de acceso

*Nota. Al momento de escribir, el modo Hotspot no funciona en la versión de Nivel 2 del firmware. *

El firmware OpenGD77 puede funcionar como un punto de acceso DMR (* solo voz *) cuando se conecta a través de su cable de programación USB a un Raspberry Pi que ejecuta PiStar o cualquier otro dispositivo que ejecute MMDVMHost.

Nota.

El modo de punto de acceso no es compatible con software como BlueDV


Primero, conecte el GD-77 a una Raspberry Pi a través de su cable de programación.

![](media/hotspot-connections.jpg)

El modo de punto de acceso funciona con Raspberry Pi Zero, pero se necesita un cable adaptador para convertir desde el puerto micro USB en el RPi Zero al enchufe USB de tamaño completo en el cable de programación GD-77.


En la pantalla de configuración de PiStar, seleccione "Punto de acceso DMR OpenGD77 (USB)" como tipo de módem.

![](media/pistar-configuration.png)

Si su versión de PiStar no contiene el Hotspot DMR de OpenGD77 como una opción, actualice su versión de PiStar.


Con el GD-77 ya conectado y encendido, después de cambiar el tipo de módem en PiStar, la pantalla cambiará en el GD-77 para mostrar su modo de punto de acceso, y mostrará el código de color, la frecuencia de recepción y la potencia aproximada de Tx en mW.

![](media/hotspot-mode.jpg)

Si el GD-77 no ingresa al modo Hotspot, apague y encienda el GD-77 y apague y encienda PiStar

Si el GD-77 aún no puede ingresar al modo de punto de acceso, verifique sus conexiones USB.

Nota.

Por defecto, PiStar configura el "módem" para que tenga una configuración de potencia de "100" en la configuración Experto -> MMDVMHost.

Esto es el 100% de la potencia máxima del módem, y en el caso del GD-77, la potencia de salida máxima es de 5W, pero la radio no está diseñada para funcionar como un punto de acceso, donde puede estar transmitiendo continuamente.

La configuración de potencia máxima que el GD-77 puede admitir para la transmisión continua variará según el entorno operativo, incluida la temperatura ambiente y la ROE de la antena, etc.

Es responsabilidad del usuario establecer un nivel de potencia adecuado que no sobrecaliente ni dañe el PA.


En el modo Hotspot, si PiStar (MMDVMHost) envía una configuración de potencia del 100%, se supone que PiStar no se configuró correctamente para OpenGD77 y que este valor no se tiene en cuenta.

En cambio, el firmware utilizará la configuración de energía especificada por el usuario en el menú Utilidades, que por defecto será 1W.

Si la configuración de energía en la configuración de PiStar MMDVMHost Expert es cualquier otro valor, p. 50%, el punto de acceso utilizará ese valor de potencia, p. 2.5W (2500mW)


La frecuencia de recepción especificada por PiStar se mostrará en la parte inferior de la pantalla.

Nota.
Las compensaciones no deben aplicarse a las frecuencias Tx o Rx en PiStar, porque el GD-77 no debería necesitar ninguna compensación, y cualquier compensación se reflejará en la frecuencia que se muestra en el GD-77, porque PiStar realmente envía la frecuencia maestra + / - el desplazamiento al punto de acceso.


Cuando el GD-77 recibe una señal de RF DMR, el LED verde en la parte superior del GD-77 se iluminará normalmente, y el nombre y el indicativo se muestran si la base de datos de ID de DMR contiene esa ID. Si la ID no está en la base de datos de ID de DMR, se mostrará el número de ID.

![](media/hotspot-rx.jpg)

Cuando PiStar recibe tráfico de Internet y lo envía al punto de acceso para su transmisión, el punto de acceso muestra el indicativo de llamada y el nombre o la ID de DMR, y se muestra la frecuencia de transmisión.

El LED en la parte superior de la radio también se vuelve rojo para indicar que la radio está transmitiendo

## Programación de canales y grupos de conversación para usar con OpenGD77.

** NOTA **: No puede usar el CPS estándar de Radioddity para escribir en un GD-77 flasheado con el firmware OpenGD77. Si desea utilizar Radioddity CPS, la radio deberá ejecutar el firmware oficial de Radioddity. Una vez que el código de conexión se ha escrito en el GD-77, puede actualizar el firmware de OpenGD77 a la radio y luego leerá y funcionará con el código de conexión escrito con el firmware estándar y el software CPS.


Como alternativa al Radioddity CPS, puede usar la última versión del "Community CPS" de Roger Clark que incluye soporte para OpenGD77. Consulte la siguiente sección para obtener información específica sobre Community CPS. La información en el resto de esta sección es aplicable tanto al Radioddity CPS estándar como al Community CPS.

### VISIÓN GENERAL

Con OpenGD77, a diferencia de la mayoría de las radios DMR comerciales, no es necesario crear múltiples canales para usar la misma frecuencia con muchos Talkgroups de transmisión diferentes.

En el modo DMR cuando se usa el VFO o las Zonas y Canales, puede usar las teclas de flecha IZQUIERDA / DERECHA para desplazarse y seleccionar cualquiera de los Grupos de conversación en la lista de Grupos de Rx asignados al canal actual, o al VFO A

Cuando programe la radio usando el CPS, primero agregue todos los grupos de conversación que cree que puede desear usar en la lista de contactos digitales.


Descargue el último CPS de la comunidad GD77 desde aquí:
https://github.com/rogerclarkmelbourne/radioddity_gd-77_cps/raw/master/installer/RadioddityGD77CPS31XCommunityEditionInstaller.exe

![](media/cps-treeview-rx-grouplist.png)

A continuación, cree una o más “Listas de grupos RX” y complete cada una con los conjuntos de grupos de conversación que desee utilizar con diferentes canales. Puede tener los mismos grupos de conversación en muchas listas de grupos RX.

![](media/cps-rx-grouplist.png)

Ahora configure los canales. Ingrese las frecuencias, la ranura y el código de color de forma normal para un canal DMR.

Nota. Actualmente el firmware OpenGD77 no utiliza el "Contacto", por ejemplo. Se muestra como TG9 a continuación. En su lugar, utiliza los TG en la lista del Grupo Rx.
Sin embargo, recomendamos a todos los usuarios que establezcan el "Contacto" en el primer canal en la lista de Grupo Rx asignado al canal

Luego seleccione la Lista de grupos RX que desea utilizar para el canal.

Actualmente, el firmware OpenGD77 no usa la lista Rx Group para filtrar la señal DMR entrante. Está en "Modo de monitor digital" (también conocido como modo promiscuo) todo el tiempo.

Sin embargo, en el futuro, el firmware opcionalmente permitirá el filtrado para que la radio solo acepte estaciones que transmitan en uno de los TG en la Lista de grupos Rx

![](media/cps-channel-rx-grouplist.png)

*Tenga en cuenta. El "Contacto" no es utilizado por el firmware OpenGD77. Debe usar la lista de Grupo Rx para definir los TG que desea usar con cada canal.
Por lo tanto, debe tener al menos 1 grupo Rx y debe contener al menos 1 contacto digital que sea un grupo de conversación *


Finalmente, guarde su codeplug en su computadora antes de escribir el enchufe del código en la radio utilizando Radioddity CPS estándar para programar la radio antes de actualizarla a OpenGD77 o si está utilizando la versión especial compatible con OpenGD77 del "Community CPS" (como se detalla en la siguiente sección) puede escribir el conector de código directamente en una radio OpenGD77 ya flasheada.

## Uso de la Community CPS para programar OpenGD77

El soporte para OpenGD77 ahora ha sido incluido en la Community CPS por Roger Clark, que se puede descargar desde aquí:
https://github.com/rogerclarkmelbourne/radioddity_gd-77_cps/raw/master/installer/RadioddityGD77CPS31XCommunityEditionInstaller.exe

Esta versión también es compatible con el firmware oficial, así como con el OpenGD77

#### Instalación del nuevo controlador

El instalador de CPS ahora también instala el controlador del puerto de comunicaciones OpenGD77, sin embargo, el controlador del puerto de comunicaciones se puede instalar manualmente descargando los archivos de
https://github.com/rogerclarkmelbourne/OpenGD77/tree/master/OpenGD77CommDriver

Para instalar el controlador, descargue y descomprima el archivo zip y ejecute el archivo .bat

Una vez que se instala el controlador, el administrador de dispositivos de Windows debe mostrar "OpenGD77" en la sección "puertos" del administrador de dispositivos de Windows

![](media/device-manager-ports.png)

#### Menú OpenGD77

En el CPS hay un nuevo elemento de menú en el menú Extras para OpenGD77 Support, que abre esta ventana

![](media/cps-opengd77-support.png)

Desde aquí puede hacer una copia de seguridad, el EEPOM interno de 64k y el chip Flash de 1 megabyte, así como leer y escribir el codeplug.
El almacenamiento de datos de calibración en el chip Flash (en la dirección 0x8f000) se puede hacer una copia de seguridad y restaurar sin hacer una copia de seguridad de todo el Flash.

* Tenga en cuenta que si restaura la Flash, también sobrescribirá los datos de calibración tal como están almacenados en el chip Flash de 1Mb. *

#### ¡Haga una copia de seguridad antes de hacer cualquier otra cosa!

Antes de escribir un codeplug en la radio, debe hacer una copia de seguridad de la EEPROM y del chip Flash, y guardar los archivos en un lugar seguro, en caso de que algo salga mal en el futuro y necesite restaurar los datos.

#### Lectura y escritura de su Codeplug

Para leer el codeplug, presione el botón "Leer codeplug", espere a que se descarguen las 3 secciones de datos y luego cierre la ventana de Soporte de OpenGD77. Para escribir un codeplug presione el botón "Escribir codeplug".

#### Escribiendo ID de DMR

OpenGD77 admite información extendida de ID de DMR, con hasta 15 caracteres para distintivo de llamada y nombre, además de duplicar la capacidad de memoria para ID de DMR.

Seleccione la casilla de verificación "Modo de firmware mejorado" y cambie el menú Número de caracteres al indicativo DMR deseado y la longitud del nombre.
Nota. Debido a que el tamaño de memoria utilizado para la ID de DMR está actualmente limitado a 256, puede almacenar más ID de DMR si asigna menos caracteres por ID.

![](media/cps-dmr-ids.png)