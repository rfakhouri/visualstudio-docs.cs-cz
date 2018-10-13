---
title: Přístup k text zobrazení pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text view
ms.assetid: 8f751f72-c972-4be3-84ee-19c281e02e25
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 943a55f09404224ec3d9b793c2ff473b90a66f0d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49296189"
---
# <a name="accessing-thetext-view-by-using-the-legacy-api"></a>Přístup k text zobrazení pomocí starší verze rozhraní API
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

