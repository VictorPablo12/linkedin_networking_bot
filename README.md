# **Linkedin Networking Automation using Selenium & BeautifulSoup** :space_invader: :trollface:

## **ABOUT** :bulb:

La finalidad de este repositorio es la **práctica y aprendizaje** con herramientas de automatización como son:

`Selenium y Beautiful Soup`

---

## **OBJETIVO** :dart:

Poder automatizar el proceso de agregación de contactos a la red de nuestro Linkedin, evitando el bloqueo del portal

---

## **CHALLENGES** :muscle:

Para hacerlo más interesante hay 2 limitaciones:

1. La navegación será en **modo incógnito y sin caché.** De este modo, no sólo habrá que loguearse y cargas los datos de usuario desde un fichero de texto.
2. El criterio para añadir o no a los contactos será el **número de conexiones en común** (editable). De tal manera que si Beautiful Soup chequea el campo y el usuario tiene menos de las conexiones establecidas en común cerrarará su tarjeta, pero si cumple el criterio, lo añadirá.

---

## **FUNCIONAMIENTO** :atom:

1. Apertura Linkedin en modo incógnito en Chrome.
2. Cierre ventana de cookies.
3. Logueo con usuario y contraseña de Linkedin. Guardados en private/user.txt que es de donde los lee la automatización.
4. Una vez logueado, se abre automáticamente la ventana de conversaciones. Una vez se carga, la minimiza.
5. Clicka en 'Mi Red' y espera a que se cargue la sección 'Más sugerencias para ti'.
6. Linkedin solo carga unas cuantas tarjetas de contactos en esta sección y a medida que se hace scroll va cargando más contactos. Primero coloca la vista a la altura de este `<div>` y después hace scroll hasta el final de la página. Cuando se cargan más contactos en esta sección, vuelve a hacer scroll hasta abajo para cargar más elementos. Hasta un total de 9 veces. Se puede cambiar el número de veces que el bot hace scroll en caso de que quisieramos cargar más contactos.
7. Una se muestran los contactos deseados en la página. Vuelve a la primera tarjeta de la sección, para ello tiene que leer el `id` de ese `div`, ya que son dinámicos, es decir cada vez que se carga Linkedin va cambiando y no es siempre fijo para el elemento.
8. Lee el `id` de todas las tarjetas de contactos cargadas y los contactos en común con esa persona.
9. Recorre tarjeta a tarjeta y aplica el criterio que establecimos.Añadir sólo contactos con más de **15 personas en común.** (editable)
10. Si el contacto cumple el criterio, se añade a la lista de contactos clicka en `Conectar` y posteriormente cierrar la tarjeta. En caso de que no sumple el criterio, cierra el contacto directamente.
11. Cuando termina de mirar todos los contactos a añadir. Devuelve el número de contactos añadidos, los descartados y el total de revisados.

---

## **DEMO**

https://user-images.githubusercontent.com/94057227/171400621-4493ba81-9917-453f-9b23-59ba2de40190.mp4

---

## **TECHNOLGY** STACK :wrench:

- Selenium [https://www.seleniumhq.org/](https://www.seleniumhq.org/)
- Beautiful Soup [https://www.crummy.com/software/BeautifulSoup/](https://www.crummy.com/software/BeautifulSoup/)
- Regex [https://regex101.com/](https://regex101.com/)
- Requests [https://requests.readthedocs.io/en/master/](https://requests.readthedocs.io/en/master/)
