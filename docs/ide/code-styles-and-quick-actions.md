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
ms.openlocfilehash: a7a478e8d3575e70a11ec776d59337ae93e7a677
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57873357"
---
# <a name="code-style-preferences"></a>Předvolby stylu kódu

Pro projekty jazyka C# a Visual Basic lze nastavit předvolby stylu kódu tak, že otevřete **možnosti** dialogové **nástroje** nabídky. V **možnosti** dialogu **textový Editor** > [**C#** nebo **základní**] > **styl kódu**  >  **Obecné**. Každá položka v seznamu zobrazí náhled předvoleb při výběru:

![Možnosti stylu kódu](media/code-style-quick-actions-dialog.png)

Možnostmi nastavenými v tomto okně se vztahují na váš účet přizpůsobení sady Visual Studio a nejsou spojeny s konkrétní projekt nebo základ kódu. Kromě toho nejsou vynucená v okamžiku sestavení, včetně v sestaveních nepřetržité integrace (CI). Pokud chcete přidružit předvolby stylu kódu vašeho projektu a styly vynucují v průběhu sestavení, zadejte předvolby v [souboru .editorconfig](#editorconfig-files).

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [chování editoru v sadě Visual Studio pro Mac](/visualstudio/mac/editor-behavior).

## <a name="preference-and-severity"></a>Priority a závažnosti

Pro každou položku, můžete nastavit **předvoleb** a **závažnost** hodnoty pomocí rozevíracích na každém řádku. Je možné nastavit závažnost **žádný**, **návrh**, **upozornění**, nebo **chyba**. Pokud chcete povolit [rychlé akce](../ide/quick-actions.md) pro styl kódu, ujistěte se, že **závažnost** nastavená na něco jiného než **žádný**. **Rychlé akce** žárovky ![žárovky](media/light-bulb-dropdown.png), chyba žárovky ![chyba žárovky](media/error-bulb.png), nebo šroubovák ![šroubovák](media/screwdriver.png) ikona se zobrazuje, kdy jiný než upřednostňovaný styl se používá, a zvolíte možnost na **rychlé akce** seznamu automaticky přepište kód upřednostňované stylu.

## <a name="editorconfig-files"></a>EditorConfig soubory

Nastavení stylu kódu pro .NET je taky možné specifikovat tak, že přidáte [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) soubor do projektu. Tyto soubory jsou spojeny se základ kódu, spíše než účtem přizpůsobení sady Visual Studio. Nastavení v souboru EditorConfig přednost možnosti vybrané v **možnosti** dialogové okno. Používejte soubor EditorConfig, pokud chcete vynutit kódování styly pro všechny uživatele k projektu nebo úložiště.

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