---
title: Aktualizátor obsahuje chyby načítání informací
description: Pokyny k vyřešení, když se zobrazí chyba 'Chyba při načítání informací o aktualizaci'. in Visual Studio 2019 for Mac
author: asb3993
ms.author: amburns
ms.date: 04/13/2019
ms.technology: vs-ide-install
ms.assetid: 31AF914A-C66B-4CD3-9429-39695E0E94AE
ms.openlocfilehash: 554633b2fc5d47d9cc4824ff9d8bf2febfbcd1f8
ms.sourcegitcommit: 16bcaca215de75479695738d3c2d703c78c3500e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2019
ms.locfileid: "67309626"
---
# <a name="troubleshooting-updater-has-errors-retrieving-information"></a>Řešení potíží: Aktualizátor obsahuje chyby načítání informací

Ve vzácných případech mohou oprávnění, může se zobrazit chybová zpráva "Chyba při načítání aktualizovat informace o" zobrazí při pokusu o [aktualizace sady Visual Studio pro Mac](update.md). Pokud k tomu dojde, zkuste ho opravit následující kroky:

- Zkontrolujte připojení k Internetu. E-maily v připojení je nejčastější příčinou této chyby.
    - Pokud komponenta nepodaří stáhnout, můžete kliknout na tlačítko Opakovat vedle názvu součásti znovu soubor ke stažení.
- Restartujte integrované vývojové prostředí.
- Pokud budete nadále zobrazí tato chybová zpráva, můžete také zkusit aktualizovat pomocí instalačního programu, pokud **.dmg** je stále v počítači, nebo můžete sadu stáhnout z [visualstudio.com](https://visualstudio.microsoft.com/vs/mac/)
    - Instalační program bude aktualizovat všechny nainstalované součásti na svém počítači.
    - Po opětovné spuštění instalačního programu, také budete moci nainstalovat všechny chybějící komponenty, které nebyly nainstalované dřív.
- Můžete taky zkusit vymazat své stažené soubory v mezipaměti tak, že odstraníte soubor umístěný ve `~/Library/Caches/VisualStudio/7.0/TempDownload/index.xml`.