---
title: Jazyk a Editor služby rozšíření | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 56c75eaca7ee97bf6ea33f3d0cce245599df5ca5
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694631"
---
# <a name="editor-and-language-service-extensions"></a>Jazyk a Editor rozšíření služeb
Většina funkcí editoru kódu sady Visual Studio můžete rozšířit. Editor je založená na Windows Presentation Foundation (WPF) a je zapsaný ve spravovaném kódu. Přestože tento přístup se liší od návrhů v dřívějších verzích sady Visual Studio, poskytuje většinu stejné funkce. Rozšíření editoru, pomocí Managed Extensibility Framework (MEF).

 Visual Studio SDK poskytuje adaptérů, označované jako *překrytí* pro podporu rozšíření VSPackages napsaných pro starší verze. Nicméně pokud máte existující VSPackage, doporučujeme aktualizovat na novou technologii získat lepší výkon a spolehlivost.

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Vytváření rozšíření pomocí šablony položky editoru](../extensibility/creating-an-extension-with-an-editor-item-template.md)|Úvod do služby pomocí šablony položky editoru.|
|[Rozšíření služby jazyk a editor](../extensibility/extending-the-editor-and-language-services.md)|Obsahuje odkazy na dokumenty, které představují návrhu a funkce základní editor a ukazují, jak ji rozšířit.|
|[Starší verze rozhraní v editoru](../extensibility/legacy-interfaces-in-the-editor.md)|Obsahuje odkazy na dokumenty, které popisují, jak získat přístup k základní editor z existujícího kódu.|
|[Vytváření vlastních editorů a návrhářů](../extensibility/creating-custom-editors-and-designers.md)|Obsahuje odkazy na dokumenty, které popisují, jak vytvořit vlastní editorů.|
|[Rozšíření služeb starší verze jazyka](../extensibility/internals/legacy-language-service-extensibility.md)|Obsahuje odkazy na dokumenty, které popisují, jak integrovat programovací jazyky do sady Visual Studio.|
|[MEF (Managed Extensibility Framework)](/dotnet/framework/mef/index)|Představuje rozhraní Managed Extensibility Framework (MEF).|
|[Windows Presentation Foundation](/dotnet/framework/wpf/index)|Zavádí Windows Presentation Foundation (WPF).|