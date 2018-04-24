---
title: Nasazení rozšíření pro modelování vrstev
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: d44e5deaa9e631255d0a4f36d7b5f175b7d14611
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="deploy-a-layer-model-extension"></a>Nasazení rozšíření pro modelování vrstev
Ostatní uživatelé sady Visual Studio můžete nainstalovat vrstvy modelování rozšíření, které vytvoříte pomocí sady Visual Studio.

## <a name="installing-your-extension"></a>Instalace rozšíření
 Toto rozšíření je kompilovat, do souboru VSIX, který můžete nainstalovat na jiných počítačích. Můžete taky nainstalovat ho na vývojovém počítači, aby rozšíření k dispozici v hlavní instance sady Visual Studio.

#### <a name="to-install-the-extension"></a>Chcete-li nainstalovat rozšíření

1.  V projektu, který obsahuje **source.vsix.manifest**, otevřete **bin\\ \***  v Průzkumníku souborů.

2.  Kopírování  **\*VSIX** soubor do počítače, na kterém chcete nainstalovat rozšíření.

3.  Na cílovém počítači poklikejte na soubor *.vsix v Průzkumníku Windows.

     Otevře se VSIX Instalační služby.

#### <a name="to-uninstall-the-extension"></a>Chcete-li odinstalovat rozšíření

1.  V sadě Visual Studio na **nástroje** nabídky, klikněte na tlačítko **rozšíření a aktualizace**.

2.  Klikněte na název rozšíření a potom klikněte na **odinstalovat**.

## <a name="installing-an-extension-on-a-team-foundation-build-server"></a>Instalace rozšíření na serveru Team Foundation Build
 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] servery obvykle nemají nainstalovanou sadu Visual Studio, a proto nemůžete nainstalovat VSIX poklepáním. Instalace [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] zahrnuje některé součásti, které umožňují rozšíření VSIX ke spuštění, ale musíte nainstalovat rozšíření ručně.

#### <a name="to-install-your-layer-extension-on-a-includeesprbuildmiscincludesesprbuildmdmd-server"></a>K instalaci rozšíření vrstvy na [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] serveru

1.  Kopírování **VSIX** soubory z počítače pro vývoj [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] počítače.

     Umístěte soubor VSIX v jednom z následujících umístění:

    -   Instalace pro všechny uživatele a služby:

         \Common7\IDE\Extensions\Microsoft %ProgramFiles%\Microsoft visual Studio [verze]

    -   Chcete-li nainstalovat pouze pro síťovou službu, který spouští [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]:

         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

    -   Pokud jste nakonfigurovali [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] spustit v interaktivním režimu jako určitého uživatele, můžete nainstalovat pouze pro tohoto uživatele:

         %LocalAppData%\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

        > [!NOTE]
        >  % LocalAppData % je obvykle *DriveName*: uživatelé*uživatelské jméno*AppDataLocal.

2.  Rozbalením každého VSIX souboru do složky, ve stejném umístění:

    1.  Změňte příponu názvu souboru z **VSIX** k **.zip**.

    2.  Extrahování obsahu souboru ZIP do složky.

    3.  Odstranit soubor .zip

3.  Restartujte [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)].
