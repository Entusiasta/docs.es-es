### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a><span data-ttu-id="aa4f7-101">Cambio en el carácter separador de ruta de acceso de la propiedad FullName de los objetos ZipArchiveEntry</span><span class="sxs-lookup"><span data-stu-id="aa4f7-101">Change in path separator character in FullName property of ZipArchiveEntry objects</span></span>

|   |   |
|---|---|
|<span data-ttu-id="aa4f7-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="aa4f7-102">Details</span></span>|<span data-ttu-id="aa4f7-103">Para las aplicaciones destinadas a .NET Framework 4.6.1 y versiones posteriores, el carácter separador de ruta de acceso ha cambiado de una barra diagonal inversa (&quot;&quot;) a una barra diagonal (&quot;/&quot;) en la propiedad <xref:System.IO.Compression.ZipArchiveEntry.FullName> de los objetos <xref:System.IO.Compression.ZipArchiveEntry> creados por sobrecargas del método <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A>.</span><span class="sxs-lookup"><span data-stu-id="aa4f7-103">For apps that target the .NET Framework 4.6.1 and later versions, the path separator character has changed from a backslash (&quot;&quot;) to a forward slash (&quot;/&quot;) in the <xref:System.IO.Compression.ZipArchiveEntry.FullName> property of <xref:System.IO.Compression.ZipArchiveEntry>  objects created by overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> method.</span></span> <span data-ttu-id="aa4f7-104">El cambio hace que la implementación de .NET sea conforme a la sección 4.4.17.1 de la [Especificación del formato de archivo .ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) y permite descomprimir archivos .ZIP en sistemas que no sean Windows. Al descomprimir un archivo ZIP creado por una aplicación destinada a una versión anterior de .NET Framework en sistemas operativos que no son de Windows, como Macintosh, impide que conserve la estructura de directorios.</span><span class="sxs-lookup"><span data-stu-id="aa4f7-104">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.Decompressing a zip file created by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="aa4f7-105">Por ejemplo, en Macintosh, crea un conjunto de archivos cuyo nombre de archivo concatena la ruta de acceso del directorio, junto con cualquier carácter de barra diagonal inversa (&quot;&quot;) y el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="aa4f7-105">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash (&quot;&quot;) characters, and the filename.</span></span> <span data-ttu-id="aa4f7-106">Como resultado, no se conserva la estructura de directorios de archivos descomprimidos.</span><span class="sxs-lookup"><span data-stu-id="aa4f7-106">As a result, the directory structure of decompressed files is not preserved.</span></span>|
|<span data-ttu-id="aa4f7-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="aa4f7-107">Suggestion</span></span>|<span data-ttu-id="aa4f7-108">El impacto de este cambio en los archivos .ZIP que se descomprimen en el sistema operativo Windows por las API del espacio de nombres de .NET Framework <xref:System.IO?displayProperty=nameWithType> debería ser mínimo, ya que estas API pueden controlar sin problemas una barra diagonal (&quot;/&quot;) o una barra diagonal inversa (&quot;\&quot;) como carácter separador de la ruta de acceso. Si no quiere este cambio, lo puede rechazar mediante la adición de una opción de configuración en la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa4f7-108">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO?displayProperty=nameWithType> namespace should be minimal, since these APIs can seamlessly handle either a slash (&quot;/&quot;) or a backslash (&quot;\&quot;) as the path separator character.If this change is undesirable, you can opt out of it by adding a configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="aa4f7-109">En el ejemplo siguiente se muestra la sección `<runtime>` y el conmutador de rechazo `Switch.System.IO.Compression.ZipFile.UseBackslash`:</span><span class="sxs-lookup"><span data-stu-id="aa4f7-109">The following example shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-out switch:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="aa4f7-110">Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en .NET Framework 4.6.1 y versiones posteriores se pueden incluir en este comportamiento si se agrega una opción de configuración a la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa4f7-110">In addition, apps that target previous versions of the .NET Framework but are running on the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="aa4f7-111">A continuación se muestra la sección `<runtime>` y el conmutador de inclusión `Switch.System.IO.Compression.ZipFile.UseBackslash`.</span><span class="sxs-lookup"><span data-stu-id="aa4f7-111">The following shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-in switch.</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="aa4f7-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="aa4f7-112">Scope</span></span>|<span data-ttu-id="aa4f7-113">Borde</span><span class="sxs-lookup"><span data-stu-id="aa4f7-113">Edge</span></span>|
|<span data-ttu-id="aa4f7-114">Versión</span><span class="sxs-lookup"><span data-stu-id="aa4f7-114">Version</span></span>|<span data-ttu-id="aa4f7-115">4.6.1</span><span class="sxs-lookup"><span data-stu-id="aa4f7-115">4.6.1</span></span>|
|<span data-ttu-id="aa4f7-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="aa4f7-116">Type</span></span>|<span data-ttu-id="aa4f7-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="aa4f7-117">Retargeting</span></span>|
|<span data-ttu-id="aa4f7-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="aa4f7-118">Affected APIs</span></span>|<ul><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType></li></ul>|
