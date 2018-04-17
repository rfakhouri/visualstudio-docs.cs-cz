---
title: Vlastní položky Colorable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- colorable items
- language services, custom colorable items
ms.assetid: b4d0ddee-c04b-48dc-ba82-f6068570cef0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b23ff39abcb9a1354ea28becab3b7df867378ddf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="custom-colorable-items"></a>Vlastní Colorable položky
Seznam typů můžete přepsat pro barevné, jako jsou klíčová slova a komentáře, implementovat vlastní colorable položky v rámci služby jazyk.  
  
## <a name="user-settings-of-colorable-items"></a>Uživatelská nastavení Colorable položek  
 Můžete zobrazit **písma a barev** dialogové okno výběrem **možnosti** na **nástroje** nabídky a pak vybrat **písma a barev** v části **prostředí**. Když vyberete zobrazení, jako například **textového editoru** nebo **příkazové okno**, **zobrazení položek** seznamu jsou uvedeny všechny colorable položky pro zobrazované. Můžete zobrazit a změnit písmo, velikost, barvu popředí a barvu pozadí pro každou colorable položku. Vaše možnosti jsou uloženy v mezipaměti v registru a přístup název colorable položky.  
  
## <a name="presentation-of-colorable-items"></a>Prezentace Colorable položek  
 Protože zpracovává přepsání uživatele colorable položek v prostředí IDE **písma a barev** dialogové okno, je třeba zadat pouze Každá vlastní colorable položka s názvem. Tento název se zobrazí v **zobrazení položek** seznamu. Zobrazí se v abecedním pořadí colorable položky. Pokud chcete seskupit služba jazyka vlastní colorable položky, můžete začít každý název nahraďte názvem jazyk, například **NewLanguage - komentář** a **NewLanguage – klíčové slovo**.  
  
> [!CAUTION]
>  Název položky colorable předejdete kolizí se stávajícími názvy colorable položky by měla obsahovat název jazyka. Pokud změníte název jednoho colorable položek během vývoje, je nutné obnovit mezipaměti, který byl vytvořen při prvním colorable položek měla přístup. Můžete resetovat experimentální mezipaměti pomocí nástroje CreateExpInstance, která se instaluje s Visual Studio SDK, obvykle v adresáři  
>   
>  **C:\Program soubory (x86) \Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin**  
>   
>  Chcete-li obnovit do mezipaměti, volejte `CreateExpInstance /Reset`. Další informace o CreateExpInstance najdete v tématu [CreateExpInstance nástroj](../../extensibility/internals/createexpinstance-utility.md).  
  
 První položka v seznamu položek colorable se nikdy odkazuje. První položka odpovídá index colorable položky 0, a [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vždy poskytuje výchozí text barvy a atributy pro tuto položku. Nejjednodušším způsobem práci s touto položkou neregistrované je zadat položku colorable zástupný symbol v seznamu jako první položka.  
  
## <a name="implementing-custom-colorable-items"></a>Implementace vlastních Colorable položky  
  
1.  Definujte, co musí být obarvené v jazyce, například – klíčové slovo, operátor a identifikátor.  
  
2.  Vytvořte výčet těchto colorable položek.  
  
3.  Přidružení tokenu typů vrácena z analyzátor nebo skener s výčtové hodnoty.  
  
     Hodnoty představující typy tokenů může být například stejné hodnoty výčtu vlastní colorable položky.  
  
4.  Vaše implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> metoda ve vaší <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> objektu, k naplnění seznamu atributy s hodnotami z výčtu vaše vlastní colorable položky odpovídající typy tokenů vrácena z analyzátor nebo skener.  
  
5.  Ve stejné třídě, která implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> rozhraní, implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> rozhraní a jeho dvě metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A>.  
  
6.  Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> rozhraní.  
  
7.  Pokud chcete podporovat barvu 24bitový nebo vysoké hodnoty, implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> rozhraní.  
  
8.  V objektu služby jazyk, vytvoří seznam, který obsahuje vaše <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> objekty, jeden pro každou colorable položku analyzátor nebo skener můžete identifikovat.  
  
     Každou položku v seznamu můžete přistupovat pomocí odpovídající hodnotu z výčtu vlastní colorable položky. Použijte hodnoty výčtu jako index do seznamu. První položka v seznamu se nikdy získat přístup, protože odpovídá text výchozí styl [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vždy zpracovává sám sebe. Můžete kompenzovat to vložením colorable položku zástupný symbol na začátku seznamu.  
  
9. V implementaci <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> metoda, vrátí počet položek v seznamu vlastní colorable položky.  
  
10. V implementaci <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> metoda, vrátí požadovaná colorable položka ze seznamu.  
  
 Příklad implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> rozhraní, najdete v části <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem>.  
  
## <a name="see-also"></a>Viz také  
 [Model služby jazyk starší verze](../../extensibility/internals/model-of-a-legacy-language-service.md)   
 [Vlastní editorů zvýrazňování syntaxe](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [Ve službě jazyk starší zvýrazňování syntaxe](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [Implementace barevné zvýrazňování syntaxe](../../extensibility/internals/implementing-syntax-coloring.md)   
 [Postupy: Použití předdefinovaných položek, které lze zabarvit](../../extensibility/internals/how-to-use-built-in-colorable-items.md)