---
title: "Přístup k text zobrazení pomocí starší verze rozhraní API | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - text view
ms.assetid: 8f751f72-c972-4be3-84ee-19c281e02e25
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bea908ee04913c5ec56678f1438229e045bf68c7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-thetext-view-by-using-the-legacy-api"></a>Přístup k zobrazení text s použitím rozhraní API starší verze
Zobrazení textu je prezentace textu, který je uložen v textové vyrovnávací paměti. Zobrazení textu můžete přistupovat pomocí starší verze rozhraní API, jak je znázorněno v následující části.  
  
## <a name="text-view-object"></a>Objekt zobrazení textu  
 Každé zobrazení souvisí s vlastním textovou vyrovnávací paměť a zobrazení je okno na data ve vyrovnávací paměti. Následující diagram znázorňuje klíče rozhraní objekt zobrazení textu, která je reprezentována <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>.  
  
 ![Visual Studio textového zobrazení objektu](../extensibility/media/vstextview.gif "vstextview")  
Objekt zobrazení textu  
  
 Zobrazení je to způsob prezentace textu ve vyrovnávací paměti. Obsahuje funkce, jako je například zalamování řádků a osnovy, tak, aby co se zobrazí v zobrazení není přesná reprezentace textu ve vyrovnávací paměti.  
  
 Zobrazení umožňuje jiných služeb nebo procesů zachytí příchozí příkazy a s nimi pracovat před zobrazení funguje na ně. Nejběžnější služby k tomu je služba jazyka. Služba jazyka může být potřeba, například příkaz pro klávesy ENTER zadejte vlastní odsazení chování nebo nástroj tipy zachytit.  
  
## <a name="adding-functionality-to-the-text-view"></a>Přidání funkcí do textového zobrazení  
 Je-li přizpůsobit chování zobrazení textu, zpracování konkrétní stisknutí kláves. Zachytávat stisknutí kláves, můžete implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> na objektu a zadejte příkaz cíl (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>) k příkazům monitorování a zachycení.  
  
 Zobrazení textu využívá sekvenční architekturu pro příkaz filtry. Nové filtry příkazu (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> objekty) jsou přidány do pořadí voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> metoda.  
  
 Oznámení o události pro zobrazení textu je zajištěno pomocí `T:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents` rozhraní. Toto rozhraní implementujte na objektu klienta pro příjem oznámení o změnách textového zobrazení. Vystavení tohoto rozhraní textového zobrazení pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> rozhraní na textového zobrazení upozornění na změny ze zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Změna nastavení zobrazení pomocí starší verze rozhraní API](../extensibility/changing-view-settings-by-using-the-legacy-api.md)   
 [Pomocí Správce Text k monitorování globální nastavení](../extensibility/using-the-text-manager-to-monitor-global-settings.md)