---
title: Řešení potíží s Azure vzdálené ladění pro Python
description: Řešení potíží při pokusu o ladění aplikace v Pythonu ve službě Azure App Service pomocí sady Visual Studio.
ms.date: 06/26/2018
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
ms.openlocfilehash: f545fa223aa929b79016352e799d112bceddaf1c
ms.sourcegitcommit: 4f82c178b1ac585dcf13b515cc2a9cb547d5f949
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341460"
---
# <a name="remote-debugging-troubleshooter-for-python-and-azure"></a>Vzdálené ladění Poradce při potížích pro Python a Azure

Visual Studio se nepodaří připojit k [služby Azure App Service pro vzdálené ladění](debugging-remote-python-code-on-azure.md) pro některý z následujících důvodů:

| Důvod | Rozlišení |
| --- | --- |
| Nemáte Visual Studio 2013 Update 4 nebo novější. | Nainstalovat vhodnou verzi z [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017). |
| Projekt, který se nasadí do služby App Service se neshoduje jeden otevřít v sadě Visual Studio. | Načtěte správný projekt do sady Visual Studio. |
| Projekt nebyl nasazen s **ladění** konfigurace. | Znovu nasadit aplikaci kliknutím pravým tlačítkem myši na projekt v **Průzkumníka řešení** a vyberete **publikovat**. V **nastavení** kartu, ujistěte se, že **ladění** se zvolenou konfiguraci. |
| App Service není spuštěna. | Spusťte ji z **Průzkumníka serveru** v sadě Visual Studio nebo na webu Azure Portal. |
| App Service není nakonfigurován pro webové sokety. | Přejděte [webu Azure portal](https://portal.azure.com), přejděte do služby App Service, otevřete **nastavení** > **nastavení aplikace**, zapnout **obecné nastavení**  >  **Webové sokety** k **na**a vyberte **Uložit**. (Všimněte si, že **ladění** možnosti zobrazené v tomto okně dělat *není* platí pro ladění Pythonu.) |
| *Web.Debug.config* byla změněna zakázat ladění proxy. | Stejný soubor odstranit také a znovu publikovat projekt do služby App Service, během kterých sady Visual Studio obnoví soubor. |

Viz také:

- [Azure vzdálené ladění pro Python](debugging-remote-python-code-on-azure.md)
