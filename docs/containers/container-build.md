---
title: Nástroje kontejneru sady Visual Studio sestavení – přehled
author: ghogen
description: Přehled procesu sestavení nástroje pro kontejnery
ms.author: ghogen
ms.date: 06/06/2019
ms.technology: vs-azure
ms.topic: conceptual
ms.openlocfilehash: 9f2da112bfeebe4e0bce976736eee5696d888105
ms.sourcegitcommit: c7b9ab1bc19d74b635c19b1937e92c590dafd736
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552825"
---
# <a name="building-containerized-apps-using-visual-studio-or-the-command-line"></a>Sestavování kontejnerizovaných aplikací pomocí sady Visual Studio nebo příkazového řádku

Zda sestavujete z integrovaného vývojového prostředí sady Visual Studio nebo nastavení sestavení příkazového řádku, musíte vědět, jak sada Visual Studio sestavuje používá soubor Dockerfile k sestavování vašich projektů.  Z důvodů výkonu sady Visual Studio se řídí pro kontejnerizované aplikace během speciálního procesu. Vysvětlení, jak sada Visual Studio sestavuje projekty je obzvláště důležité, když přizpůsobit proces sestavení tak, že upravíte soubor Dockerfile.

Když Visual Studio vytvoří projekt, který nepoužívá kontejnery Dockeru, MSBuild spustí v místním počítači a generuje výstupní soubory do složky (obvykle `bin`) v rámci vaší složky místní řešení. Kontejnerizované projektu ale proces sestavení bere v úvahu souboru Dockerfile pokyny pro vytvoření kontejnerizované aplikace. Soubor Dockerfile, který používá Visual Studio je rozdělen do několika fází. Tento proces se opírá o Docker *vícefázových sestavení* funkce.

## <a name="multistage-build"></a>Vícefázových sestavení

Funkce vícefázových sestavení pomáhá zjednodušit proces vytváření kontejnerů efektivnější a díky kontejnery menší tím, že je tak, aby obsahovala pouze bity, které vaše aplikace potřebuje za běhu. Vícefázových sestavení se používá pro projekty .NET Core, není u projektů .NET Framework.

Umožňuje vícefázových sestavení Image kontejneru bude vytvořena ve fázích, které vytvářejí zprostředkující imagí. Jako příklad, zvažte typické soubor Dockerfile vygenerované sadou Visual Studio – první fází `base`:

```
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443
```

Řádky v souboru Dockerfile začínat Nanoserver image z registru kontejneru Microsoft (mcr.microsoft.com) a vytvořit bitovou kopii zprostředkující `base` , který zpřístupňuje porty 80 a 443 a nastaví pracovní adresář na `/app`.

Další fází je `build`, která se zobrazí takto:

```
FROM mcr.microsoft.com/dotnet/core/sdk:2.2-stretch AS build
WORKDIR /src
COPY ["WebApplication43/WebApplication43.csproj", "WebApplication43/"]
RUN dotnet restore "WebApplication43/WebApplication43.csproj"
COPY . .
WORKDIR "/src/WebApplication43"
RUN dotnet build "WebApplication43.csproj" -c Release -o /app
```

Vidíte, že `build` fáze spustí z různých původní image z registru (`sdk` spíše než `aspnet`), namísto pokračování ze základu.  `sdk` Image obsahuje všechny nástroje, sestavení a z tohoto důvodu je mnohem větší než aspnet image, která obsahuje pouze součásti modulu runtime. Jasně pochopí Důvod použití samostatnou bitovou kopii, když se podíváte na zbytek souboru Dockerfile:

```
FROM build AS publish
RUN dotnet publish "WebApplication43.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication43.dll"]
```

Závěrečná fáze spuštění znovu z `base`a zahrnuje `COPY --from=publish` kopírování publikovaný výstup do finální bitové kopie. Tento proces umožní finální image budou mnohem menší, protože nemusí zahrnovat všechny nástroje pro sestavení, které byly v `sdk` bitové kopie.

## <a name="faster-builds-for-the-debug-configuration"></a>Rychlejší sestavování pro konfiguraci ladění

Existuje několik optimalizací, že se Visual Studio, které pomáhají s výkonu procesu sestavení pro kontejnerizované projekty. Při spuštění ladění (F5), dříve sestavenou image je znovu použít, pokud je to možné. Pokud nechcete, aby znovu použít předchozí kontejneru, můžete použít **znovu sestavit** nebo **Vyčistit** příkazy v sadě Visual Studio k vynucení sady Visual Studio používat nový kontejner.

Pokud chcete zlepšit výkon, není tak přímočaré jako jednoduše podle kroků uvedených v souboru Dockerfile proces sestavení pro kontejnerizované aplikace. Vytváření v kontejneru je mnohem pomalejší než sestavení v místním počítači.  Takže když vytváříte v **ladění** konfigurace sady Visual Studio, skutečně sestavuje projekty v místním počítači a pak sdílí do výstupní složky pro kontejner pomocí připojení svazku. Je volána metoda build s optimalizací povolené *rychlé* režimu sestavení.

