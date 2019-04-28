---
title: 'DA0030: Získat měření interakce vrstev pro databázové projekty | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0030
- vs.performance.rules.DA0030
- vs.performance.30
ms.assetid: 42b2f69d-0cfa-4854-82c4-589c3d8b4557
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 12a554eae05d02dda57fe29b2c627f261ba10b89
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62936011"
---
# <a name="da0030-gather-tier-interaction-measurements-for-database-projects"></a>DA0030: Získat měření interakce vrstvy pro databázové projekty

|||
|-|-|
|Id pravidla|DA0030|
|Kategorie|Použití nástroje pro profilaci|
|Metoda profilace|Vzorkování|
|Zpráva|Shromažďování měření interakce pro více vrstvé aplikace se vám pomůžou pochopit, způsobů využití databází a klíče dat přístup ke zpoždění. Zkuste profilaci aplikace znovu s povolenou možností profilace interakce vrstev.|
|Typ pravidla|Informace o|

## <a name="cause"></a>Příčina
 Volání <xref:System.Data> podstatnou část dat profilování jsou metody a nebyly shromážděných dat interakce vrstev při spuštění profilace. Zvažte profilaci znovu a přidání dat interakce vrstev.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno, vždycky, když je funkce, které se nacházejí v oborech názvů System.Data, včetně významnou aktivitu <xref:System.Data.Linq> <xref:System.Data.Linq>.

 Vícevrstvé aplikace pomocí vrstvy služeb pro své prezentaci a datové vrstvy. Často je datová vrstva samostatný proces běží systém správy databáze, jako je Microsoft SQL Server. Datová vrstva může být spuštěn i v samostatném počítači ze zbývajících částí aplikace. Vzorkování profily poskytují trochu přehled funkcí a služeb spuštěných na více instancí procesu nebo vzdáleně.

 Nástroje pro profilování může shromažďovat informace o časování pro více vrstvé aplikace, které interagují s datové vrstvě Microsoft SQL Server, pomocí asynchronního volání služeb ADO.NET. Musíte explicitně povolit profilaci interakce vrstev. Není zapnutá ve výchozím nastavení.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Toto pravidlo je pouze pro informaci a nemusí potřebovat nápravné opatření.

 Informace o způsobu přidání dat interakce vrstev data profilace v integrovaném vývojovém prostředí sady Visual Studio najdete v tématu [shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md). Informace o způsobu přidání dat interakce vrstev z příkazového řádku najdete v tématu [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md).