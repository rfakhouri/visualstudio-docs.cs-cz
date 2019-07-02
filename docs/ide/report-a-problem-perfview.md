---
title: Shromažďovat ETL trasování pomocí nástroje PerfView
ms.date: 06/27/2019
ms.topic: conceptual
helpviewer_keywords:
- perfview
- ETL Trace
author: mikeblome
ms.author: mblome
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.description: Use perfview.exe to collect ETL traces for troubleshooting issues with Visual Studio
ms.openlocfilehash: baae89b7bf45a4848c571f75e37c6cc0d203d459
ms.sourcegitcommit: 6f7a740750b2cd17ea2275c3d046caebc9782917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67518235"
---
# <a name="collect-an-etl-trace-with-perfview"></a>Shromažďovat ETL trasování pomocí nástroje PerfView

PerfView je nástroj, který vytvoří soubory ETL (protokol trasování událostí) na základě [události trasování pro Windows](/windows/desktop/ETW/event-tracing-portal) , může být užitečné při řešení potíží některých typech vypnout problémy s aplikací Visual Studio. Čas od času při nahlásit problém, produktový tým vás může požádat o spuštění PerfView ke sběru dalších informací.

## <a name="install-perfview"></a>Instalace nástroje PerfView

Stáhněte si nástroje PerfView z [Microsoft Download Center](http://www.microsoft.com/download/details.aspx?id=28567).

## <a name="run-perfview"></a>Spuštění nástroje PerfView

1. Klikněte pravým tlačítkem na **PerfView.exe** v aplikaci Windows Explorer a zvolte **spustit jako správce** jako správce
1. V nabídce shromažďovat, zvolte **shromažďování**
1. Zkontrolujte **Zip**, **sloučit**, a **Čas vlákna**.
1. Zvýšit **cyklické MB** až 1000.
1. Změna **aktuální adresář** ukládání trasování ETL do zadané složky a datový soubor, pokud budete shromažďovat více než jednou.
1. Chcete-li spustit nahrávání dat, zvolte **spustit shromažďování** tlačítko.
1. Chcete-li zastavit nahrávání dat, zvolte **zastavit shromažďování** tlačítko. PrefView.etl.zip soubor se uloží v zadaném adresáři.

PerfView lze uložit pouze nejnovější data, která se vejde do vyrovnávací paměti. Proto se pokusí zastavit shromažďování co nejdříve po spuštění sady Visual Studio zablokovat nebo zpomalit. Bez shromažďování pro více než 30 sekund poté, co dostanete se k problému.

Další informace najdete v tématu [PerfView kurzu na webu Channel 9](http://channel9.msdn.com/Series/PerfView-Tutorial/PerfView-Tutorial-1-Collecting-data-with-the-Run-command).
