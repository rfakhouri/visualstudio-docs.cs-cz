---
title: Příkaz směrování algoritmus | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, routing
- command routing
ms.assetid: 998b616b-bd08-45cb-845f-808efb8c33bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aba7ddcdda4dd4eabbb9266e0fa89c916bb028f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="command-routing-algorithm"></a>Příkaz směrování algoritmus
Příkazy v sadě Visual Studio jsou zpracovávány několik různých komponent. Příkazy jsou směrovány z nejvnitřnější kontextu, která je založena na aktuálním výběrem, kontext nejkrajnější (také označované jako globální). Další informace najdete v tématu [dostupnosti](../../extensibility/internals/command-availability.md).  
  
## <a name="order-of-command-resolution"></a>Pořadí příkaz řešení  
 Příkazy se předaly následujících úrovní kontextu příkaz:  
  
1.  Doplňky: Prostředí nejprve nabízí příkaz pro všechny moduly, které jsou k dispozici.  
  
2.  Příkazy priority: tyto příkazy, které jsou registrovány pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterPriorityCommandTarget>. Volá se pro každý příkaz v sadě Visual Studio a se nazývají v pořadí, ve kterém byly zaregistrované.  
  
3.  Příkazy nabídky kontextu: příkaz nachází v kontextové nabídce se nejprve nabízí k cíli příkazu, který je zadán do kontextové nabídky a potom pro typické směrování.  
  
4.  Panel nástrojů nastavit cíle příkazů: tyto cíle příkazů jsou registrovány při volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell4.SetupToolbar2%2A>. `pCmdTarget` Parametr může být `null`. Pokud není `null`, pak tento příkaz cíl se používá k aktualizaci žádné příkazy, na panelu nástrojů, který vytváříte. Pokud prostředí je nastavení panelu nástrojů, a poté ho předá rámce okna jako `pCmdTarget` tak, aby všechny aktualizace příkazů na vašeho nástrojů toku prostřednictvím rámce okna i když není aktivní.  
  
5.  Okno nástroje: Nástroj windows, které obvykle implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> rozhraní, by taky implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní, Visual Studio mohli získat cíl příkazu, když je aktivní okno okno nástroje. Ale pokud panel nástrojů, který má zaměřuje se **projektu** okna a potom příkaz se směruje na <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní, které se společným nadřazeným prvkem vybraných položek. Pokud tento výběr zahrnuje více projektů, příkaz se směruje na <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution> hierarchie. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> Rozhraní obsahuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A> metody, které se podobá odpovídající příkazů na <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní.  
  
6.  Okna dokumentu: Pokud příkaz má RouteToDocs příznak nastavený ve svém .vsct souboru, sada Visual Studio hledá cíl příkazu na objekt zobrazení dokumentu, který je buď instanci <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> rozhraní nebo instanci objektu dokumentu (obvykle <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>rozhraní nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> rozhraní). Pokud objekt zobrazení dokumentu nepodporuje příkaz, Visual Studio směruje příkazu <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní, která je vrácena. (Toto je volitelné rozhraní pro dokument datové objekty.)  
  
7.  Aktuální hierarchie: Aktuální hierarchie může být projekt, který vlastní aktivního okna dokumentu nebo hierarchie, který je vybraný v **Průzkumníku řešení**. Sada Visual Studio hledá <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní, které se implementuje na aktuální nebo aktivní, hierarchie. Hierarchie musí podporovat příkazy, které jsou platné vždy, když v hierarchii je aktivní, i když má právě fokus, okna dokumentu položky projektu. Však příkazy, které se týkají pouze tehdy, když **Průzkumníku řešení** má fokus musí být podporován pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní a jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>metody.  
  
     **Vyjmout**, **kopie**, **vložení**, **odstranit**, **přejmenovat**, **zadejte**a **DoubleClick** příkazy vyžadují speciální zacházení. Informace o způsobu zpracování **odstranit** a **odebrat** příkazy v hierarchiích, najdete v článku <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler> rozhraní.  
  
8.  Globální: Pokud příkaz nebyl byla zpracována výše uvedených kontexty, Visual Studio se pokusí směrovat do VSPackage, který vlastní příkaz, který implementuje <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Pokud VSPackage již nebyla načtena, není načtou při volání sady Visual Studio <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda. VSPackage je načtena pouze tehdy, když <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [Návrh příkazu](../../extensibility/internals/command-design.md)