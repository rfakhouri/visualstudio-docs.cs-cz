---
title: Přístup k text zobrazení pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text view
ms.assetid: 8f751f72-c972-4be3-84ee-19c281e02e25
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8f9396e4523e38e7313efb5668c4680f551558ab
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184956"
---
# <a name="accessing-thetext-view-by-using-the-legacy-api"></a>Přístup k textovému zobrazení pomocí zastaralého rozhraní API
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zobrazení textu je prezentace textu, který je uložen do vyrovnávací paměti textu. Text můžete zobrazit pomocí starší verze rozhraní API, jak je znázorněno v následující části.  
  
## <a name="text-view-object"></a>Objekt zobrazení textu  
 Každé zobrazení souvisí s vlastním textovou vyrovnávací paměť a zobrazení je okno na data ve vyrovnávací paměti. Následující diagram znázorňuje rozhraní klíče použitého textového objektu zobrazení, která je reprezentována <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>.  
  
 ![Visual Studio textové zobrazení objektu](../extensibility/media/vstextview.gif "vstextview –")  
Objekt zobrazení textu  
  
 Zobrazení je způsob prezentace text ve vyrovnávací paměti. Zahrnuje funkce, jako je zalamování řádků a přehledů tak, co se zobrazí v zobrazení není přesnou reprezentací text ve vyrovnávací paměti.  
  
 Zobrazení umožňuje jiných služeb nebo procesů zachytávat příchozí příkazy a na jejich základě reagovat před zobrazení funguje na ně. Nejčastěji používané služby k tomu je služba jazyka. Služba jazyka může být nutné, například příkaz pro klávesy ENTER zadejte vlastní odsazení chování nebo nástroj tipy zachytit.  
  
## <a name="adding-functionality-to-the-text-view"></a>Přidání funkce k zobrazení textu  
 Díky zpracování konkrétní stisknutí kláves můžete přizpůsobit chování zobrazení textu. Chcete-li zachytit stisknutí kláves, implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> na objekt a můžou být cílem příkazu (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>) k monitorování a zachycení příkazů.  
  
 Zobrazení textu používá sekvenční architekturu pro příkaz filtry. Nové filtry příkazu (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> objekty) jsou přidány do sekvence pomocí volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> metoda.  
  
 Oznámení události pro zobrazení textu je zajištěno pomocí `T:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents` rozhraní. Toto rozhraní implementují na objekt klienta pro příjem oznámení o změnách nástroje k zobrazení textu. Zpřístupňují toto rozhraní k zobrazení textu s využitím <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> rozhraní pro zobrazení textu na které přijde upozornění na změny ze zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Změna nastavení zobrazení pomocí starší verze rozhraní API](../extensibility/changing-view-settings-by-using-the-legacy-api.md)   
 [Použití textového správce k monitorování globálního nastavení](../extensibility/using-the-text-manager-to-monitor-global-settings.md)
