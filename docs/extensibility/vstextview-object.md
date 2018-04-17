---
title: Objekt VSTextView | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSTextView
helpviewer_keywords:
- VSTextView object, reference
- views [Visual Studio SDK], reference
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5be89d01a668fd05e70e73e31ffaf3742317c272
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vstextview-object"></a>Objekt VSTextView
Zobrazení textu je okno, které umožňuje uživatelům zobrazit a upravit text v kódu Unicode textové vyrovnávací paměti. Zobrazení je v podstatě co většina uživatelů odkazovat jako editor. Protože zobrazení je oddělená od vyrovnávací paměti podle různých vrstev text (zalamování řádků, osnovy text a tak dále), nemusí být přesná reprezentace textu ve vyrovnávací paměti zobrazení. Další informace o textového zobrazení najdete v tématu [přístup k zobrazení text s použitím rozhraní API starší verze](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
  
 V následující tabulce jsou uvedeny rozhraní v <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objektu.  
  
|Rozhraní|Popis|  
|---------------|-----------------|  
|[IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071)|Standardní rozhraní OLE.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|Standardní rozhraní OLE.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|Standardní rozhraní OLE.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Standardní rozhraní OLE.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Umožňuje vytvoření složené akcí (to znamená, akce, které jsou seskupené v jednotce jeden zpět/opakování).|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|Poskytuje základní metody pro správu a přístup k zobrazení. `IVsTextView` není přístup z více vláken bezpečné.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Vytváří a spravuje podokna.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|Komunikuje s vrstvami text.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|Operace pro zobrazení, provádí z jiného vlákna.|  
  
## <a name="see-also"></a>Viz také  
 [Úprava obrázků](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)   
 [Objekt VSTextBuffer](../extensibility/vstextbuffer-object.md)   
 [Přístup k zobrazení text s použitím rozhraní API starší verze](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)