---
title: "Písma a barev přehled | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], font and color
- font and color control [Visual Studio SDK], editors
ms.assetid: 2203e4e7-8b7f-44ec-8884-6ff718d4f278
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 13a2a8b584af507f8937fd6abb46c85f329de0b6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="font-and-color-overview"></a>Písma a barev – přehled
Toto téma popisuje nastavení písma a barvy textu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Je také seznámíte se základními pojmy, kategorie a zobrazení položek a se popisuje, jak VSPackages a editoru základní použít atributy textu.  
  
## <a name="the-fonts-and-colors-property-page"></a>Písma a barvy stránky vlastností  
 Můžete spravovat atributy zobrazeného textu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) prostřednictvím **písma a barev** stránku vlastností. Najít **písma a barev** vlastnost na stránce **nástroje** nabídky, klikněte na tlačítko **možnosti**. Rozbalte položku **prostředí**a potom klikněte na **písma a barev**.  
  
## <a name="categories-and-display-items"></a>Kategorie a zobrazit položky  
 Písma a barev jsou uspořádány do **kategorie** a **zobrazení položky**.  
  
-   A **kategorie** je logické nebo funkční kontejner pro počet **zobrazení položky**.  
  
     Seznam **kategorie** v **zobrazit nastavení pro** rozevíracího pole **písma a barev** stránku vlastností.  
  
-   A **zobrazení položky** je dobře definovaný textu entity jako komentář, řetězce nebo ovládací prvek strukturu, která má být obarvené při zobrazení.  
  
 Každý **zobrazení položky** je jedinečně definované v rámci **kategorie** který ji obsahuje. V důsledku toho více než jeden **kategorie** může mít **zobrazení položky** se stejným názvem.  
  
## <a name="vspackage-control-of-fonts-and-colors"></a>Řízení VSPackage písma a barev  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Umožňuje VSPackages na:  
  
-   Definování písma a barev **kategorie**.  
  
-   Zadejte písma a barvy, používá se k předložení **zobrazení položky**.  
  
-   Komunikovat s **písma a barev** stránku vlastností.  
  
-   Agregace více **kategorie** do skupin.  
  
-   Zachování změn ve výchozím nastavení.  
  
 Existují dva způsoby, jak pracovat s výběr písma a barev v rámci [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)].  
  
-   Dá se označuje jako *barevné zvýraznění syntaxe*. Je používána VSPackage, který upravuje existující [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] editor k implementaci jazykové služby a vytvořte zdroj editor.  
  
     Pouze jeden **kategorie** konkrétně podporuje tento mechanismus, **textového editoru**.  
  
-   Další obecné alternativní podporuje jiných **kategorie** a součásti uživatelského rozhraní než editoru zdroje při zobrazení textu. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>.  
  
## <a name="core-editor-text-settings"></a>Text editoru základní nastavení  
 Se řídí nastavení písma a barvy pro základní editor objektu služby jazyka **Text EditorCategory** najít v **zobrazit nastavení pro** rozevíracího pole **písma a barev** stránku vlastností.  
  
 Při práci s editory, byste měli použít speciální písma a mechanismu řízení barev, které poskytuje služby jazyk k řízení a rozšířit **textového editoru** nastavení. Tento mechanismus se označuje jako *barevné zvýrazňování syntaxe* a poskytuje:  
  
-   Zjednodušená technika pro správu písma a barev zobrazení položek.  
  
     Další informace naleznete v tématu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem>.  
  
-   Dobře definovaný a optimalizované zabarvení mechanismus.  
  
     Další informace naleznete v tématu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>.  
  
-   Možnost obě použití předdefinovaných zobrazení položek z **Text EditorCategory** a rozšířit je.  
  
     Další informace najdete v tématu [postupy: používání předdefinovaných Colorable položky](../extensibility/internals/how-to-use-built-in-colorable-items.md) a [vlastní Colorable položky](../extensibility/internals/custom-colorable-items.md).  
  
-   Automatické trvalost aktuálního stavu z obou předdefinované a vlastní zobrazit položky, které **textového editoru** kategorie.  
  
 Další informace o najdete zvýrazňování syntaxe [zvýrazňování syntaxe ve službě jazyk starší](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md).  
  
## <a name="see-also"></a>Viz také  
 [Starší verze rozhraní v editoru](../extensibility/legacy-interfaces-in-the-editor.md)   
 [Ve službě jazyk starší zvýrazňování syntaxe](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)