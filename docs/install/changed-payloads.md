---
title: Když se změní datové části balíčku po vydání verze
description: Při vytváření rozložení, zjistěte, jak určit, pokud datové části balíčku změnit poté, co již byla odeslaná vydanou verzi.
ms.date: 05/22/2019
ms.topic: conceptual
author: et13
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 6a4eb286344b6dce7a4814089db013965eb34c98
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66411159"
---
# <a name="package-payload-changes"></a>Změny datové části balíčku

Některé datové části balíčku mohou změnit poté, co již byla odeslaná vydanou verzi. Pokud vy nebo někdo vytvoří rozložení, toto chování může způsobit obsah jiné rozložení, v závislosti na tom, kdy byla vytvořena rozložení.

## <a name="verify-that-a-layout-includes-package-payload-changes"></a>Ověřte, že rozložení obsahuje změny datové části balíčku

Tady je postup, chcete-li zjistit, pokud rozložení, který byl dříve vytvořen získal balíček datových částí, které byly změněny po vydání verze:

1. Otevřete v protokolu instalace. Protokol je obvykle v `%TEMP%\dd_setup_[date].log` kde `[date]` při spuštění operace rozložení `yyyyMMddHHmmss` formátu.

2. Vyhledejte řádek v protokolu, který strukturovaná podobně jako následující text:

    `Falling back to signature and signer check because hash verification returned HashMismatch for path: [path]`

3. Pak vyhledejte řádky dále v protokolu, které označují, že bylo pro [cesta] úspěšné stahování. Může vypadat podobně jako následující text:

    `Download of [url] succeeded using engine 'WebClient'`

    `END: Downloading [url] to [path]`

## <a name="see-also"></a>Viz také:

* [Vytvoření síťové instalace sady Visual Studio](create-a-network-installation-of-visual-studio.md)
* [Aktualizace na základě síťové instalace sady Visual Studio](update-a-network-installation-of-visual-studio.md)