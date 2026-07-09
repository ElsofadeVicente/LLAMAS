EXPLORADOR ALTO ORBIGO / LEON - PAQUETE OFFLINE (v2)
=====================================================

Como abrirlo:
- Descomprime la carpeta entera.
- Abre index.html directamente en el navegador.
- No necesita internet, ni instalar nada, ni servidor.

QUE HA CAMBIADO EN ESTA VERSION:
- BUG GORDO CORREGIDO: las casas se generaban boca abajo (bajo tierra),
  por eso no se veian. Arreglado.
- BUG DE PISTAS RURALES CORREGIDO: el export de OSM traia caminos
  agricolas de hasta 4,5 km que salian del pueblo, y el generador
  ponia casas sueltas a lo largo de ellos. Ahora solo se usan las
  calles reales que pertenecen al nucleo real del pueblo (35 calles,
  se descartaron 19 pistas/caminos que se iban al campo).
- Todas las casas tienen ahora tejado (antes solo los 4 edificios
  con nombre).
- Texturas de piedra/enfoscado en paredes y teja en tejados
  (generadas localmente, sin depender de ninguna imagen externa).
- Arboles junto al rio y repartidos por el pueblo.
- La camara ya no atraviesa los edificios (choca y se acerca).
- El personaje anda de verdad (piernas animadas).
- Guardado de ediciones: lo que anades o quitas en modo edicion se
  guarda en el propio navegador (localStorage) y sigue ahi aunque
  cierres y vuelvas a abrir. Boton "REINICIAR EDICIONES" para borrar
  esos cambios si quieres empezar de cero.
- Joystick tactil + boton de salto en movil.

QUE SIGUE PENDIENTE (necesita que tu aportes algo):
- Relieve real del terreno: esta todo plano. Para hacerlo real
  necesitaria datos de elevacion de la zona (mismo problema de antes:
  no tengo internet en vivo, pero tu si puedes descargarlos).
- Mas edificios reales: solo 1 fachada tiene contorno real en tu
  export de OSM, y 4 mas estan modeladas a partir de tus fotos.
  El resto son cajas genericas de 1-2 plantas. Cuantas mas fotos
  mandes (calle por calle), mas casas puedo ir sustituyendo por
  las reales.
- Leon: sigue sin datos reales, pendiente de que mandes su export .osm
  igual que hicimos con Llamas.

Controles:
- WASD: moverse / joystick en movil
- Espacio o boton SALTAR: saltar
- Arrastrar con el raton/dedo: orbitar camara
- Rueda: zoom
- "MODO EDICION": click en el suelo anade un bloque, click en un
  edificio lo quita. Se guarda solo.
- "REINICIAR EDICIONES": borra tus cambios guardados de esta zona.

RELIEVE (v3):
- Se ha aplicado el relieve real del terreno (81 puntos de elevacion
  NASA/SRTM 30m que nos pasaste), interpolado. El terreno, las calles,
  el rio, las casas, los arboles y el personaje siguen esa altura real.
- El rango real en la zona es de unos 18 metros (bastante llano, es la
  vega del rio, pero con desnivel real).

IGLESIA (v4):
- Ya no es una posicion aproximada. Esta trazada del plano oficial del
  Catastro (captura que mandaste, parcela 04542, incluye "Iglesia" y
  "Torre" explicitamente etiquetadas), calibrada usando la barra de
  escala del mapa (50 m) y las coordenadas reales de Plaza Mayor como
  ancla. No es descarga de vector exacto (el WFS de Catastro no nos
  dejo), pero la posicion y el tamaño ya vienen de la cartografia real,
  no estan inventados.

EDIFICIOS REALES DEL CATASTRO (v5) - EL CAMBIO GRANDE:
- Ya no hay casas genericas inventadas. Los ~680 edificios del pueblo
  vienen del Catastro oficial (Direccion General del Catastro, servicio
  INSPIRE, municipio 24094), con su contorno exacto y su altura real
  (numero de plantas real x 3m). Ya no hay ninguna "caja de relleno".
- El Ayuntamiento, la Farmacia, el Bar Zipi y Zape y el Bar Camping
  Llamas usan tambien su contorno real del Catastro (antes eran
  rectangulos aproximados centrados en su punto real).
