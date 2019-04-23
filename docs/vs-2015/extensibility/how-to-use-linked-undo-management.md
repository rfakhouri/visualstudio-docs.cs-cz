---
title: 'Postupy: Použijte správu propojená operace vrácení zpět | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - linked undo management
ms.assetid: af5cc22a-c9cf-45b1-a894-1022d563f3ca
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 442024b7be335c0aa010ce528142ac7a205097f8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60062968"
---
# <a name="how-to-use-linked-undo-management"></a>Postupy: Použijte správu propojená operace vrácení zpět
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Propojená operace vrácení zpět mu umožní současně zpět stejné úpravy ve více souborech. Například změny souběžných textu do více souborů programu, jako je například soubor hlaviček a soubor jazyka Visual C++ je propojená operace vrácení zpět transakcí. Propojená operace vrácení zpět funkce je integrovaná do prostředí provádění správce akcí zpět a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager> umožňuje manipulaci s tuto funkci. Propojená operace vrácení zpět je implementováno nadřazenou jednotku, která můžete propojit samostatné zpět zásobníky dohromady a považovány za celek jedno vrácení zpět. Postup pro používání propojená operace vrácení zpět je podrobně popsán v následující části.  
  
### <a name="to-use-linked-undo"></a>Chcete-li použít propojená operace vrácení zpět  
  
1. Volání `QueryService` na `SVsLinkedUndoManager` získat ukazatel na `IVsLinkedUndoTransactionManager`.  
  
2. Vytvořte jednotku počáteční nadřazené propojená operace vrácení zpět voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.OpenLinkedUndo%2A>. Tím se nastaví výchozí bod pro sadu zásobníky akcí zpět na seskupené do zásobníků propojená operace vrácení zpět. V `OpenLinkedUndo` metoda budete taky muset zadat, jestli chcete propojená operace vrácení zpět striktní nebo nepřísném. Non striktní propojená operace vrácení zpět chování znamená, že některé z těchto dokumentů s propojená operace vrácení zpět na stejné úrovni můžete zavřít a nechat druhé propojené vrátit na stejné úrovni na svých zásobníků. Striktní propojená operace vrácení zpět chování Určuje, že všechny balíčky propojená operace vrácení zpět na stejné úrovni jako vrátit zpět společně nebo vůbec ne. Přidat další propojené zásobníky akcí zpět voláním [IOleUndoManager::Add](/windows/desktop/api/ocidl/nf-ocidl-ioleundomanager-add) metody.  
  
3. Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.CloseLinkedUndo%2A> vrátit zpět všechny jednotky propojená operace vrácení zpět jako jeden.  
  
    > [!NOTE]
    >  Implementace správy propojená operace vrácení zpět v editoru, přidáte zpět správy. Další informace o implementaci správy propojená operace vrácení zpět, najdete v části [jak: Implementace správy zpět](../extensibility/how-to-implement-undo-management.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>   
 [IOleParentUndoUnit](/windows/desktop/api/ocidl/nn-ocidl-ioleparentundounit)   
 [IOleUndoUnit](/windows/desktop/api/ocidl/nn-ocidl-ioleundounit)   
 [Postupy: Implementace správy zpět](../extensibility/how-to-implement-undo-management.md)
