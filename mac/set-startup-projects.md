---
title: Nastavení více projektů po spuštění v sadě Visual Studio pro Mac
description: Tento článek popisuje, jak nastavit více projektů, spusťte na spuštění nebo ladění.
author: sayedihashimi
ms.author: sayedha
ms.date: 02/21/2019
ms.topic: conceptual
ms.prod: visual-studio-mac-dev16
ms.assetid: fd354fff-ce6b-4505-a815-84a2311e39ba
ms.openlocfilehash: 84581fb3f6e33d22f0895b807998120ea7ca0cb7
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56724020"
---
# <a name="how-to-set-multiple-startup-projects"></a>Postupy: Nastavení více projektů po spuštění
Visual Studio for Mac můžete zadat více než jeden projekt je spuštěn při ladění nebo spuštění vašeho řešení.

## <a name="to-set-multiple-startup-projects"></a>Chcete-li nastavit více projektů po spuštění
1.  V **oblasti řešení**, vyberte řešení (na nejvyšší uzel).

2. Vyberte uzel řešení nabídka (kliknutí pravým tlačítkem myši) a pak zvolte **nastavit projekty po spuštění...** .

   ![Nastavení spuštění projektů kontextové nabídky](media/startup-proj-ctx-menu.png)

3. **Vytvoření konfigurace spuštění řešení** se zobrazí dialogové okno. Toto dialogové okno se vytvoří nový pojmenovaný spuštění konfigurace řešení pro vaše řešení. Můžete udělit jakýkoli název, který vám vyhovuje, je výchozí název `Multiple Projects`.

   ![Vytvořit dialogové okno Konfigurace spuštění řešení](media/create-sln-run-config.png)

4. Klikněte na tlačítko **vytvoření konfigurace spuštění**. **Možnosti řešení** otevře dialogové okno s nové řešení spustit vybranou konfiguraci.

   ![Dialogové okno možností řešení](media/sln-options-run-config-multi-projects.png)

5. Vyberte projekty, které chcete spustit při ladění nebo spuštění aplikace ze sady Visual Studio pro Mac.

   ![Dialogové okno možností řešení s nakonfigurovanou konfigurace spuštění](media/sln-options-run-config-multi-projects-configured.png)

6. Klikněte na **OK**. Dialogové okno se zavře a novou konfiguraci spuštění řešení je nastavená na aktivní konfigurace spuštění.

   ![Řešení s více projekty nakonfigurované za účelem spuštění na ladění nebo spuštění](media/startup-project-configured.png) uvidíte, že dva projekty jsou nakonfigurované na spustit, protože oba projekty jsou v **tučné** v **oblasti řešení**. Na panelu nástrojů novou konfiguraci spuštění je nakonfigurovaný jako aktuální konfigurace spuštění řešení.

## <a name="next-steps"></a>Další kroky

- [Kompilování a sestavování v sadě Visual Studio pro Mac](compiling-and-building.md)
- [Principy konfigurací sestavení](configurations.md)