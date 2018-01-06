---
title: "Nasazení rozšíření pro modelování vrstev | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
ms.assetid: 00a4675b-d20e-487e-8fd5-be2b1e0ba238
caps.latest.revision: "27"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.workload: multiple
ms.openlocfilehash: 0569b5cced2100e1ed3b746464b001d929a209be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]servery obvykle nemají nainstalovanou sadu Visual Studio, a proto nemůžete nainstalovat VSIX poklepáním. Instalace [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] zahrnuje některé součásti, které umožňují rozšíření VSIX ke spuštění, ale musíte nainstalovat rozšíření ručně.  
  
#### <a name="to-install-your-layer-extension-on-a-includeesprbuildmiscincludesesprbuildmdmd-server"></a>K instalaci rozšíření vrstvy na [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] serveru  
  
1.  Kopírování **VSIX** soubory z počítače pro vývoj [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] počítače.  
  
     Umístěte soubor VSIX v jednom z následujících umístění:  
  
    -   Instalace pro všechny uživatele a služby:  
  
         \Common7\IDE\Extensions\Microsoft %ProgramFiles%\Microsoft visual Studio [verze]  
  
    -   Chcete-li nainstalovat pouze pro síťovou službu, který spouští [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]:  
  
         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\\Extensions\Microsoft [verze]  
  
    -   Pokud jste nakonfigurovali [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] spustit v interaktivním režimu jako určitého uživatele, můžete nainstalovat pouze pro tohoto uživatele:  
  
         %LocalAppData%\Microsoft\VisualStudio\\\Extensions\Microsoft [verze]  
  
        > [!NOTE]
        >  % LocalAppData % je obvykle *DriveName*: uživatelé*uživatelské jméno*AppDataLocal.  
  
2.  Rozbalením každého VSIX souboru do složky, ve stejném umístění:  
  
    1.  Změňte příponu názvu souboru z **VSIX** k **.zip**.  
  
    2.  Extrahování obsahu souboru ZIP do složky.  
  
    3.  Odstranit soubor .zip  
  
3.  Restartujte [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)].
