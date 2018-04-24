---
title: Řešení potíží s Azure vzdálené ladění pro jazyk Python
description: Řešení potíží při ladění aplikace Python spuštěné v Azure App Service pomocí sady Visual Studio.
ms.date: 07/12/2017
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 3d792a411867686abe0734fc67dfe654320d8b38
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="remote-debugging-troubleshooter-for-python-and-azure"></a>Vzdálené ladění Poradce při potížích pro Python a Azure

Nepodaří připojit k sadě Visual Studio [Azure App Service pro vzdálené ladění](debugging-remote-python-code-on-azure.md) pro některý z následujících důvodů:

| Důvod | Rozlišení |
| --- | --- |
| Nemají Visual Studio 2013 Update 4 nebo novější. | Nainstalujte vhodnou verzi z [visualstudio.com](https://www.visualstudio.com/downloads/). | 
| Projekt, který je nasazen do služby App Service se neshoduje se jeden otevřete v sadě Visual Studio. | Načtení správný projekt do sady Visual Studio. |
| Projekt nebyl nasazen s konfigurací ladění. | Znovu nasaďte aplikaci pravým tlačítkem na projekt v Průzkumníku řešení a výběrem **publikovat**. V **nastavení** , zkontrolujte, zda **ladění** je vybrané konfigurace. |
| App Service není spuštěna. | Spusťte z Průzkumníka serveru v sadě Visual Studio nebo z portálu Azure. |
| App Service není nakonfigurován pro webové sokety. | Přejděte na [portál Azure](https://portal.azure.com), přejděte do vaší aplikace služby, otevřete **Nastavení > Nastavení aplikace** okně zapnout **obecné nastavení > webové sokety** k **Na**a vyberte **Uložit**. (Všimněte si, že **ladění** možnosti uvedené v tomto okně provést *není* platí pro ladění Python.) |
| `web.debug.config` Chcete-li zakázat ladění proxy byla změněna. | Odstraňte soubor a znovu publikovat do služby App Service, během které doby Visual Studio vytvoří soubor projektu. |

Viz také:

- [Vzdálené ladění pro jazyk Python Azure](debugging-remote-python-code-on-azure.md)
