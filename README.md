# T04. Apache vs Nginx

## Descripció

Aquest repositori correspoen a la T04 i presenta una pàgina web estàtica orientada a provar la càrrega de recursos externs i el comportament bàsic d'un servidor web.

La pàgina mostra una galeria d'imatges carregades des d'URLs externes i incorpora una petita capa de monitoratge al navegador per visualitzar:

- El temps total de càrrega de la pàgina.
- L'estat de càrrega de les imatges.
- La resposta davant errors de càrrega de recursos.

## Objectiu

L'objectiu principal és disposar d'un recurs senzill per comparar el comportament d'entorns servits amb Apache i Nginx, especialment en aspectes com:

- El lliurament de contingut estàtic.
- La gestió de múltiples peticions simultànies.
- El temps de resposta percebut al client.
- La càrrega d'actius externs en paral·lel.

## Fitxers del projecte

- index.html: pàgina principal amb l'estructura, els estils i l'script de monitoratge de càrrega.

## Funcionament

Quan s'obre la pàgina al navegador:

1. Es carreguen diverses imatges externes de manera concurrent.
2. El navegador calcula el temps total de càrrega mitjançant la Performance API.
3. Es mostra el nombre d'imatges carregades en temps real.
4. Si alguna imatge falla, es mostra un missatge d'error dins del bloc corresponent.

## Ús

Descarrega l'arxiu index.html a la carpeta /var/www/projectenexus del teu servidor web (Apache o Nginx) i usa l'eina ab per realitzar proves de càrrega.

És important assegurar-se que el servidor que està actiu és el que voleu provar:

```bash

sudo systemctl status apache2  # Per Apache
sudo systemctl status nginx    # Per Nginx
```

Si teniu actiu nginx i voleu usar Apache:

```bash

sudo systemctl disable nginx --now
sudo systemctl enable apache2 --now
```

Pel contrari, si voleu usar Nginx:

```bash
sudo systemctl disable apache2 --now
sudo systemctl enable nginx --now
```

## Tecnologies utilitzades

- HTML5
- CSS3
- JavaScript
- Performance API del navegador

## Autor

L'arxiu index.html ha estat generat amb Gemini Canva.