- La Iglesia usa el contorno real de su parcela en el Catastro para el
  cuerpo principal; la torre no viene separada en los datos del
  Catastro, asi que sigue estimada del plano visual, pero anclada a la
  posicion real de la iglesia.

v6 - LEON FUERA, MEJORAS GENERALES Y BUGS:
- Se ha quitado Leon del todo (selector de ubicacion, datos placeholder,
  todo). Solo queda Llamas de la Ribera.
- Tejados: los edificios reales del Catastro con forma irregular (en L,
  con patio, muchos vertices) ya no llevan un tejado conico estirado
  que quedaba raro; ahora llevan un tejado plano. Los edificios de
  forma simple (rectangular) siguen con tejado a cuatro aguas.
- Terreno: textura de tierra/hierba generada localmente en vez de un
  verde plano.
- Arboles: los del rio ahora son chopos (alamos altos y estrechos,
  como las choperas reales del Orbigo), distintos de los arboles
  redondeados del resto del pueblo.
- Personaje: ahora tiene brazos que se mueven al andar, no solo piernas.
- Bug de rendimiento arreglado: la camara recalculaba la lista de los
  681 edificios 60 veces por segundo solo para comprobar colisiones;
  ahora se mantiene una lista ya preparada y se reutiliza.
- Bug de fisica arreglado: los edificios apoyaban su base en la altura
  del centro de la parcela, lo que en pendiente podia dejar una esquina
  flotando o hundida. Ahora se apoyan en el punto mas bajo real de la
  parcela (comprobado: la mayor pendiente dentro de una sola parcela
  del pueblo es de 2.2 m, ya no se nota).

v7 - FIDELIDAD, AMBIENTE Y JUGABILIDAD:
- Colores de edificio con una pista real: los de una sola planta y mas
  de 110 m2 (probable nave/pajar) llevan tonos de piedra/almacen en vez
  de los colores de vivienda. El Catastro no trae el "uso" explicito en
  este export, asi que es una aproximacion basada en datos reales
  (plantas + superficie), no el dato exacto.
- Cartel con el nombre real de la calle cuando caminas por ella (si no
  hay un edificio con nombre mas cerca).
- Ciclo dia/noche completo (5 minutos por ciclo): el sol se mueve, el
  cielo y la niebla cambian de color, y unas 20 farolas reales se
  encienden de noche.
- Cielo con nubes generadas localmente (sin depender de ninguna imagen
  externa).
- Minimapa en la esquina superior derecha (solo escritorio por ahora,
  se oculta en movil por espacio) con calles, rio, casas, edificios
  con nombre y tu posicion/orientacion.
- Boton de bicicleta: mas del doble de velocidad, con ruedas visibles
  y las piernas/brazos se ocultan mientras vas en bici.
- Modo foto (icono de camara): oculta toda la interfaz para hacer
  capturas limpias, con un boton para salir.

Probado con 40 fotogramas simulados y todos los botones nuevos antes
de empaquetar, sin errores.

v8 - NEGOCIOS Y LUGARES DE INTERES (investigados por busqueda web):
- Iglesia: nombre real corregido a "Nuestra Senora de la Asuncion"
  (siglo XVII), confirmado por su fiesta patronal (15 de agosto).
- Estanco Bar la Plaza: negocio real con direccion real confirmada
  (Plaza Mayor, 2), colocado en el centro real de la Plaza Mayor.
- Fuente junto a la Plaza Mayor: existe de verdad (citada en rutas de
  senderismo, "junto a la iglesia y la fuente"), posicion aproximada.
- Zona de la playa fluvial (paraje "Los Redondales"): los dos bares
  que ya teniamos (Zipi y Zape, Bar Camping) forman parte de un
  complejo de ocio real junto al rio, confirmado por multiples fuentes:
  ahora incluye piscina fluvial, campo de futbol con porterias,
  minigolf y zona infantil, todo real, con tamano y posicion
  aproximados (no hay planos exactos de estas instalaciones).
- NO incluida a proposito: la Ermita del Calvario existe de verdad,
  pero esta fuera del pueblo (cruzando el rio Orbigo y subiendo un
  alto, segun rutas de senderismo reales), fuera del area que hemos
  mapeado. No se ha inventado su posicion.

