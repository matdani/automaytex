Documento breve (máx. 1 página) explicando: 
qué hace, qué decisiones de diseño se han tomado y, 
si se han usado herramientas de IA, cómo se han utilizado y qué partes 
se han revisado y validado manualmente


AUTOMAYTEX

author: Daniel Casadevall Jauhiainen


Automaytex es un plugin per a maya autodesk 26

Funciona de la seguent manera.

IDEA
Bakejar una geometria, passar-la per un sdxl, retronar-la al 
maya i reprojectar-la.

pre step. Guarda les uvs originals. 

STEP 01
El primer pas per aconseguir texturitzar una geometria,
es extreure les seves dades geometriques.

La primera versio del codi funcionava renderitzant 6 plans, 
(front, top, bottom, right, left, back)
aconseguint 6 imatges del depth, el normal i el diffuse de 
la geometria original.

El problema, que 6 imatges son moltes, rectangulars, no ideal per diffusion
models, i son moltes, i al reprojectar, refere el retargeting

hi ha cares que es repateixen, perque tenen diferents punts de vista

La segona version, renderitza utilitzant un tetaodrom rectangular
amb 4 punts i 4 cares, renderitzant aixi totes les cares, amb 4 imatges
mes optimitzat rapid, i menys cares repetides.

Un cop extret la geometry data de la geometria, es coloca
en un collage de 2x2, on es veuen totes les imatges desde totes les 
perspectives de la geometria

extreiem les normlas, i el depth map.

STEP 02

Amb el collage de imatges, retarget, extret, el passem per una pipline de diffusion model
amb control net i reference images

Carrega el VAE, utilitza o flux o sdxl o sd1.5 per texturitzar
quantitatizta el model, perque capiga en el local del ordinador
basat en el ram i o vram del ordinador


Utilitzant arnold api library python,



------------------------------------------

Futur

- gui de instalacio dels models en el folder corresponent, sdxl jegguar

depth map extractor
control net also



