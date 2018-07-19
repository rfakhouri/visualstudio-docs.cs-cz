---
title: Psaní kódu jazyka JavaScript v sadě Visual Studio bez řešení nebo projektu
description: Visual Studio poskytuje podporu pro vytvoření kódu bez závislosti na soubor projektu nebo soubor řešení
ms.custom: ''
ms.date: 06/06/2018
ms.technology: vs-nodejs
ms.topic: conceptual
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 7d56030b78abe57c80d816881991b9819ed6456b
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924949"
---
# <a name="develop-javascript-and-typescript-code-in-visual-studio-without-solutions-or-projects"></a>Vývoj kódu jazyka JavaScript a TypeScript v sadě Visual Studio bez řešení nebo projektů

Visual Studio 2017 zavádí se možnost [vývoj kódu bez projektů nebo řešení](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md), což vám umožní otevřít složku kódu a okamžitě začít pracovat s podporou bohaté editoru, například IntelliSense, vyhledávání, refaktoring, ladění a další.
Kromě těchto funkcí Node.js Tools for Visual Studio přidává podporu pro vytváření souborů TypeScript, Správa balíčků npm a spouštění skriptů npm.

Abyste mohli začít, vyberte **otevřít složku** z úvodní stránky, která se zobrazí při spuštění sady Visual Studio, nebo můžete vybrat **souboru** > **otevřete**  >  **Složky** z panelu nástrojů. Průzkumník řešení zobrazí všechny soubory ve složce, a můžete otevřít libovolný soubory, které chcete zahájit úpravy. Na pozadí aplikace Visual Studio indexuje soubory, které chcete povolit npm, sestavení a ladění funkcí.

> [!IMPORTANT]
> Mnoho funkcí popsaných v tomto článku, včetně integrace npm vyžaduje Visual Studio 2017 verze 15.8 3 ve verzi Preview.

## <a name="npm-integration"></a>integrace npm

Pokud obsahuje otevřené složce *package.json* souborů, které můžete kliknout pravým tlačítkem *package.json* k zobrazení místní nabídky (nabídku) specifické pro npm. 

![npm nabídky v Průzkumníku řešení](../javascript/media/solution-explorer-npm-ctx.png) 

V místní nabídce můžete spravovat balíčky nainstalované nástroj npm ve stejném způsobem, jakým [spravovat balíčky npm](npm-package-management.md) při použití souboru projektu.

Kromě toho v nabídce také umožňuje spouštět skripty, které jsou definovány v `scripts` element v *package.json*. Tyto skripty budou používat verzi Node.js k dispozici na `PATH` proměnné prostředí. Spusťte skripty v novém okně. To je skvělý způsob, jak provést sestavení nebo spouštění skriptů.

## <a name="build-and-debug"></a>Sestavení a ladění

### <a name="packagejson"></a>Soubor Package.JSON
Pokud *package.json* ve složce určuje `main` elementu, **ladění** příkaz bude k dispozici v místní nabídce klepněte pravým tlačítkem myši pro *package.json*. Kliknutím na ni se spustí *node.exe* se zadaným skriptem jako svůj argument.

### <a name="javascript-files"></a>Soubory jazyka JavaScript
Můžete ladit soubory JavaScriptu tak, že kliknete pravým tlačítkem soubor a vyberete **ladění** z místní nabídky. Tím se spustí *node.exe* se tento soubor JavaScript jako svůj argument.

### <a name="typescript-files-and-tsconfigjson"></a>Soubory TypeScript a tsconfig.json
Pokud není žádný *tsconfig.json* k dispozici ve složce, které pravým tlačítkem na soubor TypeScript zobrazíte příkazy místní nabídky pro vytvoření a odladění tento soubor. Při použití těchto příkazů můžete sestavovat nebo ladit pomocí *tsc.exe* s výchozími možnostmi. (Budete muset sestavit soubor předtím, než můžete ladit.)

> [!NOTE]
> Při sestavování kódu TypeScript, můžeme použít nejnovější verzi nainstalovanou ve `C:\Program Files (x86)\Microsoft SDKs\TypeScript`.

Pokud je *tsconfig.json* souboru ve složce, klikněte pravým tlačítkem můžete na soubor TypeScript zobrazíte příkaz nabídky, chcete-li ladit tento soubor TypeScript. Možnost se zobrazí pouze v případě, že neexistuje žádná `outFile` zadané v poli *tsconfig.json*. Pokud `outFile` je zadán tento soubor můžete ladit kliknutím pravým tlačítkem myši *tsconfig.json* a výběr správné možnosti. `tsconfig.json` Souboru nabízí také možnost sestavení, aby bylo možné určit možnosti kompilátoru.

> [!NOTE]
> Můžete získat další informace o *tsconfig.json* v [stránce TypeScript příručka tsconfig.json](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).