v9 - CORRECCION IMPORTANTE Y DATOS DE UN VECINO DEL PUEBLO:
- BUG REAL CORREGIDO: la "Avenida Principal" (con numeracion real hasta
  el 92, donde estan las carnicerias/panaderias) se habia descartado
  por error, tratandola como carretera rural. Habia casas reales del
  Catastro entre 450 y 650 metros mas al norte y al sur sin ninguna
  calle real dibujada al lado. Ahora esta restaurada entera.
- El caño de la Plaza Mayor: corregido. No es una fuente ornamental,
  es un caño con escalones para bajar hasta el, en la zona este de la
  plaza (dato de un vecino del pueblo).
- Cruz de piedra blanca: anadida en la zona noreste de la plaza (dato
  de un vecino del pueblo).
- El Calvario: SI esta dentro del pueblo (antes penso que estaba fuera
  por una ruta de senderismo que hablaba de cruzar el rio). Segun un
  vecino: saliendo hacia el norte, lado izquierdo/oeste de la carretera
  general, la ultima construccion en esa direccion. Colocado justo mas
  alla de las ultimas casas reales del Catastro en esa zona.

PENDIENTE DE CONFIRMAR (no se ha inventado la posicion a proposito):
- Las dos carnicerias (Embutidos Llamas, Avenida Principal 25-27) y
  las panaderias (Panaderia Magaz, Avenida Principal 5; Panaderia
  Rocio/Suarez, Avenida Principal 50 o 92) SI son negocios reales
  confirmados por busqueda, con direccion real en la Avenida Principal,
  pero no se en que sentido va la numeracion de esa avenida (si el
  numero 5 esta al norte o al sur), asi que no las he colocado todavia
  para no adivinar mal.
- El GUIMA (Centro de Interpretacion del Antruejo) es real y confirmado,
  pero no encontre su direccion exacta en la busqueda.

v10 - CALLES REALMENTE TRANSITABLES Y CARTELES:
- BUG REAL ENCONTRADO Y CORREGIDO: el motor comprobaba las colisiones
  contra el rectangulo envolvente de cada casa, no su forma real. Para
  casas giradas o irregulares (muy comunes en los datos reales del
  Catastro) ese rectangulo sobresalia bastante mas que la casa de
  verdad, bloqueando el paso en calles que en realidad estaban
  despejadas. Comprobado con 3775 puntos muestreados a lo largo de
  todas las calles: antes el 14% de los tramos quedaban completamente
  bloqueados en todo su ancho; ahora el 100% de las calles reales son
  transitables, garantizado por construccion (las calles dibujadas
  nunca bloquean el paso, pase lo que pase con los edificios de al lado).
- Anchos de calle mas realistas (las calles de pueblo eran demasiado
  anchas, invadian visualmente la fachada de las casas reales).
- Radio de colision del personaje reducido (una persona real no mide
  90cm de ancho).
- Carteles de calle reales en 3D: cada calle con nombre real tiene
  ahora un letrero visible en el propio mapa, no solo el aviso de
  abajo al pasar cerca.

v11 - PANADERIAS Y CARNICERIA (posicion estimada por numero de portal):
- Confirmado por el usuario (vecino del pueblo): el nº5 de la Avenida
  Principal (Panaderia Magaz) esta al sur del pueblo. Eso fija el
  sentido de la numeracion: crece hacia el norte.
- Con eso, coloco por interpolacion a lo largo de la avenida real:
  - Panaderia Magaz (nº5)
  - Embutidos Llamas / carniceria (nº25-27)
  - Panaderia Rocio, Juan y Sonia Suarez (nº50)
- Marcados en su etiqueta como "posicion estimada por numero de
  portal, no exacta": la calle y la direccion son reales, pero al no
  tener el punto exacto de cada portal, la posicion es una
  interpolacion lineal a lo largo de la avenida entre el nº5 (sur) y
  el nº92 (norte, otra direccion real conocida de otro negocio).
- GUIMA (Centro de Interpretacion del Antruejo) sigue sin colocar: es
  real y confirmado, pero no he encontrado su direccion ni una pista
  de en que zona del pueblo esta.

