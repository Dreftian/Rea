<div align="center">

[English](docs/readme/README_en.md) · [简体中文](docs/readme/README_zh.md) · [繁體中文](docs/readme/README_zh-TW.md) · [日本語](docs/readme/README_ja.md) · [한국어](docs/readme/README_ko.md) · [Türkçe](docs/readme/README_tr.md) · [Русский](docs/readme/README_ru.md) · [Tiếng Việt](docs/readme/README_vi.md) · [ไทย](docs/readme/README_th.md) · [Deutsch](docs/readme/README_de.md) · **Español** · [Français](docs/readme/README_fr.md) · [Українська](docs/readme/README_uk.md) · [Polski](docs/readme/README_pl.md) · [Português (Brasil)](docs/readme/README_pt-BR.md) · [العربية](docs/readme/README_ar.md) · [فارسی](docs/readme/README_fa.md) · [Bahasa Indonesia](docs/readme/README_id.md) · [Italiano](docs/readme/README_it.md)
· [Ελληνικά](docs/readme/README_el.md) · [മലയാളം](docs/readme/README_ml.md) · [Roman Urdu](docs/readme/README_ur-Latn.md) · [Română](docs/readme/README_ro.md) · [Български](docs/readme/README_bg.md)

# REA: Ingeniería inversa de cualquier cosa

### Un solo MCP para ingeniería inversa de binarios, aplicaciones y comportamiento en ejecución.

**¿Ves una función que te gusta? Entiende cómo funciona, hasta el nivel binario.**

