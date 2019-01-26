---
title: 'Postupy: Použití předdefinovaných položek které lze zabarvit | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2f0900792b92a185ce7da66440e0b368870e97be
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54965952"
---
# <a name="how-to-use-built-in-colorable-items"></a>Postupy: Použití předdefinovaných položek které lze zabarvit
Než použijete integrovanou které lze zabarvit položky, můžete musí nejprve signalizuje, že do integrovaného vývojového prostředí (IDE), že nejsou poskytnutí vlastní vlastní které lze zabarvit položek, které v tomto případě by byly <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> objekty. To provedete tak, že nastavíte položku registru pro službu jazyka.  
  
## <a name="to-use-built-in-colorable-items"></a>Použití předdefinovaných položek které lze zabarvit  
  
1. V části **HKEY_LOCAL_MACHINE\VisualStudio\\< X.Y > \Languages\Language služby\\< název jazyka\>**, kde \<X.Y > je verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a \<Název jazyka > je název jazyka, vytvořit vstupní hodnotu registru DWORD s názvem **RequestStockColors**.  
  
2. Nastavte **RequestStockColors** hodnotu položky registru *1*.  
  
    Po vytvoření položka registru, vaše colorizer <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> metoda může použít jako objekty její členové <xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS> výčet k vyplnění pole barevnými atributy pro použití v editoru.  
  
   > [!NOTE]
   >  Pokud poskytujete vlastní, které lze zabarvit položky není nastavený této položky registru. Další informace najdete v tématu [vlastní, které lze zabarvit položky](../../extensibility/internals/custom-colorable-items.md).  
  
## <a name="see-also"></a>Viz také:  
 [Barevné zvýrazňování syntaxe ve vlastních editorech](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [Barevné zvýrazňování syntaxe ve službě starší verze jazyka](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [Implementace barevného zvýrazňování syntaxe](../../extensibility/internals/implementing-syntax-coloring.md)   
 [Vlastní položky které lze zabarvit](../../extensibility/internals/custom-colorable-items.md)   
 [Registrace služby starší verze jazyka](../../extensibility/internals/registering-a-legacy-language-service2.md)