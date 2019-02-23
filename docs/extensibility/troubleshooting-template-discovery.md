---
title: Řešení potíží s zjišťování v sadě Visual Studio | Dokumentace Microsoftu
ms.date: 01/02/2018
ms.topic: conceptual
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1e84ff96381fb29a1728ad43df4ff558abd17243
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689835"
---
# <a name="troubleshooting-template-installation"></a>Řešení potíží s instalací šablony

Pokud narazíte na problémy, projekt nebo položku šablony nasazení, můžete povolit protokolování diagnostiky.

1. Vytvořte soubor pkgdef ve složce Common7\IDE\CommonExtensions instalace (např. C:\Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef) s následujícím obsahem:

    ```
    [$RootKey$\VsTemplate]
    "EnableTemplateDiscoveryLog"=dword:00000001
    ```

1. Otevřete "příkazový řádek pro vývojáře" pro vaši instalaci tak, že ho ve službě Windows search a spusťte `devenv /updateConfiguration`.

1. Spusťte sadu Visual Studio a spusťte nový projekt a nová položka dialogová okna inicializace obou stromech šablony. Protokol šablony se zobrazí v **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_[instanceid]\VsTemplateDiagnosticsList.csv** (instanceid odpovídá ID instalace instance sady Visual Studio). Inicializace stromu každý šablona přidá položky do tohoto protokolu.

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