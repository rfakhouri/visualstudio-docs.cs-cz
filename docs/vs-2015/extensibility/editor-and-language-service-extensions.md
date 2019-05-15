---
title: Jazyk a Editor služby rozšíření | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7fa3e4be6ee44011eb1286e3ebf22ee69f8e3397
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65683119"
---
# <a name="editor-and-language-service-extensions"></a>Editor a rozšíření služeb jazyka
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Většina funkcí editoru kódu sady Visual Studio můžete rozšířit. Editor je založená na Windows Presentation Foundation (WPF) a je zapsaný ve spravovaném kódu. Přestože tento přístup se liší od návrhů v dřívějších verzích sady Visual Studio, poskytuje většinu stejné funkce. Rozšíření editoru, pomocí Managed Extensibility Framework (MEF).  
  
 Visual Studio SDK poskytuje adaptérů, označované jako *překrytí* pro podporu rozšíření VSPackages napsaných pro starší verze. Nicméně pokud máte existující VSPackage, doporučujeme aktualizovat na novou technologii získat lepší výkon a spolehlivost.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Vytváření rozšíření pomocí šablony položky editoru](../extensibility/creating-an-extension-with-an-editor-item-template.md)|Úvod do služby pomocí šablony položky editoru.|  
|[Rozšíření pro editor a služeb jazyka](../extensibility/extending-the-editor-and-language-services.md)|Obsahuje odkazy na dokumenty, které představují návrhu a funkce základní editor a ukazují, jak ji rozšířit.|  
|[Zastaralá rozhraní v editoru](../extensibility/legacy-interfaces-in-the-editor.md)|Obsahuje odkazy na dokumenty, které popisují, jak získat přístup k základní editor z existujícího kódu.|  
|[Vytváření vlastních editorů a návrhářů](../extensibility/creating-custom-editors-and-designers.md)|Obsahuje odkazy na dokumenty, které popisují, jak vytvořit vlastní editorů.|  
|[Rozšíření služeb starší verze jazyka](../extensibility/internals/legacy-language-service-extensibility.md)|Obsahuje odkazy na dokumenty, které popisují, jak integrovat programovací jazyky do sady Visual Studio.|  
|[MEF (Managed Extensibility Framework)](https://msdn.microsoft.com/library/6c61b4ec-c6df-4651-80f1-4854f8b14dde)|Představuje rozhraní Managed Extensibility Framework (MEF).|  
|[Windows Presentation Foundation](https://msdn.microsoft.com/library/f667bd15-2134-41e9-b4af-5ced6fafab5d)|Zavádí Windows Presentation Foundation (WPF).|
