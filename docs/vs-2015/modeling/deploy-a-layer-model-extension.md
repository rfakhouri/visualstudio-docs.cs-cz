---
title: Nasazení rozšíření pro modelování vrstev | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- layer diagrams, deploying extensions
- layer models, deploying extensions
ms.assetid: 00a4675b-d20e-487e-8fd5-be2b1e0ba238
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a58adf1be92655a6ca7846e8c1d7ea41515b7109
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63422666"
---
# <a name="deploy-a-layer-model-extension"></a>Nasazení rozšíření pro modelování vrstev
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ostatní uživatelé sady Visual Studio můžete nainstalovat rozšíření, které vytvoříte pomocí sady Visual Studio modelování vrstev.  
  
## <a name="installing-your-extension"></a>Instalace rozšíření  
 Rozšíření je kompilováno do souboru VSIX, který si můžete nainstalovat na jiných počítačích. Také ho můžete nainstalovat na svém vývojovém počítači, aby bylo rozšíření k dispozici v instanci hlavní aplikace Visual Studio.  
  
#### <a name="to-install-the-extension"></a>Chcete-li nainstalovat rozšíření  
  
1. V projektu, který obsahuje **source.vsix.manifest**, otevřete **bin\\\\*** v Průzkumníku souborů.  
  
2. Kopírovat  **\*VSIX** soubor do počítače, na kterém chcete nainstalovat rozšíření.  
  
3. V cílovém počítači dvakrát klikněte na soubor *.vsix v Průzkumníku Windows.  
  
    Otevře se instalátor VSIX.  
  
#### <a name="to-uninstall-the-extension"></a>Chcete-li odinstalovat rozšíření  
  
1. V sadě Visual Studio na **nástroje** nabídky, klikněte na tlačítko **rozšíření a aktualizace**.  
  
2. Klikněte na název rozšíření a pak klikněte na tlačítko **odinstalovat**.  
  
## <a name="installing-an-extension-on-a-team-foundation-build-server"></a>Instalace rozšíření na serveru Team Foundation Build  
 [!INCLUDE[esprbuild](../includes/esprbuild-md.md)] servery obvykle nemají nainstalovanou sadu Visual Studio, a proto nelze nainstalovat VSIX poklepáním. Instalace [!INCLUDE[esprbuild](../includes/esprbuild-md.md)] obsahuje některé součásti umožňující spustit příponu VSIX, ale je nutné nainstalovat rozšíření ručně.  
  
#### <a name="to-install-your-layer-extension-on-a-includeesprbuildincludesesprbuild-mdmd-server"></a>Instalace rozšíření vrstvy na [!INCLUDE[esprbuild](../includes/esprbuild-md.md)] serveru  
  
1. Kopírovat **VSIX** soubory z vývojového počítače do [!INCLUDE[esprbuild](../includes/esprbuild-md.md)] počítače.  
  
     Uložte soubor VSIX v jednom z následujících umístění:  
  
    - Instalace pro všechny uživatele a služby:  
  
         %ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft  
  
    - Chcete-li nainstalovat pouze pro síťovou službu, na kterém běží [!INCLUDE[esprbuild](../includes/esprbuild-md.md)]:  
  
         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[version]\Extensions\Microsoft  
  
    - Pokud jste nakonfigurovali [!INCLUDE[esprbuild](../includes/esprbuild-md.md)] ke spuštění v interaktivním režimu jako určitý uživatel, můžete nainstalovat pouze pro tohoto uživatele:  
  
         %LocalAppData%\Microsoft\VisualStudio\\[version]\Extensions\Microsoft  
  
        > [!NOTE]
        > % LocalAppData % je obvykle *DriveName*: uživatelé*uživatelské jméno*AppDataLocal.  
  
2. Každý soubor VSIX rozbalte do složky ve stejném umístění:  
  
    1. Změna přípony názvu souboru z **VSIX** k **ZIP**.  
  
    2. Extrahujte obsah souboru .zip do složky.  
  
    3. Smazat soubor .zip  
  
3. Restartujte [!INCLUDE[esprbuild](../includes/esprbuild-md.md)].
