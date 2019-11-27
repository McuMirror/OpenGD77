---
Guia de l'usuari de OpenGD77
---

![](media/OpenGD77-logo.svg)

# OpenGD77 Guia de l'usuari
(19 de novembre de 2019)

## Introducció

Aquesta guia d'usuari és un treball en curs com és el firmware Open GD77. Si trobeu errors o omissions, informeu-me perquè es puguin corregir.

Aquest manual cobreix tant la versió original de Fase 1 / Fase, que inclou el mode Hotspot, com les versions Alpha de Tier 2 que no inclouen el mode Hotspot, sinó que tenen altres funcions noves.

A causa del ràpid ritme de desenvolupament, algunes de les pantalles estan actualment obsoletes, ja que les DMR TS i CC es mostren a totes les pantalles DMR.

Les fotos s'actualitzaran quan el firmware no canviï tan ràpidament

La intenció del projecte OpenGD77 és crear un firmware no comercial totalment present que substitueixi completament el firmware de fàbrica de Radioddity GD-77. Aquest firmware està dissenyat específicament per a l'ús de**ràdio amateur**i té funcions no disponibles al firmware oficial.

**Nota.**
**El firmware encara està en desenvolupament i hi ha algunes àrees clau de funcionalitat que encara no s'han d'escriure.**

1. Actualment, el firmware estable només funciona en DMR amb hotspots simplex o en altres ràdios DMR per a contactes simplex. Això es deu al fet que el firmware actualment no admet completament el nivell 2 DMR necessari per a la majoria de sistemes repetidors comercials i MMDVM.

   Tanmateix, el mode DMR es pot utilitzar amb un hotspot simplex i per a l'operació DMR simplex.

   Hi ha una versió prèvia a l'alliberament (Alpha 2) que admet el funcionament de Tier2, repetidor i hotspot dúplex, però actualment té alguns problemes importants.

   *Nota. La versió de nivell 2 no admet actualment el mode hotspot *

1. Funciona la transmissió FM Rx i Tx.

   Inclou l'operació de repetidor mitjançant CTCSS tant a Tx com a Rx.

1. A DMR, actualment només hi ha possibles "trucades" i converses privades del grup de conversa

   Actualment, la missatgeria de text i altres funcions similars no són compatibles, però es troben a la llista de tasques.

   Per obtenir una llista completa dels errors actuals i millores proposades, vegeu millores
   https://github.com/rogerclarkmelbourne/opengd77/issues

El firmware està dissenyat per a l'ús de ràdio aficionada, especialment en DMR, i té diverses funcions per a l'ús de ràdio amateur que normalment no estan disponibles a les ràdios DMR comercials.

Aquests inclouen l'entrada numèrica directa dels números de DMR TalkGroup i l'ús de la llista del Grup Rx per controlar el TG seleccionable per a cada "canal" de DMR.

A més, en la mesura del possible, el firmware és de codi obert. Això permet a qualsevol persona modificar el firmware per adaptar-se a les seves pròpies necessitats, i també per a la revisió entre pares i la millora del codi font del firmware.

#### Crèdits:

El projecte va ser ideat per Kai DG4KLU, que va desenvolupar el marc inicial i tota la funcionalitat FM i DMR Tx i Rx (Tier 1).

Kai va deixar de participar activament en el projecte el juny de 2019 i a l’hora d’escriure Roger VK3KYY n’és el principal i únic desenvolupador.

Roger VK3KYY ha desenvolupat la funcionalitat de nivell 2, la interfície d'usuari, el controlador de pantalla, l'API de Codeplug, l'API de memòria EEPROM, l'API de memòria flash, el mode Hotspot i moltes altres funcions.

Diverses correccions d'errors i addicions d'Alex DL4LEX, incloses les funcions de bloqueig de pantalla i DTMF i de tons

Millores gràfiques i altres de Daniel F1RMB

Addicions de Colin G4EML, incloent la funcionalitat de zona FM CTCSS i "Tots els canals"

Aquesta guia d'usuari ha estat escrita per Roger VK3KYY basada en treballs d'Alister G0NEF

Gràcies a tots els Beta Testers que proporcionen informes detallats d’errors i comentaris d’usuaris, especialment VK7ZCR, W1RHS i G4TSN

#### Baixeu enllaços i altres recursos

**Codi font i binaris del firmware:**

Versió estable: (Nivell 1 + Mode hotspot)
https://github.com/rogerclarkmelbourne/OpenGD77/raw/master/firmware_binaries/OpenGD77.sgl

Versió “Alpha 2” de nivell 2 (no inclou el mode hotspot)
https://github.com/rogerclarkmelbourne/OpenGD77/raw/Tier2/firmware_binaries/daily_builds/OpenGD77_Tier2_Alpha_2.sgl

**GD-77 CPS comunitari amb suport per a OpenGD77:**
https://github.com/rogerclarkmelbourne/radioddity_gd-77_cps/raw/master/installer/RadioddityGD77CPS31XCommunityEditionInstaller.exe

## Instal·lació

El firmware es pot instal·lar al GD-77 mitjançant l'eina d'actualització de firmware proporcionada per Radioddity amb els seus paquets oficials d'actualització de firmware. Es pot descarregar des del lloc web de Radioddity [radioddity.com] (https://radioddity.com/). Consulteu la documentació de Radioddity sobre com utilitzar l'eina d'actualització de firmware.

Les versions més noves del CPS comunitari també tenen una funció al menú Extres per penjar el firmware a la ràdio.

El firmware OpenGD77 (fitxer .sgl) es pot descarregar de Github, utilitzant qualsevol dels enllaços que apareixen a la secció 1.1 d'aquesta guia.

