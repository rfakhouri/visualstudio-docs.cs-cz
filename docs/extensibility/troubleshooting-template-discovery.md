---
title: Řešení potíží s zjišťování v sadě Visual Studio | Dokumentace Microsoftu
ms.date: 01/02/2018
ms.topic: conceptual
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a1ea74d3c5f3fed961a956e9a55a4930d009d530
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62432080"
---
# <a name="troubleshooting-template-installation"></a>Řešení potíží s instalací šablony

Pokud narazíte na problémy, projekt nebo položku šablony nasazení, můžete povolit protokolování diagnostiky.

::: moniker range="vs-2017"

1. Vytvořte soubor pkgdef v *Common7\IDE\CommonExtensions* složky pro instalaci. Například *C:\Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef*.

::: moniker-end

::: moniker range=">=vs-2019"

1. Vytvořte soubor pkgdef v *Common7\IDE\CommonExtensions* složky pro instalaci. Například *C:\Program Files (x86) \Microsoft Visual Studio\2019\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef*.

::: moniker-end

2. Přidejte následující text do souboru pkgdef:

    ```
    [$RootKey$\VsTemplate]
    "EnableTemplateDiscoveryLog"=dword:00000001
    ```

3. Otevřít [Developer Command Prompt](/dotnet/framework/tools/developer-command-prompt-for-vs) pro instalaci a spuštění `devenv /updateConfiguration`.

::: moniker range="vs-2017"

4. Otevřít Visual Studio a spusťte dialogových oknech Nový projekt a nová položka inicializace obou stromech šablony.

   Protokol šablony se zobrazí v **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_[instanceid]\VsTemplateDiagnosticsList.csv** (instanceid odpovídá ID instalace instance sady Visual Studio). Inicializace stromu každý šablona přidá položky do tohoto protokolu.

::: moniker-end

::: moniker range=">=vs-2019"

4. Otevřít Visual Studio a spustit **vytvořte nový projekt** a **nová položka** dialogových oknech inicializace obou stromech šablony.

   Protokol šablony se zobrazí v **%LOCALAPPDATA%\Microsoft\VisualStudio\16.0_[instanceid]\VsTemplateDiagnosticsList.csv** (instanceid odpovídá ID instalace instance sady Visual Studio). Inicializace stromu každý šablona přidá položky do tohoto protokolu.

::: moniker-end

Soubor protokolu obsahuje následující sloupce:

- **FullPathToTemplate**, který má následující hodnoty:

    - 1 pro nasazení na základě manifestu

    - 0 pro nasazení založené na disku

- **TemplateFileName**

- Další vlastnosti šablony

> [!NOTE]
> Zakázat protokolování, buď odeberte soubor pkgdef, nebo změňte hodnotu vlastnosti `EnableTemplateDiscoveryLog` k `dword:00000000`a pak spusťte `devenv /updateConfiguration` znovu.

## <a name="see-also"></a>Viz také:

- [Vytváření vlastních šablon projektů a položek](creating-custom-project-and-item-templates.md)