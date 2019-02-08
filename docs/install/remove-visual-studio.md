---
title: Odebrání sady Visual Studio
titleSuffix: ''
description: Zjistěte, jak úplně odebrat sady Visual Studio z vašeho počítače, krok za krokem.
ms.date: 09/12/2017
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- uninstall
- uninstall Visual Studio
- remove
- remove Visual Studio
- cleanup
- cleanup Visual Studio
- clean up
- clean up Visual Studio
ms.assetid: 9c81a777-9c95-4934-b517-c60c6dc78799
author: heaths
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f996e5b284393be91d4e83e3e403bdbb1073e6ac
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55909646"
---
# <a name="remove-visual-studio-2017"></a>Odebrat sady Visual Studio 2017

Pokud dojde k závažné chybě a nelze opravit nebo odinstalovat Visual Studio, můžete spustit `InstallCleanup.exe` nástroj pro odebrání instalační soubory a informace o produktu pro všechny nainstalované instance sady Visual Studio 2017 a novější. Spuštění tohoto nástroje je třeba udělat jako poslední možnost, pokud opravit nebo odinstalovat navrácení služeb po a odinstalovat funkce z jiné instalace sady Visual Studio nebo jiné produkty, které je potřeba opravit.

V níže uvedených pokynů můžete spustit nástroj pomocí přepínače příkazového řádku pomocí následujícího chování:

| Přepínač | Chování |
| ------ | -------- |
| `-i`   | Tento přepínač je výchozí, pokud je předán žádný jiný přepínač a odebere pouze hlavní instalační adresář a informace o produktu. Toto chování je vhodnější, pokud máte v úmyslu znovu nainstalovat stejnou verzi, po spuštění `InstallCleanup.exe` nástroj. |
| `-f`   | Zadání tohoto přepínače odebere hlavní instalační adresář, informace o produktech a většinu dalších funkcí, které jsou mimo instalační adresář, který může sdílet s další instalace sady Visual Studio nebo jiné produkty nainstalované. Toto chování je vhodnější, pokud máte v úmyslu odebrat sady Visual Studio bez přeinstalace později. |

1. Ukončete instalační program sady Visual Studio.
2. Otevřete příkazový řádek správce. Chcete-li otevřít příkazový řádek správce, postupujte podle těchto kroků:
   * Klikněte na tlačítko **Start** nabídky
   * Typ **cmd**.
   * Klikněte pravým tlačítkem na **příkazového řádku**a potom klikněte na tlačítko **spustit jako správce**.
3. Zadejte úplnou cestu `InstallCleanup.exe` nástroj a předat podle toho, která přepínač příkazového řádku vyžadujete. Ve výchozím nastavení je cesta nástroje:
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

Pokud nenajdete `InstallCleanup.exe` v adresáři instalačního programu sady Visual Studio – vždy umístěny v `%ProgramFiles(x86)%\Microsoft Visual Studio` – postupujte podle pokynů a [instalaci sady Visual Studio](install-visual-studio.md) a až se zobrazí na obrazovce pro výběr pracovního vytížení, zavřete okno a postupujte podle předchozích kroků znovu.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio 2017](install-visual-studio.md)
* [Update Visual Studio 2017](update-visual-studio.md)
* [Úpravy sady Visual Studio 2017](modify-visual-studio.md)
* [Odinstalace sady Visual Studio 2017](uninstall-visual-studio.md)
