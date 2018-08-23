---
title: Starší verze rozhraní v editoru | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy
ms.assetid: 741d45f5-0ea3-4614-972a-8728fe054e07
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1ae8f087a9f52ca2eff130b7972c2cd9d68a139f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669763"
---
# <a name="legacy-interfaces-in-the-editor"></a>Starší verze rozhraní v editoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [starší verze rozhraní v editoru](https://docs.microsoft.com/visualstudio/extensibility/legacy-interfaces-in-the-editor).  
  
Editor sady Visual Studio můžete přistupovat ze starší verze rozhraní. Visual Studio SDK zahrnuje adaptérů, označované jako *překrytí*, která umožňují tato rozhraní pro interakci s nového editoru. Doporučujeme však, že aktualizujete starší kód Refaktorovat pro použití nového editoru rozhraní API. Váš kód budou líp fungovat a využívat nové technologie, jako je Windows Presentation Foundation (WPF) a Managed Extensibility Framework (MEF).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Přizpůsobení starší verze kódu pro Editor](../extensibility/adapting-legacy-code-to-the-editor.md)|Vysvětluje, jak přizpůsobit kód do nového editoru.|  
|[Nové nebo změněné chování editoru adaptéry](../extensibility/new-or-changed-behavior-with-editor-adapters.md)|Vysvětluje, jak se liší od starších verzí editoru chování editoru adaptéry.|  
|[Uvnitř základní Editor](../extensibility/inside-the-core-editor.md)|Popisuje různé součásti dřívějších verzích editoru.|  
|[Vytvoření instance základní Editor pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)|Vysvětluje způsob používání starší verze rozhraní API k vytvoření instance základní editor.|  
|[Objekty pro vytváření editoru](../extensibility/editor-factories.md)|Vysvětluje, jak používat objekty pro vytváření editoru pomocí starší verze rozhraní API.|  
|[Postupy: registrace Editor typů souborů](../extensibility/how-to-register-editor-file-types.md)|Vysvětluje, jak propojit příponu názvu souboru do editoru.|  
|[Návod: Vytvoření základní Editor a registraci typu souboru editoru](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)|Vysvětluje, jak vytvořit základní editor a odkaz na něj příponu názvu souboru.|  
|[Postupy: zadání editory kontextu](../extensibility/how-to-provide-context-for-editors.md)|Vysvětluje, jak poskytnout kontext pro editor.|  
|[Jazykové služby a základní Editor](../extensibility/language-services-and-the-core-editor.md)|Vysvětluje interakce mezi služba jazyka a editoru.|  
|[Přístup k vyrovnávací paměti textu s použitím rozhraní API pro starší verze](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)|Vysvětluje, jak získat přístup k vyrovnávací paměti textu pomocí starší verze rozhraní API.|  
|[Přístup k text zobrazení pomocí starší verze rozhraní API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)|Vysvětluje, jak získat přístup k zobrazení textu pomocí starší verze rozhraní API.|  
|[Přizpůsobení Windows kód pomocí starší verze rozhraní API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)|Vysvětluje, jak přizpůsobit kód windows pomocí starší verze rozhraní API.|  
|[Přístup k textu vrstvy pomocí starší verze rozhraní API](../extensibility/accessing-text-layers-by-using-the-legacy-api.md)|Vysvětluje, jak získat přístup k jiné vrstvy textu pomocí starší verze rozhraní API.|  
|[Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)|Vysvětluje, jak přidat text značky pomocí starší verze rozhraní API.|  
|[Přizpůsobení nabídky a ovládací prvky editoru pomocí starší verze rozhraní API](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)|Vysvětluje, jak přizpůsobit ovládací prvky editoru pomocí starší verze rozhraní API.|  
|[Správa zpět a znovu pomocí starší verze rozhraní API](../extensibility/managing-undo-and-redo-by-using-the-legacy-api.md)|Vysvětluje, jak spravovat vrácení zpět a znovu pomocí starší verze rozhraní API.|  
|[Postupy: implementace najít a nahradit mechanismus](../extensibility/how-to-implement-the-find-and-replace-mechanism.md)|Vysvětluje, jak spravovat najít a nahradit pomocí starší verze rozhraní API.|  
|[Postupy: potlačení oznámení o změně souborů](../extensibility/how-to-suppress-file-change-notifications.md)|Vysvětluje, jak můžete potlačit oznámení o změně souborů pomocí starší verze rozhraní API.|  
|[Vytváření vlastních editorů a návrhářů](../extensibility/creating-custom-editors-and-designers.md)|Vysvětluje vytváření vlastních editorů a návrhářů.|  
|[Vývoj služby starší verze jazyka](../extensibility/internals/developing-a-legacy-language-service.md)|Obsahuje odkazy na dokumenty o funkcích, které umožňují přizpůsobení [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] základním editoru tak, že přidáte podporu pro jazykové služby.|  
|[Použití písem a barev](../extensibility/using-fonts-and-colors.md)|Vysvětluje, jak pomocí starší verze rozhraní písma a barvy.|

