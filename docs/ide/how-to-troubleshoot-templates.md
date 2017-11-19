---
title: "Postupy: řešení problémů se šablonami | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio templates, troubleshooting
ms.assetid: 3e577ad2-f725-4c11-93b3-477f2404ec81
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: af00efbeb759bfc41d12e0ab814ecadd4bbc7799
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-troubleshoot-templates"></a>Postupy: Řešení problémů se šablonami
Pokud šablonu se nepodaří načíst ve vývojovém prostředí, existuje několik způsobů, jak vyhledat potíže.  
  
## <a name="validating-the-vstemplate-file"></a>Ověření .vstemplate souboru  
 Pokud soubor .vstemplate v šabloně není ve správném [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] schéma šablony, šablona se nemusí zobrazit v **nový projekt** dialogové okno.  
  
#### <a name="to-validate-the-vstemplate-file"></a>K ověření souboru .vstemplate  
  
1.  Vyhledejte soubor .zip, který obsahuje šablony.  
  
2.  Rozbalte soubor .zip.  
  
3.  Na **soubor** nabídky v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], klikněte na tlačítko **otevřete**a potom klikněte na **soubor**.  
  
4.  Vyberte soubor .vstemplate pro šablonu a klikněte na tlačítko **otevřete**.  
  
5.  Ověřte, že soubor XML soubor .vstemplate dodržuje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] schéma šablony. Další informace o schématu .vstemplate najdete v tématu [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md).  
  
    > [!NOTE]
    >  Chcete-li získat podporu technologie IntelliSense při vytváření souboru .vstemplate, přidejte `xmlns` atribut `VSTemplate` elementu a přiřaďte ho hodnotu http://schemas.microsoft.com/developer/vstemplate/2005.  
  
6.  Uložte a zavřete soubor .vstemplate.  
  
7.  Vyberte soubory obsažené v šabloně, klikněte pravým tlačítkem, vyberte **odeslat**a klikněte na tlačítko **komprimované složky (ZIP)**. Do souboru .zip jsou komprimované soubory, které jste vybrali.  
  
8.  Nový soubor .zip umístíte ve stejném adresáři jako starý soubor .zip.  
  
9. Odstraňte extrahované soubory šablony a původní soubor .zip šablony.  
  
## <a name="monitoring-the-event-log"></a>Monitorování protokolu událostí  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]protokoly chyb zjištěných při zpracování souborů .zip. Pokud šablonu nezobrazuje v **nový projekt** dialogové okno jako očekávání, můžete použít **Prohlížeč událostí** k odstranění problému.  
  
#### <a name="to-locate-template-errors-in-event-viewer"></a>V prohlížeči událostí vyhledejte chyby šablony  
  
1.  V systému Windows, klikněte na tlačítko **spustit**, klikněte na tlačítko **ovládací panely**, dvakrát klikněte na **nástroje pro správu**a potom dvakrát klikněte na **Prohlížeč událostí**.  
  
2.  V levém podokně klikněte na **aplikace**.  
  
3.  Vyhledejte události s **zdroj** hodnotu `Visual Studio - VsTemplate`.  
  
4.  Dvakrát klikněte na šablonu události chcete-li zobrazit chyba.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)