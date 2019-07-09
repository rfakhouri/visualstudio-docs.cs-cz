---
title: Řešení potíží
description: Běžné problémy a řešení pro Visual Studio pro Mac.
ms.topic: troubleshooting
author: therealjohn
ms.author: johmil
ms.date: 06/18/2019
ms.assetid: CE860D79-E29E-4B93-B094-BE74B35FC1C2
ms.openlocfilehash: b0f10e1f70349126ab48c41efc40f982212836f1
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2019
ms.locfileid: "67691889"
---
# <a name="troubleshooting"></a>Poradce při potížích

## <a name="viewing-logs-in-visual-studio-for-mac"></a>Zobrazení protokolů v sadě Visual Studio pro Mac

Protokoly můžete najít tak, že přejdete na **Nápověda > otevřít adresář protokolu** položku nabídky, jak je znázorněno níže:

![Otevřete položku nabídky adresář protokolu](media/troubleshooting-image1.png)

## <a name="viewing-exceptions"></a>Zobrazení výjimky

Při zachycení výjimky, zobrazí se bublinu výjimky. Chcete-li zobrazit další podrobnosti, vyberte **zobrazit podrobnosti o** tlačítka:

![Zobrazit další podrobnosti o výjimce](media/troubleshooting-image2.png)

Zobrazí se **zobrazit podrobnosti** dialogového okna, poskytuje další informace týkající se výjimky:

![Dialogové okno pro zobrazení podrobností](media/troubleshooting-image3.png)

Důležité části dialogového okna, která jsou číslována výše jsou podrobně popsány v níže:

1. Typ výjimky, které zobrazuje úplný název typu výjimky, která je sledována.
2. Zpráva výjimky zobrazena hodnota vlastnost zprávy tohoto objektu výjimky.
3. Vnitřní typ výjimky, které zobrazuje úplný název typu výjimky pro aktuálně vybranou výjimku ve stromovém zobrazení vnitřní výjimka
4. Zpráva o vnitřní výjimce zobrazí hodnotu vlastnosti zprávy vybranou výjimku ve stromovém zobrazení vnitřní výjimka.
5. Zobrazení trasování zásobníku. To lze sbalit pomocí šipky zpřístupnění a obsahuje položky rámce zásobníku.
6. Příklad položky neuživatelský kód.
7. Příklad položky kódu uživatele.
8. Zobrazení vlastností, které zobrazuje všechny vlastnosti a pole výjimky. To lze sbalit pomocí šipky zpřístupnění.
9. Stromové zobrazení popisu vnitřní výjimky. V tomto zobrazení pomocí klávesnice šipky nahoru/dolů nebo pomocí myši nebo trackpadu vyberte vnitřní výjimky.
10. Ve výchozím nastavení, je nastavené na co **ladit jenom kód projektu** nastavena možnost v nastavení ladicího programu. Zaškrtnutím tohoto políčka vám umožní všechny neuživatelský kód sbalit do jednoho řádku v stacktrace.
11. Tlačítka kopírování zkopírujete `exception.ToString()` výstup do schránky.

Všimněte si, že některé z těchto oddílů se zobrazují pouze pokud výjimka obsahuje vnitřní výjimku.

## <a name="see-also"></a>Viz také:

- [Prostředky pro odstraňování chyb integrovaného vývojového prostředí (Visual Studio na Windows)](/visualstudio/ide/reference/resources-for-troubleshooting-integrated-development-environment-errors)