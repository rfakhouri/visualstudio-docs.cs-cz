---
title: "Služby rozšíření editoru a jazyk | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0e5ad07694604c7b61c922cd097809fa037e0501
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="editor-and-language-service-extensions"></a>Editor a rozšíření služeb jazyk
Můžete rozšířit většinu funkcí editoru kódu v sadě Visual Studio. Editor je založený na Windows Presentation Foundation (WPF) a je zapsané ve spravovaném kódu. I když tento návrh se liší od návrhů v dřívějších verzích sady Visual Studio, poskytuje nejvíc stejné funkce. Chcete-li rozšířit editor, použijte Managed Extensibility Framework (MEF).  
  
 Visual Studio SDK poskytuje adaptérů, označované jako *překrytí* pro podporu VSPackages napsaných pro starší verze. Nicméně pokud máte existující VSPackage, doporučujeme aktualizovat na novou technologií získat lepší výkon a spolehlivost.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Vytváření rozšíření pomocí šablony položky editoru](../extensibility/creating-an-extension-with-an-editor-item-template.md)|Základní informace o použití šablon položek Editor.|  
|[Rozšíření pro Editor a jazyk služby](../extensibility/extending-the-editor-and-language-services.md)|Odkazy na dokumenty, které zavést návrhu a funkce editoru jádra a ukazují, jak ji rozšířit.|  
|[Starší verze rozhraní v editoru](../extensibility/legacy-interfaces-in-the-editor.md)|Odkazy na dokumenty, které vysvětlují, jak pro přístup k editoru základní z existujícího kódu.|  
|[Vytváření vlastních editory a návrhářů](../extensibility/creating-custom-editors-and-designers.md)|Odkazy na dokumenty, které vysvětlují, jak vytvořit vlastní editory.|  
|[Rozšíření služby starší verze jazyka](../extensibility/internals/legacy-language-service-extensibility.md)|Odkazy na dokumenty, které popisují, jak integrovat programovací jazyky do sady Visual Studio.|  
|[Spravovaná rozšíření Framework (MEF)](/dotnet/framework/mef/index)|Představuje rozhraní spravované rozšiřitelnosti (MEF).|  
|[Windows Presentation Foundation](/dotnet/framework/wpf/index)|Zavádí Windows Presentation Foundation (WPF).|