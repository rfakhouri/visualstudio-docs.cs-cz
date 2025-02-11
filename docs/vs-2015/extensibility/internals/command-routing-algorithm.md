---
title: Algoritmus směrování příkazů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, routing
- command routing
ms.assetid: 998b616b-bd08-45cb-845f-808efb8c33bc
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e3b8602df40045a3f4e1fc91fee92151bf5dd4ea
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68195112"
---
# <a name="command-routing-algorithm"></a>Algoritmus směrování příkazů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Příkazy v sadě Visual Studio jsou zpracovávány celou řadou různých komponent. Příkazy jsou směrovány od nejvnitřnější kontext, který vychází z aktuálního výběru vnějšího (označované také jako globální) v kontextu. Další informace najdete v tématu [dostupnosti](../../extensibility/internals/command-availability.md).  
  
## <a name="order-of-command-resolution"></a>Pořadí řešení příkaz  
 Příkazy jsou předány na následujících úrovních kontext příkazů:  
  
1. Doplňky: Prostředí nejprve nabízí příkaz pro všechny moduly, které jsou k dispozici.  
  
2. Priorita příkazy: Tyto příkazy jsou registrované pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterPriorityCommandTarget>. Volá se pro každý příkaz v sadě Visual Studio a jsou volány v pořadí, ve kterém byly registrovány.  
  
3. Příkazy místní nabídky: Příkaz umístěné v místní nabídce se nejprve nabízí na daném cíli příkazu, který je k dispozici v místní nabídce a potom na typické směrování.  
  
4. Panel nástrojů nastavte cíle příkazů: Tyto cíle příkazů jsou registrovány při volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell4.SetupToolbar2%2A>. `pCmdTarget` Parametr může být `null`. Pokud není `null`, pak tento cíl příkazu se používá k aktualizaci všechny příkazy jsou umístěny na panelu nástrojů nastavujete. Pokud prostředí je nastavení panelu nástrojů, pak předá rámec okna, jako `pCmdTarget` tak, aby všechny aktualizace příkazy na váš tok nástrojů prostřednictvím rám okna, i když není aktivní.  
  
5. Panel nástrojů: Nástroje systému windows, které obvykle implementují <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> rozhraní, by měly také implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní tak, aby Visual Studio můžete získat cíl příkazu, když je okno nástroje aktivní okno. Pokud ale nástroj, který má okno fokus je **projektu** okno a potom příkaz se směruje na <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní, které je společným nadřazeným prvkem z vybraných položek. Pokud tento výběr zahrnuje více projektů, je předán příkazu <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution> hierarchie. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> Rozhraní obsahuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A> metody, které jsou obdobou odpovídající příkazy na <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní.  
  
6. Okno dokumentu: Pokud příkaz nemá příznak RouteToDocs nastavený v souboru .vsct, Visual Studio vyhledá cíl příkazu na zobrazení objektu dokumentu, který je buď instance <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> rozhraní nebo instance objektu dokumentu (obvykle <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> rozhraní nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> rozhraní). Pokud objekt zobrazení dokumentu nepodporuje příkaz, Visual Studio směruje příkaz, který <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní, která je vrácena. (To je volitelné rozhraní pro datové objekty dokumentu.)  
  
7. Aktuální hierarchie: Aktuální hierarchie může být projekt, který je vlastníkem aktivního okna dokumentu nebo hierarchie, který je vybraný v **Průzkumníka řešení**. Visual Studio vyhledá <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní, které je implementováno v aktuální nebo aktivní, hierarchie. Hierarchie musí podporovat příkazy, které jsou platné pokaždé, když se v hierarchii je aktivní, i v případě, že okno dokumentu projektu položky má fokus. Však příkazy, které se týkají pouze tehdy, když **Průzkumníka řešení** má fokus musí být podporován pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní a jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>metody.  
  
     **Vyjmout**, **kopírování**, **vložit**, **odstranit**, **přejmenovat**, **zadejte**a **DoubleClick** příkazy vyžadují speciální zacházení. Informace o tom, jak zpracovat **odstranit** a **odebrat** příkazy v hierarchiích, najdete v článku <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler> rozhraní.  
  
8. Globální: Pokud příkaz nebylo manipulováno podle výše uvedených kontexty, Visual Studio se pokusí směrovat do sady VSPackage, která vlastní příkaz, který implementuje <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Pokud už se nenačetl sady VSPackage, není načten při volání sady Visual Studio <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metody. Načtení sady VSPackage pouze tehdy, když <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [Návrh příkazu](../../extensibility/internals/command-design.md)
