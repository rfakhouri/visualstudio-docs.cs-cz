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
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 143a98cb6a7c805932548e61e3c1cdcdfa422a93
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941851"
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