---
title: Jak používat vlastní NuGet kanálu v připojeném prostředí | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 03/27/2018
ms.topic: conceptual
description: Použijte vlastní NuGet kanálu přístup a používání balíčků NuGet v připojeném prostředí.
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 1c4c0c53b81f29436bb7110395981071411fd6b2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
#  <a name="use-a-custom-nuget-feed-in-a-connected-environment"></a>Použít vlastní NuGet kanálu v připojeném prostředí

Informační kanál NuGet představuje pohodlný způsob pro zahrnutí zdroje balíčku do projektu. Připojeném prostředí bude muset být schopni přistupovat tohoto kanálu v pořadí pro závislosti možné správně nainstalovaný v kontejner Docker.

Nastavení NuGet kanálu:
1. Přidat [balíček odkaz](https://docs.microsoft.com/en-us/nuget/consume-packages/package-references-in-project-files) v `*.csproj` souboru pod `PackageReference` uzlu.

   ```xml
   <ItemGroup>
       <!-- ... -->
       <PackageReference Include="Contoso.Utility.UsefulStuff" Version="3.6.0" />
       <!-- ... -->
   </ItemGroup>
   ```

2. Vytvoření [NuGet.Config](https://docs.microsoft.com/en-us/nuget/reference/nuget-config-file) soubor ve složce projektu.
     * Použití `packageSources` části, chcete-li vaše NuGet kanálu umístění. Důležité: K informačnímu kanálu NuGet musí být veřejně přístupná.
     * Použití `packageSourceCredentials` část konfigurace uživatelského jména a hesla pověření. 

   ```xml
   <packageSources>
       <add key="Contoso" value="https://contoso.com/packages/" />
   </packageSources>

   <packageSourceCredentials>
       <Contoso>
           <add key="Username" value="user@contoso.com" />
           <add key="ClearTextPassword" value="33f!!lloppa" />
       </Contoso>
   </packageSourceCredentials>
   ```

3. Pokud používáte správu zdrojového kódu:
    - Referenční dokumentace `NuGet.Config` ve vaší `.gitignore` tak nejsou omylem potvrzení přihlašovací údaje k úložišti zdrojového souboru.
    - Otevřete `vsce.yaml` souborů ve vašem projektu a najděte `build` části a vložte následující fragment kódu zajistit, aby `NuGet.Config` souboru se budou synchronizovat do Azure, aby se použít během procesu vytváření bitové kopie kontejneru. (Ve výchozím nastavení, prostředí připojení nebude synchronizovat soubory, které odpovídají `.gitignore` a `.dockerignore` pravidla.)

        ```yaml
        build:
        useGitIgnore: true
        ignore:
        - “!NuGet.Config”
        ```


## <a name="next-steps"></a>Další kroky

Po dokončení výše uvedené kroky, při příštím spuštění `vsce up` (nebo stiskněte tlačítko `F5` v VSCode nebo Visual Studio), bude synchronizovat připojené prostředí `NuGet.Config` souboru do Azure, který je pak využívaných `dotnet restore` k instalaci balíčku závislosti v kontejneru.

