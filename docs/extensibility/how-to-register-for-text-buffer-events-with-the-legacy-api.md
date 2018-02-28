---
title: "Postupy: registrace pro textové vyrovnávací paměti události s rozhraním API pro starší verze | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - register for text buffer events
ms.assetid: 5fc00ced-882c-4b48-b46c-1fa5a2469f94
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 94f2e781c316f3891fdef0c324d54fa2f9742222
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-register-for-text-buffer-events-with-the-legacy-api"></a>Postupy: registrace pro textové vyrovnávací paměti události s rozhraním API pro starší verze
Pokud se připojujete textová vyrovnávací paměť pomocí starší verze rozhraní API, byste měli zaregistrovat pro textové vyrovnávací paměti události, jak je znázorněno v následujícím postupu.  
  
### <a name="to-advise-text-buffer-events"></a>Chcete-li poradit textové vyrovnávací paměti události  
  
1.  Z ukazatel k jednomu z rozhraní na <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>, volání `QueryInterface` pro ukazatel na <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>.  
  
2.  Volání <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer.FindConnectionPoint%2A> metoda a předejte jí rozhraní ID událostí, pro které chcete zaregistrovat.  
  
     Například, pokud chcete zaregistrovat pro <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>, pak předejte rozhraní ID IID_IVsTextLinesEvents.  
  
     Vrátí ukazatel na textovou vyrovnávací paměť <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> rozhraní pro objekt bodu příslušné připojení.  
  
3.  Pomocí tento ukazatel, volání <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A> metody předávání v ukazatel na implementaci rozhraní událostí, pro který chcete zaregistrovat, například `IVsTextLinesEvents` rozhraní.  
  
     Prostředí vrátí souboru cookie, který pak můžete použít k zastavení naslouchá událostem voláním <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Unadvise%2A> metoda.  
  
## <a name="see-also"></a>Viz také  
 [Textové vyrovnávací paměti události v rozhraní API starší verze](../extensibility/text-buffer-events-in-the-legacy-api.md)