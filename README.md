# Monorepo trabajo1 (web + backend)

## Estructura

```
trabajo1/
  apps/
    web/            # Frontend Vue + Vite
  backend/          # API Express (TypeScript)
  package.json      # Raíz con npm workspaces
```

## Requisitos

- Node 20+ (o 22+)
- npm 9+

## Instalación

```sh
npm install
```

## Variables de entorno

Configura la clave de Google Maps para el frontend:

1) Crea un archivo `apps/web/.env` con el contenido:

```
VITE_GOOGLE_MAPS_API_KEY=AIzaSyAkSbDeUcXH-TJMoDrKpgU4g9HYTOMU1r0
```

2) La clave debe tener habilitada la "Maps JavaScript API", facturación activa y permitir `http://localhost:*`.

## Desarrollo

- Front y API simultáneos:

```sh
npm run dev
```

- Solo web:

```sh
npm -w @repo/web run dev
```

- Solo backend (desarrollo con ts-node/nodemon):

```sh
npm -w @repo/backend run dev
```

## Build

```sh
npm run build
```

## Lint

```sh
npm run lint
```

## Producción backend

```sh
npm -w @repo/backend run build
npm -w @repo/backend run start:prod
```
