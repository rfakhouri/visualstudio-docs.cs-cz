---
title: Starší verze rozhraní v editoru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy
ms.assetid: 741d45f5-0ea3-4614-972a-8728fe054e07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 64e867430c2ae55f530bdb66844240a887bd5545
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="legacy-interfaces-in-the-editor"></a>Starší verze rozhraní v editoru
Editoru Visual Studio můžete přistupovat ze starší verze rozhraní. Visual Studio SDK zahrnuje adaptérů, označované jako *překrytí*, který povolit tato rozhraní pro interakci s novou editoru. Nicméně doporučujeme aktualizovat starší verze kódu použití editoru nové rozhraní API. Váš kód budou líp fungovat a můžete používat nové technologie, jako je Windows Presentation Foundation (WPF) a Managed Extensibility Framework (MEF).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Přizpůsobení starší verze kódu do editoru](../extensibility/adapting-legacy-code-to-the-editor.md)|Vysvětluje, jak přizpůsobit kódu do nového editoru.|  
|[Nové nebo změněné chování adaptéry editoru](../extensibility/new-or-changed-behavior-with-editor-adapters.md)|Vysvětluje, jak se liší od starších verzí editoru chování adaptéry editor.|  
|[V editoru jádra](../extensibility/inside-the-core-editor.md)|Popisuje různé komponenty dřívějších verzích editoru.|  
|[Vytváření instancí editoru základní pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)|Vysvětluje, jak používat starší verze rozhraní API pro vytvoření instance editoru jádra.|  
|[Objekty Factory editoru](../extensibility/editor-factories.md)|Vysvětluje, jak používat objekty Factory editoru pomocí starší verze rozhraní API.|  
|[Postupy: registrace Editor typů souborů](../extensibility/how-to-register-editor-file-types.md)|Vysvětluje, jak propojit příponu názvu souboru k editoru.|  
|[Návod: Vytvoření základní editoru a registraci typu souboru editoru](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)|Vysvětluje, jak vytvořit základní editoru a propojit příponu názvu souboru.|  
|[Postupy: Zadejte kontext pro editory](../extensibility/how-to-provide-context-for-editors.md)|Vysvětluje, jak zajistit kontext pro vaše editor.|  
|[Jazyk služeb a editoru jádra](../extensibility/language-services-and-the-core-editor.md)|Vysvětluje interakce mezi jazykové služby a editoru.|  
|[Přístup k textová vyrovnávací paměť s použitím rozhraní API starší verze](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)|Vysvětluje, jak získat přístup k textová vyrovnávací paměť pomocí starší verze rozhraní API.|  
|[Přístup k zobrazení text s použitím rozhraní API starší verze](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)|Vysvětluje, jak pro přístup k zobrazení textu pomocí starší verze rozhraní API.|  
|[Přizpůsobení Windows kódu pomocí starší verze rozhraní API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)|Vysvětluje, jak přizpůsobit kódu windows pomocí starší verze rozhraní API.|  
|[Přístup k vrstvy textu s použitím rozhraní API starší verze](../extensibility/accessing-text-layers-by-using-the-legacy-api.md)|Vysvětluje, jak získat přístup k různých úrovní text pomocí starší verze rozhraní API.|  
|[Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)|Vysvětluje postup přidání značek text pomocí starší verze rozhraní API.|  
|[Přizpůsobení ovládací prvky editoru a nabídky pomocí starší verze rozhraní API](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)|Vysvětluje, jak přizpůsobit ovládací prvky editoru pomocí starší verze rozhraní API.|  
|[Správa zpět a znovu pomocí starší verze rozhraní API](../extensibility/managing-undo-and-redo-by-using-the-legacy-api.md)|Vysvětluje, jak spravovat vrácení zpět a znovu proveďte pomocí starší verze rozhraní API.|  
|[Postupy: implementace najít a nahradit mechanismus](../extensibility/how-to-implement-the-find-and-replace-mechanism.md)|Vysvětluje, jak spravovat najít a nahradit pomocí starší verze rozhraní API.|  
|[Postupy: potlačení upozornění o změně souboru](../extensibility/how-to-suppress-file-change-notifications.md)|Vysvětluje, jak potlačit oznámení o změně souborů pomocí starší verze rozhraní API.|  
|[Vytváření vlastních editorů a návrhářů](../extensibility/creating-custom-editors-and-designers.md)|Vysvětluje, jak vytvořit vlastní editory a návrháři.|  
|[Vývoj služby starší verze jazyka](../extensibility/internals/developing-a-legacy-language-service.md)|Obsahuje odkazy na dokumenty o funkcích, které poskytují schopnosti přizpůsobení k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] základní editor přidáním podpory služba jazyka.|  
|[Pomocí písma a barev](../extensibility/using-fonts-and-colors.md)|Vysvětluje, jak pomocí starší verze rozhraní písma a barev.|