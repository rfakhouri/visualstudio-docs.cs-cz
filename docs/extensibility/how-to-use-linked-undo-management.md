---
title: 'Postupy: použití modulu Správa propojená operace vrácení zpět | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - linked undo management
ms.assetid: af5cc22a-c9cf-45b1-a894-1022d563f3ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 24e39bd0bde922dbe761bc9de176d43161bb985d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127634"
---
# <a name="how-to-use-linked-undo-management"></a>Postupy: použití modulu Správa propojená operace vrácení zpět
Propojená operace vrácení zpět umožňuje uživateli současně vrátit zpět stejné úpravy ve více souborech. Například souběžných text se změní na napříč více programové soubory, jako je například hlavičkový soubor a soubor Visual C++, je propojená operace vrácení zpět transakci. Propojená operace vrácení zpět funkce je integrovaná v prostředí provádění správce vrácení zpět a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager> umožňuje pracovat s Tato funkce. Propojená operace vrácení zpět je implementováno modulem jednotkou nadřazené vrácení zpět, která může propojit samostatné zpět zásobníky spolupracují, aby jednal jako jednotku jedné operace vrácení zpět. Postup pro používání propojená operace vrácení zpět je podrobně popsán v následující části.  
  
### <a name="to-use-linked-undo"></a>Chcete-li použít propojená operace vrácení zpět  
  
1.  Volání `QueryService` na `SVsLinkedUndoManager` získání ukazatele na `IVsLinkedUndoTransactionManager`.  
  
2.  Vytvořit počáteční nadřazené propojená operace vrácení zpět jednotky voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.OpenLinkedUndo%2A>. To se nastavuje počáteční bod pro sadu zásobníky vrácení zpět, byly seskupeny do zásobníky propojená operace vrácení zpět. V `OpenLinkedUndo` metoda budete také muset určit, zda má propojená operace vrácení zpět striktní nebo strict. Striktní není propojená operace vrácení zpět chování znamená, že některé z těchto dokumentů s propojená operace vrácení zpět na stejné úrovni můžete zavřít a stále ponechejte dalších spojena vrátit zpět na jejich zásobníky na stejné úrovni. Striktní propojená operace vrácení zpět chování Určuje, že všechny balíčky propojená operace vrácení zpět na stejné úrovni jako vrátit zpět společně nebo vůbec. Přidat další propojené vrátit zpátky zásobníky volání [IOleUndoManager::Add](http://msdn.microsoft.com/library/windows/desktop/ms680135) metoda.  
  
3.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.CloseLinkedUndo%2A> vrátit zpět všechny jednotky propojená operace vrácení zpět jako jeden.  
  
    > [!NOTE]
    >  K implementaci správy propojená operace vrácení zpět v editoru, přidejte management operace vrácení zpět. Další informace o implementaci správy propojená operace vrácení zpět, najdete v části [postupy: implementace vrátit zpět správu](../extensibility/how-to-implement-undo-management.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>   
 [IOleParentUndoUnit](http://msdn.microsoft.com/library/windows/desktop/ms682151)   
 [IOleUndoUnit](http://msdn.microsoft.com/library/windows/desktop/ms678476)   
 [Postupy: Implementace správy vrácení zpět](../extensibility/how-to-implement-undo-management.md)