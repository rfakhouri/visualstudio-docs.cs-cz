---
title: "Textové vyrovnávací paměti události v rozhraní API starší | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text buffer events
ms.assetid: 9be49e9f-1864-41c2-8a3c-f66895881341
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7e7847cdca2065cadd6adaf0d4b3e6ea10444725
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="text-buffer-events-in-the-legacy-api"></a>Textové vyrovnávací paměti události v rozhraní API starší verze
Objekt vyrovnávací paměti textu vysílá několik různých událostí, které vám umožní reagovat na různé situace.  
  
 Pokud používáte starší verzi rozhraní API, měli byste implementovat následující rozhraní aby bylo možné přijímat oznámení o změnách textová vyrovnávací paměť. Vystavení rozhraní textové vyrovnávací paměti pomocí `IConnectionPointContainer` rozhraní na textovou vyrovnávací paměť pro příjem oznámení řádku změní z vyrovnávací paměti. Další informace najdete v tématu [postupy: registrace pro textové vyrovnávací paměti události s rozhraním API pro starší verze](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md). U `IVsTextStreamEvents` nebo `IVsTextLinesEvents` rozhraní, změny budou vráceny v buď jeden nebo two trojrozměrným souřadnice, v uvedeném pořadí.  
  
## <a name="text-buffer-interfaces"></a>Rozhraní textové vyrovnávací paměti  
 Toto jsou rozhraní implementované objekt textové vyrovnávací paměti.  
  
|Rozhraní|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Umožňuje vytvoření složené akcí (to znamená, akce, které jsou seskupené v jednotce jeden zpět/opakování).|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Povolí zachování dokumentu data spravovaná přes textová vyrovnávací paměť.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Poskytuje základní služby; používá mnoho klientů.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Poskytuje pro čtení a zápis možnosti pomocí dvourozměrná souřadnic. Dědí z `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Poskytuje možnost rychlého, orientované na datový proud, sekvenční přístup k textu ve vyrovnávací paměti.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Poskytuje pro čtení a zápis možnosti pomocí jednorozměrné souřadnic. Dědí z `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Poskytuje přístup k obecnou kolekci vlastností. Nejdůležitější vlastnost je název, nebo Přezdívka vyrovnávací paměti. Vlastní náhodná data můžete uložit ve vyrovnávací paměti s tímto rozhraním vytvořením identifikátor GUID a jeho použití jako klíč.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Body připojení podporuje pro události.|  
  
## <a name="text-buffer-event-interfaces"></a>Textové vyrovnávací paměti události rozhraní  
 Toto jsou rozhraní pro oznámení o události textové vyrovnávací paměti.  
  
|Rozhraní|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferEvents>|Klienti upozorní, když nové jazykové služby souvisí s textovou vyrovnávací paměť.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferDataEvents>|Oznamuje klientům při inicializaci textovou vyrovnávací paměť, a při změně dat v textová vyrovnávací paměť.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStreamEvents>|Oznamuje klientům změny základní textová vyrovnávací paměť v jednorozměrné souřadnice.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>|Oznamuje klientům změny základní textová vyrovnávací paměť v dvourozměrná souřadnice.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserDataEvents>|Oznamuje klientům změny dat uživatele.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsPreliminaryTextChangeCommitEvents>|Upozorní klientům poslední gesto potvrzení aktivovat události a poskytuje řadu změněného textu. `IVsPreliminaryTextChangeCommitEvents` Rozhraní není aktivováno v reakci na vrácení nebo opakování příkazy. Události platit pouze pro vyrovnávací paměti, které mají manager vrácení zpět. `IVsPreliminaryTextChangeCommitEvents`je vyvolána před další události, jako je například velmi výpis, pokud chcete mít jistotu, že ostatní události, nijak nemění text, než se změny potvrzeny. Vaše VSPackage třeba sledovat buď `IVsPreliminaryTextChangeCommitEvents` rozhraní nebo `IVsFinalTextChangeCommitEvents` rozhraní, ale ne obojí.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFinalTextChangeCommitEvents>|Upozorní klientům poslední gesto potvrzení aktivovat události a poskytuje řadu změněného textu. `IVsFinalTextChangeCommitEvents` Rozhraní není aktivováno v reakci na vrácení nebo opakování příkazy. Události platit pouze pro vyrovnávací paměti, které mají manager vrácení zpět. `IVsFinalTextChangeCommitEvents`je určená pro použití pouze jazyk služby nebo jiné objekty, které mají úplnou kontrolu nad úpravy. Vaše VSPackage třeba sledovat buď `IVsPreliminaryTextChangeCommitEvents` rozhraní nebo `IVsFinalTextChangeCommitEvents` rozhraní, ale ne obojí.|  
  
## <a name="see-also"></a>Viz také  
 [Přístup k textová vyrovnávací paměť s použitím rozhraní API starší verze](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)   
 [Postupy: registrace pro textové vyrovnávací paměti události s rozhraním API pro starší verze](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)