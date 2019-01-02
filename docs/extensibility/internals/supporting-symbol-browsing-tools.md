---
title: Podpůrné nástroje procházení symbolů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- symbols, symbol-browsing tools
- browsers, symbol browsers
- symbol-browsing tools
- libraries
- IVsLibrary2 interface, symbol-browsing tools
- IVsSimpleLibrary2 interface, symbol-browsing tools
- symbol-browsing tools, library manager
- symbols
- libraries, symbol-browsing tools
ms.assetid: 70d8c9e5-4b0b-4a69-b3b3-90f36debe880
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 77ba75a0b62f2b0cbac1d7c60875dd322d0feaf2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53841976"
---
# <a name="supporting-symbol-browsing-tools"></a>Podpůrné nástroje procházení symbolů
**Prohlížeč objektů**, **zobrazení tříd**, **volání prohlížeče** a **výsledky hledáni symbolu** nástroje poskytují možnosti v sadě Visual Studio procházení symbolů. Tyto nástroje hierarchické stromové zobrazení symbolů a zobrazení vztahů mezi symboly ve stromové struktuře. Symboly mohou představovat obory názvů, objektů, tříd, členů třídy a další prvky jazyka, které jsou obsažené v různých komponent. Součásti zahrnují projektů sady Visual Studio, externí [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] komponenty a knihovny typů (.tlb). Další informace najdete v tématu [zobrazení struktury kódu](../../ide/viewing-the-structure-of-code.md).  
  
## <a name="symbol-browsing-libraries"></a>Procházení symbolů knihovny  
 Jako implementátora jazyk můžete rozšířit možnosti procházení symbolů Visual Studio tak, že vytvoříte knihovny, které sledovat symboly v vaše komponenty a k poskytování seznamů symbolů pro objekt správce sady Visual Studio prostřednictvím sady rozhraní. Knihovny je popsán <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2> rozhraní. Objekt správce sady Visual Studio odpovídá na požadavky pro nová data z nástroje procházení symbolů získáním dat z knihoven a uspořádání. Následně naplní nebo aktualizuje nástroje požadovaná data. K získání odkazu na objekt správce sady Visual Studio, <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2>, předat <xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager> ID do služby `GetService` metody.  
  
 Každou knihovnu musí zaregistrovat pomocí objektu správce sady Visual Studio, které shromažďuje informace o všech knihoven. Chcete-li zaregistrovat knihovnu, zavolejte <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> metody. V závislosti na tom, který nástroj zahájí požadavek správci objektu sady Visual Studio vyhledá příslušnou knihovnu a vyžádá data. Data se přenáší mezi knihoven a [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] object Manageru v seznamech symboly popsaného <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> rozhraní.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Object manager je odpovědná za aktualizaci pravidelně nástroje procházení symbolů tak, aby odrážely nejnovější data obsažená v knihovnách.  
  
 Následující diagram obsahuje příklad klíčové prvky procesu žádosti o/dat serveru exchange mezi knihovnou a správci objektu sady Visual Studio. Rozhraní v diagramu jsou součástí aplikace spravovaného kódu.  
  
 ![Tok dat mezi knihovnou a správci objektů](../../extensibility/internals/media/callbrowserdiagram.gif "CallBrowserDiagram")  
  
 Seznam symbolů poskytovat správci objektu sady Visual Studio, musíte se nejprve zaregistrovat knihovny pomocí Správce objektů sady Visual Studio pomocí volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> metoda. Po registraci knihovny požádá o objekt správce sady Visual Studio určité informace o možnostech knihovny. Například požadavky příznaky knihovny a podporované kategorie voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetLibFlags2%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetSupportedCategoryFields2%2A> metody. V určitém okamžiku v případě jedním z nástrojů vyžaduje data z této knihovny, správce objektů požaduje nejvyšší úrovně seznam symbolů voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetList2%2A> metody. V odpovědi, knihovně vyrábí seznam symbolů a zpřístupní ho do objektu správce sady Visual Studio prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> rozhraní. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Objekt správce určuje, kolik položek jsou v seznamu voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetItemCount%2A> metody. Všechny tyto požadavky se vztahují na danou položku v seznamu a zadejte číslo index položky v každém požadavku. Objekt správce sady Visual Studio pokračuje ke shromažďování informací na typ, dostupnost a další vlastnosti položky voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetCategoryField2%2A> metody.  
  
 Určuje název položky voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetTextWithOwnership%2A> – metoda a požadavky na ikonu informace pomocí volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetDisplayData%2A> metoda. Ikona se zobrazí nalevo od názvu položky a znázorňuje typ položky, dostupnost a dalších vlastností.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Objekt Správce volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetExpandable3%2A> metodu pro určení, zda daný seznam položek je rozšiřitelná a obsahuje podřízené položky. Pokud uživatelského rozhraní odešle žádost o rozšíření elementu, objekt správce požaduje podřízený seznam symbolů voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetList2%2A> metody. Proces pokračuje s různé části stromu vytváří na vyžádání.  
  
> [!NOTE]
>  Pro implementaci zprostředkovatele symbol nativní kód, použijte <xref:Microsoft.VisualStudio.Shell.Interop.IVsLibrary2> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectList2> rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Registrace knihovny pomocí Správce objektů](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [Postupy: Zveřejnění seznamů symbolů poskytovaných knihovnou správci objektů](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)   
 [Postupy: Identifikace symbolů v knihovně](../../extensibility/internals/how-to-identify-symbols-in-a-library.md)