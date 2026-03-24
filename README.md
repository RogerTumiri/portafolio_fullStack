# 🚀 Portfolio Roger Tumiri Quispe

Portafolio profesional construido con **Next.js 14 + TypeScript + PostgreSQL + Prisma**.

---

## 📦 Stack tecnológico

| Capa | Tecnología |
|------|-----------|
| Frontend | Next.js 14 (App Router), React 18, TypeScript |
| Estilos | Tailwind CSS |
| Backend | API Routes (Next.js) |
| ORM | Prisma |
| Base de datos | PostgreSQL |
| Validación | Zod + React Hook Form |
| Deploy | Vercel |

---

## ⚡ Inicio rápido

### 1. Clonar e instalar

```bash
git clone <tu-repo>
cd portfolio
npm install
```

### 2. Configurar variables de entorno

```bash
cp .env.example .env.local
# Edita .env.local con tu DATABASE_URL
```

### 3. Configurar PostgreSQL (local)

```bash
# Opción A: Docker (recomendado)
docker run --name portfolio-db -e POSTGRES_PASSWORD=password -e POSTGRES_DB=portfolio_db -p 5432:5432 -d postgres:16

# Opción B: PostgreSQL instalado localmente
createdb portfolio_db
```

### 4. Ejecutar migraciones y seed

```bash
# Generar cliente Prisma
npm run db:generate

# Crear tablas en la BD
npm run db:migrate

# Poblar con datos iniciales (¡importante!)
npm run db:seed
```

### 5. Levantar en desarrollo

```bash
npm run dev
# → http://localhost:3000
```

---

## 🗄️ Estructura del proyecto

```
portfolio/
├── prisma/
│   ├── schema.prisma        # Modelos de BD
│   └── seed.ts              # Datos iniciales
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   ├── contact/     # POST /api/contact
│   │   │   ├── projects/    # GET /api/projects
│   │   │   └── technologies/# GET /api/technologies
│   │   ├── projects/        # Página de proyectos
│   │   ├── contact/         # Página de contacto
│   │   ├── layout.tsx       # Layout raíz (SEO, fuentes)
│   │   └── page.tsx         # Página principal
│   ├── components/
│   │   ├── layout/          # Navbar, Footer
│   │   ├── sections/        # Hero, About, ContactForm, ProjectCard
│   │   └── ui/              # Badge, Button, Toast, SectionTitle
│   ├── lib/
│   │   ├── prisma.ts        # Singleton Prisma
│   │   ├── utils.ts         # Helpers (cn, sanitize, formatDate)
│   │   └── validations.ts   # Schemas Zod
│   └── types/
│       └── index.ts         # Tipos globales TypeScript
├── .env.example             # Variables de entorno (sin valores reales)
├── next.config.ts           # Configuración Next.js + headers seguridad
├── tailwind.config.ts       # Configuración Tailwind
└── vercel.json              # Config deploy Vercel
```

---

## 🌐 Deploy en Vercel

### Opción recomendada: Neon (PostgreSQL serverless gratis)

1. Crea una cuenta en [neon.tech](https://neon.tech)
2. Crea un proyecto → obtén la `DATABASE_URL`
3. En [vercel.com](https://vercel.com):
   - Import your Git repository
   - En **Environment Variables** agrega:
     ```
     DATABASE_URL=postgresql://...tu-url-de-neon...
     NEXT_PUBLIC_SITE_URL=https://tu-dominio.vercel.app
     ```
4. Deploy → Vercel ejecuta `prisma generate && prisma migrate deploy && next build` automáticamente

### Alternativas de BD gratuitas
- **Supabase** → supabase.com (PostgreSQL + extras)
- **Railway** → railway.app (muy fácil)
- **Aiven** → aiven.io

---

## 🔒 Seguridad implementada

- ✅ Validación server-side con Zod
- ✅ Sanitización de inputs (elimina `<>`, limita longitud)
- ✅ Rate limiting básico en `/api/contact` (5 req / 15 min por IP)
- ✅ Headers HTTP de seguridad (X-Frame-Options, CSP, etc.)
- ✅ Variables de entorno → credenciales nunca en el código
- ✅ No se expone información sensible en respuestas de API
- ✅ `.gitignore` excluye todos los `.env`

---

## 📝 Scripts disponibles

```bash
npm run dev              # Servidor de desarrollo
npm run build            # Build de producción
npm run start            # Inicia servidor de producción
npm run db:generate      # Genera cliente Prisma
npm run db:migrate       # Crea/aplica migraciones (desarrollo)
npm run db:migrate:prod  # Aplica migraciones (producción)
npm run db:seed          # Pobla la BD con datos iniciales
npm run db:studio        # Abre Prisma Studio (GUI para la BD)
```

---

## ✅ Checklist para producción

- [ ] `DATABASE_URL` de producción configurada en Vercel
- [ ] `NEXT_PUBLIC_SITE_URL` apuntando a tu dominio
- [ ] `npm run db:seed` ejecutado en la BD de producción
- [ ] Revisar que `.env` y `.env.local` estén en `.gitignore`
- [ ] Verificar que el formulario de contacto guarda en BD
- [ ] Comprobar SEO: meta tags en cada página
- [ ] Probar en móvil (responsive)
- [ ] Lighthouse score > 90

---

## 📬 Contacto

Roger Tumiri Quispe · La Paz, Bolivia  
📧 rogertumirideveloped@gmail.com  
🔗 [linkedin.com/in/roger-tumiri](https://linkedin.com/in/roger-tumiri)  
💻 [github.com/RogerTumiri](https://github.com/RogerTumiri)
