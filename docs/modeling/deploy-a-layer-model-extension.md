---
title: "Nasazení rozšíření pro modelování vrstev | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 311add860016c914aab232ffad6e3a4efadb15c9
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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
  
         %ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft  
  
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