La instal·lació del firmware OpenGD77 es fa al risc propi dels propietaris, però el firmware oficial normalment es pot tornar a carregar al GD-77 si l'usuari té problemes amb el firmware OpenGD77.

Nota. El programari oficial de PC CPS Radioddity GD-77 no és compatible amb el firmware OpenGD77, i s'hauria d'utilitzar el "CPS comunitari". Es pot descarregar a la presentació d'enllaços de la secció 1.1 d'aquesta guia

## Pantalles principals (pantalles VFO i Channel)

El firmware OpenGD77 té 2 pantalles principals. La pantalla VFO i la pantalla del canal. Són similars a les pantalles de canals i VFO del firmware oficial, tret que tinguin una funcionalitat addicional.

Inicialment després d’instal·lar el firmware OpenGD77, es mostrarà la pantalla VFO.

![](media/vfo-screen.jpg)

La freqüència utilitzada en el VFO tant per Tx com per a Rx es llegirà des de la configuració “VFO A” de la placa de codi.

Tant a les pantalles VFO com a Channel, el mode (DMR o FM) es mostra a la part superior esquerra de la pantalla i el percentatge de voltatge de la bateria es mostra a la part superior dreta de la pantalla.

En mode DMR, el TimeSlot actual es mostra a la dreta del text "DMR", per exemple TimeSlot 2 "TS2
i el codi de colors, p. "C1" es mostra a l'esquerra del percentatge de bateria.

La potència Tx actual es mostra a la meitat de la part superior de la pantalla. Per exemple. 750mW

A la pantalla VFO, es mostra la freqüència Tx i Rx, així com el TalkGroup quan es troba en mode DMR.

La fletxa a l’esquerra de la R (freqüència de recepció) indica que el teclat de les fletxes cap amunt i avall i les tecles d’entrada de números controlaran la freqüència Rx.

La pantalla del canal mostra la mateixa informació a la fila superior, però mostra el nom del canal (en aquest exemple “VK3RGL D”), així com la Zona (“VK3 DMR”) i en mode DMR també es mostrarà el TalkGroup.

![](media/dmr-screen.jpg)

Tant a les pantalles del VFO com del canal:

Premeu el botó de menú**Vermell**per alternar entre les pantalles VFO i Channel

Premeu la tecla de menú**Verd**per entrar al sistema de menús

Si premeu**Funció + Verd**, podreu accedir ràpidament a la pantalla de detalls del canal, a la qual també es pot accedir mitjançant el sistema de menús.
*Nota.*
El VFO és en realitat un tipus especial de canal; per tant, la pantalla Detalls del canal també funciona per al VFO.

#### Canvi del canal VFO <->

Premeu la tecla**Funció + Estrella (*)**per alternar entre el mode FM i DMR a les pantalles VFO o Channel.

#### Canvi de TimeLot en mode DMR
En mode DMR, prement la tecla**Star (*)**commuta entre Timeslot 1 i Timeslot 2

#### Control de la potència Tx

Premeu**Funció + Dreta**per augmentar la potència. Premeu**Funció + Esquerra**per reduir la potència. La potència es pot configurar a 250mW, 500mW, 750mW, 1W, 2W, 3W, 4W i 5W.
Nota. La sortida de corrent només serà correcta un cop l’operador hagi calibrat la seva pròpia ràdio, ja que el GD-77 no sembla tenir una calibració de potència molt precisa aplicada a la fàbrica per TYT.

#### Gràfic de barres de força de senyal

Tant en mode FM com DMR, la intensitat del senyal del senyal rebut es mostra com un gràfic de barres a través de l'amplada de la pantalla. El gràfic de barres del 100% és aproximadament de S9 +40 dB.

En mode DMR, el mesurador de senyal només estarà actiu quan el maquinari DMR detecti un senyal DMR.

En mode FM, el mesurador de senyal ha de funcionar tot el temps.

![](media/signal-meter.jpg)

### Funcionalitat específica de la pantalla del canal
La pantalla del canal mostra el número de canal actual i la zona actual.

![](media/channel-and-zone.jpg)

#### Canvi de canals dins la zona actual

Si premeu les tecles**Arriba**o**Fletxa avall**, canviarà el canal a la zona actual i el número de canal de la zona es mostrarà al lloc del nom de la zona.

#### Canvi de zones

Prement**Funció + fletxa amunt**o**Funció + fletxa esquerra**canvia a la zona següent o anterior

![](media/changes-zones.jpg)

#### Pantalla del canal Menú ràpid

Si premeu el botó**Taronja**a la part superior de la ràdio en mode Canal, es visualitza el menú Ràpid de la pantalla del canal.

##### Copia d'un canal a VFO

##### Llegiu el VFO al canal actual

Premeu la tecla**Verd**per confirmar i guardar el canal actualitzat a la memòria del mapa de codi**Tecla Roja**per cancel·lar-la.

![](media/channel-quick-menu.jpg)

#### VFO Menú ràpid

Si premeu el botó**Taronja**a la part superior de la ràdio en mode VFO, es visualitza el menú Ràpid de la pantalla VFO. Actualment, això té tres opcions

##### Copia la freqüència Tx a la freqüència Rx

##### Intercanviar les freqüències Tx i Rx

##### Copia la freqüència Rx a la freqüència Tx

Premeu la tecla**Verd**per confirmar la còpia o la tecla**Roja**per cancel·lar-la.

![](media/vfo-quick-menu.jpg)

**Nota.**