[![GitHub stars](https://img.shields.io/github/stars/morluto/rea?style=flat-square&logo=github)](https://github.com/morluto/rea/stargazers)
[![Monthly npm downloads](https://img.shields.io/npm/dm/rea-agents?style=flat-square&label=npm%20downloads)](https://www.npmjs.com/package/rea-agents)
[![MIT license](https://img.shields.io/badge/license-MIT-f4c430?style=flat-square)](LICENSE)
[![Join the REA Discord](https://img.shields.io/badge/Discord-5865F2?style=flat-square&logo=discord&logoColor=white)](https://discord.gg/GkcryMnJDM)
[![Follow REA on X](https://img.shields.io/badge/X-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/reatools)
[![Supported platforms: macOS, Windows, and Linux](https://img.shields.io/badge/macOS%20%7C%20Windows%20%7C%20Linux-4493F8?style=flat-square)](docs/getting-started/installation.md)
[![skills.sh](https://skills.sh/b/morluto/rea?style=flat-square)](https://skills.sh/morluto/rea/reverse-engineer-anything)

**[Sitio web](https://rea.tools/es/) · [Guías](https://rea.tools/es/guides/) · [Casos prácticos](https://rea.tools/es/showcase/)**

<a href="https://discord.com/invite/GkcryMnJDM"><img alt="Únete a la comunidad de REA en Discord" src="https://img.shields.io/badge/Join%20us%20on%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" height="40"></a>

[Inicio rápido](#inicio-rápido) · [Casos prácticos](#casos-prácticos) · [Cómo funciona REA](#cómo-funciona-rea) · [Qué puedes analizar](#qué-puedes-analizar) · [Crear entornos de RL](#build-rl-environments) · [Preguntas frecuentes](#preguntas-frecuentes) · [Documentación](#documentación)

<code>npx rea-agents setup</code>

</div>

> [!IMPORTANT]
> Obtén REA desde [morluto/rea](https://github.com/morluto/rea),
> [rea.tools](https://rea.tools/) o el [paquete npm rea-agents](https://www.npmjs.com/package/rea-agents).
> Sigue los enlaces de instalación y de versiones de estas fuentes oficiales. Un nombre
> de repositorio similar o un README copiado no demuestran que una descarga sea oficial.

<div align="center">

<br />

<img src="docs/assets/rea-hopper-analysis.png" alt="REA inicia su puente de análisis dentro de Hopper mientras inspecciona un binario nativo" width="1200" />

<br /><br />

<table aria-label="Comunidad REA">
<tr>
<td align="center" width="360">
  <a href="https://discord.gg/GkcryMnJDM">
    <img src="docs/assets/discord.svg" height="42" alt="Discord" /><br />
    <strong>Únete a la comunidad de ingeniería inversa</strong>
  </a><br />
  <sub>Discord · Preguntas y respuestas · Comparte tus resultados</sub>
</td>
</tr>
</table>

<br />

</div>

---

¿Viste una función en una aplicación que quieres incorporar a tu propio producto? Pídele a tu agente que la investigue con REA. Puede inspeccionar la aplicación sin su código fuente, explicar cómo funciona la función, mostrar la evidencia y crear una versión para tu proyecto.

REA conecta tu agente con herramientas para inspeccionar binarios nativos, aplicaciones JavaScript y Electron, ensamblados .NET y sitios web. También puedes usar las mismas herramientas desde tu terminal. El análisis se ejecuta localmente y los resultados incluyen la evidencia y las limitaciones que respaldan cada conclusión.

La configuración registra REA en tu agente e instala las instrucciones de flujo de trabajo correspondientes. El análisis nativo puede usar una instalación existente de Hopper, Ghidra, IDA o Kuna; la configuración puede instalar Hopper de forma opcional con tu aprobación. El análisis estático de JavaScript no necesita un motor de análisis nativo.

## Inicio rápido

**[Comienza en rea.tools](https://rea.tools/get-started/)** para ver instrucciones paso a paso según tu sistema operativo, agente y proveedor de análisis.

### Conecta tu agente (MCP)

Con [Node.js y npm](docs/reference/supported-targets.md) instalados, ejecuta este comando desde un directorio de confianza fuera del proyecto que planeas analizar.

```bash
npx rea-agents setup
```

Elige tu agente, revisa y aprueba el plan de configuración, y luego reinicia tu agente. La configuración hace una copia de seguridad de la configuración existente y agrega la conexión MCP de REA y la skill de investigación. Consulta la [guía de instalación](docs/getting-started/installation.md) para ver los clientes compatibles, los plugins, el registro manual y la solución de problemas.

Prueba preguntándole a tu agente:

```text
Entiende cómo funciona la búsqueda en la aplicación Notes, muéstrame la evidencia y crea
una función similar para mi proyecto.
```

Reemplaza Notes con tu aplicación objetivo y la función que quieres entender.

### Usa REA desde la terminal (CLI)

Inspecciona un directorio extraído de una aplicación JavaScript/Electron o un ASAR:

```bash
npx -y rea-agents@latest analyze-javascript-application /absolute/path/to/app --json
```

El resultado incluye módulos, importaciones, límites de Electron y su evidencia. Reemplaza la ruta con tu objetivo, por ejemplo `"D:/apps/example"` en Windows.

Para instalar el comando `rea` y usarlo de forma habitual:

```bash
npm install --global rea-agents
rea --help
```

Para el análisis nativo, configura un proveedor primero. La [guía de CLI y Evidence](docs/getting-started/cli.md) cubre la selección de proveedores, los comandos nativos, las capturas de estado y el uso en scripts. Para los requisitos previos de Linux, consulta la [guía de instalación](docs/getting-started/installation.md#linux-owned-process-prerequisite).

### Actualiza REA

Para una instalación global con npm o Bun, ejecuta el actualizador y sigue sus instrucciones de configuración.

```bash
rea update
```

Si usas `npx`, actualiza la configuración de tu agente con:

```bash
npx rea-agents@latest setup
```

Revisa los cambios de configuración y reinicia tu agente. Consulta las [instrucciones de actualización y desinstalación](docs/getting-started/installation.md#diagnose-update-and-remove) para ver las opciones del gestor de paquetes y la solución de problemas.

## Casos prácticos

<a href="https://rea.tools/showcase/">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/assets/rea-showcases-dark.svg" />
    <img alt="Ilustraciones de los casos de paneo de sonido de DX-Ball, el puente del portapapeles de Notion y el anillo de proyectiles de TH04" src="docs/assets/rea-showcases.svg" />
  </picture>
</a>

<table>
<tbody>
<tr>
<td>
<h3>DX-Ball: reconstruir un cálculo de paneo de sonido</h3>
<p>Recupera una función auxiliar que convierte la posición en paneo a partir de instrucciones x86 y verifica la reconstrucción en C contra 3,205 casos del x86 original y los 63 bytes de la función compilada.</p>
<a href="https://rea.tools/showcase/dx-ball/">Lee el caso práctico</a> ·
<a href="https://github.com/N0zoM1z0/dx-ball">Repositorio de reconstrucción</a>
</td>
</tr>
<tr>
<td>
<h3>Notion: rastrear el puente del portapapeles de Electron</h3>
<p>Sigue la API del portapapeles del proceso de renderizado a través de preload e IPC hasta el proceso principal para ver cómo Notion maneja los datos enriquecidos del portapapeles.</p>
<a href="https://rea.tools/showcase/notion/">Lee el caso práctico</a>
</td>
</tr>
<tr>
<td>
<h3>TH04: recuperar el cálculo de un anillo de proyectiles en DOS</h3>
<p>Recupera los cálculos de ángulos fijos y dirigidos a partir de las instrucciones de 16 bits del juego de PC-98 y compara el C++ reconstruido con la salida del compilador de la época.</p>
<a href="https://rea.tools/showcase/th04/">Lee el caso práctico</a> ·
<a href="https://github.com/N0zoM1z0/th04">Repositorio de reconstrucción</a>
</td>
</tr>
</tbody>
</table>

Si usaste REA para algo interesante, nos encantaría verlo. Comparte tu caso en un
[issue](https://github.com/morluto/rea/issues) o una
[pull request](https://github.com/morluto/rea/pulls), incluidos el objetivo,
tu pregunta, cómo te ayudó REA y lo que encontraste.

## Cómo funciona REA

Tu agente usa REA a través de MCP para inspeccionar un objetivo y rastrear el código relevante. Puede usar la evidencia que REA devuelve para hacer preguntas de seguimiento, explicar el comportamiento o crear y probar una implementación. La CLI usa los mismos flujos de trabajo.

![Flujo de investigación de REA: tu agente pregunta sobre un objetivo local, REA lo inspecciona y rastrea con herramientas de análisis, y el agente usa el código, las referencias y los aspectos desconocidos devueltos para explicar, implementar y probar.](website/public/assets/figures/rea-investigation-flow.svg)

[Abre la figura a tamaño completo](website/public/assets/figures/rea-investigation-flow.svg).

<a id="current-status"></a>

## Qué puedes analizar

REA cubre binarios nativos, aplicaciones JavaScript y Electron, sitios web, ensamblados .NET, aplicaciones de Android, firmware y actividad de ejecución y red registrada.

[Objetivos compatibles y requisitos](docs/reference/supported-targets.md)

<a id="choosing-a-deep-analysis-provider"></a>

Para la descompilación nativa, elige un proveedor que admita el formato de tu objetivo y el sistema operativo de tu computadora. Consulta [cómo elegir un proveedor de análisis profundo](docs/reference/supported-targets.md#choosing-a-deep-analysis-provider).

## Crear entornos de RL

Crea un entorno local a partir de una sesión web grabada o de una aplicación de escritorio Linux para que un agente practique una tarea y verifique el resultado.
[Crea un entorno de RL con REA](https://rea.tools/guides/rl-environments/).

## Preguntas frecuentes

<details>
<summary><strong>¿Qué agentes pueden usar REA?</strong></summary>

Cualquier agente que admita servidores MCP locales. La configuración prepara los
[agentes compatibles](docs/getting-started/installation.md#supported-agents); otros clientes pueden usar el
[registro manual de MCP](docs/getting-started/installation.md#mcp-registry).

</details>

<details>
<summary><strong>¿Necesito un motor de análisis nativo?</strong></summary>

El análisis nativo profundo usa Hopper, Ghidra, IDA o Kuna, según el objetivo
y la operación. La inspección estática de JavaScript y .NET funciona sin un motor de
análisis nativo. La configuración puede instalar Hopper después de tu aprobación; Ghidra, IDA y Kuna
usan tus instalaciones existentes. Consulta la [configuración de proveedores](docs/getting-started/installation.md#hopper)
para ver las opciones y los objetivos compatibles.

</details>

<details>
<summary><strong>¿Tengo que iniciar Hopper primero?</strong></summary>

REA inicia Hopper cuando una operación lo necesita. En macOS, un diálogo de primer uso puede
pedirte que elijas el modo de demostración o que actives tu licencia. Completa ese aviso en
la misma sesión de usuario antes de tu primera operación de CLI/MCP o trabajo desatendido. Abre
Hopper manualmente si es necesario. Consulta
[inicio de Hopper y solución de problemas](docs/getting-started/installation.md#launcher-paths-and-troubleshooting).

</details>

<details>
<summary><strong>¿Qué hace la instalación de la skill desde skills.sh?</strong></summary>

La skill proporciona instrucciones de investigación a tu agente. Usa `npx rea-agents setup`
para registrar el servidor MCP de REA e instalar las instrucciones correspondientes; luego reinicia
tu agente. Consulta la [instalación solo de la skill](docs/getting-started/installation.md#skill-only-installation).

</details>

<details>
<summary><strong>¿Qué código devuelve REA?</strong></summary>

El análisis nativo devuelve pseudocódigo y ensamblador. El análisis de JavaScript/Electron
recupera módulos y sus relaciones. Tu agente usa estos hallazgos para
escribir y probar una implementación; los [casos prácticos](#casos-prácticos) ofrecen ejemplos resueltos.

</details>

<details>
<summary><strong>¿REA sube mi aplicación?</strong></summary>

REA analiza los objetivos localmente. Tu agente recibe los resultados de las herramientas, y su
proveedor de modelos tiene su propia política de datos.

</details>

<details>
<summary><strong>¿Qué debo hacer si encuentro un error?</strong></summary>

Actualiza primero; es posible que una versión reciente ya lo haya corregido.

Para una CLI instalada con `npm install --global` o `bun add --global`:

```bash
rea update
```

Para la configuración del agente mediante `npx`:

```bash
npx rea-agents@latest setup
```

Si usas un agente, completa la [actualización de la configuración](#actualiza-rea) y reinícialo.
Repite la misma tarea. Si el problema persiste, [abre un issue](https://github.com/morluto/rea/issues)
con tu versión de REA, el tipo de objetivo, los pasos para reproducirlo y la salida del error.

</details>

## Documentación

Empieza con las [guías prácticas](https://rea.tools/guides/) del sitio web.
Para ver las opciones exactas, los requisitos previos y los contratos de resultados:

- [Instalación y configuración](docs/getting-started/installation.md): registro de agentes, configuración de proveedores, actualizaciones y desinstalación.
- [Preparación y solución de problemas](docs/getting-started/installation.md#check-readiness-for-your-task): diagnostica un agente o un motor de análisis.
- [CLI y Evidence](docs/getting-started/cli.md): comandos, selección de proveedores, capturas de estado, importación/exportación y estados de salida.
- [Contratos de MCP](docs/reference/mcp-contracts.md) y [prompts para agentes](docs/getting-started/mcp-prompts.md): resultados de herramientas, sesiones e investigaciones guiadas.
- [Catálogo de herramientas](docs/reference/mcp-contracts.md#generated-catalog): inventario generado de herramientas, proveedores y comandos de CLI.

Informa vulnerabilidades a través de [SECURITY.md](SECURITY.md).

## Comunidad y soporte

- **Discord** — Haz preguntas y comparte lo que estás investigando con nuestra apasionada comunidad de más de 50,000 ingenieros inversos y creadores. [![Únete al Discord de REA](https://img.shields.io/badge/Join%20Discord-5865F2?style=flat-square&logo=discord&logoColor=white)](https://discord.gg/GkcryMnJDM)
- **Twitter / X** — Sigue a [@reatools](https://x.com/reatools) para recibir novedades y anuncios.
- **Comentarios e ideas** — ¿Quieres una función nueva o compatibilidad con un formato de archivo? [Abre un issue en GitHub](https://github.com/morluto/rea/issues) o [únete a nuestro Discord](https://discord.gg/GkcryMnJDM) y cuéntanos.

## Historial de estrellas

🎉 **400,000 estrellas en GitHub: ¡gracias!**

Gracias a todas las personas que usan REA, reportan errores, solicitan funciones, prueban compilaciones y contribuyen con correcciones.

<a href="https://rea.tools/contributors/">
  <img src="website/public/contributors/avatars.png" alt="Colaboradores de REA" />
</a>

<a href="https://www.star-history.com/?repos=morluto%2Frea&amp;type=date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=morluto/rea&amp;type=date&amp;theme=dark&amp;legend=top-left" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=morluto/rea&amp;type=date" />
    <img alt="Historial de estrellas de REA en GitHub" src="https://api.star-history.com/chart?repos=morluto/rea&amp;type=date" />
  </picture>
</a>

## Contribuir

¡Nos encantaría contar con tu ayuda en REA! [Abre un issue](https://github.com/morluto/rea/issues) para
reportar un error o sugerir una función, o [envía una pull request](https://github.com/morluto/rea/pulls)
para mejorar el código o la documentación.

Consulta [CONTRIBUTING.md](CONTRIBUTING.md) para la configuración del entorno de desarrollo y las comprobaciones. Consulta la
[guía de pruebas](docs/development/testing.md) para los procesos de verificación.

## Aviso legal

Consulta [DISCLAIMER.md](DISCLAIMER.md) para obtener orientación sobre el uso responsable.

La postura del proyecto sobre el uso ilegal o no autorizado abarca todas las versiones, canales de distribución y plataformas de REA; cada copia conserva sus licencias aplicables.

REA es para investigación lícita, educación, interoperabilidad, preservación de software y análisis de software que posees o estás autorizado a examinar.

## Licencia

[MIT](LICENSE)

El código creado por REA está bajo licencia MIT. El material de terceros conserva sus propias licencias y avisos de derechos de autor; consulta [Avisos de terceros](THIRD_PARTY_NOTICES.md) para ver el inventario de dependencias, los textos de licencia conservados y los términos de las herramientas externas.

**Debes obtener y estar autorizado legalmente para usar herramientas comerciales**, incluidos los descompiladores IDA Pro / Hex-Rays, Hopper y JEB, bajo sus licencias aplicables. REA no otorga licencias, claves ni derechos de activación de herramientas. Las pruebas y demostraciones siguen sujetas a los términos del proveedor, incluidas las restricciones de usuarios, funciones, automatización y uso compartido de resultados. Las copias pirateadas, las claves robadas, el uso compartido no autorizado de claves y la evasión de restricciones de licencia no están autorizados. Esta orientación no modifica las licencias MIT ni las de terceros.
