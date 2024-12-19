# Tiendas Fiso

## Requerimientos
- Crear un E-commerce para la tienda física.
  - **API independiente para este servicio**
  - [Tienda similar a la que se quiere](https://www.soccer.com/)
- Crear un Dashboard que permita la gestión de productos, etc...
<!--  - Se usará un template [Sakai-PrimeVue](https://sakai.primevue.org/#/?af_id=4218) -->
- Crear una web para la liga
  - **API independiente para este servicio**
  - [página actual de ligas](https://consola.zione.com.mx/rol.juegos.asp?dts=DTS543&m=1)
  - [KingCup Las Vegas](https://kingcup.vegas/)
  - Está página tiene que tener una membresía mensual en la que te permite principalmente obtener descuentos en el ecommerce y algunas cosas exclusivas dentro de la página.
- App Mobile de la liga

> [!NOTE]
> Está app Mobile, se planteará en un inicio como una PWA, si el cliente no quiere una PWA, se optará por Ionic o Flutter.

## Tecnologías

### E-commerce y Ligas

- Vue
- Typescript
- Pinia
- TailwindCSS
- Vue-Router
- Stripe

> [!NOTE]
> La web de ligas es un proyecto separado que se hará a partir de un template de PWA, para seguir usando Vue. En dado caso se quiera una app nativa se agregara a la lista de tecnologías Ionic o Flutter.

### Dashboard

- Vue
- Prime Vue

### APIs

- Rust -> Actix
- Postgres

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

- $150,000

- [ ] Diseño (5-10 pantallas, diseño funcional y simple)
- [ ] Autentificación y autorización.
    - Login
    - Register
    - Recover Password

#### Tareas completas, tanto como frontend y backend.

- [ ] Landing Page.
- [ ] Página de información (Acerca de, Contacto, Servicios).
- [ ] Carrito de compras y pagos.
- [ ] Productos
    - Página de productos
    - Filtros
    - Recomendaciones

##### Dashboard

- [ ] Diseño (5-10 pantallas, diseño funcional y simple)

Es el panel de adminsitración

- [ ] CRUD básico (Adminsitración de productos, usuarios y noticias)
- [ ] Mostrar estadisticas (Producto más vendido, ingresos, etc...)

### Ligas

- [ ] Diseño (5-10 pantallas, diseño funcional y simple)

#### Tareas completas, tanto como frontend y backend.

- [ ] Página de listado de jugadores
    - Básico:
    - Avanzado:
        - Incluye filtros dinámicos, búsqueda avanzada y ranking en tiempo real.
        - Estadísticas visuales con gráficos o tablas interactivas.
- [ ] Página de blog o noticias
- [ ] Página de perfil de usuario
- [ ] Página de accesos directos (selección de jugadores por posición)

## Conceptos mensuales o cotizaciones externas

### VPS

#### DigitalOcean

#### Hostinger

Hostinger nos ofrece diferentes VPS:

| **Plan**  | **Precio (MX$)**    | **Precio al renovar (MX$)** | **vCPU**  | **RAM** | **Espacio NVMe** | **Ancho de banda** | **Centros de datos** | **Sistema operativo** |
|-----------|---------------------|-----------------------------|-----------|---------|------------------|--------------------|----------------------|-----------------------|
| **KVM 1** | 90.99 (Ahorra 61%)  | 151.99                      | 1 núcleo  | 4 GB    | 50 GB            | 4 TB               | En todo el mundo     | Linux                 |
| **KVM 2** | 124.99 (Ahorra 59%) | 201.99                      | 2 núcleos | 8 GB    | 100 GB           | 8 TB               | En todo el mundo     | Linux                 |
| **KVM 4** | 184.99 (Ahorra 66%) | 436.99                      | 4 núcleos | 16 GB   | 200 GB           | 16 TB              | En todo el mundo     | Linux                 |
| **KVM 8** | 335.99 (Ahorra 70%) | 873.99                      | 8 núcleos | 32 GB   | 400 GB           | 32 TB              | En todo el mundo     | Linux                 |

Y nos ofrece diferentes tiempos de contratación con un mismo precio:

- 1 mes
- 12 meses
- 24 meses

Si tomamo el paquete **KVM 2** a un plazo de **24 meses** nos da un subtotal de: **$2,999.76 MXN**

> [!NOTE]
> Este subtotal no incluye impuestos

### Dominio

#### Hostinger

Hostinger ofrece un servicio de dominios, `.com`, `.io`, `.online`, etc...

El dominio `https://tiendasfiso.com` en Hostinger cuesta:

> [!NOTE]
> Este subtotal no incluye impuestos

- Por un plazo de 1 año: **$176.99 MXN**.
- Por un plazo de 2 años: **$399.98 MXN**.
- Por un plazo de 3 años: **$699.97 MXN**.

### Cloudflare

Este servicio lo utilizariamos para manejar la seguridad y subdominios, para los diferentes servicios.

#### Ejemplo

- Dominio: `https://tiendasfiso.com`
- Subdominios:
    - Ligas: `https://liga.tiendasfiso.com`
    - Dashboard: `https://dashboard.tiendasfiso.com`

### Stripe

**Tarifa estándar de Stripe en México**

- **3.6%** + **$3.00 MXN** por transacción exitosa.

#### Ejemplo

Si el cliente realiza una compra de **$1,000 MXN** el calculo seria:

1. **3.6%** de **$1,000 MXN** es **$36 MXN**.
2. **Tarifa fija** de **$3 MXN**.
3. **Total descontado** de **$39 MXN**.

El comerciante recibira:

**$1,000 MXN** - **$39 MXN** = **$961 MXN**

