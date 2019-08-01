---
title: 'Postupy: Sestavení více konfigurací současně'
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
ms.assetid: ba830937-3317-4674-8cc2-c0cd565603c5
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7f4abd95c2a37366b4f6dfabe141e6418d23301d
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416757"
---
# <a name="how-to-build-multiple-configurations-simultaneously"></a>Postupy: Sestavení více konfigurací současně

Většinu typů projektů s více nebo dokonce i všemi konfiguracemi sestavení můžete sestavit současně pomocí dialogového okna **dávkové sestavení** . Nemůžete však sestavit následující typy projektů ve více konfiguracích sestavení současně:

1. [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]aplikace sestavené pro Windows pomocí JavaScriptu

2. Všechny projekty Visual Basic.

   Další informace o konfiguracích sestavení naleznete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).

## <a name="to-build-a-project-in-multiple-build-configurations"></a>Sestavení projektu v rámci více konfigurací sestavení

1. Na řádku nabídek klikněte na položku **sestavit** > **dávkovou**sestavování.

2. Ve sloupci **sestavení** zaškrtněte políčka pro konfigurace, ve kterých chcete sestavit projekt.

    > [!TIP]
    > Chcete-li upravit nebo vytvořit konfiguraci sestavení pro řešení, vyberte možnost **sestavit** > **Configuration Manager** na řádku nabídek, čímž otevřete dialogové okno **Configuration Manager** . Po úpravě konfigurace sestavení pro řešení klikněte na tlačítko **znovu sestavit** v dialogovém okně **dávkové sestavení** , aby se aktualizovaly všechny konfigurace sestavení pro projekty v řešení.

3. Kliknutím na tlačítko **sestavení** nebo znovu **sestavit** Sestavte projekt s konfiguracemi, které jste určili.

## <a name="see-also"></a>Viz také:

- [Postupy: Vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)
- [Principy konfigurací sestavení](../ide/understanding-build-configurations.md)
- [Paralelní sestavení více projektů](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)