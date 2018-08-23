---
title: 'Postupy: řešení problémů se šablonami | Dokumentace Microsoftu'
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
- Visual Studio templates, troubleshooting
ms.assetid: 3e577ad2-f725-4c11-93b3-477f2404ec81
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b249fe28f91a8dfb24e73ab86f785103910ee9d9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675590"
---
# <a name="how-to-troubleshoot-templates"></a>Postupy: Řešení problémů se šablonami
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: řešení potíží s šablony](https://docs.microsoft.com/visualstudio/ide/how-to-troubleshoot-templates).  
  
Pokud šablonu se nepodaří načíst ve vývojovém prostředí, nalezení problému několika způsoby.  
  
## <a name="validating-the-vstemplate-file"></a>Ověřování souboru .vstemplate  
 Pokud soubor .vstemplate v šabloně nedrží se [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] schéma šablony, šablony se nemůže nacházet v **nový projekt** dialogové okno.  
  
#### <a name="to-validate-the-vstemplate-file"></a>K ověření souboru .vstemplate  
  
1.  Vyhledejte soubor .zip, který obsahuje šablonu.  
  
2.  Extrahujte soubor ZIP.  
  
3.  Na **souboru** v nabídce [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], klikněte na tlačítko **otevřít**a potom klikněte na tlačítko **souboru**.  
  
4.  Vyberte soubor .vstemplate šablony a klikněte na tlačítko **otevřít**.  
  
5.  Ověřte, že kód XML souboru .vstemplate dodržuje [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] schéma šablony. Další informace o schématu .vstemplate naleznete v tématu [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md).  
  
    > [!NOTE]
    >  Chcete-li získat podporu technologie IntelliSense při vytváření souboru .vstemplate, přidejte `xmlns` atribut `VSTemplate` element a přiřaďte ho hodnotu http://schemas.microsoft.com/developer/vstemplate/2005.  
  
6.  Uložte a zavřete soubor .vstemplate.  
  
7.  Vyberte soubory, které jsou součástí šablony, klikněte pravým tlačítkem, vyberte **odeslat**a klikněte na tlačítko **komprimovaná složka (metoda ZIP)**. Do souboru .zip jsou komprimované soubory, které jste vybrali.  
  
8.  Nový soubor ZIP umístíte ve stejném adresáři jako starý soubor .zip.  
  
9. Odstraňte extrahované soubory šablony a starý soubor ZIP šablony.  
  
## <a name="monitoring-the-event-log"></a>Monitorování protokolu událostí  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] protokoly chyb zjištěných při zpracování šablony soubory .zip. Pokud šablona není uveden v **nový projekt** dialogové okno jako očekávání, můžete použít **Prohlížeč událostí** k odstranění tohoto problému.  
  
#### <a name="to-locate-template-errors-in-event-viewer"></a>V prohlížeči událostí vyhledejte chyby šablony  
  
1.  Ve Windows, klikněte na tlačítko **Start**, klikněte na tlačítko **ovládací panely**, dvakrát klikněte na panel **nástroje pro správu**a potom dvakrát klikněte na **Prohlížeč událostí**.  
  
2.  V levém podokně klikněte na tlačítko **aplikace**.  
  
3.  Vyhledat události se **zdroj** hodnotu `Visual Studio - VsTemplate`.  
  
4.  Dvakrát klikněte na šablonu událost, abyste viděli chybu.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)