V **rychlé** režimu, volání sady Visual Studio `docker build` s argumentem, který říká Dockeru k vytvoření pouze `base` fázi.  Visual Studio se stará o zbytek procesu bez ohledu na obsah souboru Dockerfile. Takže když upravíte vašem souboru Dockerfile, například k přizpůsobení prostředí kontejneru nebo nainstalovat další závislosti, byste měli umístit provedené změny v první fázi.  Všechny vlastní kroky umístěny v souboru Dockerfile `build`, `publish`, nebo `final` fáze nebude provedeno.

Optimalizace výkonu dochází pouze při sestavování **ladění** konfigurace. V **vydání** konfiguraci, sestavení dochází v kontejneru, jak je uvedeno v souboru Dockerfile.

Pokud chcete zakázat optimalizace výkonu a sestavení jako Určuje soubor Dockerfile, nastavte **ContainerDevelopmentMode** vlastnost **regulární** v projektu soubor následujícím způsobem:

```xml
<PropertyGroup>
   <ContainerDevelopmentMode>Regular</ContainerDevelopmentMode>
</PropertyGroup>
```

Chcete-li obnovit optimalizaci výkonu, odeberte vlastnost ze souboru projektu.

## <a name="building-from-the-command-line"></a>Sestavování z příkazového řádku

Můžete použít `docker build` nebo `MSBuild` k sestavení z příkazového řádku.

### <a name="docker-build"></a>sestavení dockeru

K vytvoření kontejnerové řešení z příkazového řádku, můžete obvykle použít příkaz `docker build <context>` pro každý projekt v řešení. Můžete zadat *sestavení kontextu* argument. *Sestavení kontextu* pro soubor Dockerfile je složce na místním počítači, který se používá jako pracovní složku pro vytvoření bitové kopie. Například je složka, která kopírování souborů z při kopírování do kontejneru.  V projektech .NET Core použijte složku obsahující soubor řešení (.sln).  Vyjádřena jako relativní cesta, tento argument je obvykle ".." pro soubor Dockerfile v složky projektu a soubor řešení v nadřazené složky.  Kontext sestavení pro projekty .NET Framework je složky projektu, nikoli složku řešení.

```cmd
docker build -f Dockerfile ..
```

### <a name="msbuild"></a>MSBuild

Soubory Dockerfile vytvořené pomocí sady Visual Studio pro projekty .NET Framework (a pro projekty .NET Core, které jsou vytvořené pomocí verze sady Visual Studio před Visual Studio 2017 Update 4) nejsou vícefázových soubory Dockerfile.  Kroky v tyto soubory Dockerfile, nejde zkompilovat kód.  Místo toho když Visual Studio vytvoří soubor Dockerfile rozhraní .NET Framework, nejprve kompilaci projektu pomocí nástroje MSBuild.  Když se tato operace úspěšná, Visual Studio vytvoří soubor Dockerfile, který jednoduše kopíruje výstup sestavení z nástroje MSBuild do výsledné image Dockeru.  Vzhledem k tomu, že kroky ke kompilaci kódu nejsou zahrnuty v souboru Dockerfile, nelze sestavit soubory Dockerfile rozhraní .NET Framework pomocí `docker build` z příkazového řádku. Měli byste použít MSBuild k sestavení těchto projektů.

K vytvoření image pro jeden docker kontejneru projektu MSBuild s parametrem/můžete `/t:ContainerBuild` možnost příkazu. Příklad:

```cmd
MSBuild MyProject.csproj /t:ContainerBuild /p:Configuration=Release
```

Zobrazí výstup podobný uvidíte v **výstup** okno při sestavování řešení v integrovaném vývojovém prostředí sady Visual Studio. Vždy používejte `/p:Configuration=Release`, protože v případech, kde sada Visual Studio používá vícefázových sestavení výsledků optimalizace, při vytváření **ladění** konfigurace nemusí být podle očekávání.

Pokud používáte projektu Docker Compose, použijte příkaz k vytvoření imagí:

```cmd
msbuild /p:SolutionPath=<solution-name>.sln /p:Configuration=Release docker-compose.dcproj
```

## <a name="next-steps"></a>Další kroky

Zjistěte, jak dále přizpůsobit sestavení tak, že nastavíte další vlastnosti nástroje MSBuild v souborech projektu. Zobrazit [vlastnosti nástroje MSBuild pro projekty kontejneru](container-msbuild-properties.md).

## <a name="see-also"></a>Viz také:

[Nástroj MSBuild](../msbuild/msbuild.md)
[souboru Docker na Windows](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
[kontejnery Linuxu ve Windows](/virtualization/windowscontainers/deploy-containers/linux-containers)
