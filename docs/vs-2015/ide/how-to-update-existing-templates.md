---
title: 'Postupy: aktualizace existujících šablon | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- item templates, updating existing templates
- Visual Studio templates, updating existing templates
- project templates, updating existing templates
ms.assetid: d585e45b-7fe2-45fa-9cf3-7f2bc060f3c4
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9c5d091e58904cae058c5a2a5ade1b8ceec4c738
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666114"
---
# <a name="how-to-update-existing-templates"></a>Postupy: Aktualizace existujících šablon
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: aktualizace existujících šablon](https://docs.microsoft.com/visualstudio/ide/how-to-update-existing-templates).  
  
Po vytvoření šablony a soubory zkomprimujte do souboru .zip, můžete upravit šablonu. Můžete to provést ručně změnou soubory v šabloně, nebo tak, že vyexportujete novou šablonu z projektu, který je založen na šabloně.  
  
## <a name="using-the-export-template-wizard-to-update-an-existing-template"></a>Pomocí Průvodce exportem šablony, a aktualizovat existující šablony  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] poskytuje **exportovat šablonu** průvodce, který slouží k aktualizaci existující šablony.  
  
#### <a name="to-use-export-template-to-update-an-existing-template"></a>Chcete-li exportovat šablonu použít k aktualizaci existující šablony  
  
1.  Na **souboru** nabídky, klikněte na tlačítko **nový** a potom klikněte na tlačítko **nový projekt**.  
  
2.  Vyberte šablonu, kterou chcete aktualizovat, zadejte název a umístění dočasného projektu a klikněte na tlačítko **OK**.  
  
3.  Upravit projekt v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
4.  Na **souboru** nabídky, klikněte na tlačítko **exportovat šablonu**a použít **exportovat šablonu** Průvodce vytvořením nové šablony.  
  
5.  Po aktualizovanou šablonu zkomprimována do souboru .zip, odstraňte starý soubor ZIP šablony.  
  
## <a name="manually-updating-an-existing-template"></a>Ruční aktualizace existujících šablon  
 Můžete aktualizovat existující šablony mimo [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] tak, že upravíte soubor v komprimovaném souboru ZIP.  
  
#### <a name="to-manually-update-an-existing-template"></a>Chcete-li ručně aktualizovat existující šablony  
  
1.  Vyhledejte soubor .zip, který obsahuje šablonu. Ve výchozím nastavení je tento soubor umístěn ve Documents\Visual Studio *verze*\My exportované šablony\\.  
  
2.  Extrahujte soubor ZIP.  
  
3.  Upravit nebo odstranit aktuální soubory šablon nebo přidejte nové soubory do šablony.  
  
4.  Otevřít, upravit a uložit XML souboru .vstemplate pro zpracování aktualizované chování nebo nové soubory. Další informace o schématu .vstemplate naleznete v tématu [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md). Další informace o můžete parametrizovat ve zdrojových souborech najdete v tématu [parametry šablony](../ide/template-parameters.md)  
  
5.  Vyberte soubory do šablony, klikněte pravým tlačítkem, klikněte na tlačítko **odeslat**a potom klikněte na tlačítko **komprimovaná složka (metoda ZIP)**. Do souboru .zip jsou komprimované soubory, které jste vybrali.  
  
6.  Vložte nový soubor ZIP ve stejném adresáři jako starý soubor .zip.  
  
7.  Odstraňte extrahované soubory šablony a starý soubor ZIP šablony.  
  
8.  Spuštění (jako správce) instance Developer Command Prompt (v nabídce start v části **Visual Studio 2010 a Visual Studio Tools/Developer Command Prompt**).  
  
9. Spusťte následující příkaz: `devenv /installvstemplates`.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Parametry šablony](../ide/template-parameters.md)   
 [Postupy: Vytváření startovních sad](../ide/how-to-create-starter-kits.md)



