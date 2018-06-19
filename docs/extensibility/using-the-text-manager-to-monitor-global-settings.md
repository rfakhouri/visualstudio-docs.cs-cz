---
title: Pomocí Správce Text k monitorování globální nastavení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - monitor global settings
- editors [Visual Studio SDK], legacy - text manager
ms.assetid: 023e7671-cf65-419c-9bc1-3c4ee92aa436
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e6c61a6859a2e8d359b2185ce959aa941944380f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31141669"
---
# <a name="using-the-text-manager-to-monitor-global-settings"></a>Pomocí Správce Text k monitorování globální nastavení
Pokud implementujete základní editor, je třeba sledovat změny, které jsou vytvářeny pro globální nastavení, protože tyto změny mohou ovlivnit vaše instance editoru. Změny můžete sledovat prostřednictvím naslouchání události vyvolané službou textový správce. Například když zadáte globální předvolby pro vzhled nebo chování komponenty v editoru jádra, jako je jeho datový objekt dokumentu textový správce ukládá tyto informace a komunikuje se všechny příslušné klienty.  
  
## <a name="text-manager-functions"></a>Funkce textový správce  
 Textový správce vyvolává události pro řadu nastavení, včetně následujících:  
  
-   Jestli vyrovnávací paměti je pod správu zdrojového kódu  
  
-   Postup registrace pro oznámení o změně souboru  
  
-   Postupy ke sledování zobrazení, které jsou přidružené určité vyrovnávací paměti  
  
-   Předvolby zabarvení textu  
  
-   Kartě a předvolby místa  
  
 Předvolby, které jsou jedinečné pro daný jazyk nespravuje textový správce. Tato nastavení musí být spravované službou každý jazyk.  
  
 Oznámení události pro textový správce poskytuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents> rozhraní. Toto rozhraní implementovat na vašeho klienta objekt pro zpracování události vyvolané textový správce. Registrace pro tyto události pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> rozhraní na textový správce.  
  
## <a name="see-also"></a>Viz také  
 [V editoru jádra](../extensibility/inside-the-core-editor.md)   
 [Funkce editoru](http://msdn.microsoft.com/en-us/bdac940d-1f14-4019-a01f-fd0bb3dc7198)