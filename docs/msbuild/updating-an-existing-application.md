# <a name="updating-an-existing-application-for-msbuild-15"></a>Aktualizace stávající aplikace pro 15 nástroje MSBuild

Ve verzích nástroje MSBuild před 15.0 MSBuild byla načtena z globální mezipaměti sestavení (GAC) a rozšíření MSBuild byly nainstalovány v registru. To zajistit, že všechny aplikace použít stejnou verzi nástroje MSBuild a měl přístup ke stejným modulové, ale brání vedle sebe instalace různých verzí sady Visual Studio.

Za účelem podpory rychlejší, instalace menší a vedle sebe, Visual Studio 2017 už umístí MSBuild v mezipaměti GAC nebo upraví registru. Bohužel to znamená, že aplikace, které chcete použít rozhraní API nástroje MSBuild vyhodnotit, nebo vytváříte projekty nelze implicitně spoléhají na instalaci sady Visual Studio.

## <a name="using-msbuild-from-visual-studio"></a>Pomocí nástroje MSBuild ze sady Visual Studio

Aby se zajistilo, že programový sestavení z vaší aplikace shodují s těmi, provést v rámci sady Visual Studio nebo MSBuild.exe, načtení sestavení nástroje MSBuild ze sady Visual Studio a používat sady SDK, které jsou k dispozici v sadě Visual Studio. Balíček Microsoft.Build.Locator NuGet zjednodušuje to.

## <a name="using-microsoftbuildlocator"></a>Pomocí Microsoft.Build.Locator

Pokud je znovu distribuovat `Microsoft.Build.Locator.dll` s vaší aplikací, nebudete muset distribuovat ostatních MSBuild sestavení.

Aktualizace projektu pro použití nástroje MSBuild 15 a Lokátor rozhraní API vyžaduje několik změn ve vašem projektu popsané dole. Příklad změny vyžaduje k aktualizaci projektu, najdete v sekci [potvrzení provedené příklad projektu v úložišti MSBuildLocator](https://github.com/Microsoft/MSBuildLocator/commits/example-updating-to-msbuild-15).

### <a name="change-msbuild-references"></a>Změna MSBuild odkazů

Aby se zajistilo, že MSBuild je načtena z centrálního umístění, nesmí distribuovat jeho sestavení s vaší aplikací.

Tento mechanismus pro změnu projektu předejít přetížení MSBuild z centrálního umístění závisí na tom, jak odkazovat MSBuild.

#### <a name="using-nuget-packages-preferred"></a>Pomocí balíčků NuGet (doporučeno)

Tyto pokyny předpokládají, že používáte [ `PackageReference`– styl odkazů NuGet](https://docs.microsoft.com/en-us/nuget/consume-packages/package-references-in-project-files).

Změňte projekt soubory k odkazování MSBuild sestavení z jejich balíčků NuGet. Zadejte `ExcludeAssets=runtime` s oznámením NuGet, že sestavení jsou potřeba pouze v době sestavení a nemá být zkopírována do výstupního adresáře.

Hlavní a vedlejší verzi nástroje MSBuild balíčky musí být menší než nebo rovna minimální verze sady Visual Studio, které chcete podporovat. Pokud chcete podporovat všechny verze aplikace Visual Studio 2017, odkazovat verze balíčku `15.1.548`.

Například můžete použít tento XML:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.Build" Version="15.1.548" ExcludeAssets="runtime" />
  <PackageReference Include="Microsoft.Build.Utilities" Version="15.1.548" ExcludeAssets="runtime" />
</ItemGroup>
```

#### <a name="using-extension-assemblies"></a>Použití rozšíření sestavení

Pokud nemůžete použít balíčky NuGet, můžete odkazovat MSBuild sestavení, které jsou distribuovány pomocí sady Visual Studio. Pokud odkazujete MSBuild přímo, ujistěte se, se nebude zkopírovat adresáře výstup nastavením `Copy Local` k `False`. V souboru projektu bude vypadat takto:

```xml
    <Reference Include="Microsoft.Build, Version=15.1.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL">
      <Private>False</Private>
    </Reference>
```

#### <a name="binding-redirects"></a>Přesměrování vazby

Odkazování na balíček Microsoft.Build.Locator automaticky zajistí, že vaše aplikace používá přesměrování požadovaná vazba všech verzí nástroje MSBuild sestavení verzi `15.1.0.0`.

### <a name="ensure-output-clean"></a>Zkontrolujte výstup vyčištění

Sestavení projektu a zkontrolovat výstupního adresáře a ujistěte se, že neobsahuje žádné `Microsoft.Build.*.dll` sestavení (jiné než `Microsoft.Build.Locator.dll`, přidané v dalším kroku).

### <a name="add-package-reference"></a>Přidat odkaz na balíček

Přidat odkaz na balíček NuGet [Microsoft.Build.Locator](https://www.nuget.org/packages/Microsoft.Build.Locator/).

```xml
    <PackageReference Include="Microsoft.Build.Locator">
      <Version>1.0.7-preview-ge60d679b53</Version>
    </PackageReference>
```

### <a name="register-instance-before-calling-msbuild"></a>Registrace instance před voláním funkce MSBuild

Přidejte volání do rozhraní API Lokátor před voláním jakékoli metody, která používá MSBuild.

Nejjednodušší způsob, jak to udělat, je přidání volání

```c#
MSBuildLocator.RegisterDefaults();
```

v kódu spuštění aplikace.

Pokud chcete řídit citlivější načítání MSBuild, můžete vybrat výsledek `MSBuildLocator.QueryVisualStudioInstances()` předat `MSBuildLocator.RegisterInstance()` ručně, ale to není obvykle nutné.
