---
title: "Ve službě jazyk starší zvýrazňování syntaxe | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- syntax coloring
- language services, syntax coloring
ms.assetid: f65ff67e-8c20-497a-bebf-5e2a5b5b012f
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 88af397feba9b06eabd73ec23dcf1204ebe755e6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="syntax-coloring-in-a-legacy-language-service"></a>Ve službě jazyk starší zvýrazňování syntaxe
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]barevné zvýrazňování služby se používá k identifikaci elementy jazyka a jejich zobrazení pomocí zadaného barev v editoru.  
  
## <a name="colorizer-model"></a>Colorizer modelu  
 Implementuje služba jazyka <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> rozhraní, což je pak používaný editory. Tato implementace je samostatný objekt ze služby jazyk, jak je znázorněno na následujícím obrázku.  
  
 ![Obrázek SVC Colorizer](../../extensibility/internals/media/figlgsvccolorizer.gif "FigLgSvcColorizer")  
Jednoduché colorizer modelu  
  
> [!NOTE]
>  Je oddělená od obecné služby zvýrazňování syntaxe [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] mechanismus pro barevné text. Další informace o Obecné [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] mechanismus podpora barevné, najdete v části [pomocí písma a barev](../../extensibility/using-fonts-and-colors.md).  
  
 Kromě toho colorizer služba jazyka můžete zadat vlastní colorable položky, které jsou používány inzerování poskytne vlastní colorable položky pomocí editoru. To provedete tím, že implementujete <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> rozhraní na stejný objekt, který implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> rozhraní. Vrátí počet položek vlastní colorable při volání editoru <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> metodu a vrátí jednotlivé položky vlastní colorable při volání editoru <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> metoda.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> Metoda vrátí objekt, který implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> rozhraní. Pokud služba jazyka podporuje barvu 24bitový nebo vysoké hodnoty, musí implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> rozhraní na stejný objekt, jako <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> rozhraní.  
  
## <a name="how-a-vspackage-uses-a-language-service-colorizer"></a>Jak VSPackage používá Colorizer služby jazyk  
  
1.  VSPackage musí získat služby odpovídající jazyk, který vyžaduje službu jazyk VSPackage provést následující akce:  
  
    1.  Použít implementaci objektu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> rozhraní se získat text, který má být obarvené.  
  
         Zobrazí se text obvykle pomocí objektu, který implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> rozhraní.  
  
    2.  Získáte jazyk služby dotazováním služby zprostředkovatele VSPackage pro službu jazyk identifikátor GUID. Jazyk služby jsou označeny v registru příponu souboru.  
  
    3.  Přidružení službu jazyk s <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> voláním jeho <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> metoda.  
  
2.  VSPackage teď můžete získat a použít objekt colorizer následujícím způsobem:  
  
    > [!NOTE]
    >  VSPackages používající editoru jádra není nutné získat jazyk služby colorizer objekty explicitně. Jakmile instance editoru základní obdrží služby odpovídající jazyk, provede všechny úlohy zabarvení zobrazeny zde.  
  
    1.  Získejte objekt colorizer služba jazyka, který implementuje `T:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer`, a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2> rozhraní voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> metodu služba jazyka <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> objektu.  
  
    2.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> metoda se získat informace o colorizer pro konkrétní rozpětí textu.  
  
         <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>Vrátí pole hodnot, jednu pro každý znak v právě obarvené rozpětí textu. Hodnoty jsou indexy do colorable položku seznamu, který je výchozím seznamu colorable položky spravuje pomocí editoru základní nebo vlastní colorable položky seznamu udržované samotnou službu jazyka.  
  
    3.  Vrácené informace zabarvení <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> metodu pro zobrazení vybraný text.  
  
> [!NOTE]
>  Kromě použití colorizer služby jazyk, VSPackage můžete použít pro obecné účely [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] text zvýrazňování mechanismus. Další informace o tento mechanismus najdete v tématu [pomocí písma a barev](../../extensibility/using-fonts-and-colors.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Implementace barevné zvýrazňování syntaxe](../../extensibility/internals/implementing-syntax-coloring.md)  
 Popisuje, jak přistupuje k editoru barevné zvýrazňování syntaxe a služba jazyka musí implementace pro podporu syntaxe zvýrazňování služba jazyka.  
  
 [Postupy: použití předdefinované Colorable položek](../../extensibility/internals/how-to-use-built-in-colorable-items.md)  
 Ukazuje, jak používat integrované colorable položek ze služby jazyk.  
  
 [Vlastní Colorable položky](../../extensibility/internals/custom-colorable-items.md)  
 Popisuje, jak implementovat vlastní colorable položky.  
  
## <a name="see-also"></a>Viz také  
 [Pomocí písma a barev](../../extensibility/using-fonts-and-colors.md)