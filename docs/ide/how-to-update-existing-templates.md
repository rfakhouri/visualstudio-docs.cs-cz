---
title: "Postupy: aktualizace existujících šablon | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- item templates, updating existing templates
- Visual Studio templates, updating existing templates
- project templates, updating existing templates
ms.assetid: d585e45b-7fe2-45fa-9cf3-7f2bc060f3c4
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0fffcc55953e394c5efd00b86949f04474a66111
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-update-existing-templates"></a>Postupy: aktualizace existujících šablon
Po vytvoření šablony a komprimovat soubory do souboru ZIP, můžete upravit šablonu. Můžete to provést ruční změnou soubory v šabloně, nebo tak, že vyexportujete novou šablonu z projektu, který je založený na šabloně.  
  
## <a name="using-the-export-template-wizard-to-update-an-existing-template"></a>Pomocí Průvodce šablonou exportovat, a aktualizovat existující šablony  
Visual Studio poskytuje **exportovat šablonu** průvodce, který slouží k aktualizaci existující šablony.  
  
#### <a name="to-use-export-template-to-update-an-existing-template"></a>Chcete-li exportovat šablonu použít k aktualizaci existující šablony  
  
1.  Otevřete **nový projekt** dialogové okno a vybrat **soubor**, **nový**, **projektu**.  
  
2.  Vyberte šablonu, kterou chcete aktualizovat, zadejte název a umístění pro svůj projekt a zvolte **OK**.  
  
3.  Změňte na projekt v sadě Visual Studio.  
  
4.  Na **projektu** nabídce zvolte **exportovat šablonu**.  

    **Průvodce exportem šablony** otevře.  

5.  Postupujte podle pokynů v Průvodci vyexportujte šablonu jako soubor ZIP.  

6.  Odstraňte původní soubor .zip šablony.  
  
## <a name="manually-updating-an-existing-template"></a>Ruční aktualizace existující šablony  
Úprava souborů v komprimovaném souboru ZIP, můžete aktualizovat existující šablony mimo Visual Studio.  
  
#### <a name="to-manually-update-an-existing-template"></a>Chcete-li ručně aktualizovat existující šablony  
  
1.  Vyhledejte soubor .zip, který obsahuje šablony. Ve výchozím nastavení je tento soubor umístěný ve %USERPROFILE%\Documents\Visual Studio \<verze\>\My Export šablony\.  
  
2.  Rozbalte soubor .zip.  
  
3.  Upravit nebo odstranit aktuální soubory šablon nebo přidejte nové soubory do šablony.  
  
4.  Otevřít, upravit a uložit .vstemplate soubor XML pro zpracování chování aktualizované nebo nové soubory.  

    Další informace o schématu .vstemplate najdete v tématu [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md). Další informace o můžete parametrizovat ve zdrojových souborech najdete v tématu [parametry šablony](../ide/template-parameters.md).  
  
5.  Vyberte soubory v šabloně, klikněte pravým tlačítkem myši, vyberte **odeslat**a potom zvolte **komprimované složky (ZIP)**.  

    Do souboru .zip jsou komprimované soubory, které jste vybrali.  
  
6.  Nový soubor .zip umístěte do stejného adresáře jako starý soubor .zip.  
  
7.  Odstraňte extrahované soubory šablony a původní soubor .zip šablony.  
  
8.  Spuštění z příkazového řádku vývojáře zvýšenými instance:  

  1. V nabídce Start, přejděte na **Visual Studio \<verze\>**, **příkazový řádek vývojáře**.  

  2. Z nabídky kontextu (klikněte pravým tlačítkem), zvolte **Další**, **spustit jako správce**.  
  
9. Spusťte následující příkaz: `devenv /installvstemplates`.  
  
## <a name="see-also"></a>Viz také  
[Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)   
[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
[Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
[Parametry šablony](../ide/template-parameters.md)   
[Postupy: vytváření Startovních sad](../ide/how-to-create-starter-kits.md)