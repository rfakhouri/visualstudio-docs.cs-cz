---
title: "Řešení potíží s | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: CE860D79-E29E-4B93-B094-BE74B35FC1C2
ms.openlocfilehash: 4e483548e916bf00b07c472b18adac8504b6e967
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshooting"></a>Poradce při potížích

## <a name="viewing-logs-in-visual-studio-for-mac"></a>Prohlížení protokolů v sadě Visual Studio pro Mac
 
Protokoly můžete najít procházením **pomoci > otevřete adresář protokolu** položky nabídky, jak je uvedeno dále:

![Otevřete položku nabídky adresář protokolu](media/troubleshooting-image1.png)

## <a name="viewing-exceptions"></a>Zobrazení výjimky

Když zachytil výjimku, objeví se bublin k výjimce. Chcete-li zobrazit další podrobnosti, vyberte **zobrazit podrobnosti** tlačítko:

![Zobrazit další podrobnosti o výjimce](media/troubleshooting-image2.png)

Bude se zobrazovat **zobrazit podrobnosti** dialogové okno, že poskytuje další informace týkající se výjimky:

![](media/troubleshooting-image3.png)

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