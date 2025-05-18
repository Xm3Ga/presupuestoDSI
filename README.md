# Costes y límites de aplicación formularios DSI-Ex

Límites de uso (cuotas) y posibles costes de servicio para el **backend** (Google Apps Script) y el **frontend** (GitHub Pages) de la aplicación.

---

## TL;DR

| Servicio               | Limite Plan gratuito               | Plan de pago                          |
| ---------------------- | -----------------------------------| ------------------------------------- |
| Google Apps Script     | **12.960.000 solicitudes/día**     | Google Workspace desde **4,68 €/mes** |
| GitHub Pages           | **416.666 descargas/día**          | GitHub Pro **4 €/mes**                |

---

## 1. Google Apps Script (Backend)

### 1.1 Cuotas de ejecución (Cuenta gratuita)

* **Tiempo de ejecución por llamada**: hasta 6 minutos (360 segundos).

* **Ejecuciones simultáneas (por secuencia de comandos)**: hasta 1 000 instancias concurrentes.

* **Ejecuciones simultáneas (por usuario)**: hasta 30 instancias concurrentes.

* **Límite diario de tiempo de ejecución**: no hay un límite diario fijo para llamadas Web App (GET/POST).

* **Referencia oficial de cuotas**: [Documentación de cuotas de Google Apps Script](https://developers.google.com/apps-script/guides/services/quotas)

### 1.2 Cálculo de 50.000 usuarios/día

* **Total de solicitudes**: 50.000 GET + 50 000 POST = **100.000 solicitudes/día**.
* **Tasa media**: 100 000 solicitudes / 86.400 s ≈ **1,16 solicitudes/segundo**.
* **Margen de concurrencia**: con un límite de 30 ejecuciones concurrentes, tasa sostenible máxima = 30 / (tiempo medio de ejecución).
  * Si la ejecución media es ~0,2 s: tasa sostenible ≈ 150 solicitudes/s o **12.960.000 solicitudes/día** de capacidad.

---

## 2. GitHub Pages (Frontend)

### 2.1 Límites de sitio y repositorio (Cuenta gratuita)

* **Tamaño del repositorio**:

  * Tamaño recomendado: **1 GB**.
  * Límite por fichero: **100 MiB** (aviso a partir de 50 MiB).

* **Tamaño del sitio publicado**: **≤ 1 GB** en total.

* **Ancho de banda**: límite suave de **100 GB/mes**.

* **Referencia oficial de límites**: [Uso y límites de GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits)

### 2.2 Cálculo de 50.000 usuarios/día

* **Tamaño del HTML**: 8 kB de descarga por usuario.
* **Ancho de banda diario**: 50.000 × 8 kB = **400 MB/día**.
* **Ancho de banda mensual**: 400 MB × 30 ≈ **12 GB/mes**.
  * Para poder alcanzar el límite máximo: 100 GB / 8 kB = 12.500.000 descargas/mes ≈ **416.666 descargas/día**
