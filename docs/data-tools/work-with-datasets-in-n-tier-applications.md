---
title: Práce s datovými sadami ve vícevrstvých aplikacích
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
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: c6da3f51a249aaf52cf3f20b90f3add6ceeb7aa1
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936548"
---
# <a name="work-with-datasets-in-n-tier-applications"></a>Práce s datovými sadami ve vícevrstvých aplikacích

*Vícevrstvé datové aplikace* datově orientovaných aplikací, které jsou rozdělené do několika logické vrstvy jsou (nebo *úrovně*). Jinými slovy vícevrstvé datové aplikace je aplikace, která je rozdělena do několika projektů s vrstvě přístupu k datům, vrstvu obchodní logiky a prezentační vrstvou každý ve svém vlastním projektu. Další informace najdete v tématu [přehled vícevrstvých datových aplikací](../data-tools/n-tier-data-applications-overview.md).

Typové datové sady vylepšené tak, aby do samostatných projektů se můžou generovat třídy TableAdapter a datové sady. To poskytuje schopnost rychle samostatné aplikace a generovat vícevrstvých datových aplikací.

N-vrstvá podpora v typových datových sadách umožňuje iterativního vývoje návrhu, n vrstvá architektura aplikací. Odebere také nutnost ručně rozdělení kódu do více než jeden projekt. Začíná návrh datové vrstvě pomocí **Návrhář Dataset**. Jakmile budete připraveni, abyste při návrhu n vrstvé architektury aplikace, nastavte **projektu DataSet** vlastnosti datové sady, chcete-li vytvořit třídu dataset do samostatného projektu.

## <a name="reference"></a>Odkaz

- <xref:System.Data.DataSet>
- <xref:System.Data.TypedTableBase%601>

## <a name="see-also"></a>Viz také:

- [Přehled vícevrstvých datových aplikací](../data-tools/n-tier-data-applications-overview.md)
- [Návod: Vytvoření vícevrstvé datové aplikace](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [Přidávání kódu do objektů TableAdapter ve vícevrstvých aplikacích](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)
- [Přidávání kódu do datových sad ve vícevrstvých aplikacích](../data-tools/add-code-to-datasets-in-n-tier-applications.md)
- [Přidávání ověřování do vícevrstvé datové sady](../data-tools/add-validation-to-an-n-tier-dataset.md)
- [Rozdělování datových sad a objektů TableAdapter do různých projektů](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)
- [Hierarchická aktualizace](../data-tools/hierarchical-update.md)
- [Nástroje datových sad v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
- [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)
- [Vytvoření a konfigurace objektů TableAdapter](../data-tools/create-and-configure-tableadapters.md)
- [N-vrstvé a vzdálené aplikace s LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)