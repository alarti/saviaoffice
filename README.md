# SaviaOffice PDF (Fork)

> **Autor del Fork / Maintainer:** Alberto Arce Rodríguez ([@alarti](https://github.com/alarti))  
> **Licencia:** Apache-2.0 (conforme al proyecto original)

---

## 📌 Descripción

**SaviaOffice PDF** es una aplicación de escritorio multiplataforma (Windows, macOS, Linux) de alto rendimiento centrada exclusivamente en la **edición real y visualización avanzada de documentos PDF**.

Este proyecto es un **fork independiente** enfocado en desacoplar y potenciar la subaplicación de PDF del proyecto original [GenOffice](https://github.com/genspark-ai/genoffice), optimizando la distribución para un paquete ligero, rápido y especializado.

---

## 🚀 Características Principales

- **Edición real de texto en PDF**: Selección a nivel de párrafo con reflujo dinámico (*reflow*), preservación de fuentes originales y sin trucos de capas opacas.
- **Manipulación de contenido**: Inserción y edición de imágenes mediante reescritura de streams con *PDFium WASM*.
- **Herramientas de Anotación y Formularios**: Soporte completo para notas, resaltado, sellos, firmas digitales y formularios interactivos (`pdf.js` + `pdf-lib`).
- **Conversión Local y OCR**: Conversión directa de PDF a Word (`.docx`) y reconocimiento óptico de caracteres (OCR nativo en Windows/macOS).

---

## 💻 Requisitos Previos

- **Node.js**: v20 o superior
- **pnpm**: v8 o v9 (recomendado) o npm
- **Git**

---

## 📦 Instalación y Desarrollo Local

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/alarti/saviaoffice.git
   cd saviaoffice
   git checkout pdf-only-fork
   ```

2. **Instalar dependencias:**
   ```bash
   pnpm install
   ```

3. **Ejecutar en modo desarrollo:**
   ```bash
   cd apps/pdf
   pnpm run dev
   ```

---

## 🪟 Generación del Instalador para Windows

Para compilar y empaquetar el instalador `.exe` (NSIS) para Windows:

```bash
# Compilar el paquete de PDF para Windows
pnpm --filter ./apps/pdf build
pnpm --filter ./apps/pdf exec electron-builder --win --x64
```

El instalador generado se ubicará en:
`apps/pdf/dist/` (por ejemplo, `SaviaOffice-PDF-Setup.exe`).

---

## 🔄 Compatibilidad y Actualizaciones de Seguridad con Upstream

Al ser un fork de [genspark-ai/genoffice](https://github.com/genspark-ai/genoffice), puedes sincronizar parches de errores y seguridad siguiendo este flujo:

1. **Configurar el remoto upstream:**
   ```bash
   git remote add upstream https://github.com/genspark-ai/genoffice.git
   git fetch upstream
   ```

2. **Aplicar parches específicos a la app PDF:**
   ```bash
   # Para traer un commit específico de seguridad o bugfix
   git cherry-pick <commit-hash>
   ```

---

## ⚖️ Aviso Legal y Atribución

Este proyecto es un trabajo derivado distribuido bajo la licencia **Apache 2.0**.
- **Autor y Mantenedor del Fork:** Alberto Arce Rodríguez.
- **Código Base Original:** [GenOffice](https://github.com/genspark-ai/genoffice), creado y publicado por Genspark (MainFunc.ai).
- Consulta los archivos `LICENSE` y `NOTICE` en la raíz para ver los términos completos y las atribuciones a librerías de terceros (PDFium, pdf.js, pdf-lib, etc.).
