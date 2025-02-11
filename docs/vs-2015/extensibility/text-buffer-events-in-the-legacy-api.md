---
title: Události vyrovnávací paměti textu v rozhraní API pro starší verze | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text buffer events
ms.assetid: 9be49e9f-1864-41c2-8a3c-f66895881341
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e82fa31ca435d0c850a4d9e75e927cff9613b046
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68186408"
---
# <a name="text-buffer-events-in-the-legacy-api"></a>Události vyrovnávací paměti textu v zastaralém rozhraní API
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Objekt vyrovnávací paměti textu vysílá několik různých událostí, které umožní reagovat na různé situace.  
  
 Pokud používáte starší verzi rozhraní API, měli byste implementovat následující rozhraní za účelem přijímání oznámení změn do vyrovnávací paměti textu. Zveřejňují rozhraní vyrovnávací paměti na text pomocí `IConnectionPointContainer` rozhraní na textovou vyrovnávací paměť pro příjem oznámení o řádek se změní z vyrovnávací paměti. Další informace najdete v tématu [jak: Zaregistrujte se na textové vyrovnávací paměti události s rozhraním API starší verze](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md). V případě třídy `IVsTextStreamEvents` nebo `IVsTextLinesEvents` rozhraní, změny se vrátí v buď jeden nebo two trojrozměrným souřadnice, v uvedeném pořadí.  
  
## <a name="text-buffer-interfaces"></a>Text Buffer Interfaces  
 Následující části jsou rozhraní implementované objekt vyrovnávací paměti textu.  
  
|Rozhraní|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Povolí vytváření složených akce (to znamená, akce, které jsou seskupeny do jednoho zpět/znovu jednotka).|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Povolí trvalost dat dokumentu spravuje vyrovnávací paměti textu.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Poskytuje základní služby; používá mnoho klientů.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Umožňuje číst a zapisovat možnosti použití dvojrozměrné souřadnice. Dědí z `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Poskytuje možnost rychlého, orientovaný na stream, sekvenční přístup k textu ve vyrovnávací paměti.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Umožňuje číst a zapisovat možnosti pomocí souřadnic jednorozměrné. Dědí z `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Poskytuje přístup k obecnou kolekci vlastností. Nejdůležitější vlastnost je název nebo moniker vyrovnávací paměti. Náhodná data můžete ukládat do vyrovnávací paměti s tímto rozhraním vytvořením identifikátor GUID a jeho použití jako klíč.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Podporuje spojovací body události.|  
  
## <a name="text-buffer-event-interfaces"></a>Textové vyrovnávací paměti událostí rozhraní  
 Následující části jsou rozhraní pro oznámení události vyrovnávací paměti textu.  
  
|Rozhraní|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferEvents>|Klienti upozorní, když se nová jazyková služba je spojen s textovou vyrovnávací paměť.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferDataEvents>|Oznamuje klientům při inicializaci textové vyrovnávací paměti a při změně dat v textové vyrovnávací paměti.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStreamEvents>|Oznamuje klientům změny základní jednorozměrný souřadnice vyrovnávací paměti textu.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>|Oznamuje klientům změny základní vyrovnávací paměti textu v dvojrozměrné souřadnice.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserDataEvents>|Oznamuje klientům změny k uživatelským datům.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsPreliminaryTextChangeCommitEvents>|Oznamuje klientům poslední potvrzení gesta pro aktivaci události a poskytuje řadu změněného textu. `IVsPreliminaryTextChangeCommitEvents` Rozhraní není aktivováno v reakci na vrácení zpět nebo opakování příkazů. Události aktivovaly jenom u vyrovnávacích pamětí, které mají správce akcí zpět. `IVsPreliminaryTextChangeCommitEvents` je aktivována před další události, jako je například přehlednou výpis, pokud chcete mít jistotu, že další události nemění text předtím, než se změny potvrdí. Vaše VSPackage musí monitorování buď `IVsPreliminaryTextChangeCommitEvents` rozhraní nebo `IVsFinalTextChangeCommitEvents` rozhraní, ale ne obojí.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFinalTextChangeCommitEvents>|Oznamuje klientům poslední potvrzení gesta pro aktivaci události a poskytuje řadu změněného textu. `IVsFinalTextChangeCommitEvents` Rozhraní není aktivováno v reakci na vrácení zpět nebo opakování příkazů. Události aktivovaly jenom u vyrovnávacích pamětí, které mají správce akcí zpět. `IVsFinalTextChangeCommitEvents` je určen pro použití pouze jazykové služby nebo jiné objekty, které mají plnou kontrolu nad úpravy. Vaše VSPackage musí monitorování buď `IVsPreliminaryTextChangeCommitEvents` rozhraní nebo `IVsFinalTextChangeCommitEvents` rozhraní, ale ne obojí.|  
  
## <a name="see-also"></a>Viz také  
 [Přístup k vyrovnávací paměti textu s použitím rozhraní API pro starší verze](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)   
 [Postupy: Registrace událostí vyrovnávací paměti textu pomocí zastaralého rozhraní API](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)
