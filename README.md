---
layout: pagina
title: Facturación Electrónica
permalink: /
canonical_url: https://schema.coderic.net/
sitemap: false
---

## ¿Qué estamos haciendo?
Hemos comprendido que existe la necesidad de integración entre las plataformas de comercio electrónico y los proveedores de integración, por lo que hemos dispuesto desarrollar los módulos de facturación electrónica para todas las aplicaciones de software libre que puedan integrarse con los distintos proveedores de facturación electrónica.

Entendemos que desarrollar un módulo de facturación electrónica para cada una de las aplicaciones es un trabajo complejo, y que requiere de un equipo significativo, lo que nos lleva al hecho de que es absurdo que cada proveedor tecnológico deba desarrollar el mismo módulo, cuando todas tienen entre sí, las mismas necesidades. 

El asunto de la facturación electrónica será una tendencia reglamentaria que será una necesidad internacional, por lo que esta necesidad no se limita a Colombia, sino a muchos países.
La naturaleza de este tipo de integración es que sea de software libre, por varios motivos, el primero es que hay mucho trabajo y muchas variantes según cada proveedor tecnológico, y según cada nación, lo que hace que el trabajo complejo, además de las variantes del tipo de software a integrar y asuntos de internacionalización.

Esto nos lleva a la necesidad de establecer un núcleo central de integración y desarrollo. Nosotros Coderic, no nos dedicamos a la facturación, ni nos dedicamos a comercializar módulos, nosotros nos dedicamos a crear ecosistemas tecnológicos, como este, lo cual permite que podamos desarrollar software libre y accesible, al alcance de todos, desde una posición neutral. Tal como lo enuncia la misión de Coderic Ecosistemas:

>Nuestros ecosistemas tecnológicos son nuestra exposición al mundo de lo que hacemos ofreciendo herramientas e integración al alcance de todos.

No nos lucramos de ello, por el contrario, utilizamos los recursos desarrollados entre todos. Nuestro papel respecto a esta necesidad (y otras relacionadas) es la integración y el desarrollo de ingeniería de software.

Es un placer, para mi, y un honor, extenderle una invitación a ser parte de nuestro proyecto, y a beneficiarse de la tecnología que estaremos desarrollando, en un marco de cooperación y participación activa, para establecer un desarrollo inteligente, sostenible y estable que pueda satisfacer la necesidad del mercado que demanda sus productos servicios que estén relacionados con el trabajo que estaremos haciendo.

Así mismo sus desarrolladores podrán proponer ideas y cambios, que nos ayuden a mejorar las aplicaciones que estaremos desarrollando, así como los desarrolladores de las demás empresas participantes, lo cual nos dará una fuerza de desarrollo realmente significativa. Desde una posición neutral respecto al "negocio" de la facturación electrónica (ya que nosotros no proveemos servicios de facturación electrónica), permítame expresarle el requerimiento necesario para la integración con los sistemas que estaremos desarrollando.

A Continuación lo que necesitamos a nivel de desarrollo para desarrollar la integración:
- EndPoint de Producción
- EndPoint de Sandbox
- Tipo de Autenticación (Ejemplo: OAuth, OAuth2, Bearer Token, Basic Auth, HTTP)
- Documentación

Por ejemplos:

- EndPoint de Producción: [https://endpoint.example.com/api/v1](https://endpoint.example.com/api/v1)
- EndPoint de Sandbox: [https://test.endpoint.example.com/api/v1](https://test.endpoint.example.com/api/v1)
- Tipo de Autenticación: Bearer Token
- Documentación: [https://docs.example.com/api/index.html](https://docs.example.com/api/index.html)
## ¿Cómo funcionará la integración?
Disponemos un portal de desarrollo, dentro de github, [https://github.com/CodericEcosystem/](https://github.com/CodericEcosystem/)

Accesible desde la siguiente dirección:
[https://schema.coderic.net/](https://schema.coderic.net/)

Dentro existe el proyecto de facturación en cuestión [https://github.com/CodericEcosystem/Billing](https://github.com/CodericEcosystem/Billing) el cual será la puerta de enlace desde dónde los módulos podrán descargar el esquema de configuración de cada uno de los proveedores tecnológicos.

Para esto hemos creado un esquema modelo, y crearemos uno por cada versión. Es natural que con el paso del tiempo la tecnología con la que interactúan los módulos avance y deba ser distinta la integración. Por ejemplo, en un principio se estaba desarrollando un sólo método de autenticación el Bearer Token, pero al conocer que hay algunos proveedores tecnológicos han elegido utilizar otros métodos de autenticación, entre ellos el OAuth2, por lo cuál hemos tenido que reescribir nuestro código para poder integrarlo, es muy simple reescribir el código que tenemos sobre la mesa, pero no lo es cuando ya cientos o miles de aplicaciones ya tengan instalados los módulos. pues por eso es tan necesario el versionado.

Vayamos al siguiente paso.
En la siguiente dirección crearemos el directorio de proveedor.
[https://github.com/CodericEcosystem/Billing/tree/master/Providers](https://github.com/CodericEcosystem/Billing/tree/master/Providers)
El cual será accesible desde los módulos al invocar el nombre del proveedor.
Como por ejemplo:
- [https://schema.coderic.net/Billing/Providers/Example/v1/schema.json](https://schema.coderic.net/Billing/Providers/Example/v1/schema.json)
- [https://github.com/CodericEcosystem/Billing/blob/master/Providers/Example/v1/schema.json](https://github.com/CodericEcosystem/Billing/blob/master/Providers/Example/v1/schema.json)
