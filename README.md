# Tiendas Fiso

## Requerimientos
1. Crear un E-commerce para la tienda física.
1.1 **API independiente para este servicio**
1.2 [Tienda similar a la que se quiere](https://www.soccer.com/)
2. Crear un Dashboard que permita la gestión de productos, etc...
2.1 Se usará un template [Sakai-PrimeVue](https://sakai.primevue.org/#/?af_id=4218)
3. Crear una web para la liga
3.1 **API independiente para este servicio**
3.2 [página actual de ligas](https://consola.zione.com.mx/rol.juegos.asp?dts=DTS543&m=1)
3.3 [KingCup Las Vegas](https://kingcup.vegas/)
3.4 Está página tiene que tener una membresía mensual en la que te permite principalmente obtener descuentos en el ecommerce y algunas cosas exclusivas dentro de la página.
4. App Mobile de la liga

> [!NOTE]
> Está app Mobile, se planteará en un inicio como una PWA, si el cliente no quiere una PWA, se optará por Ionic o Flutter.

## Tecnologías

### E-commerce y Ligas

1. Vue
2. Typescript
3. Pinia
4. TailwindCSS
5. Vue-Router
6. Stripe

> [!NOTE]
> La web de ligas es un proyecto separado que se hará a partir de un template de PWA, para seguir usando Vue. En dado caso se quiera una app nativa se agregara a la lista de tecnologías Ionic o Flutter.

### Dashboard

1. Vue
2. Prime Vue

### APIs

1. Rust -> Actix
2. Postgres

## GIT

Se usará la organización ya creada [NexOrbs](https://github.com/nexorbs) con un repositorios privado para el desarrollo de los servicios requeridos.

```txt
📦TiendasFiso
 ┣ 📂ecommerce
 ┣ 📂dashboard
 ┣ 📂ligas
 ┣ 📂mobile            <- Solo si es app nativa
 ┣ 📂backend_ligas
 ┗ 📂backend_ecommerce
```

> [!TIP]
> Sería ideal que el código se mueva a una cuenta en específico del cliente para que el se quede con el código.

### Plataforma

Se optó por usar [github.com](https://github.com) por sus beneficios en el plan gratuito.

Véase en el [pricing](https://docs.github.com/es/get-started/learning-about-github/githubs-plans)

### GIT FLOW

```mermaid
gitGraph
    commit
    branch develop
    checkout develop
    commit
    branch feature
    commit
    commit
    commit
    checkout develop
    merge feature
    checkout main
    merge develop
```

Podemos ver que el flujo de trabajo de GitFlow se divide en las siguientes ramas:

- **main**: Es producción.
- **develop**: Contiene el código en desarrollo.
- **feature**: Contiene las nuevas funcionalidades que se están desarrollando.

Un ejemplo de una rama de Feature sería:

`feature/backend/create-products`

- `feature`: Indica que es una rama de una nueva funcionalidad.
- `backend`: Indica que es una funcionalidad de backend.
- `create-products`: Es el nombre de la tarea.

## Desglose de actividades

### Ecommerce

### Ligas

### Mobile
