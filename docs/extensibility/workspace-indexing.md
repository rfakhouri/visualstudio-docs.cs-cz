---
title: Pracovní prostor indexování v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 3163e98c-1c79-48a7-813f-7923be894ba1
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 5004db0d895d1fdc697c18606c346c24cd484527
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143423"
---
# <a name="workspace-indexing"></a>Pracovní prostor indexování

V řešení, jsou zajišťuje funkce pro sestavení projektu systémy, ladit, **GoTo** symbol vyhledávání a další. Systémy projektu můžete provést činnost, vzhledem k tomu, že porozumí vztah a možnosti souborů v rámci projektu. [Otevřít složku](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) prostoru musí stejné přehledy zajistit také bohaté funkce rozhraní IDE. Kolekce a trvalé úložiště těchto dat je procesu označovaného jako indexování pracovního prostoru. Tato data indexované můžete vyhledávat pomocí sada asynchronní rozhraní API. Extender mohl stát součástí procesu indexování tím, že poskytuje <xref:Microsoft.VisualStudio.Workspace.Indexing.IFileScanner>s, který vědět, jak pro zpracování určitých typů souborů.

## <a name="types-of-indexed-data"></a>Typy indexovaná data

Existují tři typy dat, které jsou uloženy. Poznámka: na typ očekávaný ze souboru skenerů se liší od typu deserializovat z indexu.

|Data|Skener typu souboru|Typ výsledku dotazu indexu|Souvisejících typů|
|--|--|--|--|
|Odkazy|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceInfo>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceResult>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceInfoType>|
|Symboly|<xref:Microsoft.VisualStudio.Workspace.Indexing.SymbolDefinition>|<xref:Microsoft.VisualStudio.Workspace.Indexing.SymbolDefinitionSearchResult>|<xref:Microsoft.VisualStudio.Workspace.Indexing.ISymbolService> slouží místo `IIndexWorkspaceService` pro dotazy|
|Hodnoty data|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileDataValue>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileDataResult`1>||

## <a name="querying-for-indexed-data"></a>Dotazování pro indexovaná data

Existují dva asynchronní typy, které jsou k dispozici pro přístup k trvalá data. První je prostřednictvím <xref:Microsoft.VisualStudio.Workspace.Indexing.IIndexWorkspaceData>. Poskytuje základní přístup do jednoho souboru `FileReferenceResult` a `FileDataResult` data a ukládá do mezipaměti výsledky. Druhá <xref:Microsoft.VisualStudio.Workspace.Indexing.IIndexWorkspaceService> která nepoužívá ukládání do mezipaměti, ale umožňuje více možností dotazování.

```csharp
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Indexing;

private static IIndexWorkspaceData GetCachedIndexedData(IWorkspace workspace)
{
    // Gets access to indexed data wrapped in a cache.
    return workspace?.GetIndexWorkspaceDataService()?.CreateIndexWorkspaceData();
}

private static IIndexWorkspaceService GetDirectIndexedData(IWorkspace workspace)
{
    // Gets direct access to indexed data.
    // Can also be casted to IIndexWorkspaceService2.
    return workspace?.GetIndexWorkspaceService();
}
```

## <a name="participating-in-indexing"></a>Účastní indexování

Indexování prostoru zhruba následuje následující sekvenci:

1. Zjišťování a trvalost souboru systémových entit v pracovním prostoru (pouze na počáteční otevírání kontrola).
1. Na soubor, odpovídající zprostředkovatele s nejvyšší prioritou se zobrazí výzva k vyhledání `FileReferenceInfo`s.
1. Na soubor, odpovídající zprostředkovatele s nejvyšší prioritou se zobrazí výzva k vyhledání `SymbolDefinition`s.
1. Na soubor, všechny poskytovatele vyzváni k `FileDataValue`s.

Rozšíření můžete exportovat skener implementací `IWorkspaceProviderFactory<IFileScanner>` a export na typ s <xref:Microsoft.VisualStudio.Workspace.Indexing.ExportFileScannerAttribute>. `SupportedTypes` Argument atributu by měla být jedna nebo více hodnot z <xref:Microsoft.VisualStudio.Workspace.Indexing.FileScannerTypeConstants>. Na příkladu skener, najdete v části VS SDK [ukázka](https://github.com/Microsoft/VSSDK-Extensibility-Samples/blob/master/Open_Folder_Extensibility/C%23/SymbolScannerSample/TxtFileSymbolScanner.cs).

> [!WARNING]
> Neexportovat skener souboru, který podporuje `FileScannerTypeConstants.FileScannerContentType` typu. Používá se pro Microsoft interní pouze pro účely.

V situacích, pokročilé může podporovat rozšíření dynamicky libovolnou sadu typy souborů. Místo abyste exportovali MEF `IWorkspaceProviderFactory<IFileScanner>`, můžete exportovat rozšíření `IWorkspaceProviderFactory<IFileScannerProvider>`. Po zahájení indexování bude tento typ objektu pro vytváření být importován, vytváření instance a mít jeho <xref:Microsoft.VisualStudio.Workspace.Indexing.IFileScannerProvider.GetSymbolScannersAsync%2A> volaná metoda. `IFileScanner` instance podpora libovolná hodnota od `FileScannerTpeConstants` bude přijmout, ne jenom symboly.

## <a name="next-steps"></a>Další kroky

* [Pracovní prostory a jazyk služby](workspace-language-services.md) – zjistěte, jak integrovat jazykových služeb do pracovní prostor služby otevřít složku.
* [Pracovní prostor sestavení](workspace-build.md) -otevřít složku podporuje sestavení systémů, jako jsou nástroje MSBuild a soubory pravidel.