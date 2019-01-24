---
title: IntelliSense Hosting | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - IntelliSense hosting
ms.assetid: 20c61f8a-d32d-47e2-9c67-bf721e2cbead
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a5c378aec6822a436de0d8fc2656fcac7be4149f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54763666"
---
# <a name="intellisense-hosting"></a>IntelliSense Hosting
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio umožňuje hostování technologie IntelliSense. IntellSense hostování umožňuje poskytovat technologii IntelliSense pro kód, který není hostitelem textový editor sady Visual Studio.  
  
## <a name="intellisense-hosting-usage"></a>IntelliSense Hosting Usage  
 Veškerý kód, který má přístup k dokončení sady a textové vyrovnávací paměti v sadě Visual Studio, můžete získat IntelliSense windows z libovolného místa v uživatelském rozhraní (UI). Ukázkové scénáře to jsou k dokončování příkazů ve **Watch** okna nebo v poli podmínku zarážky okna Vlastnosti.  
  
### <a name="implementation-interfaces"></a>Implementace rozhraní  
  
#### <a name="ivsintellisensehost"></a>IVsIntellisenseHost  
 Musí podporovat všechny součásti uživatelského rozhraní, který je hostitelem technologie IntelliSense automaticky otevíraná okna <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> rozhraní. Výchozí zobrazení textového editoru core zahrnuje stejných akcií <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> zachovat aktuální funkce IntelliSense implementace rozhraní. Ve většině případů metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> rozhraní představují podmnožinu co se implementuje na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> rozhraní. Dílčí zahrnuje zpracování uživatelského rozhraní technologie IntelliSense, blikajícího kurzoru a výběru manipulaci a funkce náhradní jednoduchý text. Kromě toho <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> rozhraní umožňuje samostatné technologie IntelliSense "předmět" a "kontext" tak, aby IntelliSense lze zadat pro témata, která přímo neexistují ve vyrovnávací paměti textu, který se používá pro kontext.  
  
#### <a name="ivsintellisensehostgethostflags"></a>IVsIntellisenseHost.GetHostFlags  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> Musí implementovat rozhraní poskytovatele <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetHostFlags%2A> metoda umožňují klientovi k určení, jaký typ IntelliSense funkce hostitel podporuje.  
  
 Příznaky hostitele, definované v [IntelliSenseHostFlags](../extensibility/intellisensehostflags.md), jsou shrnuté níž.  
  
|IntelliSense Host Flag|Popis|  
|----------------------------|-----------------|  
|IHF_READONLYCONTEXT|Nastavení tohoto příznaku znamená, že vyrovnávací paměti kontextu je jen pro čtení a úpravy dojde pouze v textu, předmětu.|  
|IHF_NOSEPERATESUBJECT|Nastavení to znamená, že příznak, který existuje se žádný samostatný předmět technologie IntelliSense. Předmět existuje ve vyrovnávací paměti kontextu, například v tradiční <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> technologie IntelliSense.|  
|IHF_SINGLELINESUBJECT|Nastavení tohoto příznaku znamená, že není předmětem Víceřádkový podporuje, například v jednom řádku upravit v **Watch** okna.|  
|IHF_FORCECOMMITTOCONTEXT|Pokud je nastavený tento příznak a musí se aktualizovat vyrovnávací paměti kontextu, umožňuje hostiteli příznak vyrovnávací paměti kontextu mají ignorovat jen pro čtení a úpravy, aby bylo možné pokračovat.|  
|IHF_OVERTYPE|Úpravy (v předmětu nebo kontext) by mělo být provedeno režim přepisování.|  
  
#### <a name="ivsintellisensehostbeforecompletorcommit-and-ivsintellisensehostaftercompletorcommit"></a>IVsIntellisenseHost.BeforeCompletorCommit a IVsIntellisenseHost.AfterCompletorCommit  
 Tyto metody zpětného volání jsou volány v okně dokončení před a za text je zpracovat, aby úkony předběžného zpracování a následné zpracování.  
  
#### <a name="ivsintellisensecompletor"></a>IVsIntellisenseCompletor  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseCompletor> Rozhraní je společně vytvořitelný verze standard dokončení okna, která používá integrované vývojové prostředí (IDE). Žádné <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> rozhraní můžete rychle implementovat technologie IntelliSense pomocí tohoto rozhraní completor.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop>
