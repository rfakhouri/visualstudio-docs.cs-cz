---
title: Pracovní prostory a jazykových služeb v sadě Visual Studio | Dokumentace Microsoftu
ms.date: 02/21/2018
ms.topic: conceptual
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 2893ae2bcd70ff317ba799fea6cfd2751c685731
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62952693"
---
# <a name="workspaces-and-language-services"></a>Pracovní prostory a služeb jazyka

Jazykové služby může poskytnout [otevřít složku](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) uživatelů ke stejným funkcím bohatou jazykovou jsou slouží jako při práci s projekty a řešeními. Služba jazyka svým může aktivovat na základě přípony souboru nebo obsah otevřený dokument i když tato "dojde ke ztrátě soubor" služba jazyka je omezená na zvýraznění syntaxe. Další informace, je potřeba poskytnout pohodlnější a pestřejší prostředí při úpravách/kontrola zdrojového kódu. Každá služba jazyk má svůj vlastní rozhraní API pro inicializaci s těmito daty velmi kontextové pro dokument. To je obvykle spravuje systém projektu, který je pevně spárován služba jazyka a systém sestavení.

## <a name="initialization"></a>Inicializace

V [pracovního prostoru](workspaces.md), jsou inicializovány jazykové služby <xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider> rozšiřovací bod, který se specializuje pouze na tuto službu jazyka a neví nic o vytváření sestavení. Tímto způsobem může vlastník služby jazyka udržovat jeden otevřít složku rozšíření bez ohledu na to, kolik vzory existovat v rámci složky a soubory ke spuštění jejich kompilátoru během sestavování (například MSBuild soubory pravidel, atd.). Soubory, ze které se vytvoří místní soubor se změnil na disku a aktualizuje kontext souboru, je zprostředkovatel služby jazyka upozornění aktualizované sady kontexty souborů. Poskytovatel služeb jazyka může aktualizovat svůj model.

Při otevření dokumentu v editoru sady Visual Studio uvažuje pouze jazyk poskytovatelů služeb, které vyžadují kontextu typy souborů, u kterých odpovídající poskytovatel kontextu souboru najdete. Poté předá kontexty souborů z odpovídající poskytovatelů pro vybraný jazyk poskytovatele služeb prostřednictvím `ILanguageServiceProvider.InitializeAsync`. Poskytovatel služeb jazyka čemu se, že soubor kontext dat je podrobnost implementace poskytovatele služeb jazyka, ale byl očekáván typ user prostředí je bohatší služba jazyka pro daný dokument otevřel.

## <a name="using-ilanguageserviceprovider"></a>Pomocí ILanguageServiceProvider

Služba jazyka budete upozorněni při vytvoření kontextu souboru se `ContextType` , který odpovídá jednomu z `SupportedContextTypes` hodnoty jazyka serveru pro export – atribut.

Pro podporu služby jazyka, bude nutné rozšíření:

- Jedinečné `Guid`. Ten se použije pro `SupportedContextTypes` atribut argumenty a `FileContext` objektu.
- Jazyk souboru kontextu
  - Objekt pro vytváření zprostředkovatele
    - `ExportFileContextProviderAttribute` atribut pomocí výše uvedeného jednoznačně generované `Guid` v `SupportedContextTypes`
    - Implementuje `IWorkspaceProviderFactory<IFileContextProvider>`
  - Používaná implementace poskytovatele `IFileContextProvider.GetContextsForFileAsync`
    - Vytvořit nový `FileContext` s `contextType` argument konstruktoru jako jednoznačně vygenerované `Guid`
    - Použití `Context` vlastnost `FileContext` poskytnout další data k `ILanguageServiceProvider`
- Služba jazyka
  - Objekt pro vytváření zprostředkovatele
    - `ExportLanguageServiceProvider` atribut pomocí výše uvedeného jednoznačně generované `Guid` v `SupportedContextTypes`
    - Implementuje `IWorkspaceProviderFactory<ILanguageServiceProvider>`
  - Poskytovatel
    - Implementuje `ILanguageServiceProvider`
    - Použití `ILanguageServiceProvider.InitializeAsync` povolit jazykové služby pro argumenty předané, když je soubor otevřen
    - Použití `ILanguageServiceProvider.UninitializeAsync` zakázat jazykové služby pro argumenty předané při zavření souboru

>[!WARNING]
>`ILanguageServiceProvider` Metody může vyvolávat pracovního prostoru na hlavním vlákně. Zvažte možnost plánování práce na jiném vlákně, aby nedošlo k zavedení opoždění v uživatelském rozhraní.

## <a name="language-server-protocol"></a>Protokol jazyka serveru

`Microsoft.VisualStudio.Workspace.*` API nejsou jediný způsob, jak povolit službě jazyka v otevřené složce. Další možností je použít server jazyka. Další informace, přečtěte si informace o [protokol jazyka serveru](language-server-protocol.md).

## <a name="related-interfaces"></a>Související rozhraní

- <xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider> je vyvolána při otevření nebo zavření pro úpravy souboru odpovídajících typů souborů.

## <a name="next-steps"></a>Další kroky

* [Pracovní prostor sestavení](workspace-build.md) -podporuje funkce Otevřít složku sestavení systémy, jako je MSBuild a soubory pravidel.