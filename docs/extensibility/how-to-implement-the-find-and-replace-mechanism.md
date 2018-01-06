---
title: "Postupy: implementace najít a nahradit mechanismus | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c971d4565c95cab23e683a1a4f20c75ebea81b8f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>Postupy: implementace najít a nahradit mechanismus
Visual Studio poskytuje dva způsoby implementace vyhledání a nahrazení. Jedním ze způsobů je předat bitovou kopii text do prostředí a nechat ji zpracovat vyhledávání, zvýraznění a nahraďte text. To umožňuje uživatelům zadat více rozpětí textu. Vaše VSPackage Alternativně můžete řídit tuto funkci, sám sebe. V obou případech musíte upozornit prostředí o aktuální cíl a cíle pro všechny otevřené dokumenty.  
  
### <a name="to-implement-findreplace"></a>K implementaci vyhledání a nahrazení  
  
1.  Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget> rozhraní na některý z objektů vrácené vlastnosti rámce <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> nebo <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>. Pokud vytváříte vlastní editor, měli byste implementovat toto rozhraní v rámci třídy vlastní editor.  
  
2.  Použití <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A> metoda zadejte možnosti, které podporuje vaše editoru a označuje, zda implementuje hledání textu bitové kopie.  
  
     Pokud vaše editor podporuje hledání textu bitové kopie, implementujte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>.  
  
     Jinak, implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>.  
  
3.  Pokud implementujete <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A> metod, můžete zjednodušit vyhledávání úkoly voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper> rozhraní.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>