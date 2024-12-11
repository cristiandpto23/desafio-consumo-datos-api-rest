# Desafio - Consumo de datos desde una API REST

💡 Realizado [cristiandpto23](https://github.com/cristiandpto23) con HTML y JS<br>
➡ Front-End G17 - Desafío Latam<br>
🔗 Desplegado en Vercel [aquí](https://desafio-consumo-datos-api-rest.vercel.app/)<br>

## Introducción

En este desafío validaremos nuestros conocimientos del consumo de API's. Para lograrlo, necesitarás usar el ciclo de vida de un componente para consumir una API justo luego de renderizar la aplicación.

## Descripción

Para poner a prueba tus conocimientos del consumo de API's deberás realizar una mini aplicación con temática de chat para permitir el diálogo entre 2 desconocidos.

Ambas personas deberán ser obtenidas a través de la API [Random User](https://randomuser.me/).

<div align="center"><img src="./src/assets/img/image.png"> </div>

La aplicación debe cumplir lo siguiente:

-   Cada persona deberá poder enviar un nuevo mensaje al chat definiendo el contenido textual y un color representativo.
-   El chat que se visualiza al centro debe ser un componente hijo que se encargue de exponer todos los mensajes indicando el nombre del propietario en cada uno.
-   Apenas se cargue la aplicación, deberán cargarse 2 personas completamente aleatorias obtenidas por la API Random User.

## Requerimientos

1. Utilizar Axios para el consumo de datos de la API Random User.
2. Usar el ciclo de vida de los componentes para obtener la información de los usuarios al cargar la aplicación.
3. Utilizar los eventos para agregar las interacciones que permitan el registro de nuevos mensajes de chat.
4. Hacer uso del style y/o class binding paar el direccionamiento y el color de fondo de los mensajes según corresponda a su propietario.

## Tecnologías utilizadas

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E) ![VueJS](https://img.shields.io/badge/Vue%20js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D) ![NPM](https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white) ![Axios](https://img.shields.io/badge/axios-671ddf?&style=for-the-badge&logo=axios&logoColor=white)