Escoltar l’entrada d’un repetidor només funcionarà en mode DMR si tant la freqüència Tx com la freqüència Rx són les mateixes. Això és degut a que la majoria de les ràdios DMR no ofereixen cap opció de seleccionar el mode Tier2 Active o el nivell passiu de Tier 2 i, en canvi, suposen que si les freqüències Tx i Rx són iguals, la ràdio ha d'estar en mode Actiu, on la ràdio és el mestre DMR. . Si bé, si les freqüències Tx i Rx són les mateixes, la ràdio suposa que ha de funcionar en mode Passiu de nivell 2, on el senyal del repetidor controla la sincronització del temps de sortida DMR.

Tot i això, per escoltar l’entrada d’un repetidor, el senyal que es rep no conté la informació de sincronització, per tant, s’ha de posar la ràdio al mode DMR Active per rebre el senyal.

No estic segur de si el firmware oficial és capaç de rebre l’entrada d’un repetidor si es va configurar un canal amb les freqüències Tx i Rx intercanviades, però a causa de la forma en què el firmware OpenGD77 realitza el control de tots dos TimeSlots simultàniament, però només descodifica el TG / ID i àudio per al TS seleccionat.

### Funcionalitat específica DMR (pantalles de VFO i de canal)

#### Selecció de full de temps

La clau**Star (*)**commuta entre Timeslot 1 i Timeslot 2 (versió de nivell 2)

Nota. El número de Timeslot no es mostra en aquesta foto, sinó que apareix a la dreta del "DMR", també es mostra el codi de colors a l'esquerra del percentatge de la bateria.

#### Identificador de trucades i identificació DMR

Quan es rep un senyal DMR que utilitza el mateix codi de colors que el VFO o el canal seleccionat, la pantalla de ràdio mostrarà el grup de conversa i l'ID de DMR de l'estació.

![](media/talkgroup-and-dmr-id.jpg)

Si la identificació DMR es troba a la base de dades de la identificació DMR carregada prèviament a la ràdio, es mostrarà el nom de trucada i el nom.

![](media/callsign-and-name.jpg)

#### Visualització de l'àlies parlant

A la xarxa de Brandmeister, si l’ID de DMR de l’estació no es troba a la base de dades de l’ID de DMR, a la pantalla es mostrarà la informació de Talker Alias ​​enviada per Brandmeister.

![](media/talker-alias.jpg)

La signatura de trucades es mostrarà al centre de la pantalla i es mostrarà informació addicional a la part inferior de la pantalla. La informació addicional es farà per defecte al text "ID de DMR:" seguit del número d'ID de DMR de les estacions.

Si l'estació ha introduït alguna dada a la secció APRS de la pàgina "Autoatenció" de Brandmeister, el text es mostrarà en lloc del número d'ID de DMR.

![](media/talker-alias-data.jpg)

Nota. A mesura que les dades del Talker Alias ​​s’envien lentament a mesura que s’incorporen als fotogrames de dades d’àudio DMR, la signatura de trucades apareixerà primer i aproximadament mig segon després la identificació DMR o un altre text arribarà a través de les dades DMR i es mostrarà.

#### Selecció del grup de discussió de la llista del grup Rx

Premeu les tecles**Esquerra**o**Fletxa dreta**per passar els grups de conversa al grup RxG assignat al VFO o al canal del CPS.
Aquest TalkGroup s'aplicarà tant a Rx com a Tx.

#### Assignació de Timeslot al grup de contacte digital de contacte

Una nova característica introduïda al CPS comunitari permet aplicar un TimeSlot a cada grup de contacte digital de contacte

De manera predeterminada, la substitució de TS TS està desactivada. Això vol dir que si es prem les fletxes**Left**o**Right**per seleccionar aquest TG dins de la llista del Grup Rx, el Timeslot assignat al Channel (al CPS) o canviat manualment mitjançant**Star**la clau no canviarà

Tanmateix, si el contacte digital té assignat un TS de substitució. Per exemple. TS 1.
Si se selecciona aquest TG de contacte digital, premeu les fletxes dreta o esquerra, el Timeslot s’establirà al Timeslot assignat al Digital Contact TG.

#### TalkGroup mostrat en vídeo invers

Si un Talkgroup es mostra en vídeo invers durant la recepció d’un senyal DMR, això indica que el Tx TalkGroup actual no coincideix amb el TalkGroup rebut, per tant, si premeu el PTT no es tornaria a transmetre a l’estació del mateix TalkGroup.

Si voleu transmetre al mateix TalkGroup que el senyal rebut actualment, premeu el botó**Funció**(blau) del costat de la ràdio mentre el TalkGroup es mostra en vídeo invers i Tx TalkGroup s’establirà a Rx. TalkGroup

![](media/talkgroup-invers-video.jpg)

#### Entrada del número de TalkGroup manual

