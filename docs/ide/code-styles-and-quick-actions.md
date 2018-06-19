---
title: Visual Studio kódu stylu předvoleb
ms.date: 03/10/2017
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 6dd046fa8a01cde7abdc33484da3ff8227eda966
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
ms.locfileid: "34063681"
---
# <a name="code-style-preferences"></a>Kód stylu předvoleb

Kód stylu předvoleb lze nastavit pro projekty C# a Visual Basic otevřením **možnosti** dialogové okno z **nástroje** nabídky. Vyberte **textového editoru** > **C#** nebo **základní** > **kódu stylu**  >   **Obecné**. Možnosti nastavení v tomto okně platí pro místní počítač.

Každá položka v seznamu se zobrazí ukázka předvoleb při výběru:

![Možnosti styl kódu](media/code-style-quick-actions-dialog.png)

## <a name="preference-and-severity"></a>Předvoleb a závažnost

Pro každou položku, můžete nastavit **předvoleb** a **závažnost** hodnoty pomocí rozevírací seznamy na každém řádku. Závažnost může být nastaven na **žádné**, **návrhu**, **upozornění**, nebo **chyba**. Pokud chcete povolit [rychlé akce](../ide/quick-actions.md) pro kód styl, zkontrolujte, zda **závažnost** nastavení nastavena na jinou hodnotu než **žádné**. Rychlé akce ikonou žárovky ![malé ikonou žárovky](media/vs2015_lightbulbsmall.png) apspear, když je použit jiný než upřednostňovaný styl a zvolíte možnost v seznamu Rychlé akce automaticky přepisovat kód na styl upřednostňované.

## <a name="editorconfig-files"></a>EditorConfig soubory

Kód nastavení stylů pro rozhraní .NET můžete také spravovat pomocí [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) souboru. Nastavení v souboru EditorConfig mají přednost před možnosti vybrané v **možnosti** dialogové okno. Soubor EditorConfig slouží k vynucení a nakonfigurovat stylu psaní kódu pro celý úložišti nebo projektu.

## <a name="see-also"></a>Viz také

- [Rychlé akce](../ide/quick-actions.md)
- [Kódování nastavení konvence pro EditorConfig rozhraní .NET](../ide/editorconfig-code-style-settings-reference.md)