---
title: Nastavení více projektů po spuštění v sadě Visual Studio pro Mac
description: Tento článek popisuje, jak nastavit více projektů, spusťte na spuštění nebo ladění.
author: sayedihashimi
ms.author: sayedha
ms.date: 02/21/2019
ms.topic: conceptual
ms.prod: visual-studio-mac
ms.assetid: fd354fff-ce6b-4505-a815-84a2311e39ba
ms.openlocfilehash: cd76eaf30dd0151216a503bbaf1d76414ed56eef
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043503"
---
# <a name="set-multiple-startup-projects"></a>Nastavení více projektů po spuštění

Visual Studio for Mac umožňuje určit, že více než jeden projekt by měl být spuštěn při ladění nebo spuštění vašeho řešení.

## <a name="to-set-multiple-startup-projects"></a>Chcete-li nastavit více projektů po spuštění

1. V oblasti řešení vyberte řešení (na nejvyšší uzel).

2. Klikněte pravým tlačítkem na uzel řešení a pak vyberte **nastavit projekty po spuštění**:

   ![Vybraná sada spouštěných projektů](media/startup-proj-ctx-menu.png)

3. **Vytvoření konfigurace spuštění řešení** zobrazí se dialogové okno. Toto dialogové okno umožňuje vytvořit nový s názvem spustit konfigurace řešení pro vaše řešení. Můžete použít libovolný název, který vám vyhovuje. Výchozí název je `Multiple Projects`.

   ![Vytvoření dialogového okna konfigurace spuštění řešení](media/create-sln-run-config.png)

4. Vyberte **vytvoření konfigurace spuštění**. **Možnosti řešení** dialogové okno s nové řešení spustit vybranou konfiguraci:

   ![Dialogové okno Možnosti řešení](media/sln-options-run-config-multi-projects.png)

5. Vyberte projekty, které chcete spustit při ladění nebo spuštění aplikace ze sady Visual Studio pro Mac:

   ![Dialogové okno možností řešení s vybraných projektů](media/sln-options-run-config-multi-projects-configured.png)

6. Vyberte **OK**. Nová konfigurace spuštění řešení je nastaven jako aktivní konfigurace spuštění:

   ![Řešení s více projekty nakonfigurované za účelem spuštění na ladění nebo spuštění](media/startup-project-configured.png)

   Uvidíte, že dva projekty jsou nakonfigurované na spustit, protože jsou oba projekty **tučné** v oblasti řešení. Na panelu nástrojů novou konfiguraci spuštění nastavit jako aktuální konfigurace spuštění řešení.

## <a name="next-steps"></a>Další kroky

- [Kompilování a sestavování v sadě Visual Studio pro Mac](compiling-and-building.md)
- [Principy konfigurací sestavení](configurations.md)
