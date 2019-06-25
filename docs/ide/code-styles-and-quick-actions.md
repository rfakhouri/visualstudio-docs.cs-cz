---
title: Předvolby stylu kódu
ms.date: 03/12/2019
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: 689bdb62d5a4bc9aea21da67e8e5e844660756d6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62975302"
---
# <a name="code-style-preferences"></a>Předvolby stylu kódu

Pro projekty jazyka C# a Visual Basic lze nastavit předvolby stylu kódu tak, že otevřete **možnosti** dialogové **nástroje** nabídky. V **možnosti** dialogu **textový Editor** > [**C#** nebo **základní**] > **styl kódu**  >  **Obecné**.

Každá položka v seznamu zobrazí náhled předvoleb při výběru:

::: moniker range="vs-2017"

![Možnosti stylu kódu](media/code-style-quick-actions-dialog.png)

::: moniker-end

::: moniker range=">=vs-2019"

![Možnosti stylu kódu](media/vs-2019/code-style-quick-actions-dialog.png)

::: moniker-end

Možnostmi nastavenými v tomto okně se vztahují na váš účet přizpůsobení sady Visual Studio a nejsou spojeny s konkrétní projekt nebo základ kódu. Kromě toho nejsou vynucená v okamžiku sestavení, včetně v sestaveních nepřetržité integrace (CI). Pokud chcete přidružit předvolby stylu kódu vašeho projektu a styly vynucují v průběhu sestavení, zadejte předvolby v [souboru .editorconfig](#editorconfig-files).

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [chování editoru v sadě Visual Studio pro Mac](/visualstudio/mac/editor-behavior).

## <a name="editorconfig-files"></a>EditorConfig soubory

Nastavení stylu kódu pro .NET je taky možné specifikovat tak, že přidáte [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) soubor do projektu.

::: moniker range=">=vs-2019"

Klikněte na tlačítko **souboru .editorconfig Generovat z nastavení** kódování souboru .editorconfig styl budou automaticky generovány podle požadované možnosti, které jste nastavili v tomto **možnosti** stránky.

![Generovat editorconfig soubor z nastavení v VS 2019](media/vs-2019/generate-editorconfig-file-small.png)

::: moniker-end

EditorConfig soubory jsou spojeny se základ kódu, spíše než účtem přizpůsobení sady Visual Studio. Nastavení v souboru EditorConfig přednost možnosti vybrané v **možnosti** dialogové okno. Používejte soubor EditorConfig, pokud chcete vynutit kódování styly pro všechny uživatele k projektu nebo úložiště.

## <a name="preference-and-severity"></a>Priority a závažnosti

Pro každé nastavení stylu kódu na této stránce, můžete nastavit **předvoleb** a **závažnost** hodnoty pomocí rozevíracích na každém řádku. Je možné nastavit závažnost **žádný**, **návrh**, **upozornění**, nebo **chyba**. Pokud chcete povolit [rychlé akce](../ide/quick-actions.md) pro styl kódu, ujistěte se, že **závažnost** nastavená na něco jiného než **žádný**. **Rychlé akce** žárovky ![žárovky](media/light-bulb-dropdown.png), chyba žárovky ![chyba žárovky](media/error-bulb.png), nebo šroubovák ![šroubovák](media/screwdriver.png) ikona se zobrazuje, kdy jiný než upřednostňovaný styl se používá, a zvolíte možnost na **rychlé akce** seznamu automaticky přepište kód upřednostňované stylu.

## <a name="format-document-command"></a>Formátovat dokument

Můžete nakonfigurovat **formátovat dokument** příkazu (**upravit** > **Upřesnit** > **formátovat dokument**) do Vyčistěte další kód v souboru, například odebrat a seřadit direktivy using nebo použít předvolby stylu kódu. Můžete definovat nastavení, které chcete, aby **formátovat dokument** použít [stránka možností formátování](reference/options-text-editor-csharp-formatting.md#format-document-settings).

Kód čištění respektuje konfiguraci v nastavení *.editorconfig* souboru nebo ve kterém chybí dané pravidlo nebo soubor, nastavení **nástroje** > **možnosti**  >  **Textový Editor**  >  **C#** > [**styl kódu** nebo **formátování**].

Poprvé spustíte **formátovat dokument** příkaz v sadě Visual Studio, žlutý informační panel zobrazí výzvu, mohli konfigurovat svá nastavení vyčištění kódu.

> [!TIP]
> Se závažností z nakonfigurovaných pravidel **žádný** nehrají roli, v vyčištění kódu však lze použít jednotlivě prostřednictvím **rychlé akce a Refaktoringy** nabídky.

## <a name="see-also"></a>Viz také:

- [Rychlé akce](../ide/quick-actions.md)
- [EditorConfig nastavení konvence psaní kódu .NET](../ide/editorconfig-code-style-settings-reference.md)
- [Chování editoru (Visual Studio for Mac)](/visualstudio/mac/editor-behavior)