v12 - GUIMA COLOCADO:
- Confirmado por el usuario: GUIMA (Centro de Interpretacion del
  Antruejo) es el mismo edificio que el Pabellon Municipal.
- Direccion real encontrada: "Calle Real, 93". Ese numero (93) es casi
  identico al nº92 ya usado para otro negocio real de la Avenida
  Principal, asi que es casi seguro el mismo tramo de calle con un
  nombre historico distinto. Colocado con el mismo metodo de
  estimacion por numero de portal, cerca del extremo norte del pueblo.

v13 - RECALIBRACION CON EL DATO DEL GUIMA:
- Corregido: la direccion real del GUIMA es Avenida Principal, 117
  (no "Calle Real, 93"). Como el 117 es mas alto que el 92 que tenia
  como referencia del extremo norte, he recalibrado el calculo de
  posicion de TODOS los negocios de la avenida (panaderias,
  carniceria, GUIMA) usando el nº5 (sur, confirmado) y el nº117 (norte,
  confirmado) como nuevos extremos. El GUIMA queda ahora practicamente
  en el extremo norte del pueblo, junto al Calvario.

v14 - MURAL REAL DEL GUIMA:
- La fachada del GUIMA ahora usa la foto real del mural del Antruejo
  que mandaste, como textura de verdad en la pared (no un color liso).
  La imagen va incluida en la carpeta textures/ del paquete, sigue
  siendo 100% offline (no depende de ninguna URL externa).

v15 - INVESTIGACION Y MEJORAS GRANDES:
- Sonido ambiente (boton altavoz): viento y pajaros sintetizados con
  Web Audio, sin ningun archivo de audio externo, 100% offline.
- Guardado de posicion: cada 4 segundos se guarda donde estas; al
  volver a abrir el explorador, reapareces donde lo dejaste.
- Modo VISITA GUIADA: recorre automaticamente todos los lugares reales
  (iglesia, ayuntamiento, bares, playa fluvial, negocios, Calvario...)
  uno detras de otro, con boton de "siguiente parada".
- Campos de lupulo: cultivo real y caracteristico de esta zona del
  Alto Orbigo (confirmado por busqueda), anadidos como elemento de
  paisaje en un par de parcelas junto al pueblo.
- Investigado (contexto, no siempre colocable en el mapa): el Antruejo
  de Llamas es Bien de Interes Cultural desde 2023, uno de los
  carnavales tradicionales mas antiguos de España; Llamas de la Ribera
  es ademas el lugar donde nace el rio Orbigo, por la union de los
  rios Luna y Omaña.

PENDIENTE (necesita trabajo dedicado aparte):
- Fusionar la geometria de los 680 edificios en menos objetos para
  mejorar el rendimiento en moviles antiguos: three.js no trae esa
  utilidad incluida en la version que usamos y hacerlo a mano con
  garantias necesita su propia pasada, no lo he metido con prisas.

v16 - RESPUESTA A CRITICA DURA (rendimiento, interfaz, escala):
- INTERFAZ REHECHA DE CERO: fuera el panel de texto permanente, las
  estadisticas, la descripcion larga. Ahora solo hay 4 botones
  pequeños (editar / bici / visita / mas), un icono (i) para ver la
  info si se quiere, y las etiquetas contextuales que ya existian
  (nombre de calle, lugar cercano). Nada de texto forzado en pantalla.
- RENDIMIENTO: los ~680 tejados, los arboles, los postes de farolas y
  del lupulo y los carteles de calle ya no son cientos de objetos
  sueltos; estan fusionados en un puñado de mallas (menos llamadas de
  dibujo, deberia notarse sobre todo en moviles). Ademas se ha reducido
  el numero de arboles, farolas con luz real y postes de lupulo.
- ANCHO DE CALLE MEDIDO DE VERDAD: antes era un numero adivinado por
  tipo de via. Ahora se mide contra las casas reales del Catastro a
  cada lado, en muchos puntos a lo largo de cada calle (no solo en las
  esquinas), con margen asimetrico (el trazado de la calle no siempre
  esta centrado entre las casas). Sigue sin ser perfecto al 100% en
  cada metro (dos fuentes de datos independientes nunca van a encajar
  del todo), pero ha pasado de anchos inventados a anchos medidos, y
  el solape se ha reducido significativamente.

