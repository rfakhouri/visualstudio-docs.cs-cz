---
title: Visual Studio pro řešení potíží s Mac
description: Běžné problémy a řešení pro sadu Visual Studio pro Mac uživatele.
ms.topic: troubleshooting
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: CE860D79-E29E-4B93-B094-BE74B35FC1C2
ms.openlocfilehash: 135a71f18451eb209f9f351ae9224c1606bc50d6
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="troubleshooting"></a>Poradce při potížích

## <a name="viewing-logs-in-visual-studio-for-mac"></a>Prohlížení protokolů v sadě Visual Studio pro Mac

Protokoly můžete najít procházením **pomoci > otevřete adresář protokolu** položky nabídky, jak je uvedeno dále:

![Otevřete položku nabídky adresář protokolu](media/troubleshooting-image1.png)

## <a name="viewing-exceptions"></a>Zobrazení výjimky

Když zachytil výjimku, objeví se bublin k výjimce. Chcete-li zobrazit další podrobnosti, vyberte **zobrazit podrobnosti** tlačítko:

![Zobrazit další podrobnosti o výjimce](media/troubleshooting-image2.png)

Bude se zobrazovat **zobrazit podrobnosti** dialogové okno, že poskytuje další informace týkající se výjimky:

![Zobrazit dialogové okno Podrobnosti](media/troubleshooting-image3.png)

Důležité části dialogového okna, které jsou číslované výše jsou podrobně popsány v níže:

1. Typ výjimky, které zobrazuje úplný název typu výjimka, který je používán.
2. Zpráva o výjimce, která zobrazuje hodnotu vlastnosti zprávy objekt výjimky.
3. Typ výjimky vnitřní, který se zobrazuje úplný název typ výjimky pro aktuálně vybrané výjimka ve stromovém zobrazení vnitřní výjimka.
4. Zpráva o vnitřní výjimce, zobrazuje hodnotu vlastnosti zprávy, vybrané výjimky v zobrazení stromu vnitřní výjimka.
5. Zobrazení, trasování zásobníku. To lze sbalit pomocí zpřístupnění šipku a obsahuje položky rámce zásobníku.
6. Příklad položky bez uživatelského kódu.
7. Příklad položky kódu uživatele.
8. Zobrazení vlastností, které jsou uvedeny všechny vlastnosti a pole výjimky. To lze sbalit pomocí zpřístupnění šipku.
9. Zobrazení stromu informacích o vnitřní výjimce. V tomto zobrazení z klávesnice šipek nahoru/dolů nebo pomocí myši nebo trackpadu vyberte vnitřní výjimky.
10. Ve výchozím nastavení, to je nastavena na co **ladění projektu kódu pouze** možnost v nastavení ladicího programu je nastavena na. Výběrem toto políčko povolí všechny bez uživatelského kódu na Sbalit na jeden řádek v stacktrace.
11. Tlačítko Kopírovat zkopírovat `exception.ToString()` výstup do schránky.

Všimněte si, že některé z těchto částí budou zobrazeny pouze při výjimce má vnitřní výjimku.