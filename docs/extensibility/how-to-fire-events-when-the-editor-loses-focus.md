---
title: 'Postupy: vyvolání události při editoru ztratí fokus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bbdcf30443bc548fd8d182db301cbc7119d8ceae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127034"
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>Postupy: vyvolání události při editoru ztratí fokus
V některých případech je potřeba vědět, kdy přestane být aktivní v rámce okna editoru. Například budete muset po editoru se už zaměřuje na něm extrahovat kód z okna kódu. Následující postup popisuje, jak postupovat, na které přijde upozornění editoru došlo ke ztrátě fokus.  
  
### <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>Chcete-li aktivovat událost v reakci na editoru došlo ke ztrátě fokusu  
  
1.  Sledování událostí výběr získáním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> objektu z <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>.  
  
2.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A> a poskytnout ho vaše <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents> objektu.  
  
3.  Ve volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>, vyhledejte `elementid==SEID_WindowFrame`.  
  
4.  Testovací `varValueNew` parametr pro dvě věci:  
  
    1.  Rámec okna, které hledáte.  
  
    2.  Bod, ve kterém vašeho programu ztratí výběr tohoto rámce okna.