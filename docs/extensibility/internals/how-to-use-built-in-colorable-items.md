---
title: "Postupy: použití předdefinované Colorable položek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 519b842f99ff3e4460626b82aafd24a02f9e720d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-built-in-colorable-items"></a>Postupy: použití předdefinované Colorable položek
Než použijete integrovanou colorable položky, můžete musí nejprve signál integrované vývojové prostředí (IDE), nejsou poskytuje svoje vlastní vlastní colorable položky, které v tomto případě by byly <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> objekty. To provedete nastavením položky registru pro službu jazyka.  
  
### <a name="to-use-built-in-colorable-items"></a>Chcete-li použít předdefinované colorable položky  
  
1.  V části HKEY_LOCAL_MACHINE\VisualStudio\\*X.Y*\Languages\Language služby\\*název jazyka*, kde *X.Y* verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a *název jazyka* je název jazyka, vytvořit hodnotu položky registru DWORD s názvem `RequestStockColors`.  
  
2.  Nastavte `RequestStockColors` hodnotu položky registru na 1.  
  
     Po vytvoření položka registru, vaše colorizer <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> metoda může používat členů <xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS> výčtu vyplnit pole barev atributy pro použití v editoru.  
  
    > [!NOTE]
    >  Pokud zadáte vlastní colorable položky není nastavena tato položka registru. Další informace najdete v tématu [vlastní Colorable položky](../../extensibility/internals/custom-colorable-items.md).  
  
## <a name="see-also"></a>Viz také  
 [Vlastní editorů zvýrazňování syntaxe](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [Ve službě jazyk starší zvýrazňování syntaxe](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [Implementace barevné zvýrazňování syntaxe](../../extensibility/internals/implementing-syntax-coloring.md)   
 [Vlastní Colorable položky](../../extensibility/internals/custom-colorable-items.md)   
 [Registrace služby jazyk starší verze](../../extensibility/internals/registering-a-legacy-language-service2.md)