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


## 📬 Contacto

Roger Tumiri Quispe · La Paz, Bolivia  
📧 rogertumirideveloped@gmail.com  
🔗 [linkedin.com/in/roger-tumiri](https://linkedin.com/in/roger-tumiri)  
💻 [github.com/RogerTumiri](https://github.com/RogerTumiri)
