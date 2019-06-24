---
title: Možnosti stylu kódu a kód čištění
ms.date: 04/25/2019
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: c31a04d5471224ed8433bba70baa5bd1dae9125e
ms.sourcegitcommit: 7eb2fb21805d92f085126f3a820ac274f2216b4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2019
ms.locfileid: "67328766"
---
# <a name="code-style-preferences"></a>Předvolby stylu kódu

Kód stylu nastavení jednotlivých projektů můžete definovat pomocí [souborů EditorConfig](#code-styles-in-editorconfig-files), nebo pro celý kód upravíte v sadě Visual Studio v textovém editoru [ **možnosti** stránky](#code-styles-in-the-options-dialog-box). Pro C# kódu, můžete taky nakonfigurovat sady Visual Studio, chcete-li použít tyto předvolby stylu kódu pomocí **vyčištění kódu** (Visual Studio 2019) a **formátovat dokument** příkazy (Visual Studio 2017).

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [chování editoru v sadě Visual Studio pro Mac](/visualstudio/mac/editor-behavior).

## <a name="code-styles-in-editorconfig-files"></a>Styly kódu v souborech EditorConfig

[Nastavení stylu kódu](../ide/editorconfig-code-style-settings-reference.md) pro .NET se dá nastavit tak, že přidáte [EditorConfig](create-portable-custom-editor-options.md) soubor do projektu. EditorConfig soubory jsou spojeny se základ kódu, spíše než účtem přizpůsobení sady Visual Studio. Nastavení v souboru EditorConfig přednost styly kódu, které jsou určené v **možnosti** dialogové okno. Používejte soubor EditorConfig, pokud chcete vynutit kódování styly pro všechny uživatele k projektu nebo úložiště.

::: moniker range=">=vs-2019"

EditorConfig souboru můžete naplnit ručně nebo můžete automaticky vygenerovat soubor podle nastavení stylu kódu, kterou jste zvolili v sadě Visual Studio **možnosti** dialogové okno. Tato stránka možností je k dispozici na **nástroje** > **možnosti** > **textový Editor** > [**C#** nebo  **Základní**] > **styl kódu** > **Obecné**. Klikněte na tlačítko **souboru .editorconfig Generovat z nastavení** styl psaní kódu budou automaticky generovány *.editorconfig* souboru na základě nastavení na tomto **možnosti** stránky.

![Generovat editorconfig soubor z nastavení v aplikaci Visual Studio 2019](media/vs-2019/generate-editorconfig-file-small.png)

::: moniker-end

## <a name="code-styles-in-the-options-dialog-box"></a>Styly kódu v dialogovém okně Možnosti

Předvolby stylu kódu můžete nastavit pro všechny vaše C# a projekty Visual Basic tak, že otevřete **možnosti** dialogové **nástroje** nabídky. V **možnosti** dialogu **textový Editor** > [**C#** nebo **základní**] > **styl kódu**  >  **Obecné**.

Každá položka v seznamu zobrazí náhled předvoleb při výběru:

::: moniker range="vs-2017"

![Možnosti stylu kódu](media/code-style-quick-actions-dialog.png)

::: moniker-end

::: moniker range=">=vs-2019"

![Možnosti stylu kódu](media/vs-2019/code-style-quick-actions-dialog.png)

::: moniker-end

Možnostmi nastavenými v tomto okně se vztahují na váš účet přizpůsobení sady Visual Studio a nejsou spojeny s konkrétní projekt nebo základ kódu. Kromě toho nejsou vynucená v okamžiku sestavení, včetně v sestaveních nepřetržité integrace (CI). Pokud chcete přidružit předvolby stylu kódu vašeho projektu a styly vynucují v průběhu sestavení, zadejte předvolby v [souboru .editorconfig](#code-styles-in-editorconfig-files) , který je asociován s projektem.

### <a name="preference-and-severity"></a>Priority a závažnosti

Pro každé nastavení stylu kódu na této stránce, můžete nastavit **předvoleb** a **závažnost** hodnoty pomocí rozevíracích na každém řádku. Je možné nastavit závažnost **žádný**, **návrh**, **upozornění**, nebo **chyba**. Pokud chcete povolit [rychlé akce](../ide/quick-actions.md) pro styl kódu, ujistěte se, že **závažnost** nastavená na něco jiného než **žádný**. **Rychlé akce** žárovky ![žárovky](media/light-bulb-dropdown.png), chyba žárovky ![chyba žárovky](media/error-bulb.png), nebo šroubovák ![šroubovák](media/screwdriver.png) ikona se zobrazuje, kdy jiný než upřednostňovaný styl se používá, a zvolíte možnost na **rychlé akce** seznamu automaticky přepište kód upřednostňované stylu.

## <a name="apply-code-styles"></a>Použití stylů kódu

::: moniker range="vs-2017"

Můžete nakonfigurovat **formátovat dokument** příkazu (**upravit** > **Upřesnit** > **formátovat dokument**) do nastavení stylu kódu použijte (ze souboru EditorConfig nebo **styl kódu** možnosti) spolu s regulární formátování, který provádí (např. odsazení). Pokud *.editorconfig* existuje soubor projektu, tato nastavení mají přednost.

> [!NOTE]
> Aplikování stylů kódu s použitím **formátovat dokument** příkaz je dostupná jenom pro C# soubory kódu. Toto je experimentální funkce.

Nakonfigurujte nastavení, které chcete, aby **formátovat dokument** použít [stránka možností formátování](reference/options-text-editor-csharp-formatting.md#format-document-settings).

![Nastavení stylu kódu pro formát dokumentu v sadě Visual Studio 2017](media/format-document-settings-experiment.png)

> [!TIP]
> Se závažností z nakonfigurovaných pravidel **žádný** nehrají roli, v vyčištění kódu však lze použít jednotlivě prostřednictvím **rychlé akce a Refaktoringy** nabídky.

Poprvé spustíte **formátovat dokument** příkazu žlutý informační panel zobrazí výzvu, mohli konfigurovat svá nastavení vyčištění kódu.

::: moniker-end

::: moniker range=">=vs-2019"

Pro C# má soubory kódu, Visual Studio 2019 **vyčištění kódu** tlačítko v dolní části editoru (klávesnice: **CTRL**+**K**, **Ctrl**+**E**) Chcete-li použít styly kódu ze souboru EditorConfig nebo z **styl kódu**  stránka možností. Pokud *.editorconfig* existuje soubor projektu, jsou nastavení, která mají přednost.

![Spuštění kódu čištění v aplikaci Visual Studio 2019](media/execute-code-cleanup.png)

> [!TIP]
> Se závažností z nakonfigurovaných pravidel **žádný** nehrají roli, v vyčištění kódu však lze použít jednotlivě prostřednictvím **rychlé akce a Refaktoringy** nabídky.

Nejprve nakonfigurujte styly kódu, které chcete použít (v jednom ze dvou profilů) v **konfigurace vyčištění kódu** dialogové okno. Chcete-li otevřít toto dialogové okno, klikněte na rozbalovací šipku vedle ikony zarovnání vyčištění kódu a klikněte na tlačítko **konfigurace vyčištění kódu**.

![Konfigurace vyčištění kódu ve Visual Studio 2019](media/configure-code-cleanup.png)

Po dokončení konfigurace vyčištění kódu, můžete kliknutím na ikonu zarovnání nebo stisknutím klávesy **Ctrl**+**K**, **Ctrl**+**E** ke spuštění kódu čištění. Můžete také spustit čištění kódu napříč celý projekt nebo řešení. Klikněte pravým tlačítkem na název projektu nebo řešení v **Průzkumníka řešení**vyberte **analyzovat a vyčištění kódu**a pak vyberte **spuštění kódu čištění**.

![Spuštění kódu čištění přes celý projekt nebo řešení](media/run-code-cleanup-project-solution.png)

Pokud chcete, aby vaše nastavení stylu kódu použít pokaždé, když uložíte soubor, může jako [vyčištění kódu při uložení](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.CodeCleanupOnSave) rozšíření.

::: moniker-end

## <a name="see-also"></a>Viz také:

- [Rychlé akce](../ide/quick-actions.md)
- [EditorConfig nastavení konvence psaní kódu .NET](../ide/editorconfig-code-style-settings-reference.md)
- [Chování editoru (Visual Studio for Mac)](/visualstudio/mac/editor-behavior)