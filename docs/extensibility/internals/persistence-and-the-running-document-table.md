---
title: Trvalost a spuštění tabulky dokumentů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- persistence, managing
- IVsPersistHierarchyItem interface, implementing
- architecture, persistence
- running document table (RDT), architecture
ms.assetid: 27117eae-6c58-4189-a61a-1397a43b5ecf
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d80932ab926b7ef26eaef10991e4f5782e81c4b5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66328523"
---
# <a name="persistence-and-the-running-document-table"></a>Trvalost a spuštěná tabulka dokumentů
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE, projekty jsou zcela zodpovědní za správu trvalost jejich položky projektu, které jsou-li toho dosáhnout pomocí služby, <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>. Dokumenty představují základní jednotkou přetrvávání v prostředí sady Visual Studio. Projekty koordinovat otevření, uložení a přejmenování dokumentů s tabulce spuštěných dokumentů (r...), prostředek, který sleduje stav všech otevřených dokumentech.

## <a name="managing-persistence"></a>Správa trvalosti
 Projekty řízen implementace službu trvalého uložení prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> rozhraní. Zatímco prostředí nikdy nesmí přímo dotazem dokument k uchování samotné, požádá vlastnící projekt (nebo hierarchie) k uložení dokumentu. Umožňuje pro projekt uložte jeho data položky projektu do místních souborů, vzdálené soubory, databáze, úložiště nebo jiné médium.

 Globální prostředí udržuje rámcový. Prostředí udržuje položky pro všechna otevřená okna a dokumenty v r..., díky tomu je možné pro něho přijímat speciální oznámení, jako je například při zavření řešení. Kromě toho rámcový umožňuje prostředí tak, aby sledovat jejich odpovídající uzly v **Průzkumníka řešení**. Rámcový udržuje jeden záznam na otevřené, trvalé objektu, včetně souborů projektu a položek projektů dokumenty.

## <a name="see-also"></a>Viz také
- [Spuštění tabulky dokumentů](../../extensibility/internals/running-document-table.md)
- [Výběr a měna v prostředí IDE](../../extensibility/internals/selection-and-currency-in-the-ide.md)