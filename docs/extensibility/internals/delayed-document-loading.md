---
title: Odložené načtení dokumentu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: fb07b8e2-a4e3-4cb0-b04f-8eb11c491f35
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc10d7807633433b38fa8587d41c2ac3c0273ebe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="delayed-document-loading"></a>Odložené načtení dokumentu
Když uživatel neotevře řešení sady Visual Studio, většina související dokumenty nenačtou okamžitě. Rámec okna dokumentu se vytvoří ve stavu čekající na vyřízení inicializace a zástupný symbol dokumentu (říká se zakázaným inzerováním rámečkem) je umístěn v spuštění dokumentu tabulky (r...).  
  
 Rozšíření může způsobit dokumenty projektu zbytečně načíst pomocí dotazu prvky v dokumentech před načtením. To může zvýšit nároky na celkové paměti pro sadu Visual Studio.  
  
## <a name="document-loading"></a>Načtení dokumentu  
 Rámec se zakázaným inzerováním a dokumentu jsou plně inicializovat když uživatel získá přístup k dokumentu, například tak, že vyberete kartu rámce okna. Dokument může být navíc inicializované v rámci rozšíření, které vyžadují data dokumentu, přístup k r... přímo získat data dokumentu nebo přístup k r... nepřímo tím, že jedno z následujících volání:  
  
-   Rámec okna show – metoda: <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A>.  
  
-   GetProperty – metoda rámce okna <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> na žádném z následujících vlastností:  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
    -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>  
  
 Používá-li toto rozšíření spravovaného kódu, by neměl volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> Pokud si nejste jisti, že dokument není ve stavu čekající na vyřízení inicializace, nebo chcete dokumentu, který má být plně inicializovat... Důvodem je, že tato metoda vždy vrátí hodnotu na dokumentů datový objekt, jeho vytváření v případě potřeby. Místo toho jednu z metod by měly volat na rozhraní IVsRunningDocumentTable4.  
  
 Pokud toto rozšíření používá C++, můžete předat `null` pro parametry, které nechcete.  
  
 Načítání nepotřebné dokumentu se můžete vyhnout voláním jednu z následujících metod bez vyzvání relevantní vlastnosti: předtím, než je požádat o další vlastnosti.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> pomocí <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID6>.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A>. Tato metoda vrátí hodnotu <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> objekt, který obsahuje hodnotu pro <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> Pokud dokument ještě nebyla inicializovaná.  
  
 Můžete zjistit při načtení dokumentu se přihlásíte k r... událost, která se vyvolá, když je dokument plně inicializovat odběru. Existují dvě možnosti:  
  
-   Pokud jímky událostí implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2>, můžete <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2.OnAfterAttributeChangeEx%2A>,  
  
-   Jinak můžete přihlásíte k odběru <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterAttributeChange%2A>.  
  
 Toto je scénáři hypotetický dokumentu přístup. Visual Studio rozšíření chcete zobrazit některé informace o otevřené dokumenty, například úpravy zamykací počet a něco o data dokumentu. Výčtu dokumenty v r... pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IEnumRunningDocuments>, pak zavolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> pro každý dokument, chcete-li načíst data zámku upravit počet a dokumentu. Pokud je ve stavu čekající na vyřízení inicializace, žádají o data dokumentu způsobí zbytečně inicializovat.  
  
 Efektivnější způsob to jde použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentEditLockCount%2A> získat počet zámků upravit a pak použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A> k určení, zda byla inicializována dokumentu. Pokud nebudou obsahovat příznaků <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4>, již byl inicializován dokumentu a požadavek na data dokument s <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentData%2A> nezpůsobí všechny nepotřebné inicializace. Pokud obsahovat příznaků <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4>, rozšíření byste neměli žádají o data dokumentu, dokud se neinicializuje dokumentu. To lze zjistit v obslužné rutině události OnAfterAttributeChange(Ex).  
  
## <a name="testing-extensions-to-see-if-they-force-initialization"></a>Testování rozšíření, které chcete zobrazit, pokud jejich vynutit inicializace  
 Není k dispozici žádné viditelné cue indikující, zda byla inicializována dokumentu, tak může být obtížné zjistit, pokud je toto rozšíření vynucení inicializace. Můžete nastavit klíč registru, který usnadňuje ověření, protože způsobuje, že název každého dokumentu, který není plně inicializovat tak, aby měl text `[Stub]` v názvu.  
  
 V **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0\BackgroundSolutionLoad]**, nastavte **StubTabTitleFormatString** k **{0} [se zakázaným inzerováním]**.