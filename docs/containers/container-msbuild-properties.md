---
title: Vlastnosti sestavení kontejnerů sady Visual Studio
author: ghogen
description: Přehled procesu sestavení nástrojů kontejneru
ms.author: ghogen
ms.date: 06/06/2019
ms.technology: vs-azure
ms.topic: conceptual
ms.openlocfilehash: 4bc6cb4221d85bd43b98b2ac36c34c919937960b
ms.sourcegitcommit: 3cda0d58c5cf1985122b8977b33a171c7359f324
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/29/2019
ms.locfileid: "70152530"
---
# <a name="container-tools-build-properties"></a>Vlastnosti sestavení kontejnerových nástrojů

Můžete přizpůsobit způsob, jakým Visual Studio sestaví projekty kontejneru, nastavením vlastností, které nástroj MSBuild používá k sestavení projektu. Můžete například změnit název souboru Dockerfile, zadat značky a štítky pro obrázky, poskytnout další argumenty předané příkazům Docker a určit, zda aplikace Visual Studio provede určité optimalizace výkonu, jako je například sestavování mimo prostředí kontejneru. Můžete také nastavit vlastnosti ladění, jako je název spustitelného souboru, který se má spustit, a argumenty příkazového řádku, které mají být zadány.

Chcete-li nastavit hodnotu vlastnosti, upravte soubor projektu. Předpokládejme například, že vaše souboru Dockerfile má název *MyDockerfile*. `DockerfileFile` Vlastnost můžete nastavit v souboru projektu následujícím způsobem.

```xml
<PropertyGroup>
   <DockerfileFile>MyDockerfile</DockerfileFile>
</PropertyGroup>
```

Nastavení vlastnosti můžete přidat do existujícího `PropertyGroup` prvku, nebo pokud není jedna, vytvořte nový `PropertyGroup` prvek.

V následující tabulce jsou uvedeny vlastnosti MSBuild dostupné pro projekty kontejnerů.

| Název vlastnosti | Popis | Výchozí hodnota  |
|---------------|-------------|----------------|
| DockerfileFile | Popisuje výchozí souboru Dockerfile, který bude použit k sestavení nebo spuštění kontejneru pro projekt. Může to být i cesta. | Souboru Dockerfile |
| DockerfileTag | Značka, která bude použita při sestavování image Docker. V ladění je k značce připojen ":d EV". | Název sestavení po odstranění nealfanumerických znaků pomocí následujících pravidel: <br/> Pokud je výsledná značka všechna číselná, pak se jako předpona vloží "image" (například image2314). <br/> Pokud je výsledná značka prázdným řetězcem, použije se jako značka "image". |
| DockerContext | Výchozí kontext použitý při vytváření image Docker. | Nastaveno sadou Visual Studio. |
| ContainerDevelopmentMode | Určuje, jestli je povolená optimalizace optimalizace sestavení na úrovni hostitele (rychlý režim).  Povolené hodnoty jsou **rychlé** a **pravidelné**. | Světl |
| DockerDefaultTargetOS | Výchozí cílový operační systém, který se používá při vytváření image Docker. | Nastaveno sadou Visual Studio. |
| DockerImageLabels | Výchozí sada popisků použitých pro bitovou kopii Docker. | com.microsoft.created-by=visual-studio;com.microsoft.visual-studio.project-name=$(MSBuildProjectName) |
| ContainerVsDbgPath | Cesta k ladicímu programu VSDBG | `%USERPROFILE%\vsdbg\vs2017u5` |
| DockerfileBuildArguments | Do příkazu Docker Build byly předány další argumenty. | Není k dispozici. |
| DockerfileRunArguments | Další argumenty předané příkazu Docker run. | Není k dispozici. |
| DockerfileRunEnvironmentFiles | Středníky oddělený seznam souborů prostředí použitých při spuštění Docker. | Není k dispozici. |
| DockerfileFastModeStage | Fáze souboru Dockerfile (tj. Target), která se má použít při sestavování image v režimu ladění. | V souboru Dockerfile se našla první fáze (Base). |
| DockerDebuggeeProgram | Při ladění je ladicí program vyzván ke spuštění tohoto spustitelného souboru. | Pro projekty .NET Core: dotnet, ASP.NET .NET Framework projekty: Nejde použít (služba IIS se vždycky používá) |
| DockerDebuggeeArguments | Při ladění je ladicí program vyzván k předání těchto argumentů spuštěnému spustitelnému souboru. | Nedá se použít pro projekty ASP.NET .NET Framework. |
| DockerDebuggeeWorkingDirectory | Při ladění je ladicí program vyzván k použití této cesty jako pracovního adresáře. | C:\app (Windows) nebo/App (Linux) |
| DockerDebuggeeKillProgram | Tento příkaz slouží k ukončení běžícího procesu v kontejneru. | Nedá se použít pro projekty ASP.NET .NET Framework. |

## <a name="next-steps"></a>Další postup

Informace o vlastnostech MSBuildu obecně naleznete v tématu [vlastnosti MSBuild](../msbuild/msbuild-properties.md).

## <a name="see-also"></a>Viz také:

[Docker Compose vlastnosti sestavení](docker-compose-properties.md)

[Nastavení spuštění nástrojů kontejneru](container-launch-settings.md)

[Rezervované a dobře známé vlastnosti nástroje MSBuild](../msbuild/msbuild-reserved-and-well-known-properties.md)
