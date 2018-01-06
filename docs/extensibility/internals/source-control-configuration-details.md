---
title: "Podrobnosti o konfiguraci řízení zdroje | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], configuration details
ms.assetid: adbee9fc-7a2e-4abe-a3b8-e6615bcd797f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2f8a2cc2f1c13c46b3ac4838d95ce588d0461347
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="source-control-configuration-details"></a>Podrobnosti o konfiguraci řízení zdroje
Chcete-li implementovat řízení zdrojů, je třeba správně nakonfigurovat systém projektu nebo editor proveďte následující:  
  
-   Požádat o oprávnění k přechodu do změněné stavu  
  
-   Požádat o oprávnění k uložení souboru  
  
-   Požádat o oprávnění k přidat, odebrat nebo přejmenovat soubory v projektu  
  
## <a name="request-permission-to-transition-to-changed-state"></a>Požádat o oprávnění k přechodu do změněné stavu  
 Projekt nebo editoru musíte požádat o oprávnění k přechodu do stavu změněné (dirty) voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>. Každý editor, který implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty%2A> musí volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> a přijímat schválení Chcete-li změnit dokumentu z prostředí před vrácením `True` pro `M:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty(System.Int32@)`. Projekt je v podstatě editoru soubor projektu a v důsledku toho má stejné odpovědnost pro implementaci sledování změnit stav pro soubor projektu textového editoru stejně jako pro jeho soubory. Prostředí zpracovává změněné stav řešení, ale je nutné zpracovat změněné stav libovolného objektu řešení odkazuje, ale neukládá, podobně jako soubor projektu nebo jeho položky. Obecně platí Pokud projekt nebo editoru je zodpovědný za správu trvalosti pro položku, je zodpovědný za implementaci změnil stav sledování.  
  
 V reakci `IVsQueryEditQuerySave2::QueryEditFiles` volat, prostředí můžete provádět následující:  
  
-   Odmítnout volání změnit, v takovém případě editor nebo projektu musí zůstat v nezměněném stavu (čistou).  
  
-   Označuje, že data dokumentu znovu načíst. Pro projekt prostředí dojde k opětovnému načtení dat pro projekt. Editor musí znovu načíst data z disku prostřednictvím jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> implementace. V obou případech můžete změnit kontextu v projektu nebo editoru, když je znovu načíst data.  
  
 Je složitá a obtížná úloh pozměnit odpovídající `IVsQueryEditQuerySave2::QueryEditFiles` volání do existujícího základu kódu. V důsledku toho by měla být těchto volání integrované během vytváření projektu nebo editoru.  
  
## <a name="request-permission-to-save-a-file"></a>Požádat o oprávnění k uložení souboru  
 Před projektu nebo editoru uloží soubor, musí volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>. Pro soubory projektu jsou tyto volání automaticky dokončit řešení, které zná, kdy se má uložit soubor projektu. Editory jsou zodpovědní za těchto volání Pokud editor implementace `IVsPersistDocData2` používá pomocné funkce <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>. Pokud vaše editor implementuje `IVsPersistDocData2` v tímto způsobem a potom volání `IVsQueryEditQuerySave2::QuerySaveFile` nebo `IVsQueryEditQuerySave2::QuerySaveFiles` se provádí za vás.  
  
> [!NOTE]
>  Vždy provádět tyto volání ho preventivně – to znamená, v době, když je schopný přijímat zrušit vaše editor.  
  
## <a name="request-permission-to-add-remove-or-rename-files-in-the-project"></a>Požádat o oprávnění k přidat, odebrat nebo přejmenovat soubory v projektu  
 Před projektu můžete přidat, přejmenovat nebo odebrat soubor nebo adresář, musí volat odpovídající `IVsTrackProjectDocuments2::OnQuery*` metoda žádostí o oprávnění z prostředí. Pokud je povoleno, pak projektu musí dokončit operaci a pak zavolají odpovídající `IVsTrackProjectDocuments2::OnAfter*` metoda oznámit prostředí, je operace dokončena. Projekt musí volat metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> rozhraní pro všechny soubory (například speciální soubory) a ne jenom soubory nadřazené. Volání souboru jsou povinné, ale volání adresáře jsou volitelné. Pokud váš projekt má informací v adresáři, pak by měly volat odpovídající <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> metody, ale pokud se tyto informace pak prostředí bude odvození informací v adresáři.  
  
 Projekt by neměl volat metody `IVsTrackProjectDocuments2` v projektu spustit nebo zavřít. Počkejte, až naslouchací procesy, které chcete tyto informace při spuštění <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A> událostí a iteraci v rámci řešení, aby se najít informace o potřebují. Při ukončení není potřeba tyto informace. `IVsTrackProjectDocuments2`zajišťuje z <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>.  
  
 Pro každou přidat, přejmenování a odebrat akce, je `OnQuery*` metoda a `OnAfter*` metoda. Volání `OnQuery*` metoda požádat oprávnění k přidávání, přejmenujte nebo odeberte soubor nebo adresář. Volání `OnAfter*` metoda po soubor nebo adresář má byla přidat, přejmenovat nebo odebrat, a stav projektu odráží nový stav.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>   
 [Podpora správy zdrojového kódu](../../extensibility/internals/supporting-source-control.md)