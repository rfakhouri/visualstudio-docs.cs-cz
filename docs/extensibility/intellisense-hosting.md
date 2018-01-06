---
title: "Hostování IntelliSense | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - IntelliSense hosting
ms.assetid: 20c61f8a-d32d-47e2-9c67-bf721e2cbead
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9727b6fcbe3c552273ca521e8fd14ab5e5181eb7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="intellisense-hosting"></a>Hostování IntelliSense
Visual Studio umožňuje hostování IntelliSense. IntellSense hostování umožňuje poskytovat technologii IntelliSense pro kód, který není hostitelem textového editoru Visual Studio.  
  
## <a name="intellisense-hosting-usage"></a>Využití hostování IntelliSense  
 Kód, který má přístup k sadě dokončení a textovou vyrovnávací paměť v sadě Visual Studio, můžete získat IntelliSense windows z libovolného místa v uživatelském rozhraní (UI). Ukázkové scénáře to jsou dokončení v **sledovat** okno nebo v poli podmínku zarážku – vlastnosti – okno.  
  
### <a name="implementation-interfaces"></a>Implementace rozhraní  
  
#### <a name="ivsintellisensehost"></a>IVsIntellisenseHost  
 Musí podporovat libovolné součásti uživatelského rozhraní, který je hostitelem IntelliSense automaticky otevíraná okna <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> rozhraní. Výchozí základní editor textového zobrazení zahrnuje populace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> implementace, které chcete zachovat aktuální funkci IntelliSense rozhraní. Ve většině případů metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> rozhraní představují podmnožinu co se implementuje na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> rozhraní. Podmnožinu zahrnuje zpracování uživatelského rozhraní IntelliSense, pomocí kurzoru a výběr manipulaci a jednoduchý text nahrazení funkce. Kromě toho <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> rozhraní umožňuje samostatné IntelliSense "předmět" a "context", takže lze zadat IntelliSense pro témata, která nejsou k dispozici přímo ve vyrovnávací paměti text, který se používá pro kontext.  
  
#### <a name="ivsintellisensehostgethostflags"></a>IVsIntellisenseHost.GetHostFlags  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> Rozhraní poskytovatel musí implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetHostFlags%2A> metoda povolení klienta určit, jaký typ IntelliSense funkce hostitel podporuje.  
  
 Příznaky hostitele, který je definovaný v [IntelliSenseHostFlags](../extensibility/intellisensehostflags.md), jsou shrnuté níž.  
  
|Příznak hostitele IntelliSense|Popis|  
|----------------------------|-----------------|  
|IHF_READONLYCONTEXT|Tento příznak znamená, že vyrovnávací paměti kontextu nastavení jen pro čtení a úpravy dojde pouze v rámci textu subjektu.|  
|IHF_NOSEPERATESUBJECT|Nastavíte tento příznak znamená, že existuje je žádné samostatné subjektu IntelliSense. Předmět existuje ve vyrovnávací paměti kontextu, například v tradiční <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> IntelliSense systému.|  
|IHF_SINGLELINESUBJECT|Nastavení tento příznak znamená, že předmět není Víceřádkový podporující, například jeden řádek upravit v **sledovat** okno.|  
|IHF_FORCECOMMITTOCONTEXT|Pokud je nastavený tento příznak a musí být aktualizované vyrovnávací paměti kontextu, umožňuje hostiteli příznak jen pro čtení na vyrovnávací paměti kontextu, který se má ignorovat a úpravy, aby bylo možné pokračovat.|  
|IHF_OVERTYPE|Úpravy (v předmětu nebo kontextu) by mělo být provedeno v režimu přepisování.|  
  
#### <a name="ivsintellisensehostbeforecompletorcommit-and-ivsintellisensehostaftercompletorcommit"></a>IVsIntellisenseHost.BeforeCompletorCommit a IVsIntellisenseHost.AfterCompletorCommit  
 Tyto metody zpětného volání jsou volány okno dokončení před a po potvrzené, chcete-li povolit zpracování před a po zpracování textu.  
  
#### <a name="ivsintellisensecompletor"></a>IVsIntellisenseCompletor  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseCompletor> Rozhraní je společně vytvořitelné verze okna standardní dokončení, který je používán integrované vývojové prostředí (IDE). Všechny <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> rozhraní můžete rychle implementovat IntelliSense pomocí tohoto rozhraní completor.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop>