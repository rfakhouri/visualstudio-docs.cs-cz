---
title: "Vlastnosti – okno Přehled | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Properties window
ms.assetid: 289ed4f2-02ac-4899-855e-42dfe57ee05f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1f766fe903df4f7a7ea36fb4ec1654b889457f65
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="properties-window-overview"></a>Přehled vlastností okna
**Vlastnosti** okno se používá k zobrazení vlastností objektů vybraných v dva hlavní typy k dispozici v systému windows [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Jsou tyto dva typy systému windows:  
  
-   Nástroje systému windows, jako je například Průzkumník řešení, zobrazení tříd a objektů prohlížeče  
  
-   Windows dokument obsahující tyto editory a návrháři jako Návrhář formulářů, editoru XML a HTML editor  
  
## <a name="using-the-properties-window"></a>Pomocí okna Vlastnosti  
 **Vlastnosti** okno zobrazuje vlastnosti jeden nebo více vybraných položek. Pokud je vybraných více položek, zobrazí se průnik všechny vlastnosti pro všechny vybrané objekty.  
  
 Události související s vybraný objekt v okně návrhu formuláře nebo editor HTML pomocí metadat modelu COM + se zobrazují v **vlastnosti** okno. Například můžete vybrat tlačítko a zobrazit související události, jako například `OnClick` událostí, které může být na toto tlačítko.  
  
 Události zobrazené v **vlastnosti** okno se primárně používají s objekty, které jsou vázány na kódu. Pokud upravujete formát souboru, který nemá nic dělat s kód, ale nebudete mít žádné události. Události se zobrazí pouze v **vlastnosti** okno při vytvoření vazby mezi systémem kódu a určité události související s konkrétní objekty. Příkladem může být kódu na pozadí vybraný objekt, který spouští při aktivaci tento objekt.  
  
 Následující tabulka uvádí primární rozhraní používaných **vlastnosti** okno.  
  
|Název rozhraní|Popis|  
|--------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>|Obsahuje seznam kategorií, které **vlastnosti** okno a každé vlastnosti se mapuje na kategorie.|  
|[IDispatch – rozhraní](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx)|Poskytuje metody a vlastnosti, které chcete programování nástroje a další aplikace, které podporují automatizace objektu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IProvidePropertyBuilder>|Obsahuje znak výpustky (...) tlačítka názvem *počítačů* , otevřete modálních dialogových oken implementované samotného objektu. Použít, když hodnota není snadno zadaný uživatelem v textovém poli. Například se může použít k otevření volby barev, které určuje hodnoty RGB pro vás.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>|Poskytuje přístup k objektům použít k aktualizaci informací zobrazených v **vlastnosti** okno. <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>je implementováno modulem VSPackages pro každé okno, který obsahuje vybrat objekty s souvisejících vlastností, který se má zobrazit.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>|Poskytuje informace o typu objektu, například metody rozhraní a pole do struktury.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>|Umožňuje VSPackages přijímat oznámení o události výběr a načíst informace o aktuální projekt hierarchii, položky, hodnota elementu a kontext uživatelského rozhraní příkazů.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMultiItemSelect>|Poskytuje prostředí s přístupem k více výběrů.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>|Použitý k poskytnutí lokalizovaných názvů na některé vlastnosti zobrazené na **vlastnosti** okno.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents>|Upozorní registrované VSPackages změn pro aktuální výběr, hodnota elementu nebo kontext uživatelského rozhraní příkazů.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>|Upozorní prostředí změny v aktuálním výběru a poskytuje přístup k hierarchii a položku informace týkající se nového výběru.|  
  
 Další informace o `IDispatch`, najdete v knihovně MSDN.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření vlastnosti](../../extensibility/internals/extending-properties.md)   
 [Pole a rozhraní okna Vlastnosti](../../extensibility/internals/properties-window-fields-and-interfaces.md)