Si sigue viendose mal en algun sitio concreto del pueblo, decir
exactamente donde (que calle, que zona) ayuda mucho mas que "esta mal"
en general - con el criterio de quien vive alli se puede afinar mucho
mas rapido que a ciegas.

v17 - COLOR REAL DE CADA EDIFICIO (ya no es una suposicion):
- Habia buscado mal la primera vez: el Catastro SI trae el uso real
  de cada edificio (currentUse), estaba en el fichero building.gml,
  no en buildingpart.gml (que es el que habia revisado). Encontrado
  y aplicado.
- 698 de los 699 edificios del nucleo del pueblo tienen uso real
  confirmado: 553 vivienda, 107 industrial/nave-almacen, 18 agricola
  (cuadra/pajar), 2 servicios publicos. Cada uno lleva ahora el color
  que le corresponde de verdad, no una suposicion por tamaño y plantas.

v18 - MURAL BIEN RECORTADO Y PISCINAS REALES:
- Mural del GUIMA: recortado para quitar el cielo y la acera (antes
  metia la foto entera), y ya no se estira para llenar el ancho del
  edificio (se respeta la proporcion real de la foto, antes salia
  deformada).
- 8 piscinas privadas reales encontradas: resulta que ya tenia el
  archivo (otherconstruction.gml, parte de la descarga de edificios
  del Catastro) pero no lo habia mirado. Registra piscinas al aire
  libre como construccion aparte. Colocadas con su forma y posicion
  EXACTA (no aproximada), tal cual las registra el Catastro.

PENDIENTE (para saber que es huerta, patio o zona pavimentada dentro
de cada parcela, no solo la piscina): habria que descargar tambien
"Parcela Catastral" (CadastralParcels), que es un dataset distinto al
de Edificios que ya tienes. Mismo proceso que Edificios/Direcciones:

https://www.catastro.hacienda.gob.es/INSPIRE/CadastralParcels/ES.SDGC.CP.atom.xml

Si te animas a bajarlo (Leon -> Llamas de la Ribera, tipo "urbana"),
lo cruzo con lo que ya tengo para poder distinguir de verdad zona
construida / huerta / patio / pavimento dentro de cada parcela.

v19 - PISCINA DEL CAMPING CORREGIDA CON DATO REAL:
- La piscina fluvial ya no es una posicion/tamaño estimado a mano.
  Encontrada en el mismo archivo del Catastro (otherconstruction.gml,
  que ya tenia descargado): una piscina real de 1449 m2 (tamaño claro
  de piscina publica, no privada) a 99 metros de donde yo la habia
  puesto a ojo. Corregida con su forma y posicion exactas.
- Pistas deportivas (campo de futbol, pista polideportiva, frontón):
  revisadas en el mismo archivo, no aparecen. El Catastro solo registra
  aqui piscinas al aire libre (13 en todo el municipio, ninguna pista
  deportiva clasificada). El campo de futbol y demas siguen siendo
  una estimacion de posicion/tamaño, no he encontrado su dato real
  en ningun archivo que tenga descargado.

v20 - ZONA DEPORTIVA DEL CAMPING CALIBRADA CON TU FOTO DE SATELITE:
- Usando la piscina real (dato exacto del Catastro, 43.6x47m) como
  ancla de escala sobre tu captura de Google Earth con las zonas
  coloreadas, he recalculado posicion y tamaño de:
  - Campo de futbol 11 (verde): reposicionado y redimensionado
  - Minigolf (amarillo): reposicionado y redimensionado
  - Parque infantil de arena (rojo): reposicionado
  NUEVO, no existia antes:
  - Recinto multicancha (blanco): baloncesto + tenis + futbol sala,
    con valla perimetral
  - Pista de padel cubierta (morado): con tejado sobre postes
  - Tirolina + maquinas de ejercicio (rosa)
- Los bares (granate en tu foto) no se han tocado: ya tenian posicion
  real de antes (nodos OSM), y encajan bien con la zona recalibrada.

Este metodo (usar algo con dato 100% real como ancla de escala sobre
una foto/captura tuya) es mucho mas fiable que estimar a ojo, asi que
si hay mas zonas del pueblo que quieras afinar y tienes algo real
cerca para anclar la escala, es el camino a seguir.
