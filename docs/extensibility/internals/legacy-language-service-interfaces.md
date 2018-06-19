---
title: Rozhraní služeb starší verze jazyka | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IVsLanguageInfo interface
- language services, objects
ms.assetid: 03b2d507-f463-417e-bc22-bdac68eeda52
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b2861c4d6307442e1650b44d2b15f2a084ac7715
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134617"
---
# <a name="legacy-language-service-interfaces"></a>Rozhraní služeb starší verze jazyka
Pro žádný konkrétní programovací jazyk může být pouze jednu instanci služby jazyk najednou. Služba jednoho jazyka však může sloužit více než jeden editor.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Nepřidruží žádné konkrétní editor služba jazyka. Proto pokud budete požadovat jazyk operace služby, musíte určit editor odpovídající jako parametr.  
  
## <a name="common-interfaces-associated-with-language-services"></a>Společné rozhraní související s jazyk službami  
 Editor voláním získá vaše služba jazyka <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> na příslušné VSPackage. Službu, kterou ID (SID) předaná toto volání identifikuje požadované služby jazyk.  
  
 Rozhraní služeb základní jazyk můžete implementovat na libovolný počet samostatné třídy. Běžný postup je však k implementaci rozhraní následující do jedné třídy:  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageBlock> (volitelné)  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> Rozhraní musí být implementováno na všechny služby jazyk. Poskytuje informace o službě jazyk, jako je například lokalizovaný název jazyka, přidružená služba jazyka a jak načíst colorizer přípony názvů souborů.  
  
## <a name="additional-language-service-interfaces"></a>Rozhraní pro další jazyk služeb  
 Pomocí služby jazyk lze zadat dalších rozhraní. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] požádá o samostatnou instanci tato rozhraní pro každou instanci textová vyrovnávací paměť. Proto měli byste implementovat každé z těchto rozhraní u svého vlastního objektu. V následující tabulce jsou uvedeny rozhraní, které vyžadují jednu instanci na instanci textové vyrovnávací paměti.  
  
|Rozhraní|Popis|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>|Spravuje kód okno vylepšení, například panelu rozevíracího seznamu. Toto rozhraní můžete získat pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> metoda. Existuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> za kódu – okno.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>|Vybarví klíčová slova jazyka a oddělovače. Toto rozhraní můžete získat pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> metoda. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> je volána v době Malování. Vyhněte se výpočetně náročných na výpočetní uvnitř <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> nebo může sníží výkon.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>|Poskytuje popisy tlačítek parametr IntelliSense. Když služba jazyk rozpozná znak, který označuje dat metoda by měla být zobrazeny, jako je například otevřené závorky, zavolá <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> zobrazit metoda oznámit text, který služba jazyka je připraven k zobrazení popisu tlačítka informace o parametru. Textového zobrazení pak zavolá zpátky do provozu jazyk podle pomocí metody <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> rozhraní získat požadované informace k zobrazení popisu tlačítka.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet>|Poskytuje dokončování IntelliSense. Jazyk služba je připravena k zobrazení seznamu dokončení, zavolá <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> metodu textového zobrazení. Textového zobrazení pak zavolá zpátky do provozu jazyk podle pomocí metody na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> objektu.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter>|Umožňuje úpravu textového zobrazení pomocí obslužná rutina příkazu. Třída, ve kterém můžete implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> také musí implementovat rozhraní <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Načte textového zobrazení <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> objekt pomocí dotazu <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> objekt, který je předán do <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> metoda. By měl být jeden <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> objekt pro každého zobrazení.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Zabrání příkazy, že uživatel zadá do okna kódu. Monitorování výstup z vaší <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> implementace Zobrazit úpravy a poskytují informace o vlastní dokončení<br /><br /> Předat vaše <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> objekt, který chcete textového zobrazení, volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>.|  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby jazyk starší verze](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [Kontrolní seznam: Vytvoření služby starší verze jazyka](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)