---
title: Rozšíření služby jazyka pro podporu EditorConfig
ms.date: 11/22/2017
ms.topic: conceptual
helpviewer_keywords:
- editorconfig [extensibility]
- editorconfig, supporting in a language service
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5c6974c7943a751f50cafb0b141ba9c1dfc85677
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353494"
---
# <a name="supporting-editorconfig-for-your-language-service"></a>Podpora EditorConfig pro vaši službu jazyka

[EditorConfig](http://editorconfig.org/) soubory umožňují popsat běžné možnosti textového editoru, jako je například velikost odsazení v jednotlivých projektů. Další informace o Visual Studio – podpora pro EditorConfig soubory, naleznete v tématu [vytvoření přenosné editor nastavení pomocí EditorConfig](../ide/create-portable-custom-editor-options.md).

Ve většině případů při implementaci jazyka služby Visual Studio bez další práce je potřeba podpory EditorConfig univerzální vlastnosti. Základní editor automaticky zjistí a načte soubor .editorconfig, když uživatelé otevřít soubory, a nastaví odpovídající text vyrovnávací paměť a zobrazení možností. Ale pro úpravy, jako jsou karty a mezery, některých jazykových služeb vyjádřit souhlas se službou použijte možnost zobrazení odpovídající kontextové text, nikoli pomocí globální nastavení. V těchto případech služba jazyka musí být aktualizována o podporu souborů EditorConfig.

Toto jsou změny, které jsou potřeba k aktualizaci služby jazyka pro podporu souborů EditorConfig nahrazením globální _specifické pro jazyk_ spolu s možností _kontextové_ možnost:

## <a name="indent-style"></a>Odsazení stylu

Možnosti specifické pro jazyk | Kontextové možnosti
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs|!textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)<br/>!textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)

## <a name="indent-size"></a>Velikost odsazení

Možnosti specifické pro jazyk | Kontextové možnosti
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize|textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)

## <a name="tab-size"></a>Velikost tabulátoru

Možnosti specifické pro jazyk | Kontextové možnosti
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize|textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)

## <a name="see-also"></a>Viz také:

- [Vytvoření přenosné editor nastavení pomocí EditorConfig](../ide/create-portable-custom-editor-options.md)
- [Rozšíření služeb jazyk a editor](../extensibility/extending-the-editor-and-language-services.md)