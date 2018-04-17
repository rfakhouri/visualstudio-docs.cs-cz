---
title: Služby rozšíření editoru a jazyk | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d2fceb0487c23dc34d3f4f4937d7a5998340ae3d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="editor-and-language-service-extensions"></a>Editor a rozšíření služeb jazyk
Můžete rozšířit většinu funkcí editoru kódu v sadě Visual Studio. Editor je založený na Windows Presentation Foundation (WPF) a je zapsané ve spravovaném kódu. I když tento návrh se liší od návrhů v dřívějších verzích sady Visual Studio, poskytuje nejvíc stejné funkce. Chcete-li rozšířit editor, použijte Managed Extensibility Framework (MEF).  
  
 Visual Studio SDK poskytuje adaptérů, označované jako *překrytí* pro podporu VSPackages napsaných pro starší verze. Nicméně pokud máte existující VSPackage, doporučujeme aktualizovat na novou technologií získat lepší výkon a spolehlivost.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Vytváření rozšíření pomocí šablony položky editoru](../extensibility/creating-an-extension-with-an-editor-item-template.md)|Základní informace o použití šablon položek Editor.|  
|[Rozšíření pro editor a služeb jazyka](../extensibility/extending-the-editor-and-language-services.md)|Odkazy na dokumenty, které zavést návrhu a funkce editoru jádra a ukazují, jak ji rozšířit.|  
|[Starší verze rozhraní v editoru](../extensibility/legacy-interfaces-in-the-editor.md)|Odkazy na dokumenty, které vysvětlují, jak pro přístup k editoru základní z existujícího kódu.|  
|[Vytváření vlastních editorů a návrhářů](../extensibility/creating-custom-editors-and-designers.md)|Odkazy na dokumenty, které vysvětlují, jak vytvořit vlastní editory.|  
|[Rozšíření služeb starší verze jazyka](../extensibility/internals/legacy-language-service-extensibility.md)|Odkazy na dokumenty, které popisují, jak integrovat programovací jazyky do sady Visual Studio.|  
|[MEF (Managed Extensibility Framework)](/dotnet/framework/mef/index)|Představuje rozhraní spravované rozšiřitelnosti (MEF).|  
|[Windows Presentation Foundation](/dotnet/framework/wpf/index)|Zavádí Windows Presentation Foundation (WPF).|