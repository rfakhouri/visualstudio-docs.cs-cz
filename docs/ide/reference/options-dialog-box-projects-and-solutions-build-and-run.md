---
title: Dialogové okno Možnosti, Projekty a řešení, Sestavit a spustit
ms.date: 07/14/2017
ms.technology: vs-ide-compile
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 24ba5bbf34ecc12c2508c538e74909ee0a10aef4
ms.sourcegitcommit: 85d66dc9fea3fa49018263064876b15aeb6f9584
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "68461397"
---
# <a name="options-dialog-box-projects-and-solutions--build-and-run"></a>Dialogové okno Možnosti: Sestavení a spuštění \> projektů a řešení

V tomto dialogovém okně můžete zadat maximální počet C++ nebo C# projekty, které mohou být sestaveny současně, určité výchozí chování sestavení a některá nastavení protokolu sestavení. Chcete-li získat přístup k těmto možnostem, vyberte možnost **nástroje** > **Možnosti** rozbalit **projekty a řešení**a pak vyberte **sestavení a spustit**.

**Maximální počet paralelně sestavovaných projektů**

Určuje maximální počet C++ a C# projekty, které lze současně sestavit. Pro optimalizaci procesu sestavení je maximální počet paralelních sestavení projektu automaticky nastaven na počet procesorů počítače. Maximální hodnota je 32.

**Při běhu sestavovat pouze spouštěné projekty a závislosti**

Vytvoří pouze spouštěný projekt a jeho závislosti, pokud  > použijete klávesu **F5** , příkaz nabídky**Spustit ladění** a příslušné příkazy v nabídce **sestavení** . Pokud není zaškrtnuto, jsou sestaveny všechny projekty a závislosti.

**Spustit, pokud jsou projekty zastaralé**

*Platí jenom C++ pro projekty.*

Při spuštění projektu pomocí klávesy **F5** nebo příkazu**Spustit ladění** pro **ladění** > se ve výchozím nastavení zobrazí zpráva s **výzvou k sestavení** zobrazí zprávu, pokud je konfigurace projektu neaktuální. Vyberte **vždy sestavit** a sestavte projekt pokaždé, když je spuštěn. Vyberte **nikdy Nesestavit** , pokud chcete potlačit všechna Automatická sestavení při spuštění projektu.

**Při spuštění, když dojde k chybám sestavení nebo nasazení**

*Platí jenom C++ pro projekty.*

Při spuštění projektu pomocí klávesy **F5** nebo příkazu**Spustit ladění** **pro** **ladění** > se ve výchozím nastavení zobrazí zpráva, pokud se má projekt spustit i v případě, že se sestavení nezdařilo. Vyberte možnost **Spustit starou verzi** , chcete-li automaticky spustit poslední funkční sestavení, což může vést k neshodě mezi běžícím kódem a zdrojovým kódem. Vyberte **nespouštět** , pokud chcete zprávu potlačit.

**Pro nová řešení použijte aktuálně vybraný projekt jako spouštěný projekt.**

Pokud je tato možnost nastavena, nová řešení použijí aktuálně vybraný projekt jako spouštěný projekt.

**Podrobnosti výstupu sestavení projektu nástroje MSBuild**

Určuje, kolik informací z procesu sestavení se zobrazí v okně **výstup** .

**Podrobnosti souboru protokolu sestavení projektu nástroje MSBuild**

*Platí jenom C++ pro projekty.*

Určuje, kolik informací je zapsáno do souboru protokolu sestavení, který je umístěn  *\\ \<v ProjectName >\\\debug.\<ProjectName >. log*.

## <a name="see-also"></a>Viz také:

- [Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)
- [Dialogové okno Možnosti, projekty a řešení](projects-and-solutions-options-dialog-box.md)
- [Dialogové okno Možnosti, Projekty a řešení, Webové projekty](options-dialog-box-projects-and-solutions-web-projects.md)