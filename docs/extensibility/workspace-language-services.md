---
title: Pracovní prostory a jazyk služby v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 8631ffea-83c8-4fd4-a01e-c59772e89c84
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 551a621ab97c232970d6ef67da14379c5cdfbd46
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="workspaces-and-language-services"></a>Pracovní prostory a jazyk služby

Můžete zadat jazyk služby [otevřít složku](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) uživatelé stejné bohaté jazykové funkce jsou slouží jako při práci s projekty a řešení. Služba jazyka může aktivovat samoobslužné podle příponu souboru nebo obsah otevřenou dokumentu, i když tato služba jazyka "přijít soubor" je omezený na zvýraznění syntaxe. Další informace, je nutné k zajištění bohatší možnosti při úpravě nebo revizi zdrojového kódu. Každá služba jazyk má svou vlastní rozhraní API pro inicializaci pomocí této velmi kontextuální data pro dokument. To je obvykle spravuje systém projektu, který je úzce párované, aby se služba jazyka a systém sestavení.

## <a name="initialization"></a>Inicializace

V [prostoru](workspaces.md), jsou iniciovány jazyk služby <xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider> rozšíření bod, který se specializuje pouze na této službě jazyk a neví nic vytváření sestavení. Tímto způsobem můžete vlastník služby jazyk udržovat jeden otevřít složku rozšíření bez ohledu na to, kolik vzory existovat v rámci složek a souborů ke spuštění jejich kompilátoru během sestavení (například MSBuild soubory pravidel, atd.). Soubory, ze které byl vytvořen kontext souboru se změní na disku a kontext souboru se aktualizují, je poskytovatele služeb jazyk upozornění aktualizovanou sadu kontexty souboru. Poskytovatel služeb jazyk aktualizovat svůj model.

Po otevření dokumentu v editoru Visual Studio uvažuje pouze jazyk poskytovatelé služeb, kteří vyžadují kontextu typy souborů, pro které můžete najít odpovídající zprostředkovatele kontextu souboru. Poté předá kontexty souboru z odpovídající následující zprostředkovatele k poskytovateli služby vybraný jazyk prostřednictvím `ILangaugeServiceProvider.InitializeAsync`. Co poskytovatele služeb jazyk v případě data kontextu souboru je podrobností implementace poskytovatele služeb jazyk, že očekávané uživatelské prostředí je bohatší služba jazyka, pro který otevřít dokument.

## <a name="using-ilanguageserviceprovider"></a>Pomocí ILanguageServiceProvider

Služba jazyka bude upozorněn kontext soubor je vytvořen s `ContextType` odpovídá jednomu z `SupportedContextTypes` hodnoty jazyk serveru exportovat atribut.

Pro podporu služby jazyk, bude nutné rozšíření:

- Jedinečný `Guid`. Bude se používat pro `SupportedContextTypes` atribut argumenty a v `FileContext` objektu.
- Kontext souboru jazyka
  - Objekt pro vytváření zprostředkovatelů
    - `ExportFileContextProviderAttribute` atribut s výše jednoznačně generované `Guid` v `SupportedContextTypes`
    - Implementuje `IWorkspaceProviderFactory<IFileContextProvider>`
  - Implementace zprostředkovatele `IFileContextProvider.GetContextsForFileAsync`
    - Vytvořit novou `FileContext` s `contextType` argument konstruktoru jako jednoznačně generovaného `Guid`
    - Použití `Context` vlastnost `FileContext` poskytnout dodatečná data k `ILanguageServiceProvider`
- Služba jazyka
  - Objekt pro vytváření zprostředkovatelů
    - `ExportLanguageServiceProvider` atribut s výše jednoznačně generované `Guid` v `SupportedContextTypes`
    - Implementuje `IWorkspaceProviderFactory<ILanguageServiceProvider>`
  - Zprostředkovatel
    - Implementuje `ILanguageServiceProvider`
    - Použití `ILanguageServiceProvider.InitializeAsync` povolit jazyk služeb pro zadané argumenty při otevření souboru
    - Použití `ILanguageServiceProvider.UninitializeAsync` zakázat jazykových služeb pro zadané argumenty při zavření souboru

>[!WARNING]
>`ILanguageServiceProvider` Metody může vyvolat prostoru na hlavní vlákno. Zvažte možnost plánování práce v jiném podprocesu aby nedošlo k zavedení uživatelské rozhraní se zpozdí.

## <a name="language-server-protocol"></a>Jazyk serveru protokolu

`Microsoft.VisualStudio.Workspace.*` Rozhraní API nejsou jediný způsob, jak povolit jazyk služby v otevřené složce. Další možností je použít server jazyk. Další informace najdete v tématu o [jazyk serveru protokol](language-server-protocol.md).

## <a name="related-interfaces"></a>Související rozhraní

- <xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider> je voláno, když je soubor odpovídající typy souborů otevřít nebo uzavřený pro úpravy.

## <a name="next-steps"></a>Další kroky

* [Pracovní prostor sestavení](workspace-build.md) -otevřít složku podporuje sestavení systémů, jako jsou nástroje MSBuild a soubory pravidel. 