---
title: Nasazení rozšíření pro modelování vrstev
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e8fe915f31181af4158bdfe7e292313886ed7d4c
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "57983101"
---
# <a name="deploy-a-layer-model-extension"></a>Nasazení rozšíření pro modelování vrstev

Ostatní uživatelé sady Visual Studio můžete nainstalovat rozšíření, které vytvoříte pomocí sady Visual Studio modelování vrstev.

## <a name="install-your-extension"></a>Instalace rozšíření

Rozšíření je kompilováno do souboru VSIX, který si můžete nainstalovat na jiných počítačích. Také ho můžete nainstalovat na svém vývojovém počítači, aby bylo rozšíření k dispozici v instanci hlavní aplikace Visual Studio.

### <a name="to-install-the-extension"></a>Chcete-li nainstalovat rozšíření

1. V projektu, který obsahuje **source.vsix.manifest**, otevřete *bin* adresáře v Průzkumníku souborů.

2. Kopírovat  **\*VSIX** soubor do počítače, na kterém chcete nainstalovat rozšíření.

3. V cílovém počítači dvakrát klikněte na soubor *.vsix v Průzkumníku Windows.

    Otevře se instalátor VSIX.

### <a name="to-uninstall-the-extension"></a>Chcete-li odinstalovat rozšíření

::: moniker range="vs-2017"

1. V sadě Visual Studio, zvolte **nástroje** > **rozšíření a aktualizace**.

::: moniker-end

::: moniker range=">=vs-2019"

1. V sadě Visual Studio, zvolte **rozšíření** > **spravovat rozšíření**.

::: moniker-end

2. Klikněte na název rozšíření a pak klikněte na tlačítko **odinstalovat**.

## <a name="install-an-extension-on-team-foundation-server"></a>Nainstalovat rozšíření serveru Team Foundation Server

Servery Team Foundation Server, obvykle nemají nainstalovanou sadu Visual Studio, a proto nelze nainstalovat VSIX poklepáním. Je nutné nainstalovat rozšíření ručně.

### <a name="to-install-your-layer-extension-on-a-team-foundation-server-server"></a>Instalace rozšíření vrstvy na serveru Team Foundation Server

1.  Kopírování. *vsix* soubory z vývojového počítače do počítače Team Foundation Server (TFS).

     Uložte soubor VSIX v jednom z následujících umístění:

    -   Instalace pro všechny uživatele a služby:

         %ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft

    -   Instalace pouze pro síťovou službu, který spouští sestavení:

         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

    -   Pokud jste nakonfigurovali sestavení ke spuštění v interaktivním režimu jako určitý uživatel, můžete nainstalovat pouze pro tohoto uživatele:

         %LocalAppData%\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

2.  Každý soubor VSIX rozbalte do složky ve stejném umístění:

    1.  Změna přípony názvu souboru z **VSIX** k **ZIP**.

    2.  Extrahujte obsah souboru .zip do složky.

    3.  Smazat soubor .zip

3.  Restartování serveru TFS.
