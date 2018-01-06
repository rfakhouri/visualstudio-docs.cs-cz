---
title: "Řešení potíží s šablony zjišťování v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 72663d56844fcc34164e9408ab14c8ead234683e
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="troubleshooting-template-installation"></a>Řešení potíží s instalací šablony

Pokud narazíte na problémy nasazení vašeho projektu nebo šablony položek, můžete povolit protokolování diagnostiky.

1. Vytvořte soubor pkgdef ve složce Common7\IDE\CommonExtensions pro instalaci (například C:\Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef) s tímto obsahem:

    ```
    [$RootKey$\VsTemplate]
    "EnableTemplateDiscoveryLog"=dword:00000001
    ```

1. Otevřete "příkazový řádek vývojáře" pro instalaci vyhledáním ve Windows search a spusťte `devenv /updateConfiguration`.

1. Spuštění sady Visual Studio a spusťte dialogová okna Nový projekt a nové položky k chybě při inicializaci stromy obě šablony. Protokol šablony se teď zobrazí v **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_[instanceid]\VsTemplateDiagnosticsList.csv** (identifikátor instanceid odpovídá ID instalace vaší instance sady Visual Studio). Každý inicializace stromu šablona připojí položky do tohoto protokolu.

Soubor protokolu obsahuje následující sloupce:

- **FullPathToTemplate**, který má následující hodnoty:

    - 1 pro nasazení na základě manifestu

    - 0 pro nasazení založené na disku

- **TemplateFileName**

- Ostatní vlastnosti šablony

> [!NOTE]
> Zakázat protokolování, buď odeberte soubor pkgdef, nebo změňte hodnotu `EnableTemplateDiscoveryLog` k `dword:00000000`a poté spusťte `devenv /updateConfiguration` znovu.

## <a name="see-also"></a>Viz také

[Vytváření vlastních šablon projektů a položek](creating-custom-project-and-item-templates.md)