---
title: Co je nového ve Visual Studio SDK. 2019 | Dokumentace Microsoftu
ms.date: 03/29/2019
ms.topic: conceptual
ms.assetid: 4a07607b-0c87-4866-acd8-6d68358d6a47
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: daa4203ccdcbce89f1eb09efdd9433210bcbc987
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856642"
---
# <a name="whats-new-in-the-visual-studio-2019-sdk"></a>Co je nového ve Visual Studio SDK. 2019

Visual Studio SDK obsahuje následující nové a aktualizované funkce pro Visual Studio 2019.

## <a name="synchronously-autoloaded-extensions-warning"></a>Synchronně rozšíření automaticky načtený upozornění

Uživatelům se nyní zobrazí upozornění, pokud kterýkoliv z jejich nainstalovaná rozšíření je synchronně automaticky načtený při spuštění. Další informace o upozornění na [synchronně rozšíření automaticky načtený](synchronously-autoloaded-extensions.md).

## <a name="single-unified-visual-studio-sdk"></a>Jediné, jednotné Visual Studio SDK

Teď můžete získat všechny prostředky sady Visual Studio SDK prostřednictvím jeden balíček NuGet [Microsoft.VisualStudio.SDK](https://www.nuget.org/packages/microsoft.visualstudio.sdk).

## <a name="editor-registration-enhancements"></a>Vylepšení editoru registrace

Od jeho vytvoření se Visual Studio podporuje registraci vlastního editoru, kde editoru můžete deklarovat její přidružení pro konkrétní rozšíření (například .xaml a .rc), nebo, který je vhodný pro jakoukoli příponu (. *). Od verze Visual Studio 2019 verze 16.1, můžeme rozšířit podporu pro registraci editoru.

### <a name="filenames"></a>Názvy souborů

Kromě, nebo místo registrace podpory pro specifickou příponu souboru, můžete zaregistrovat editor podporuje konkrétní názvy souborů s použitím nového `ProvideEditorFilename` atribut balíčku editoru.

Například editor, který podporuje všechny soubory .json by použít `ProvideEditorExtension` atribut svého balíčku:

```cs
[ProvideEditorExtension(typeof(MyEditor), ".json", MyEditor.Priority)]
```

Počínaje 16.1, pokud MyEditor podporuje pouze několik souborů dobře známé .json, můžete místo toho použije tyto `ProvideEditorFilename` atributy do svého balíčku:

```cs
[ProvideEditorFilename(typeof(MyEditor), "particular.json", MyEditor.Priority)]
[ProvideEditorFilename(typeof(MyEditor), "special.json",    MyEditor.Priority)]
```

### <a name="uicontexts"></a>Kontextu UIContexts

Editor můžete registrovat jednu nebo více kontextu UIContexts, které představují, je-li povolena. S použitím jednoho nebo víc instancí jsou registrovány kontextu UIContexts `ProvideEditorUIContextAttribute` do balíčku, která se registruje v editoru.

Pokud editor registrovaného kontextu UIContexts:

- Pokud alespoň jedna z jeho registrovaného kontextu UIContexts aktivní při otevření souboru s danou příponou, editoru je zahrnutý do vyhledávání editoru.
- Pokud žádná z registrovaného kontextu UIContexts není aktivní, editoru není zahrnutý do vyhledávání editoru.

Pokud editor není zaregistrovat libovolný kontextu UIContexts, je vždy součástí hledání editor pro tuto příponu.

Například, pokud editor je k dispozici pouze při C# projektu je otevřen, tato přidružení ji lze deklarovat s použitím `ProvideEditorUIContext` atribut:

```cs
[ProvideEditorUIContext(typeof(MyEditor), KnownUIContexts.CSharpProjectContext)]
```