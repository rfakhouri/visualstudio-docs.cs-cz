---
title: Práce s datových sad ve víceúrovňových aplikacích
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- datasets [Visual Basic], n-tier applications
- multi-tier database applications
- DataSet project [VS n-tier applications]
- distributed applications [VS n-tier applications]
- data [Visual Basic], n-tier applications
- TableAdapters, n-tier applications
- n-tier applications
- tiers, n-tier applications
- typed datasets, n-tier applications
- multiple tier applications
ms.assetid: f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 1bf94efcfa7c3829328b3ddabcfa96b779cb1b9f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="work-with-datasets-in-n-tier-applications"></a>Práce s datových sad ve víceúrovňových aplikacích

*Vícevrstvé datové aplikace* datově zaměřená aplikace, které jsou rozdělené do několika logických vrstev (nebo *vrstev*). Jinými slovy vícevrstvé datové aplikace je aplikace, která rozdělen do více projektů, s úroveň přístupu dat, vrstvu obchodní logiky a prezentační vrstvou každý svůj vlastní projektu. Další informace najdete v tématu [vícevrstvé datové aplikace přehled](../data-tools/n-tier-data-applications-overview.md).

Typové datové sady vylepšily tak, aby do diskrétní projektů možné vygenerovat třídy TableAdapters a datové sady. To umožňuje rychle samostatných aplikací vrstev a vytvářet vícevrstvé datové aplikace.

N-vrstvá podpora v typových datových sadách umožňuje iterativní vývoj architektury aplikace n vrstvá návrhu. Také odebere požadavek na ručně oddělení kód do více než jeden projekt. Spustí navrhování Datová vrstva pomocí **návrháře Dataset**. Pokud jste připraveni provést Architektura aplikace na návrh n vrstvé, nastavit **DataSet projekt** vlastnosti datové sady pro generování třídu datové sady do samostatného projektu.

## <a name="reference"></a>Odkaz

- <xref:System.Data.DataSet>
- <xref:System.Data.TypedTableBase%601>

## <a name="see-also"></a>Viz také

- [Přehled vícevrstvých datových aplikací](../data-tools/n-tier-data-applications-overview.md)
- [Návod: Vytvoření víceúrovňové datové aplikace](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [Přidávání kódu do objektů TableAdapter ve vícevrstvých aplikacích](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)
- [Přidávání kódu do datových sad ve vícevrstvých aplikacích](../data-tools/add-code-to-datasets-in-n-tier-applications.md)
- [Přidávání ověřování do vícevrstvé datové sady](../data-tools/add-validation-to-an-n-tier-dataset.md)
- [Rozdělování datových sad a objektů TableAdapter do různých projektů](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)
- [Hierarchická aktualizace](../data-tools/hierarchical-update.md)
- [Datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
- [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)
- [Vytvoření a konfigurace TableAdapters](../data-tools/create-and-configure-tableadapters.md)
- [N-vrstvé a vzdálené aplikace s LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)