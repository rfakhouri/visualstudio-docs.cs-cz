---
title: "Postupy: vytváření šablon projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ExportTemplateWizard
helpviewer_keywords:
- Visual Studio templates, creating project templates
- project templates, metadata files
- Visual Studio templates, project templates
- project templates, custom template locations
- project templates, creating
ms.assetid: a1a6999d-a34c-48a8-b1cf-027eb5c76398
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a473ac2be65acc9b08455fe687b52468f5ca9fa6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-project-templates"></a>Postupy: Vytváření šablon projektu
Tento postup umožňuje vytvářet šablony pomocí **exportovat šablonu** průvodce, který balíčky šablony do souboru ZIP. Můžete také vytvořit šablony ve formátu souboru VSIX pro vylepšené nasazení pomocí rozšíření Průvodce exportem šablony, nebo pomocí šablony, které jsou součástí [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)], nebo můžete ručně vytvořit šablony.  
  
### <a name="to-create-a-custom-project-template-with-the-standard-export-template-wizard"></a>Vytvoření vlastní šablonu projektu pomocí Průvodce standardní šablony exportu.  
  
1.  Vytvořte projekt.  
  
    > [!NOTE]
    >  Používejte pouze platný identifikátor – znaky pojmenování projektu, který bude sloužit jako zdroj pro šablonu. Šablona exportovaná z projektu s názvem se neplatné znaky může způsobit chyby při kompilaci v budoucnosti projekty založené na šabloně. Další informace o platný identifikátor – znaky naleznete v tématu [deklarované názvy elementů](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names).  
  
2.  Upravte projekt, dokud je připraven k exportu jako šablona.  
  
3.  Podle potřeby upravte soubory kódu k označení, kde by měl proběhnout nahrazení parametru. Další informace o nahrazování parametru najdete v tématu [postup: Substitute parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md).  
  
4.  Na **projektu** nabídky, klikněte na tlačítko **exportovat šablonu**. **Exportovat šablonu** otevře se průvodce.  
  
5.  Klikněte na tlačítko **projektu šablony**.  
  
6.  Pokud máte více než jeden projekt v aktuálním řešení, vyberte projekty, které chcete provést export do šablony.  
  
7.  Klikněte na tlačítko **Další**.  
  
8.  Vyberte ikonu a náhled obrázku pro vaši šablonu. Tyto se zobrazí v **nový projekt** dialogové okno.  
  
9. Zadejte název šablony a popis.  
  
10. Klikněte na tlačítko **Dokončit**. Projekt je exportovali do souboru ZIP a umístit do zadané výstupní složky a pokud je vybrána, importovat do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     Pokud máte [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] nainstalován, můžete zabalit dokončenou šablonu v soubor VSIX pro nasazení pomocí **projektu VSIX** šablony. Další informace najdete v tématu [Začínáme s šablona projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Postupy: vytváření šablon položek](../ide/how-to-create-item-templates.md)
