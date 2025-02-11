---
title: Možnosti stylu kódu a vyčištění kódu
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
ms.openlocfilehash: 4c7bb8f3e94a761023a19a5ea3361073b73d9f3b
ms.sourcegitcommit: 90c3187d804ad7544367829d07ed4b47d3f8a72d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2019
ms.locfileid: "68822428"
---
# <a name="code-style-preferences"></a>Předvolby stylu kódu

Můžete definovat nastavení stylu kódu pro jednotlivé projekty pomocí [souboru EditorConfig](#code-styles-in-editorconfig-files)nebo pro veškerý kód, který upravíte v aplikaci Visual Studio na [stránce **Možnosti** ](#code-styles-in-the-options-dialog-box)textového editoru. Pro C# kód můžete také nakonfigurovat aplikaci Visual Studio, aby používala Tyto předvolby stylu kódu pomocí příkazů pro **Vyčištění kódu** (Visual Studio 2019) a **formátovat dokument** (Visual Studio 2017).

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [chování editoru v sadě Visual Studio pro Mac](/visualstudio/mac/editor-behavior).

## <a name="code-styles-in-editorconfig-files"></a>Styly kódu v souborech EditorConfig

[Nastavení stylu kódu](../ide/editorconfig-code-style-settings-reference.md) pro rozhraní .NET lze určit přidáním souboru [EditorConfig](create-portable-custom-editor-options.md) do projektu. Soubory EditorConfig jsou přidruženy k základu kódu a nikoli k účtu přizpůsobení sady Visual Studio. Nastavení v souboru EditorConfig mají přednost před styly kódu, které jsou uvedeny v dialogovém okně **Možnosti** . Soubor EditorConfig použijte, pokud chcete vymáhat styly kódování pro všechny přispěvatele do vašeho úložiště nebo projektu.

::: moniker range=">=vs-2019"

Můžete ručně naplnit soubor EditorConfig nebo můžete soubor automaticky vygenerovat na základě nastavení stylu kódu, které jste zvolili v dialogovém okně **Možnosti** sady Visual Studio. Tato > stránka možností je k dispozici v **nabídce nástroje** > –**textový editor** > [**C#** nebo **Basic**] > **styl** > kódu**Obecné**. Klikněte na **Generovat soubor. editorconfig z nastavení** a automaticky vygenerujte soubor *. editorconfig* stylu kódování na základě nastavení na této stránce **Možnosti** .

![Generování souboru editorconfig z nastavení v aplikaci Visual Studio 2019](media/vs-2019/generate-editorconfig-file-small.png)

::: moniker-end

## <a name="code-styles-in-the-options-dialog-box"></a>Styly kódu v dialogovém okně Možnosti

Předvolby stylu kódu lze nastavit pro všechny vaše C# projekty a Visual Basic otevřením dialogového okna **Možnosti** v nabídce **nástroje** . V **možnosti** dialogu **textový Editor** > [**C#** nebo **základní**] > **styl kódu**  >  **Obecné**.

Každá položka v seznamu zobrazí náhled předvoleb při výběru:

::: moniker range="vs-2017"

![Možnosti stylu kódu](media/code-style-quick-actions-dialog.png)

::: moniker-end

::: moniker range=">=vs-2019"

![Možnosti stylu kódu](media/vs-2019/code-style-quick-actions-dialog.png)

::: moniker-end

Možnosti nastavené v tomto okně se vztahují na váš účet přizpůsobení sady Visual Studio a nejsou přidružené ke konkrétnímu projektu nebo základu kódu. Kromě toho nejsou vynutily při sestavování, včetně v sestaveních průběžné integrace (CI). Chcete-li přidružit předvolby stylu kódu k vašemu projektu a nechat styly vynutily během sestavování, určete předvolby v [souboru. editorconfig](#code-styles-in-editorconfig-files) , který je přidružen k projektu.

### <a name="preference-and-severity"></a>Priority a závažnosti

U každého nastavení stylu kódu na této stránce můžete nastavit hodnoty **předvoleb** a **závažnosti** pomocí rozevíracích seznamu na každém řádku. Závažnost se dá nastavit **jenom**na refaktoring, **Návrh**, **varování**nebo **chybu**. Pokud chcete povolit [rychlé akce](../ide/quick-actions.md) pro styl kódu, zajistěte, aby bylo **Vážnost** nastavení závažnosti nastaveno na jinou hodnotu než **refaktoring**. V případě, že se používá nepreferovaný styl, se v případě použití nepreferovaného stylu zobrazí ikona pro **rychlé akce** ![žárovky](media/light-bulb-dropdown.png), chyba žárovky ![chyba žárovky](media/error-bulb.png) nebo ![Screwdriver](media/screwdriver.png). a můžete zvolit možnost v seznamu **rychlé akce** pro automatické přepsání kódu na preferovaný styl.

## <a name="apply-code-styles"></a>Použít styly kódu

::: moniker range="vs-2017"

Můžete nakonfigurovat příkaz **formátovat dokument** (**Upravit** > **Rozšířený** > **Formát dokumentu**), chcete-li použít nastavení stylu kódu (ze souboru EditorConfig nebo možnosti **stylu kódu** ) spolu s běžné formátování, které dělá (například odsazení). Pokud soubor *. editorconfig* pro projekt existuje, mají tato nastavení přednost.

> [!NOTE]
> Použití stylů kódu pomocí příkazu **formátovat dokument** je k dispozici pouze pro C# soubory kódu. Toto je experimentální funkce.

Nakonfigurujte nastavení, které má **formátovat dokument** použít na [stránce možnosti formátování](reference/options-text-editor-csharp-formatting.md#format-document-settings).

![Nastavení stylu kódu pro formát dokumentu v aplikaci Visual Studio 2017](media/format-document-settings-experiment.png)

> [!TIP]
> Pravidla konfigurovaná se závažností **none** se nepodílejí na čištění kódu, ale lze je individuálně použít prostřednictvím nabídky **rychlé akce a** refaktoringu.

Při prvním spuštění příkazu **Formát dokumentu** vás žlutý informační panel vyzve ke konfiguraci nastavení pro vyčištění kódu.

::: moniker-end

::: moniker range=">=vs-2019"

V C# případě souborů kódu má Visual Studio 2019 tlačítko pro **Vyčištění kódu** v dolní části editoru (klávesnice: **CTRL** **k,** CTRLE+), chcete-li použít styly kódu ze souboru EditorConfig nebo ze stránky možností **stylu kódu.** + Pokud soubor *. editorconfig* existuje pro projekt, jsou to nastavení, která mají přednost.

![Spustit čištění kódu v aplikaci Visual Studio 2019](media/execute-code-cleanup.png)

> [!TIP]
> Pravidla konfigurovaná se závažností **none** se nepodílejí na čištění kódu, ale lze je individuálně použít prostřednictvím nabídky **rychlé akce a** refaktoringu.

Nejprve nakonfigurujte styly kódu, které chcete použít (v jednom ze dvou profilů) v dialogovém okně **Konfigurovat vyčištění kódu** . Chcete-li otevřít toto dialogové okno, klikněte na šipku vedle ikony vyčištění kódu Broom a pak zvolte možnost **Konfigurovat vyčištění kódu**.

![Konfigurace vyčištění kódu v aplikaci Visual Studio 2019](media/configure-code-cleanup.png)

Po nakonfigurování vyčištění kódu můžete buď kliknout na ikonu Broom, nebo stisknout **kombinaci kláves CTRL**+**k**, **CTRL**+**E** a spustit program Vyčištění kódu. Můžete také spustit vyčištění kódu v celém projektu nebo řešení. Klikněte pravým tlačítkem myši na název projektu nebo řešení v **Průzkumník řešení**, vyberte **Analýza a vyčištění kódu**a pak vyberte **Spustit vyčištění kódu**.

![Spustit čištění kódu v celém projektu nebo řešení](media/run-code-cleanup-project-solution.png)

Pokud chcete, aby nastavení stylu kódu bylo použito při každém uložení souboru, může se stát, že v rozšíření [pro uložení bude provedeno vyčištění kódu](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.CodeCleanupOnSave) .

::: moniker-end

## <a name="see-also"></a>Viz také:

- [Rychlé akce](../ide/quick-actions.md)
- [EditorConfig nastavení konvence psaní kódu .NET](../ide/editorconfig-code-style-settings-reference.md)
- [Chování editoru (Visual Studio for Mac)](/visualstudio/mac/editor-behavior)
