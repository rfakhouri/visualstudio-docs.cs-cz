---
title: "Řešení potíží s Azure vzdálené ladění pro jazyk Python v sadě Visual Studio | Microsoft Docs"
description: "Řešení potíží při ladění aplikace Python spuštěné v Azure App Service pomocí sady Visual Studio."
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 543358e02f37fffbcc2c3981808fded87a3cb12a
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
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
| `web.debug.config`Chcete-li zakázat ladění proxy byla změněna. | Odstraňte soubor a znovu publikovat do služby App Service, během které doby Visual Studio vytvoří soubor projektu. |

Viz také:

- [Vzdálené ladění pro jazyk Python Azure](debugging-remote-python-code-on-azure.md)
