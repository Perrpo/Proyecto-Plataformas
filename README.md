<<<<<<< HEAD
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
=======
# Food Donation App

## Overview
The Food Donation App is a web application designed to facilitate the donation of food items that are nearing their expiration date. It connects donors, such as individuals and organizations, with NGOs and consumers who can benefit from these food items. The application consists of a backend built with Node.js and Express, and a frontend developed using Vue.js.

## Features
- **User Authentication**: Users can register and log in to the application.
- **Product Dashboard**: A dashboard that displays a list of food items that are close to expiration.
- **Donation and Discount Options**: Users can choose to donate food items or apply discounts to encourage quick sales.
- **Map of Collection Points**: A map view that shows nearby NGOs or consumers who can collect the donated food.
- **Notifications Panel**: Alerts users about inventory levels and expiration dates of products.

## Project Structure
```
food-donation-app
├── backend
│   ├── src
│   │   ├── controllers
│   │   │   └── productsController.ts
│   │   ├── routes
│   │   │   └── productsRoutes.ts
│   │   ├── models
│   │   │   └── product.ts
│   │   └── app.ts
│   ├── package.json
│   └── tsconfig.json
├── frontend
│   ├── src
│   │   ├── components
│   │   │   ├── Login.vue
│   │   │   ├── Register.vue
│   │   │   ├── Dashboard.vue
│   │   │   ├── ProductList.vue
│   │   │   ├── DonateButton.vue
│   │   │   ├── DiscountButton.vue
│   │   │   ├── MapView.vue
│   │   │   └── NotificationsPanel.vue
│   │   ├── App.vue
│   │   └── main.ts
│   ├── package.json
│   └── tsconfig.json
└── README.md
```

## Getting Started

### Prerequisites
- Node.js
- npm (Node Package Manager)
- Vue CLI (for frontend development)

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/food-donation-app.git
   cd food-donation-app
   ```

2. Install backend dependencies:
   ```
   cd backend
   npm install
   ```

3. Install frontend dependencies:
   ```
   cd frontend
   npm install
   ```

### Running the Application

1. Start the backend server:
   ```
   cd backend
   npm start
   ```

2. Start the frontend application:
   ```
   cd frontend
   npm run serve
   ```

### Usage
- Navigate to `http://localhost:8080` to access the frontend application.
- Use the login or registration forms to create an account or log in.
- Access the dashboard to view products and manage donations.

## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any enhancements or bug fixes.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
>>>>>>> 9e85581c41eb0594215053e95c34b6bb5982f86f
