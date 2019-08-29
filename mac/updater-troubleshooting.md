---
title: Aktualizační program obsahuje chyby při načítání informací
description: Pokyny, jak opravit, když se zobrazí chyba "Chyba při načítání informací o aktualizaci". in Visual Studio 2019 for Mac
ms.topic: troubleshooting
author: asb3993
ms.author: amburns
ms.date: 04/13/2019
ms.technology: vs-ide-install
ms.assetid: 31AF914A-C66B-4CD3-9429-39695E0E94AE
ms.openlocfilehash: 5ba295defe19c6f3c6c56d5bccc7cc3fa367bb50
ms.sourcegitcommit: cf8c0fef2b9690595e99ce3802586cdd55fd37c2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107795"
---
# <a name="troubleshooting-updater-has-errors-retrieving-information"></a>Řešení potíží: Aktualizační program obsahuje chyby při načítání informací

V některých případech se může zobrazit chybová zpráva "Chyba při načítání informací o aktualizaci", která se zobrazí při pokusu o [aktualizaci Visual Studio pro Mac](update.md). Pokud k tomu dojde, vyzkoušejte následující kroky a opravte je:

- Ověřte připojení k Internetu. V rámci připojení je nejčastější příčinou této chyby.
  - Pokud se součást nepovede stáhnout, můžete zkusit stáhnout znovu kliknutím na tlačítko Opakovat vedle názvu součásti.
- Restartujte integrované vývojové prostředí (IDE).
- Pokud se tato chybová zpráva zobrazuje i nadále, můžete se také pokusit aktualizovat pomocí instalačního programu, pokud je soubor **. dmg** stále na vašem počítači, nebo si ho můžete stáhnout z [VisualStudio.com](https://visualstudio.microsoft.com/vs/mac/) .
  - Instalační program aktualizuje všechny nainstalované komponenty na vašem počítači.
  - Po opětovném spuštění instalačního programu budete moct nainstalovat i všechny chybějící součásti, které jste předtím nenainstalovali.
- Můžete také zkusit vymazat soubory stažené z mezipaměti tím, že odstraníte soubor umístěný v `~/Library/Caches/VisualStudio/7.0/TempDownload/index.xml`.
