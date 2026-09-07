# m23 · Menús AR

Plataforma SaaS multi-tenant de **menús digitales con Realidad Aumentada (WebAR)** para restaurantes.

Marca: **m23** · White-label total (subdominio de plataforma o dominio propio del local, ej. `kokepollo.cl`).

## Características

- **3 interfaces**
  - Super Admin (+ soporte)
  - Panel del restaurante (self-service)
  - Menú público 100 % white-label
- **Login**: Google · Apple · Email/contraseña (Supabase Auth)
- **AR / 360°**: `@google/model-viewer` (WebXR, AR Quick Look, Scene Viewer)
- **Dominios**
  - Subdominio: `restaurante.tudominio.com`
  - Dominio propio del cliente: `kokepollo.cl` (CNAME + verificación)
- **Cloudflare**: wildcard DNS, Custom Hostnames, WAF, SSL
- **Automatización 3D**: foto/video → modelo GLB/USDZ

## Previews (HTML estático)

| Archivo | Descripción |
|---------|-------------|
| [previews/login.html](previews/login.html) | Pantalla de inicio de sesión (branding m23) |
| [previews/menu-koke-pollo.html](previews/menu-koke-pollo.html) | Ejemplo de menú público white-label + botón AR |

Abre los HTML en el navegador (el logo m23 va embebido en el login).

## Documentación técnica

Ver carpeta [`docs/`](docs/) (esqueleto de arquitectura, schema, roadmap).

## Stack previsto

- Next.js 15 (App Router) + TypeScript + Tailwind + shadcn/ui
- Supabase (Auth, PostgreSQL + RLS, Storage)
- `@google/model-viewer`
- Cloudflare (proxy, wildcard, Custom Hostnames)
- Jobs 3D: Inngest / APIs IA (Meshy, Tripo) o fotogrametría

## Estructura prevista del código

```
app/
  (auth)/login/
  (superadmin)/admin/
  (restaurant)/dashboard/
  (public-menu)/          # white-label por Host
  middleware.ts           # resuelve tenant por subdomain | custom_domain
  api/
components/
  model-viewer.tsx
  ar-preview-modal.tsx
  custom-domain-setup.tsx
lib/
  tenants.ts
  domains.ts
  supabase/
supabase/migrations/
```

## Estado

Proyecto en fase de diseño y esqueleto. Previews de UI y documento técnico listos para arrancar el desarrollo en local.

## Licencia

Privado / uso del propietario del repositorio (m23).
