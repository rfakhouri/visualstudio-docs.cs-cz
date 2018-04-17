---
title: 'Postupy: Implementace správy vrácení zpět | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 1942245d-7a1d-4a11-b5e7-a3fe29f11c0b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b01b7b8edf5ebe4b8c3e5277e87f9797860b552f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-implement-undo-management"></a>Postupy: Implementace správy vrácení zpět
Primární rozhraní používá pro správu vrácení zpět je <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager>, které je implementované v prostředí. Pro podporu správy vrácení zpět, implementovat zpět samostatné jednotky (tedy <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit>, která může obsahovat více jednotlivé kroky.  
  
 Jak implementovat management operace vrácení zpět se liší v závislosti na tom, jestli vaše editor podporuje více zobrazení, nebo ne. V následujících částech jsou podrobné postupy pro každou implementaci.  
  
## <a name="cases-where-an-editor-supports-a-single-view"></a>Případy, kdy editoru podporuje jediné zobrazení  
 V tomto scénáři editoru nepodporuje více zobrazení. Existuje pouze jeden editor a jeden dokument a podporují vrácení zpět. Použijte následující postup k implementaci správy vrácení zpět.  
  
#### <a name="to-support-undo-management-for-a-single-view-editor"></a>Pro podporu správy vrácení zpět pro editor jedním – zobrazení  
  
1.  Volání `QueryInterface` na `IServiceProvider` rozhraní na rámec okna pro `IOleUndoManager`, z objektu zobrazení dokumentu pro přístup k vrácení zpět manager (`IID_IOLEUndoManager`).  
  
2.  Když zobrazení je umístěný na rámec okna, získá ukazatel lokality, které můžete použít k volání `QueryInterface` pro `IServiceProvider`.  
  
## <a name="cases-where-an-editor-supports-multiple-views"></a>Případy, kdy editoru podporuje více zobrazení  
 Pokud máte oddělení a zobrazení dokumentů, je obvykle jednu zpět správce přidruženého k samotného dokumentu. Všechny jednotky vrácení zpět se umístí na jednu zpět správce přidruženého k dokumentu datový objekt.  
  
 Místo zobrazení dotazu pro vrácení zpět správce, které je jedna pro každou zobrazení data dokumentu objektu volání <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> k vytvoření instance správce vrácení zpět, určující identifikátor třídy z CLSID_OLEUndoManager. Identifikátor třídy je definována v souboru OCUNDOID.h.  
  
 Při použití <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> k vytvoření instance správce vlastní vrácení zpět, pomocí následujícího postupu připojí manager vaší vrácení zpět do prostředí.  
  
#### <a name="to-hook-your-undo-manager-into-the-environment"></a>Připojí správce svého vrácení zpět do prostředí  
  
1.  Volání `QueryInterface` pro objekt vrácený z <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2> pro `IID_IOleUndoManager`. Uložení má ukazatel na <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager>.  
  
2.  Volání `QueryInterface` na `IOleUndoManager` pro `IID_IOleCommandTarget`. Uložení má ukazatel na <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
3.  Předávání vaše <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> volání do uložené `IOleCommandTarget` rozhraní pro následující příkazy StandardCommandSet97:  
  
    -   cmdidUndo  
  
    -   cmdidMultiLevelUndo  
  
    -   cmdidRedo  
  
    -   cmdidMultiLevelRedo  
  
    -   cmdidMultiLevelUndoList  
  
    -   cmdidMultiLevelRedoList  
  
4.  Volání `QueryInterface` na `IOleUndoManager` pro `IID_IVsChangeTrackingUndoManager`. Uložení má ukazatel na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>.  
  
     Použít má ukazatel na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager> k volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager.MarkCleanState%2A>, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager.AdviseTrackingClient%2A>a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager.UnadviseTrackingClient%2A> metody.  
  
5.  Volání `QueryInterface` na `IOleUndoManager` pro `IID_IVsLinkCapableUndoManager`.  
  
6.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkCapableUndoManager.AdviseLinkedUndoClient%2A> s dokumentem, který by měl taky implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoClient> rozhraní. Při zavření dokumentu volání `IVsLinkCapableUndoManager::UnadviseLinkedUndoClient`.  
  
7.  Při zavření dokumentu volání `QueryInterface` na správce svého vrácení zpět pro `IID_IVsLifetimeControlledObject`.  
  
8.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLifetimeControlledObject.SeverReferencesToOwner%2A>.  
  
9. Provedení změn v dokumentu, volání <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager.Add%2A> na správce s `OleUndoUnit` třídy. <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager.Add%2A> Metoda udržuje odkaz na objekt, takže obvykle ji uvolnit hned po <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager.Add%2A>.  
  
 `OleUndoManager` Třída reprezentuje instanci zásobníku a jeden vrácení zpět. Proto se jeden objekt manager zpět za data entity sledované pro zpět nebo znovu.  
  
> [!NOTE]
>  Zatímco objekt správce vrácení zpět je hojně používá textový editor, je obecné komponenty, která nemá žádné konkrétní podporu pro textový editor. Pokud chcete podporovat víceúrovňovou zpět nebo znovu, můžete to udělat tento objekt.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLifetimeControlledObject>   
 [Postupy: Vymazat zásobníku vrácení zpět](../extensibility/how-to-clear-the-undo-stack.md)