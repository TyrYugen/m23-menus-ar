# Arquitectura · m23 Menús AR

Documento resumido del esqueleto técnico (v1.3).

## Interfaces

1. **Super Admin** — Alta de restaurantes, subdominios, dominios personalizados, soporte, moderación 3D.
2. **Panel Restaurante** — CRUD menú, subida foto/video, generación 3D, QR, configuración de dominio propio.
3. **Menú público white-label** — Solo marca del restaurante. URL: subdominio de plataforma o dominio propio (`kokepollo.cl`).

## Auth

- Google OAuth
- Apple Sign in
- Email + contraseña (registro, login, recuperación)

Proveedor: Supabase Auth. Redirección según `profiles.role` (`superadmin` | `restaurant_admin`).

## Dominios white-label

| Tipo | Ejemplo | DNS |
|------|---------|-----|
| Subdominio plataforma | `kokepollo.tudominio.com` | Wildcard `*.tudominio.com` |
| Dominio propio | `kokepollo.cl` | CNAME del cliente + Custom Hostnames (Cloudflare for SaaS) / Vercel Domains |

Middleware de Next.js resuelve el tenant por header `Host` (`subdomain` o `custom_domain`).

## Stack

- Next.js 15 + TypeScript + Tailwind + shadcn/ui
- Supabase (PostgreSQL + RLS + Storage + Auth)
- `@google/model-viewer` (AR + 360°)
- Cloudflare (WAF, SSL, CDN, Custom Hostnames)
- Jobs 3D: Inngest / Meshy / Tripo / fotogrametría

## Tablas clave

- `profiles` — role, nombre
- `restaurants` — subdomain, custom_domain, custom_domain_status
- `categories`, `dishes` — menú + URLs GLB/USDZ
- `support_tickets`
- `domain_verifications`

## Roadmap (resumen)

0. Setup → 1. Auth → 2. Super Admin + subdominios → 3. Middleware multi-tenant → 4. Panel restaurante → 5. Dominios personalizados → 6. Pipeline 3D → 7. AR → 8. Página pública → 9. Cloudflare → 10. Polish

## Previews

Ver carpeta `/previews` en este repositorio.
