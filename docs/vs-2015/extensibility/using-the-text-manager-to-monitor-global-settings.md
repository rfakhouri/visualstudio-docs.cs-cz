---
title: Pomocí Správce Text monitorování globální nastavení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - monitor global settings
- editors [Visual Studio SDK], legacy - text manager
ms.assetid: 023e7671-cf65-419c-9bc1-3c4ee92aa436
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ece51450b8344ae4715a912399ec538171a26a5c
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65695459"
---
# <a name="using-the-text-manager-to-monitor-global-settings"></a>Pomocí Správce Text monitorování globální nastavení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud se rozhodnete implementovat základní editor, je třeba sledovat změny, které jsou provedeny ke globálnímu nastavení, protože tyto změny mohou ovlivnit vaše instance editoru. Změny můžete sledovat prostřednictvím naslouchání události vyvolané službou textový správce. Například když zadáte globální předvoleb pro vzhled nebo chování součásti v základní editor, například jeho datový objekt dokumentu, textový správce ukládá tyto informace a komunikuje se všechny příslušné klienty.  
  
## <a name="text-manager-functions"></a>Funkce text Manageru  
 Textový správce vyvolává události pro celou řadu nastavení, včetně následujících:  
  
- Určuje, zda vyrovnávací paměti je pod správou zdrojového kódu  
  
- Postup registrace pro oznámení o změně souboru  
  
- Tom, jak udržovat přehled o zobrazení, které jsou spojeny s určitým vyrovnávací paměti  
  
- Předvolby zabarvení textu  
  
- Karta oproti předvolby místa  
  
  Předvolby, které jsou jedinečné pro daný jazyk nespravuje textový správce. Tato nastavení se musí spravovat přes každá služba jazyka.  
  
  Oznámení události pro textový správce poskytuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents> rozhraní. Toto rozhraní implementují u svého klienta vyvolá objekt zpracování událostí textový správce. Tyto události můžete zaregistrovat pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> rozhraní na textový správce.  
  
## <a name="see-also"></a>Viz také  
 [Uvnitř základní Editor](../extensibility/inside-the-core-editor.md)   
 [Funkce editoru](https://msdn.microsoft.com/bdac940d-1f14-4019-a01f-fd0bb3dc7198)
