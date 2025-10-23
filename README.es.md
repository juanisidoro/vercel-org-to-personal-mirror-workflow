# 💡 Vercel Org to Personal Mirror Workflow

**Mantén tus despliegues de Vercel activos, incluso si tu código está en una organización de GitHub.**

Este Workflow de GitHub crea un **mirror automático** entre tu repositorio de organización y un **repositorio personal**, permitiendo que Vercel (u otra plataforma CI/CD) despliegue sin las restricciones del plan gratuito.

---

## 🚀 Qué hace

Cada vez que haces `push` a `main` o `develop`:

1️⃣ Clona el repositorio de la organización  
2️⃣ Hace push de la misma rama al repositorio personal (el “mirror”)  
3️⃣ Vercel detecta el cambio y despliega automáticamente  

⏱️ En unos 15 segundos sincroniza + 2–3 minutos de build = deploy listo ✅

---

## ⚙️ Cómo configurarlo

1. Crea un **repositorio personal vacío** en tu cuenta de GitHub.  
2. Genera un **Personal Access Token (PAT)** con permisos `repo`.  
3. En tu **repositorio de organización**, ve a:  
   **Settings → Secrets and variables → Actions → New repository secret**  
   Añade:
   - `PERSONAL_REPO_PAT` → tu token  
   - `PERSONAL_REPO_URL` → ej. `https://github.com/tuusuario/repo-mirror.git`
4. Copia [`vercel-org-to-personal-mirror.yml`](.github/workflows/vercel-org-to-personal-mirror.yml) en:
   ```
   .github/workflows/
   ```
5. Haz push a `main` o `develop` → el mirror se sincroniza automáticamente 🚀

---

## 🎯 Ideal para

- ✅ Usuarios de Vercel en plan gratuito  
- ✅ Repositorios dentro de organizaciones  
- ✅ Evitar configuraciones complejas de CI/CD  

---

## 🔐 Secrets necesarios

| Secret | Descripción |
|--------|--------------|
| `PERSONAL_REPO_PAT` | Token personal con permiso `repo` |
| `PERSONAL_REPO_URL` | URL HTTPS del repositorio personal |

---

## 🧠 Por qué existe

Vercel no permite conectar repositorios de organizaciones en planes gratuitos.  
Este flujo es una **solución sencilla y automatizada**: crea un espejo en tu cuenta personal y deja que Vercel despliegue como siempre.

---

## 📜 Licencia

[MIT License](LICENSE) — libre para usar, modificar y compartir con atribución.

---

👨‍💻 Creado por [@juanisidoro](https://github.com/juanisidoro)  
🔗 Proyecto: **Vercel Org to Personal Mirror Workflow**
