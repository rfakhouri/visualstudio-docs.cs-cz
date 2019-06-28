---
title: Nástroje kontejneru sady Visual Studio vlastnosti sestavení
author: ghogen
description: Přehled procesu sestavení nástroje pro kontejnery
ms.author: ghogen
ms.date: 06/06/2019
ms.technology: vs-azure
ms.topic: conceptual
ms.openlocfilehash: e3ce803f13b8dde82ffe71906e5f7a43a029dbb6
ms.sourcegitcommit: 0cd282a7584b9bfd4df7882f8fdf3ad8a270e219
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2019
ms.locfileid: "67467413"
---
# <a name="container-tools-build-properties"></a>Nástroje kontejneru sady vlastnosti sestavení

Můžete přizpůsobit, jak sada Visual Studio sestavuje projekty kontejneru nastavením vlastnosti, které používá MSBuild k sestavení projektu. Například můžete změnit název souboru Dockerfile, zadejte značky a popisky pro váš obrázky zadat další argumenty předány příkazy Dockeru a řízení, zda sady Visual Studio nepodporuje některé optimalizace výkonu, jako je například vytváření mimo kontejnerové prostředí. Můžete také nastavit vlastnosti, jako je například název spustitelného souboru k argumentů příkazového řádku a spuštění ladění poskytnout.

Pokud chcete nastavit hodnotu vlastnosti, upravte soubor projektu. Předpokládejme například, že má název vašeho souboru Dockerfile *MyDockerfile*. Můžete nastavit `DockerfileFile` vlastnost v projektu soubor následujícím způsobem.

```xml
<PropertyGroup>
   <DockerfileFile>MyDockerfile</DockerfileFile>
</PropertyGroup>
```

Nastavení vlastností můžete přidat do existujícího `PropertyGroup` element, nebo pokud není k dispozici, vytvořte nový `PropertyGroup` elementu.

V následující tabulce jsou uvedeny vlastnosti nástroje MSBuild, který je k dispozici pro projekty kontejneru.

| Název vlastnosti | Popis | Výchozí hodnota  |
|---------------|-------------|----------------|
| DockerfileFile | Popisuje výchozí soubor Dockerfile, který se použije k sestavení nebo spuštění kontejneru pro projekt. To může být i cesta. | Dockerfile |
| DockerfileTag | Značky, který se použije při sestavování image Dockeru. Při ladění, ": vývoj" se připojí ke značce. | Název sestavení po odstranění jiné než alfanumerické znaky, pomocí následujících pravidel: <br/> Pokud výsledná značka je všechny číselné, pak "image" je vložena jako předpona (například image2314) <br/> Pokud výsledná značka je prázdný řetězec, použije se jako značky "image". |
| DockerContext | Výchozí kontext, který používá při sestavování image Dockeru. | Nastavte Visual Studio. |
| ContainerDevelopmentMode | Určuje, zda je povolena optimalizace "sestavení na hostitele" ("Rychlý režim" ladění).  Povolené hodnoty jsou **rychlé** a **regulární**. | Rychlé |
| DockerDefaultTargetOS | Výchozí cílový operační systém používá při sestavování image Dockeru. | Nastavte Visual Studio. |
| DockerImageLabels | Výchozí sada popisky u image Dockeru. | com.microsoft.created-by=visual-studio;com.microsoft.visual-studio.project-name=$(MSBuildProjectName) |
| ContainerVsDbgPath | Cesta pro VSDBG ladicího programu. | `%USERPROFILE%\vsdbg\vs2017u5` |
| DockerfileBuildArguments | Další argumenty jsou předány do příkaz sestavení Dockeru. | Není k dispozici. |
| DockerfileRunArguments | Další argumenty předané Dockeru, spusťte příkaz. | Není k dispozici. |
| DockerfileRunEnvironmentFiles | Středníkem oddělený seznam souborů prostředí platily Docker run. | Není k dispozici. |
| DockerfileFastModeStage | Soubor Dockerfile fáze (cíl) se použije při vytváření bitové kopie v režimu ladění. | V první fázi najít v souboru Dockerfile (base) |
| DockerDebuggeeProgram | Při ladění, ladicí program je nastaven na spuštění tohoto spustitelného souboru. | Pro projekty .NET Core: dotnet projekty ASP.NET rozhraní .NET Framework: Není k dispozici (služba IIS vždy používá) |
| DockerDebuggeeArguments | Při ladění, ladicí program je nastaven na předání těchto argumentů spuštěný spustitelný soubor. | Není k dispozici pro projekty ASP.NET rozhraní .NET Framework |
| DockerDebuggeeWorkingDirectory | Při ladění, ladicí program je nastaven na použití tuto cestu jako pracovní adresář. | C:\app (Windows) nebo /app (Linux) |
| DockerDebuggeeKillProgram | Tento příkaz slouží k ukončení procesu spuštěného v kontejneru. | Není k dispozici pro projekty ASP.NET rozhraní .NET Framework |

## <a name="next-steps"></a>Další kroky

Informace o MSBuild vlastnosti Obecné najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).

## <a name="see-also"></a>Viz také:

[Nástroj MSBuild vyhrazené a dobře známé vlastnosti](../msbuild/msbuild-reserved-and-well-known-properties.md).
