---
title: Předvolby stylu kódu
ms.date: 03/10/2017
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: a9571456a5c9b277b69e6045e1277f78d586f3e0
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55923367"
---
# <a name="code-style-preferences"></a>Předvolby stylu kódu

Pro projekty jazyka C# a Visual Basic lze nastavit předvolby stylu kódu tak, že otevřete **možnosti** dialogové **nástroje** nabídky. V **možnosti** dialogu **textový Editor** > [**C#** nebo **základní**] > **styl kódu**  >  **Obecné**. Možnostmi nastavenými v tomto okně platí pouze v místním počítači.

Každá položka v seznamu zobrazí náhled předvoleb při výběru:

![Možnosti stylu kódu](media/code-style-quick-actions-dialog.png)

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [chování editoru v sadě Visual Studio pro Mac](/visualstudio/mac/editor-behavior).

## <a name="preference-and-severity"></a>Priority a závažnosti

Pro každou položku, můžete nastavit **předvoleb** a **závažnost** hodnoty pomocí rozevíracích na každém řádku. Je možné nastavit závažnost **žádný**, **návrh**, **upozornění**, nebo **chyba**. Pokud chcete povolit [rychlé akce](../ide/quick-actions.md) pro styl kódu, ujistěte se, že **závažnost** nastavená na něco jiného než **žádný**. **Rychlé akce** žárovky ![žárovky](media/vs2015_lightbulbsmall.png), chyba žárovky ![chyba žárovky](media/error-bulb.png), nebo šroubovák ![šroubovák](media/screwdriver.png) ikona se zobrazuje, kdy jiný než upřednostňovaný styl se používá, a zvolíte možnost na **rychlé akce** seznamu automaticky přepište kód upřednostňované stylu.

## <a name="editorconfig-files"></a>EditorConfig soubory

Nastavení stylu kódu pro .NET je také možné spravovat pomocí [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) souboru. Nastavení v souboru EditorConfig přednost možnosti vybrané v **možnosti** dialogové okno. Soubor s příponou EditorConfig slouží k vynucení a konfigurujte typ kódování pro celé úložiště nebo projektu.

## <a name="format-document-command"></a>Formátovat dokument

V sadě Visual Studio 2017 verze 15,8 a vyšší můžete nakonfigurovat **formátovat dokument** příkazu (**upravit** > **Upřesnit**  >  **Formátovat dokument**) v souboru provést čištění dalšího kódu, například odebrat a seřadit direktivy using nebo použít předvolby stylu kódu. Můžete definovat nastavení, které chcete, aby **formátovat dokument** použít [stránka možností formátování](reference/options-text-editor-csharp-formatting.md#format-document-settings).

Kód čištění respektuje konfiguraci v nastavení *.editorconfig* souboru nebo ve kterém chybí dané pravidlo nebo soubor, nastavení **nástroje** > **možnosti**  >  **Textový Editor**  >  **C#** > [**styl kódu** nebo **formátování**].

Poprvé spustíte **formátovat dokument** příkaz v sadě Visual Studio 2017, žlutý informační panel zobrazí výzvu, mohli konfigurovat svá nastavení vyčištění kódu.

> [!TIP]
> Pravidla, které jsou nakonfigurované jako **žádný** v *.editorconfig* soubor není součástí vyčištění kódu však lze použít jednotlivě prostřednictvím **rychlé akce a Refaktoringy** nabídky.

## <a name="see-also"></a>Viz také:

- [Rychlé akce](../ide/quick-actions.md)
- [EditorConfig nastavení konvence psaní kódu .NET](../ide/editorconfig-code-style-settings-reference.md)
- [Chování editoru (Visual Studio for Mac)](/visualstudio/mac/editor-behavior)