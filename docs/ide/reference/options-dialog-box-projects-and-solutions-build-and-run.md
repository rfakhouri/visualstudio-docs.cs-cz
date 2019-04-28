---
title: Dialogové okno Možnosti, Projekty a řešení, Sestavit a spustit
ms.date: 07/14/2017
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3d0f24dc1afa875183f03e15e46cc2331f27cbf0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996835"
---
# <a name="options-dialog-box-projects-and-solutions--build-and-run"></a>Dialogové okno Možnosti: Projekty a řešení \> sestavit a spustit

V tomto dialogovém okně můžete zadat maximální počet C++ nebo C# projekty, které můžete vytvářet ve stejnou dobu, určité výchozí chování, ale taky popustit některé nastavení protokolu sestavení. Zpřístupníte tyto možnosti, vyberte **nástroje** > **možnosti** rozbalte **projekty a řešení**a pak vyberte **sestavíte a spustíte**.

**maximální počet paralelních projektu sestavení**

Určuje maximální počet C++ a C# projekty, které můžete vytvářet ve stejnou dobu. K optimalizaci procesu sestavení, je maximální číslo sestavení paralelního projektu automaticky nastaví počet procesorů počítače. Maximální počet je 32.

**Pouze při spuštění sestavit projekty a závislosti**

Při použití sestavení spouštěný projekt a jeho závislosti **F5** klíč, **ladění** > **spustit ladění** příkaz nabídky nebo použít příkazy v **sestavení** nabídky. Pokud není zaškrtnuto, jsou vytvořeny všechny projekty a závislosti.

**Spustit, pokud projekty jsou zastaralé**

*Platí pro projekty v jazyce C++.*

Při spuštění projektu s **F5** nebo **ladění** > **spustit ladění** příkazu, ve výchozím nastavení **zobrazit výzvu k vytvoření** Zobrazí zprávu, pokud konfigurace projektu je zastaralý. Vyberte **vždy sestavení** a sestavte projekt pokaždé, když je spuštěn. Vyberte **nikdy nesestavovat** potlačit všechny automatické sestavení při spuštění projektu.

**Při spuštění, při sestavení nebo dojde k chybě nasazení**

*Platí pro projekty v jazyce C++.*

Při spuštění projektu s **F5** nebo **ladění** > **spustit ladění** příkazu, ve výchozím nastavení **výzva ke spuštění**zobrazí zprávu, pokud projekt by měl spustit i v případě, že sestavení selhalo. Vyberte **spuštění starší verze** automaticky spustit poslední úspěšný build, což může způsobit neshody mezi spuštěním kódu a zdrojový kód. Vyberte **nespouštět** k potlačení zprávy.

**Nové řešení použít aktuálně zvolený projekt jako spouštěný projekt**

Když nastavíte tuto možnost, nová řešení použít aktuálně zvolený projekt jako spouštěný projekt.

**Podrobnost výstupu sestavení projektu nástroje MSBuild**

Určuje, kolik informací z procesu sestavení je zobrazen v **výstup** okna.

**Úroveň podrobností MSBuild projektu sestavení protokolu souborů**

*Platí pro projekty v jazyce C++.*

Určuje, kolik informací je zapsána do souboru protokolu sestavení, které se nacházejí v  *\\ \<ProjectName > \Debug\\\<ProjectName > .log*.

## <a name="see-also"></a>Viz také:

- [Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)
- [Dialogové okno Možnosti, projekty a řešení](projects-and-solutions-options-dialog-box.md)
- [Dialogové okno Možnosti, Projekty a řešení, Webové projekty](options-dialog-box-projects-and-solutions-web-projects.md)