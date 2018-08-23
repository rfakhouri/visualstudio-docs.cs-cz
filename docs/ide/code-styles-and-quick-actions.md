---
title: Předvolby stylu kódu Visual Studio
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
ms.openlocfilehash: c008462ded2b84b5978b65fc41344477c36bee76
ms.sourcegitcommit: 4c60bcfa2281bcc1a28def6a8e02433d2c905be6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/14/2018
ms.locfileid: "42623907"
---
# <a name="code-style-preferences"></a>Předvolby stylu kódu

Pro projekty jazyka C# a Visual Basic lze nastavit předvolby stylu kódu tak, že otevřete **možnosti** dialogové **nástroje** nabídky. V **možnosti** dialogu **textový Editor** > [**jazyka C#** nebo **základní**] > **styl kódu**  >  **Obecné**. Možnostmi nastavenými v tomto okně platí pouze v místním počítači.

Každá položka v seznamu zobrazí náhled předvoleb při výběru:

![Možnosti stylu kódu](media/code-style-quick-actions-dialog.png)

## <a name="preference-and-severity"></a>Priority a závažnosti

Pro každou položku, můžete nastavit **předvoleb** a **závažnost** hodnoty pomocí rozevíracích na každém řádku. Je možné nastavit závažnost **žádný**, **návrh**, **upozornění**, nebo **chyba**. Pokud chcete povolit [rychlé akce](../ide/quick-actions.md) pro styl kódu, ujistěte se, že **závažnost** nastavená na něco jiného než **žádný**. **Rychlé akce** ikonou žárovky ![ikonou žárovky malé](media/vs2015_lightbulbsmall.png) se zobrazí, když se používá jiný než upřednostňovaný styl a zvolíte možnost na **rychlé akce** do seznamu automaticky revize kódu upřednostňované stylu.

## <a name="editorconfig-files"></a>EditorConfig soubory

Nastavení stylu kódu pro .NET je také možné spravovat pomocí [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) souboru. Nastavení v souboru EditorConfig přednost možnosti vybrané v **možnosti** dialogové okno. Soubor s příponou EditorConfig slouží k vynucení a konfigurujte typ kódování pro celé úložiště nebo projektu.

## <a name="format-document-command"></a>Formátovat dokument

V sadě Visual Studio 2017 verze 15,8 a vyšší můžete nakonfigurovat **formátovat dokument** příkazu (**upravit** > **Upřesnit**  >  **Formátovat dokument**) v souboru provést čištění dalšího kódu, například odebrat a seřadit direktivy using nebo použít předvolby stylu kódu. Můžete definovat nastavení, které chcete, aby **formátovat dokument** použít [stránka možností formátování](reference/options-text-editor-csharp-formatting.md#format-document-settings).

Kód čištění respektuje konfiguraci v nastavení *.editorconfig* souboru nebo ve kterém chybí dané pravidlo nebo soubor, nastavení **nástroje** > **možnosti**  >  **Textový Editor** > **jazyka C#** > [**styl kódu** nebo **formátování**].

Poprvé spustíte **formátovat dokument** příkaz v sadě Visual Studio 2017, žlutý informační panel zobrazí výzvu, mohli konfigurovat svá nastavení vyčištění kódu.

> [!TIP]
> Pravidla, které jsou nakonfigurované jako **žádný** v *.editorconfig* soubor není součástí vyčištění kódu však lze použít jednotlivě prostřednictvím **rychlé akce a Refaktoringy** nabídky.

## <a name="see-also"></a>Viz také:

- [Rychlé akce](../ide/quick-actions.md)
- [EditorConfig nastavení konvence psaní kódu .NET](../ide/editorconfig-code-style-settings-reference.md)