Premeu el botó**Hash (#)**per introduir el número del grup de discussió. Seguit de la tecla**Verd**per confirmar

![](media/talkgroup-entry.jpg)

#### Entrada de número de trucada privada

Torna a prémer el botó**(#)**per introduir un número d'identificació DMR de trucada privada.

![](media/private-call-entry.jpg)

A totes les pantalles d’entrada numèrica, si premeu la tecla del menú vermell, es torna a la pantalla anterior, ja sigui a la pantalla VFO o a la pantalla del canal

#### Selecció de contacte digital

Torneu a prémer el botó**(#)**per accedir als contactes digitals definits al CPS

![](media/contact-selection.jpg)

El nom del contacte es mostra a la meitat de la pantalla, p. El text "TG 505 TS2" i el número de TalkGroup o PC es mostren en un text més petit a la part inferior de la pantalla

Premeu les fletxes**Ampliar**o**Baixar**per desplaçar-vos per la llista de contactes digitals

Premeu**Verd**per seleccionar o**Vermell**per cancel·lar.

També es poden seleccionar trucades privades.

![](media/private-call-selection.jpg)

#### Entrada del número d'identificació DMR de l'estació

Al mode de selecció de contactes, premeu la tecla**Funció + Hash (#)**i es pot introduir un ID DMR alternatiu, per a propòsits de prova, per substituir temporalment el vostre número d'ID DMR normal carregat des del mapa de codis.

Aquest identificador DMR s'utilitzarà per a la transmissió * fins que * es reinicie la ràdio o introduïu un altre ID de DMR a la mateixa pantalla.

Per fer que el canvi sigui permanent, de manera que es torni a escriure al mapa de codis, premeu**Funció + Verd**en lloc de**Verd**per introduir el número.

![](media/user-dmr-id.jpg)

### Funcions específiques de FM (pantalles VFO i Channel)

#### FM / FM Estret

**Per a FM amb banda de 25 kHz, amb el text "FM", es mostra a la part superior esquerra de la pantalla.
Per a banda estreta / 12,5kHz es mostra el text "FMN"**

#### to CTCSS

Es pot configurar per al canal o per VFO, a la part superior de la pantalla es mostraran les lletres**CT****CR**o**CTR**al costat de la indicació FM.

**CT**significa només CTCSS Tx to.**CR**significa només el to CTCSS Rx.**CTR**significa tons CTCSS Tx i Rx.

![](media/ctcss-tone.jpg)

#### Squelch

Si premeu les tecles**Esquerra**o**Dreta**, s'activa el control d'esquadra FM

![](media/squelch.jpg)

Un cop al mode control de squelch, premeu**Dret**el squelch més,**A l’esquerra**s’obri més l’esquelet.

El VFO i cada canal tenen configuracions de squelch individuals

La variable squelch es pot configurar en valors diferents per a cada canal i per al VFO mitjançant una funció nova al CPS de la comunitat, on es pot configurar l’esquiló en qualsevol lloc entre Obert i Tancat amb passos del 5%.

En aquest exemple, l'esquadra al VFO es defineix en 20%


Si es canvia l'esquadra al VFO, es recordarà el valor, fins i tot si la ràdio està activada. Tanmateix, si es canvia l'esquadra d'un canal, el valor només és una substitució temporal.

Per fer que el canvi d’esquadra sigui permanent a un canal, premeu**Funció + Verd**per entrar a la pantalla Detalls del canal i, a continuació, premeu**Verd**de nou per guardar les dades del canal a l’enllaç de codis.

Nota.
Si Rx CTCSS està habilitat, això té prioritat sobre el control de squelch, i la baixada del llindar de l’esquadra no farà que s’obri l’esquadra.

#### 1750Hz Ton per a l'operació del repetidor

Si premeu el botó**Funció**durant la transmissió de FM, s'envia el to de 1750Hz requerit per a alguna operació de repetidor.

#### Transmissió de to DTMF

Si premeu qualsevol tecla del teclat, excepte les tecles del menú Verd i Vermell, es transmetran els tons DTMF per a aquesta tecla.

El to també serà audible a través de l’altaveu.

### Funcionalitat específica del VFO

![](media/vfo-screen.jpg)

El VFO mostra la freqüència Tx i Rx en tot moment.

Quan la freqüència actualment seleccionada és la freqüència**Rx**, es mostra una fletxa a l’esquerra del “**R**”, els canvis a la freqüència s’ajustaran tant a les freqüències Tx com a Rx.

#### Canvi de freqüència al pas / avall

Si premeu les tecles**Up**o**Fletxes cap avall**, canviarà la freqüència pel valor definit en el valor Freqüència pas definit pel VFO del CPS.

Es pot ajustar el pas prement**Funció + Verd**per entrar al mode Detalls del canal i, a continuació, ajustant la configuració "Pas"

#### Entrada de freqüència numèrica

Si premeu qualsevol de les tecles numèriques es permet l'entrada directa de la freqüència.

![](media/frequency-entry.jpg)

Quan s'han introduït tots els dígits, es reprodueixen els pitjos d'acceptació i la pantalla torna a la pantalla VFO.

Si s’introdueix una freqüència no vàlida, es reprodueixen els pitjos d’error.

Quan introduïu una freqüència:

En prémer la tecla**Vermell**, es cancela l'entrada

Si premeu**Fletxa esquerra**, se suprimeixen els dígits un per un.

#### Per ajustar la freqüència Tx, independent de la freqüència Rx.

Premeu el botó**Funció (Blau)**del costat de la ràdio i**Fletxa cap avall**.

Això canviarà la freqüència actualment seleccionada per la freqüència Tx i la fletxa es desplaçarà a l'esquerra de la "**T**" en lloc de la "**R**"

Per canviar de nou la freqüència Rx, premeu**Funció + fletxa amunt**.

Quan es canvia la freqüència Tx, no es canviarà la freqüència Rx.

Utilitzeu aquest mètode per configurar diferents freqüències Tx i Rx, p. això pot ser útil per a l'operació per satèl·lit, ja que permet l'operació entre bandes i l'operació simplex de freqüència dividida a la mateixa banda.

**Nota**

Si s'estableixen diferents freqüències Tx i Rx, i l'entrada seleccionada actualment s'estableix en Rx. Canviar la freqüència Rx també canviarà la freqüència Tx i es mantindrà la diferència entre la freqüència Rx i Tx si és possible.

L’únic cas en què no es mantindrà la diferència de freqüència és si la freqüència Tx queda fora del rang de freqüències suportat pel maquinari de ràdio.

## transmissió

Durant la transmissió, el temporitzador de conversa, compta o augmenta en funció de si el canal té definit un temps d'espera.

Si es defineix un temps d'espera al CPS, o s'ajusta a la pantalla de detalls del canal, el temporitzador de conversa es comptabilitzarà i quan s'arribi al període de temps d'espera es reproduirà un pit i el Tx s'aturarà.

A DMR Tier2, el temporitzador no començarà a comptar fins que el repetidor estigui actiu.

Durant DMR Tx es mostra un comptador VU que mostra el nivell de micròfon d'entrada, en forma de gràfic a barra a la part superior de la pantalla.

![](media/dmr-mic-level.jpg)

##### Bip d'alerta de temps mort

Es pot configurar un avís de temps d'espera al menú Utilitats. La ràdio emet un so cada 5 segons quan el temps de trucada restant sigui inferior al temps d’avís que ha configurat a la pantalla Opcions

##### TOT

Si es configura TOT per al canal actual o VFO, quan el temporitzador compta a zero, la transmissió s’aturarà, es reproduirà un pitge d’avís i la ràdio deixarà de transmetre

![](media/timeout.jpg)

## Altres pantalles

#### Pantalla de bloqueig

![](media/lock-screen.jpg)

Per bloquejar el teclat.

A la pantalla del canal VFO o al canal, premeu la tecla de menú**Verd**per mostrar el menú principal i, a continuació, premeu la tecla**Estrella (*)**.

Per desbloquejar el teclat

Manteniu premut el botó**Funció (Blau)**i premeu la tecla**Estrella (*)**

## Les tecles i botons de control

! [] (multimèdia / claus i botons.png)

## El sistema de menús

Si premeu la tecla**VERD**, entra al sistema de menús, premeu de nou per entrar a un subapartat de menú o per sortir del menú.

Premeu la tecla**RED**per retrocedir un nivell o per sortir del sistema de menús.

Les tecles de fletxa**UP**i**DOWN**s’enfilen cap amunt i cap avall a través de les diverses pàgines del sistema de menús.

Les tecles de fletxa**LEFT**i**RIGHT**canviaran els elements del sistema de menú on es canvien.

El botó**BLAU**del costat de la ràdio, conegut com a SK2, s'utilitza com a "Funció**". S'accedeix a diverses funcions prement la tecla "funció" en prémer un botó al teclat.

## Menú principal

![](media/main-menu.jpg)

### Zona

Aquest menú s'utilitza per seleccionar quins grups de canals, anomenats Zona, s'utilitzen a la pantalla del canal i funciona de la mateixa manera que el firmware oficial de Radioddity, excepte amb una addició.

![](media/zones.jpg)

A més de les zones definides al CPS i penjades al GD-77 mitjançant el CPS comunitari. El firmware crea una zona especial anomenada tots els canals

![](media/all-channel.jpg)

Si està seleccionada la zona Tots els canals, la pantalla del canal mostra el número del canal en lloc del nom de la zona, p. CH 1

! [] (multimèdia / tots els canals-canal-pantalla.jpg)

Si premeu les tecles de fletxa**Up**i**Down**es farà cicle per tots els canals de totes les zones

Si premeu una de les tecles numèriques del teclat, entra al "mode de número de canal got"

![](media/goto-channel-number.jpg)

En aquest mode, podeu introduir diversos dígits i, a continuació, premeu la tecla Verda per confirmar o la tecla vermella per canviar.

### RSSI

Mostra un indicador de intensitat del senyal que mostra el valor RSSI numèric en dBm, juntament amb un gràfic de barres de la unitat S.

![](media/rssi.jpg)

* Notes *

Tant el comptador RSSI com S no estan calibrats i variaran una mica entre diferents ràdios en funció de la seva precisió

Els senyals DMR per la seva naturalesa, ja que són transmissions de pols no proporcionaran valors RSSI precisos.

El número que hi ha a la part superior dreta de la pantalla és amb finalitats de depuració i és el número que informa el maquinari del receptor.

### Pila

Mostra la tensió actual de la bateria.

![](media/Battery.jpg)

### Últim sentit

Mostra un registre de les darreres 16 emissores DMR que ha rebut la ràdio.

![](media/last-heard.jpg)

Si premeu les fletxes**Up**o**Down**, es desplaça a la llista per mostrar les emissores que s'han escoltat.

La ràdio emmagatzema dades de les darreres 16 emissores que s’han escoltat

### Informació del firmware

![](media/firmware-info.jpg)

Mostra la data i l'hora en què es va crear el firmware i, a més, el codi de compromís Github entre claudàtors.

Per veure els detalls sobre Github, afegiu el codi
https://github.com/rogerclarkmelbourne/OpenGD77/commit/

per exemple.
https://github.com/rogerclarkmelbourne/OpenGD77/commit/a0ebbc7

### Opcions

La pantalla**Opcions**és el nou nom del menú**Utilitats**.

![](media/menu-options.jpg)

Aquest menú controla diverses configuracions específiques del firmware OpenGD77

![](media/options-screen.jpg)

#### DMR mic

Es controla el guany d'àudio del sistema d'entrada de micròfon DMR, en relació amb el valor predeterminat.

Això només ajusta el guany sobre DMR i no afecta el guany de micròfons FM.
La configuració es realitza en passos de 3dB, i amb la configuració predeterminada de 0dB, que és el mateix que el firmware oficial.

#### Volum del pit

Això controla el volum del pit i altres tons, i es pot configurar del 100% al 10%

#### Bip de temps d'espera

Aquesta configuració controla si la ràdio emet avisos de retard durant la transmissió quan finalitzi el temps d'espera i la transmissió s'acabarà.

#### Restabliment de fets

Restableix la ràdio a la configuració predeterminada i llegeix els valors de CPS VFO A de la pantalla de codis a la pantalla VFO.

**La ràdio també es pot configurar als paràmetres predeterminats prement la tecla Blau (Funció) mentre encén la ràdio.**

#### Calibració

Activa / desactiva la funció de calibració (OFF per defecte).

Sembla que algunes ràdios tenen dades de calibració no vàlides, possiblement perquè el firmware oficial ha corromput els paràmetres de calibració a la memòria Flash.

Si la ràdio no sembla transmetre o rebre correctament. Intenteu desactivar la calibració i reiniciar la ràdio, ja que els paràmetres de calibració nominals utilitzats pel firmware OpenGD77 funcionen de manera gairebé adequada i correcta.

#### Límits de banda

Activa / desactiva la funció límit de banda de transmissió que impedeix la transmissió fora de les bandes de ràdio amateur. (Predeterminat activat).

### Opcions de visualització

![](media/display-options.jpg)

Mode de color
: Aquesta opció permet mostrar un color normal o invers. El normal és el fons blanc amb píxels negres; La inversa és de fons negre amb píxels blancs.
: Nota. Això no va replicar completament la versió de maquinari de pantalla GD-77 "Negre", perquè la ràdio utilitza un panell LCD diferent que físicament té un fons de fons, mentre que el GD-77 normal té un panell LCD amb fons blanc.

Brillantor
: El firmware OpenGD77 permet controlar la brillantor de la llum del fons de pantalla del 100% al 0%, en passos del 10% entre el 10% i el 100% i per sota del 10% la brillantor es controla en passos de l'1%.
: La luminositat del retroil·luminació predeterminada (predeterminada 100%).
: Utilitzeu les tecles de fletxa dreta i esquerra per ajustar la brillantor.

Contrast
: El firmware OpenGD77 permet controlar el contrast del display.
: Els valors són el nombre enviat al controlador de panells LCD, amb un rang utilitzable de 12 a 30. Els valors més alts produeixen més contrast, però també augmenten la foscor del fons.
: El firmware oficial utilitza un valor de 12, no sembla que sigui el valor òptim, de manera que el firmware OpenGD77 utilitza 18 com a defecte.

Retard de temps
: Estableix el temps abans que s’apague la llum de fons de la pantalla (predeterminada 5 segons).
: Seleccioneu aquest valor a zero per evitar que la llum de fons s’apagui del tot.

### Detalls del canal

![](media/channel-details.jpg)

Pas
: Selecciona la mida del pas de freqüència VFO / Channel.

Codi de colors
: Estableix el codi de color quan el VFO / Channel està ajustat a DMR

Ranura de temps
: Selecciona DMR Timeslot 1 o 2 quan el VFO / Channel està ajustat a DMR.

Tx CTCSS
: Estableix el to de transmissió CTCSS quan el VFO / Channel està ajustat a FM

RX CTCSS
: Estableix el to CTCSS de recepció quan el VFO / Channel està ajustat a FM

Ample de banda
: Estableix l'amplada de banda Rx i Tx en mode FM a 25Khz o 12.5Khz

Si premeu la tecla de menú**Verd**es confirmen els canvis i es desa la configuració al connector o, en el cas del VFO, es desaran els canvis als paràmetres no volàtils.
Si premeu la tecla de menú**Vermell**, es tanca el menú sense fer cap canvi al canal.

### Crèdits

![](media/credits.jpg)

Detalls dels creadors del firmware OpenGD77.

Si altres desenvolupadors contribueixen a l’esforç de desenvolupament s’afegiran a aquesta pantalla i es veuran els detalls de l’addició prement la tecla**Fletxa cap avall**per desplaçar el text.

## Realització i recepció de trucades privades DMR

### Per fer una trucada privada

En mode DMR, ja sigui a la pantalla del VFO o al canal ...

* Premeu la tecla # dues vegades per introduir l’ID de DMR de trucada privada

* La part superior de la pantalla ara mostrarà "entrada de PC"

* Introduïu l'ID de DMR de l'estació, per exemple. 5053238

* Premeu la tecla de menú verd per conformar-la, o bé la tecla de menú vermella per sortir.

Nota.

Si cometeu un error en introduir el número, premeu la tecla de fletxa**Esquerra**per esborrar els dígits un per un.

Si l'identificador de PC que heu introduït es troba a la base de dades de la identificació DMR, ja havíeu carregat a la ràdio, ara apareixerà a la pantalla les estacions de trucades i el nom.

Si l’ID no es troba a la base de dades de l’ID de DMR, es mostrarà el text “ID:“ seguit del número

**La ràdio està en mode de trucada privada.**

Per tornar al funcionament normal de Talkgroup, hi ha 3 mètodes

1. Premeu la tecla de menú**Funció + Vermell**

2. Premeu la tecla de fletxa**Esquerra o Dreta**que carregarà el següent TG a la llista del Grup Rx assignat al VFO o al canal

3. Premeu la tecla**Hash (#)**i introduïu un número TG i premeu la tecla de menú**Verd**.


*Nota*

Quan es trobi en mode de trucada privada, canvieu al mode VFO el mode canal i viceversa, mitjançant la tecla del menú vermell, no canvieu cap al mode TalkGroup.

### Per rebre una trucada privada

En rebre una trucada privada, la ràdio mostrarà aquesta pantalla

![](media/accept-call.jpg)

Amb el nom de trucades i el nom (o ID) apareixen a la part superior d’aquest text a la pantalla.

Per acceptar la trucada i configurar la ràdio per retornar la trucada privada a l'estació de trucades, premeu el botó de menú**Verd**, per a SÍ. En cas contrari, premeu la tecla de menú**Vermell**, per No, o ignoreu la sol·licitud i continueu fent servir la ràdio amb normalitat.

Si accepteu la trucada privada, la ràdio es canviarà al mode de trucada privada, a punt per a la seva transmissió. Per tal que es mostri l’identificador o nom de la persona que truca, p.

![](media/private-call.jpg)

Un cop finalitzada la trucada privada, podeu tornar al grup de conversa que teníeu abans d’acceptar la trucada privada, prement la tecla de menú**Funció + Vermell**. (o per qualsevol dels mètodes descrits a la secció per fer una trucada privada)

## Mode hotspot

*Nota. En el moment d’escriure el mode Hotspot no funciona a la versió de nivell 2 del firmware. *

El firmware OpenGD77 pot funcionar com un punt de mira DMR (* només veu *) quan es connecta a través del seu cable de programació USB a un Raspberry Pi que executa PiStar o qualsevol altre dispositiu que estigui executant MMDVMHost.

Nota.

El mode hotspot no és compatible amb programari com BlueDV


Primer connecteu el GD-77 a un Raspberry Pi mitjançant el seu cable de programació.

![](media/hotspot-links.jpg)

El mode Hotspot funciona amb el Raspberry Pi Zero, però es necessita un cable adaptador per convertir del port micro USB del RPi Zero al connector USB a mida completa del cable de programació GD-77.


A la pantalla de configuració de PiStar, seleccioneu "OpenGD77 hotspot DMR (USB)" com a tipus de mòdem.

![](media/pistar-configuration.png)

Si la vostra versió de PiStar no conté l'OpenGD77 DMR Hotspot com a opció, actualitzeu la vostra versió de PiStar.


Amb el GD-77 ja connectat i activat, després que el tipus de mòdem hagi canviat a PiStar, la pantalla canviarà al GD-77 per mostrar-la en mode hotspot i mostrarà el codi de colors, rebrà freqüència i potència aproximada Tx. mW

![](media/hotspot-mode.jpg)

Si el GD-77 no entra al mode Hotspot, activeu el GD-77 i el cicle d’alimentació PiStar

Si el GD-77 encara no entra al mode hotspot, comproveu les vostres connexions USB.

Nota.

Per defecte, PiStar configura el "mòdem" per tenir una configuració de "100" a la configuració Expert -> MMDVMHost.

Es tracta del 100% de la potència màxima del mòdem i, en el cas del GD-77, la potència màxima és de 5 W, però la ràdio no està dissenyada per funcionar com a punt de connexió, on es pot transmetre contínuament.

La configuració de potència màxima que pot suportar el GD-77 per a transmissió contínua, variarà segons l’entorn de funcionament, inclosa la temperatura ambiental i el SWR de l’antena etc.

És responsabilitat de l’usuari establir un nivell de potència adequat que no sobrecalenti i danyi l’AP.


En el mode hotspot, si PiStar (MMDVMHost) envia una configuració de potència del 100%, l’assumpció és que PiStar no s’ha configurat correctament per a l’OpenGD77 i aquest valor no es ignora.

En canvi, el firmware utilitzarà la configuració de potència especificada per l’usuari al menú Utilitats, que per defecte serà 1W.

Si la configuració d'energia a la configuració de PiStar MMDVMHost Expert és qualsevol altre valor, p. Al 50%, l’hotspot utilitzarà aquest valor de potència, per exemple. 2,5W (2500mW)


La freqüència de recepció especificada per PiStar es mostrarà a la part inferior de la pantalla.

Nota.
Les compensacions no s’han d’aplicar a les freqüències Tx o Rx a PiStar, perquè el GD-77 no hauria de necessitar cap compensació, i qualsevol desplaçament es reflectirà en la freqüència mostrada al GD-77, ja que PiStar envia la freqüència mestra + / - la compensació a l’hotspot.


Quan el GD-77 rep un senyal de DMR RF, el LED verd de la part superior del GD-77 s’il·lumina de forma normal i es mostrarà el nom i el signign si la base de dades ID ID DMR conté aquest ID. Si l’ID no es troba a la base de dades de l’ID de DMR, es mostrarà el número d’identificació.

![](media/hotspot-rx.jpg)

Quan PiStar rep trànsit d’Internet i l’envia a l’hotspot per a la seva transmissió, a l’hotspot es visualitza el Callign and name o l’ID de DMR i es mostra la freqüència Tx.

El LED de la part superior de la ràdio també es torna vermell per indicar que la ràdio transmet

## Canals de programació i grups de discussió per utilitzar amb OpenGD77.

**NOTA**: No podeu utilitzar el CPS de Radioddity estàndard per escriure a un GD-77 llampat amb el firmware OpenGD77. Si voleu utilitzar el CPS de Radioddity, la ràdio haurà de fer funcionar el firmware oficial de Radioddity. Un cop escrit el connector de codi al GD-77, podeu fer flash al firmware OpenGD77 a la ràdio i després llegirà i funcionarà amb el connector de codi escrit amb el firmware estàndard i el programari CPS.


Com a alternativa al CPS de Radioddity, podeu utilitzar la versió més recent del "Community CPS" de Roger Clark que inclou suport per a OpenGD77. Consulteu la secció següent per obtenir informació específica del CPS de la comunitat. La informació de la resta d'aquesta secció és aplicable tant a la norma CPS de radiació com al CPS comunitari.

### VISTA GENERAL

Amb OpenGD77, a diferència de la majoria de ràdios DMR comercials, no és necessari crear diversos canals per utilitzar la mateixa freqüència amb molts grups de converses diferents.

En mode DMR quan utilitzeu el VFO o les Zones i canals, podeu fer servir les tecles de fletxa IQUERRA / Dreta per desplaçar-se i seleccionar qualsevol dels grups de conversa de la llista del grup Rx assignats al canal actual o al VFO A

Quan programeu la ràdio amb el CPS, afegiu-hi tots els grups de conversa que cregueu que voleu utilitzar a la llista de contactes digitals.


Descarregueu aquí l’últim CPS de la comunitat GD77:
https://github.com/rogerclarkmelbourne/radioddity_gd-77_cps/raw/master/installer/RadioddityGD77CPS31XCommunityEditionInstaller.exe

![](media/cps-treeview-rx-grouplist.png)

A continuació, creeu una o més “Llistes de grups RX” i reuneix-ne cadascun dels conjunts de grups de conversa que voldreu utilitzar amb diferents canals. Podeu tenir els mateixos grups de conversa en moltes llistes de grups RX.

![](media/cps-rx-grouplist.png)

Ara configura els canals. Introduïu les freqüències, les ranures i el codi de color amb normalitat per a un canal DMR.

Nota. Actualment, el firmware OpenGD77 no utilitza, per exemple, el "contacte". A continuació es mostra TG9. En lloc d'això, utilitza el TG de la llista del grup Rx.
Tot i això, aconsellem a tots els usuaris que configurin el “Contacte” al primer canal de la llista del Grup Rx assignat al canal

A continuació, seleccioneu la llista de grups RX que voleu utilitzar per al canal.

Actualment, el firmware OpenGD77 no utilitza la llista Grup Rx per filtrar el senyal DMR entrant. Està en "Mode monitor digital" (també mode promiscu) tot el temps.

Tanmateix, en el futur el firmware permetrà opcionalment filtrar de manera que la ràdio només accepti estacions que es transmetin a una de les TG de la llista de grups Rx

![](media/cps-channel-rx-grouplist.png)

* Tingueu en compte. El firmware d'OpenGD77 no utilitza el "Contacte". Heu d'utilitzar la llista del grup Rx per definir els canvis que voleu utilitzar amb cada canal.
Per tant, ha de tenir almenys 1 grup Rx i ha de contenir almenys 1 contacte digital que és un grup de discussió *


Finalment, deseu el connector d’ordres al vostre ordinador abans d’escriure el connector de codis a la ràdio mitjançant el CPS de Radioddity estàndard per programar la ràdio abans de fer-lo llampar a OpenGD77 o si feu servir la versió especial especial OpenGD77 del “Community CPS”, tal i com es detalla a la secció següent) podeu escriure el connector de codi directament a una ràdio OpenGD77 ja brillant.

## Utilitzant el CPS comunitari per programar l'OpenGD77

Roger Clark ha inclòs el suport per a l'OpenGD77 al CPS de la comunitat, que es pot descarregar des d'aquí:
https://github.com/rogerclarkmelbourne/radioddity_gd-77_cps/raw/master/installer/RadioddityGD77CPS31XCommunityEditionInstaller.exe

Aquesta versió també admet el firmware oficial i l'OpenGD77

#### Nova instal·lació del controlador

L’instal·lador CPS ara també instal·la el controlador de port comú OpenGD77, tot i que el controlador de port comú es pot instal·lar manualment baixant els fitxers de
https://github.com/rogerclarkmelbourne/OpenGD77/tree/master/OpenGD77CommDriver

Per instal·lar el controlador, descarregueu i descomprimiu el fitxer zip i executeu el fitxer .bat

Un cop instal·lat el controlador, el gestor de dispositius Windows hauria de mostrar el "OpenGD77" a la secció "ports" del gestor de dispositius Windows

![](media/device-manager-ports.png)

#### Menú OpenGD77

Al CPS hi ha un nou element del menú al menú Extres per al suport d'OpenGD77, que obre aquesta finestra

![](media/cps-opengd77-support.png)

Des d’aquí podeu fer còpies de seguretat, el EEPOM intern de 64 k i el xip Flash d’1 mega byte, a més de llegir i escriure el codi de sortida.
El magatzem de dades de calibració del xip Flash (a l'adreça 0x8f000) es pot fer una còpia de seguretat i restaurar sense fer còpia de seguretat del flaix complet.

* Tingueu en compte que, si restableix el flaix, també sobreescriuran les dades de calibració ja que es troben emmagatzemades al xip de 1Mb. *

#### Còpia de seguretat abans de fer qualsevol altra cosa!

Abans d’escriure un connector de ràdio a la ràdio, hauríeu de fer una còpia de seguretat tant del xip EEPROM com del xip Flash i guardar els fitxers en algun lloc segur, en cas que alguna cosa vagi malament en el futur i haureu de restaurar les dades.

#### Llegir i escriure el vostre Codeplug

Per llegir el mapa de codis, premeu el botó “Llegir el codi de lectura”, espereu que es descarreguin totes les 3 seccions de dades i, a continuació, tanqueu la finestra de suport d’OpenGD77. Per escriure un enllaç de codi, premeu el botó “Escriure codeplug”.

#### Escriptura dels ID de DMR

L'OpenGD77 és compatible amb la informació de la identificació DMR ampliada, amb fins a 15 caràcters per a la signatura i el nom, a més de duplicar la capacitat de memòria dels ID de DMR.

Marqueu la casella de selecció "Mode de firmware millorat" i canvieu el menú Nombre de caràcters al nom de trucada i al nom de nom desitjats DMR.
Nota. Com que la mida de memòria que s’utilitza per a l’ID de DMR es limita actualment a 256, podeu emmagatzemar més ID de DMR si assigneu menys caràcters per identificador.

![](media/cps-dmr-ids.png)