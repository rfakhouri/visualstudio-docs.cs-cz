---
title: 'Postupy: otevření více řešení'
description: Zjistěte, jak otevřít více než jednoho řešení v sadě Visual Studio pro Mac a otevřít více než jednu instanci aplikace.
author: conceptdev
ms.author: crdun
ms.date: 07/19/2018
ms.assetid: 592BA4E3-8DEF-4FCD-8BA0-519A4CEEE03E
ms.openlocfilehash: a8001e9511f0c8864792dba783368d03ee6eef81
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624168"
---
# <a name="opening-multiple-solutions-or-instances-of-visual-studio-for-mac"></a>Otevření více řešení nebo instance sady Visual Studio pro Mac

Ve výchozím nastavení, všechny aplikace na počítači Mac, včetně sady Visual Studio pro Mac, jsou _jednou instancí_ aplikace. To znamená, že pokud aplikace, kterou chcete použít už otevřené (návodu "tečku" v části ikonu v doku), znovu kliknutím na ikonu se otevře spuštěnou instanci, nikoli nové.  Pokud budete potřebovat další instance aplikace, může vyzvat systém a otevřete ho za vás, jak je popsáno v [další části](#open-a-second-instance-of-visual-studio-for-mac).

Kromě toho když otevřete řešení, výchozí chování je otevřete řešení v nový pracovní prostor a zavřít aktuální pracovní prostor (v případě potřeby). Toto výchozí chování můžete přepsat udržováním aktuální pracovní prostor otevřít, jak je popsáno v [otevřete druhou řešení](#open-a-second-solution-inside-a-single-instance) oddílu.

## <a name="open-a-second-instance-of-visual-studio-for-mac"></a>Spusťte druhou instanci aplikace Visual Studio pro Mac

Chcete-li otevřít druhou instanci integrovaného vývojového prostředí, otevřete **terminálu** aplikace a zadejte následující řádek:

```bash
open -n "/Applications/Visual Studio.app"
```

## <a name="open-a-second-solution-inside-a-single-instance"></a>Otevřete druhou řešení v jediné instance

Chcete-li otevřít druhé řešení spolu s svoje první řešení, postupujte následovně:

1. S svoje první řešení otevřen, vyberte **soubor > Otevřít**.
2. Procházejte a najít stávající řešení v systému souborů.
3. Vyberte **.sln** souboru a stiskněte klávesu **možnosti** tlačítka:
    
    ![umístění možnosti tlačítka](media/open-multiple-solutions-image3.png)
4. Zrušte výběr **zavřít aktuální pracovní prostor** pole:

    ![snímek obrazovky s aktuální pracovní prostor](media/open-multiple-solutions-image1.png)

1. Stisknutím tlačítka Otevřít otevřete druhou řešení v oblasti řešení.

**Můžete také**, pokud jste nedávno otevřeli řešení, můžete použít následující kroky:

1. Přejděte na soubor > položka nabídky poslední řešení:

    ![snímek obrazovky nabídky poslední řešení](media/open-multiple-solutions-image2.png)

1. Podržte stisknutou klávesu **Ctrl** klíče a vyberte řešení. Tato kombinace otevře druhý řešení v oblasti řešení.
