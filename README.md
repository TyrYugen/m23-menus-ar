# m23 · Menús AR

Plataforma SaaS multi-tenant de **menús digitales con Realidad Aumentada (WebAR)** para restaurantes.

Marca: **m23** · White-label (subdominio o dominio propio del local, ej. `kokepollo.cl`).

## GitHub Pages (previews en vivo)

Cuando actives Pages (Settings → Pages → Branch: `main` / folder: `/ (root)`), la URL base será:

**https://tyryugen.github.io/m23-menus-ar/**

| Página | URL |
|--------|-----|
| Inicio (índice) | https://tyryugen.github.io/m23-menus-ar/ |
| Login | https://tyryugen.github.io/m23-menus-ar/previews/login.html |
| Super Admin | https://tyryugen.github.io/m23-menus-ar/previews/super-admin.html |
| Panel restaurante (Koke Pollo) | https://tyryugen.github.io/m23-menus-ar/previews/restaurant-admin.html |
| Menú público white-label | https://tyryugen.github.io/m23-menus-ar/previews/menu-koke-pollo.html |

### Activar GitHub Pages (1 minuto)

1. Abre https://github.com/TyrYugen/m23-menus-ar/settings/pages  
2. **Source**: Deploy from a branch  
3. **Branch**: `main` → folder `/ (root)` → **Save**  
4. Espera 1–2 minutos y abre las URLs de arriba.

## Interfaces en el repo

- `index.html` — hub de previews
- `previews/login.html` — Google / Apple / Email (branding m23)
- `previews/super-admin.html` — dashboard global, restaurantes, 3D, soporte
- `previews/restaurant-admin.html` — panel del cliente (Koke Pollo)
- `previews/menu-koke-pollo.html` — menú público + AR

## Stack previsto

Next.js 15 · Supabase · model-viewer · Cloudflare · Jobs 3D

## Docs

[docs/ARQUITECTURA.md](docs/ARQUITECTURA.md)
