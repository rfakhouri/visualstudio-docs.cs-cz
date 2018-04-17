---
title: Visual Studio kódu stylu předvoleb | Microsoft Docs
ms.custom: ''
ms.date: 03/10/2017
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: 4898a2e4a55f5c11179ae5a00e46c87a44519a7b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="code-style-preferences"></a>Kód stylu předvoleb

Kód stylu předvoleb lze nastavit pro projekty C# a Visual Basic otevřením **možnosti** dialogové okno z **nástroje** nabídky. Vyberte **textového editoru** > **C#** nebo **základní** > **kódu stylu**  >   **Obecné**. Možnosti nastavení v tomto okně platí pro místní počítač. Každá položka v seznamu se zobrazí náhled předvoleb při výběru, jak je uvedeno níže.

![Možnosti styl kódu](media/code-style-quick-actions-dialog.png)

Pro každou položku, můžete nastavit **předvoleb** a **závažnost** hodnoty pomocí rozevírací nabídky na každém řádku. Závažnost může být nastaven na **žádné**, **návrhu**, **upozornění**, nebo **chyba**. Pokud chcete povolit [rychlé akce](../ide/quick-actions.md) pro kód styl, zkontrolujte, zda **závažnost** nastavení nastavena na jinou hodnotu než **žádné**. Rychlé akce ikonou žárovky ![malé ikonou žárovky](media/vs2015_lightbulbsmall.png) se zobrazí, když je použit jiný než upřednostňovaný styl a zvolíte možnost v seznamu Rychlé akce automaticky přepisovat kód na styl upřednostňované.

Kód nastavení stylů pro rozhraní .NET můžete také spravovat pomocí [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) souboru. V takovém případě nastavení v souboru EditorConfig mají přednost před možnosti vybrané v **možnosti** dialogové okno. Soubor EditorConfig slouží k vynucení a nakonfigurovat stylu psaní kódu pro celý úložišti nebo projektu.

### <a name="see-also"></a>Viz také

[Rychlé akce](../ide/quick-actions.md)  
[Kódování nastavení konvence pro EditorConfig rozhraní .NET](../ide/editorconfig-code-style-settings-reference.md)