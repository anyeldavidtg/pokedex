---


---

<h1 id="pokedex-y-aplicaciones-web-de-azure">PokeDex y aplicaciones web de Azure</h1>
<p>Esta aplicación permite que los usuarios exploren y conozcan las diferentes especies de Pokémon, incluyendo información detallada sobre sus características y habilidades. Está desarrollada con <strong>Angular</strong> y consume la <strong>PokéAPI</strong>.</p>
<p>En este repositorio tenemos el despliegue de la aplicación en <strong>Microsoft Azure (Azure for Students)</strong> para la compañía ficticia <em>Pueblo Paleta Inc.</em></p>
<p>| Dato | Valor |</p>
<p>|—|---|</p>
<p>| Aplicación en línea | <a href="https://anyeldavidtg-fyfyetezhzc4f3gr.brazilsouth-01.azurewebsites.net">https://anyeldavidtg-fyfyetezhzc4f3gr.brazilsouth-01.azurewebsites.net</a> |</p>
<p>| Repositorio | <a href="https://github.com/anyeldavidtg/pokedex">https://github.com/anyeldavidtg/pokedex</a> |</p>
<p>| Nube pública | Microsoft Azure (Azure Web Apps) |</p>
<p>| Calificación <a href="http://SecurityHeaders.com">SecurityHeaders.com</a> | <strong>A+</strong> |</p>
<p>| Calificación SSL Labs | <strong>A+</strong> |</p>
<blockquote>
<p>La explicación de cómo se publica la aplicación está en <a href="Despliegue.md">Despliegue.md</a>.</p>
</blockquote>
<hr>
<h2 id="tutorial-creación-de-la-cuenta-en-la-nube-pública-azure-for-students">Tutorial: creación de la cuenta en la nube pública (Azure for Students)</h2>
<p>Este tutorial sigue el laboratorio guiado <em>“Despliegue de una Aplicación Web en Azure Web Apps”</em> entregado en el curso.</p>
<h3 id="crear-la-cuenta-de-azure-for-students">1. Crear la cuenta de Azure for Students</h3>
<ol>
<li>Se ingresa a la página de <strong>Azure for Students</strong> (<a href="https://azure.microsoft.com/free/students">https://azure.microsoft.com/free/students</a>).2. Se hace clic en <strong>Empezar gratis</strong>.3. Se inicia sesión con su cuenta estudiantil <strong>cuenta de estudiante (correo institucional)</strong> de la universidad.4. Como mi cuenta tiene verificación en dos pasos, Microsoft envía un mensaje de confirmación a mi teléfono y a mi correo, se verifica el código para continuar.5. Se completa el registro con la información solicitada.6. Una vez sea creada la cuenta, se entra al portal de Azure: <a href="https://portal.azure.com">https://portal.azure.com</a></li>
</ol>
<p>Al terminar, la suscripción aparece con el nombre <strong>Azure for Students</strong>.</p>
<h3 id="crear-el-recurso-web-app">2. Crear el recurso Web App</h3>
<ol>
<li>En el <strong>Portal de Azure</strong>, haz clic en <strong>Crear un recurso</strong>.2. se busca el servicio <strong>Web App</strong> y se hace clic en <strong>Crear</strong>.3. se Completa la pestaña <strong>Aspectos básicos</strong> con estos valores:</li>
</ol>
<p>| Campo | Valor utilizado |</p>
<p>|—|---|</p>
<p>| Suscripción | Azure for Students |</p>
<p>| Grupo de recursos | <code>anyel_torres</code> |</p>
<p>| Nombre de la aplicación | <code>anyeldavidtg</code> |</p>
<p>| Publicar | Código |</p>
<p>| Pila en tiempo de ejecución | .NET 10 |</p>
<p>Sistema operativo | Windows |</p>
<p>| Región | Brazil South |</p>
<p>| Plan de Windows | <code>ASP-anyeltorres-88f0</code> |</p>
<p>| Plan de precios | <strong>Free F1</strong> (infraestructura compartida) |</p>
<ol start="4">
<li>Se hace clic en <strong>Revisar y crear</strong>.5. Se Verifica en el resumen que el SKU sea <strong>Free</strong> (precio estimado: gratis).6. Se hace clic en <strong>Crear</strong> y espera un par de minutos hasta ver <strong>Su implementación está completa</strong>.7. Se hace clic en <strong>Ir al recurso</strong>. El estado del Web App debe aparecer como <strong>En ejecución</strong>.</li>
</ol>
<p>Al crearse con el nombre <code>anyeldavidtg</code>, Azure asigna esta dirección:</p>
<p><code></code> <code>https://anyeldavidtg-fyfyetezhzc4f3gr.brazilsouth-01.azurewebsites.net</code> <code></code></p>
<h3 id="configuración-inicial-del-web-app">3. Configuración inicial del Web App</h3>
<p>Después de crear el recurso se hizo esta configuración inicial:</p>
<ol>
<li>Se entro a la Web App y se revisaro la <strong>Información general</strong> (Overview): el estado <em>En ejecución</em>, el sistema operativo <em>Windows</em>, plan <em>Free F1</em> y el <strong>dominio predeterminado</strong>.2. Hay que ir a <strong>Configuración &gt; Configuración general</strong> y activar la opción <strong>Credenciales de publicación de autenticación básica de SCM</strong>. Viene desactivada por defecto y es necesaria para que GitHub Actions pueda publicar en el Web App.3. Se guardan los cambios con <strong>Aplicar</strong>.4. Se descarga el <strong>perfil de publicación</strong> desde *Información general</li>
</ol>
<blockquote>
<p>El perfil de publicación contiene credenciales. No se sube al repositorio: se guarda como <em>secret</em> de GitHub y el archivo descargado se elimina.</p>
</blockquote>
<hr>
<h2 id="estructura-del-repositorio">Estructura del repositorio</h2>
<p>| Elemento | Descripción |</p>
<p>|—|---|</p>
<p>| <code>src/</code> | Código fuente de la aplicación Angular |</p>
<p>| <code>src/web.config</code> | Configuración de IIS: reescritura de rutas y encabezados de seguridad |</p>
<p>| <code>src/environments/</code> | Variables de entorno (URLs de la API y ruta de imágenes) |</p>
<p>| <code>.github/workflows/pipelines.yml</code> | Flujo de GitHub Actions que compila y despliega a Azure |</p>
<p>| <code>Despliegue.md</code> | Guía de despliegue paso a paso |</p>
<p>Créditos</p>
<ul>
<li>
<p>Aplicación original: <strong>Keiler Mora</strong> (<a href="https://github.com/keilermora/pokedex-angular">https://github.com/keilermora/pokedex-angular</a>).</p>
</li>
<li>
<p>Se uso como Código fuente del laboratorio: repositorio de <strong>rcuello</strong> (<a href="https://github.com/rcuello/ac4dem1a">https://github.com/rcuello/ac4dem1a</a>).</p>
</li>
<li>
<p>Datos de los Pokémon: <a href="https://pokeapi.co/">PokéAPI</a>.</p>
</li>
<li>
<p>Pokémon y los nombres de sus personajes son marcas registradas de Nintendo.</p>
</li>
</ul>

