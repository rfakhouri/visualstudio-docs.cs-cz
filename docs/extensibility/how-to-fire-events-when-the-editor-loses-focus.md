---
title: 'Postupy: Aktivovat události při editoru ztratí fokus. | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d579b30c5eac25c815739149d3b3baacc22dc439
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990763"
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>Postupy: Aktivovat události při editoru ztratí fokus.
Někdy je potřeba vědět, pokud editor ztratí fokus na okno rámce. Například můžete potřebovat po editoru už nemá fokus na něj extrahovat kód, z okna kódu. Následující postup vysvětluje, jak postupovat podle k přijímání oznámení tom editor ztráta fokusu.  
  
## <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>Chcete-li vyvolat událost v reakci na editor ztráta fokusu  
  
1.  Monitorování událostí výběru získáním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> objektu z <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>.  
  
2.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A> a poskytnout mu vaše <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents> objektu.  
  
3.  Ve volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>, vyhledejte `elementid==SEID_WindowFrame`.  
  
4.  Test `varValueNew` parametr pro dvě věci:  
  
    1.  Snímek okna, které hledáte.  
  
    2.  Bod, ve kterém aplikace ztratí výběr do tohoto okna rámce.