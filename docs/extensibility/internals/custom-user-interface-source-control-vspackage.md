---
title: "Vlastní uživatelské rozhraní (Zdroj ovládacího prvku VSPackage) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user interface, source control packages
- source control packages, user interface
ms.assetid: f35ddb24-53bf-461e-b34f-7414f657c082
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3d3c223b45d0228781779a73f057ef3518374344
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="custom-user-interface-source-control-vspackage"></a>Vlastní uživatelské rozhraní (Zdroj ovládacího prvku VSPackage)
VSPackage deklaruje jeho položek nabídky a jejich výchozí stavy prostřednictvím soubor Visual Studio příkaz tabulky (.vsct). [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE) zobrazí položek nabídky v jejich výchozí stavy, dokud VSPackage je načtena. Následně <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda je volána k povolení nebo zakázání položky nabídky.  
  
 VSPackage můžete nastavit klíč registru, takže VSPackage mohou být načteny automaticky v závislosti na kontextu příkaz uživatelské rozhraní (UI), i když obvykle zdroj řízení VSPackage by se měly načíst na vyžádání místo právě probíhá přepínání na konkrétní kontext uživatelského rozhraní. Další informace o tomto klíči registru AutoLoadPackages najdete v tématu [Správa VSPackages](../../extensibility/managing-vspackages.md).  
  
## <a name="vspackage-ui"></a>VSPackage uživatelského rozhraní  
 Zdroj balíčku ovládací prvek je implementovaný jako VSPackage a nepoužívá žádné uživatelské rozhraní z [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Každý zdrojového kódu VSPackage musíte zadat vlastní prvky uživatelského rozhraní, například položky nabídky, skupiny nabídek, nástroj windows, panely nástrojů a všechny požadované uživatelského rozhraní pro nastavení možností konkrétní k řízení zdrojů VSPackage. Tyto prvky uživatelského rozhraní lze povolit staticky nebo dynamicky. Statické prvky uživatelského rozhraní jsou definovány v souboru .vsct a zobrazují, jestli VSPackage je načtena, nebo ne. Dynamické prvky uživatelského rozhraní můžou být vidět v závislosti na kontextu konkrétní příkaz uživatelského rozhraní, jako například <xref:EnvDTE.Constants.vsContextNoSolution>, nebo v důsledku volání <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda. Viditelnost dynamické prvky uživatelského rozhraní v souladu s strategie pro zpožděné načítání VSPackages.  
  
## <a name="ui-constraints-on-source-control-vspackages"></a>Omezení uživatelského rozhraní pro řízení VSPackages zdroje  
 Protože správa zdrojového kódu VSPackage nelze odebrat z prostředí IDE po je načtena, musí být VSPackage moci zadat neaktivním stavu. Když VSPackage obdrží oznámení, že již není aktivní, VSPackage zakáže jeho uživatelském rozhraní a ignoruje interakce externí IDE. Implementace VSPackage <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda by měla skrýt příkazy, když VSPackage není aktivní.  
  
 Každý zdrojového kódu VSPackage musí implementovat `IVsSccProvider` rozhraní. Dvě metody pro rozhraní je <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetActive%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetInactive%2A>, musí být implementované VSPackage.  
  
 Správa zdrojového kódu VSPackage může mít předplatné různé IDE události, které jsou implementované <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>a tak dále. Navíc VSPackage může byla implementována rozhraní registru povoleno zpětného volání, jako <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>. Ty se musí všechny ignorovat. Pokud není aktivní.  
  
 V následujícím seznamu jsou rozhraní vliv na aktivní stav VSPackage Správa zdrojového kódu:  
  
-   Sledování dokumentů projektu události.  
  
-   Řešení události.  
  
-   Rozhraní trvalost řešení. Pokud není aktivní, by neměl balíčky zápis do souborů .sln a .suo.  
  
-   Vlastnost Extender.  
  
 Požadované <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, a také všechny volitelné rozhraní přidružené k správě zdrojového kódu, nejsou volána, když se správa zdrojového kódu VSPackage je neaktivní.  
  
 Když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] spustí IDE, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nastaví kontext příkaz uživatelského rozhraní na ID aktuálního zdrojového kódu pro výchozí VSPackage ID. To způsobí, že rozhraní statické prvku aktivní zdrojová VSPackage se objeví v prostředí IDE bez ve skutečnosti načítání VSPackage. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]pozastaví pro VSPackage při registraci s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider> před umožňuje volání VSPackage.  
  
 Následující tabulka popisuje konkrétní podrobnosti o tom, jak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE skryje různé položky uživatelského rozhraní.  
  
|Položka uživatelského rozhraní|Popis|  
|-------------|-----------------|  
|Nabídek a panelů nástrojů|Zdrojový balíček řízení musíte nastavit počáteční stav viditelnosti nabídek a panelů nástrojů ID balíčku řízení zdroje v [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md) .vsct souboru. To umožňuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE správně nastavit stav položky nabídky bez načítání VSPackage a volání implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda.|  
|Nástroje systému windows|Správa zdrojového kódu VSPackage skryje všechny nástroj windows, které vlastní, když je proveden neaktivní.|  
|Správa zdrojového kódu VSPackage specifické možnosti stránky|Klíč registru HKLM\SOFTWARE\Microsoft\VisualStudio\X.Y\ToolsOptionsPages\VisibilityCmdUIContexts umožňuje VSPackage nastavovat kontexty, ve kterých se vyžaduje její stránky možnosti, které se zobrazí. Položky registru pod tímto klíčem musel být vytvořené pomocí služby ID (SID) služby zdroj ovládacího prvku a jeho přiřazení hodnotu DWORD s hodnotou 1. Vždy, když událost uživatelského rozhraní v kontextu dojde zdrojového kódu, který není zaregistrována VSPackage, bude mít název VSPackage, pokud je aktivní.|  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider>   
 <xref:EnvDTE.Constants.vsContextNoSolution>   
 [Správa rozšíření VSPackages](../../extensibility/managing-vspackages.md)