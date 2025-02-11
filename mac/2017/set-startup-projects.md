---
title: Nastavení více projektů po spuštění
description: Tento článek popisuje, jak nastavit více projektů, které se spustí při spuštění nebo ladění.
author: sayedihashimi
ms.author: sayedha
ms.date: 02/21/2019
ms.topic: conceptual
ms.prod: visual-studio-mac
ms.assetid: fd354fff-ce6b-4505-a815-84a2311e39ba
ms.openlocfilehash: 55519960a6b84968ced43183833167a365e91b35
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68872315"
---
# <a name="set-multiple-startup-projects"></a>Nastavení více projektů po spuštění

Visual Studio pro Mac umožňuje určit, že při ladění nebo spuštění řešení by měl být spuštěn více než jeden projekt.

## <a name="to-set-multiple-startup-projects"></a>Nastavení více projektů po spuštění

1. V Oblast řešení vyberte řešení (nejvyšší uzel).

2. Klikněte pravým tlačítkem na uzel řešení a pak vyberte **nastavit projekty po spuštění**:

   ![Vyberte nastavit projekty po spuštění.](media/startup-proj-ctx-menu.png)

3. Otevře se dialogové okno **vytvořit konfiguraci spuštění řešení** . Toto dialogové okno umožňuje vytvořit novou konfiguraci spuštění pojmenovaného řešení pro vaše řešení. Můžete použít libovolný název, který chcete. Výchozí název je `Multiple Projects`.

   ![Dialogové okno vytvořit konfiguraci spuštění řešení](media/create-sln-run-config.png)

4. Vyberte **vytvořit konfiguraci spuštění**. Otevře se dialogové okno **Možnosti řešení** s vybranou možností nová konfigurace spuštění řešení:

   ![Dialogové okno Možnosti řešení](media/sln-options-run-config-multi-projects.png)

5. Vyberte projekty, které chcete spustit při ladění nebo spuštění vaší aplikace z Visual Studio pro Mac:

   ![Dialogové okno Možnosti řešení s vybranými projekty](media/sln-options-run-config-multi-projects-configured.png)

6. Vyberte **OK**. Nová konfigurace spuštění řešení je nastavená jako aktivní konfigurace spuštění:

   ![Řešení s více projekty nakonfigurovanými na spouštění při ladění nebo běhu](media/startup-project-configured.png)

   Můžete vidět, že dva projekty jsou nakonfigurovány pro spuštění, protože oba projekty jsou tučné v oblast řešení. Na panelu nástrojů je nová konfigurace spuštění nastavena jako aktuální konfigurace spuštění řešení.

## <a name="next-steps"></a>Další postup

- [Kompilace a sestavování v Visual Studio pro Mac](compiling-and-building.md)
- [Principy konfigurací sestavení](configurations.md)
