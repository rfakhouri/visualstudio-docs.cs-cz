---
title: Najít a nahradit text
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.find
- vs.findreplacecontrol
- vs.findreplace.findsymbol
- vs.findreplace.symbol
- findresultswindow
- vs.findreplace.quickreplace
- vs.findsymbol
- vs.findinfiles
- vs.findresults1
- vs,findsymbolwindow
- vs.findreplace.quickfind
- vs.lookin
- vs.replace
helpviewer_keywords:
- text searches
- Replace in Files dialog box
- Find in Files dialog box
- text searches, finding and replacing text
- text, finding and replacing
- find and replace
- find text
- replace text
ms.assetid: a62545c3-1570-4d12-99fb-a82607eb35a1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7051b90dde45965b76e8a9e08b33b5326ff2848c
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
---
# <a name="find-and-replace-text"></a>Najít a nahradit text

Můžete najít a nahradit text v editoru Visual Studio pomocí [najít a nahradit](#find-and-replace-control) nebo [vyhledání a nahrazení v souborech](#find-in-files-and-replace-in-files).

> [!TIP]
> Pokud jste přejmenování kód symboly, například proměnné a metody, je lepší *[refactor](../ide/reference/rename.md)* je než chcete použijte hledání a nahrazování. Refaktoring je inteligentní a porozuměl jim oboru, zatímco hledání a nahrazování slepě nahradí všechny instance.

Vyhledání a nahrazení funkce je k dispozici v editoru, v některých jiných založený na textu windows, jako **Najít výsledky** windows návrháře windows například návrháře XAML a Návrhář formulářů Windows a nástroj windows.

Můžete určit obor vyhledávání aktuálním dokumentu, aktuální řešení nebo vlastní sadu složek. Můžete také zadat sadu přípon názvů souborů pro hledání několika souborů. Přizpůsobit syntaxe vyhledávání pomocí .NET [regulární výrazy](../ide/using-regular-expressions-in-visual-studio.md).

> [!TIP]
> [Najít/příkaz](../ide/find-command-box.md) pole je k dispozici jako ovládacím prvku panel nástrojů, ale nejsou viditelná ve výchozím nastavení. Chcete-li zobrazit **najít/příkaz** vyberte **přidat nebo odebrat tlačítka** na **standardní** nástrojů a pak vyberte **najít**.

## <a name="find-and-replace-control"></a>Najít a nahradit ovládací prvek

**Najít a nahradit** ovládací prvek se zobrazí v pravém horním rohu okna editoru kódu. **Najít a nahradit** řízení okamžitě označuje všechny výskyty řetězce zadaný hledaný řetězec v aktuálním dokumentu. Můžete přejít z výskytů do jiného tak, že zvolíte **najít další** tlačítko nebo **najít předchozí** tlačítko u ovládacího prvku vyhledávání.

![Najít a nahradit ovládací prvek](media/find-and-replace-box.png)

Možnosti můžete nahrazení kliknutím na tlačítko Další na **najít** textové pole. Chcete-li jeden nahrazení najednou, vyberte **nahradit další** vedle položky **nahradit** textové pole. Pokud chcete nahradit všechny shody, vyberte **nahradit všechny** tlačítko.

Chcete-li změnit barvu zvýraznění pro shody, vyberte **nástroje** nabídce vyberte možnost **možnosti**a potom zvolte **prostředí**a vyberte **písma a barev** . V **zobrazit nastavení pro** seznamu, vyberte **textového editoru**a potom v **zobrazení položek** seznamu, vyberte **najít zvýrazněte (rozšíření)**.

### <a name="search-tool-windows"></a>Okna nástrojů vyhledávání

Můžete použít **najít** řízení v kódu nebo text systému windows, jako například **výstup** windows a **Najít výsledky** windows tak, že vyberete **upravit**  >  **Najít a nahradit** nebo stiskněte **Ctrl + F**.

Verzi **najít** ovládací prvek je k dispozici také v některé nástroje systému windows. Například můžete filtrovat seznam ovládacích prvků v **sada nástrojů** okna tak, že zadáte text do vyhledávacího pole. Zahrnout další okna nástrojů, které vám umožní vyhledat jejich obsah **Průzkumníku řešení**, **vlastnosti** okně a **Team Explorer**.

## <a name="find-in-files-and-replace-in-files"></a>Najít v souborech a nahradit v souborech

**Vyhledání a nahrazení v souborech** funguje, jako **najít a nahradit** řídit, s tím rozdílem, že můžete definovat obor pro hledání. Nejen můžete hledat aktuální soubor otevřete v editoru, ale také všechny otevřít dokumenty, celé řešení, aktuální projekt a vybrané složky sad. Můžete také prohledat podle přípony názvu souboru. Pro přístup k **vyhledání a nahrazení v souborech** dialogové okno, vyberte **najít a nahradit** na **upravit** nabídky nebo klikněte na tlačítko **Ctrl + Shift + F**.

![Najít v souborech – dialogové okno](media/find-in-files-box.png)

### <a name="find-results"></a>Výsledky hledání

Pokud vyberete **najít všechny**, **Najít výsledky** se otevře okno a uvádí pro hledání shody. Výběr výsledek v seznamu zobrazí přidružený soubor a klade důraz na shodu. Pokud soubor již není otevřený pro úpravy, je otevřen v karta náhled na pravé straně karty dobře. Můžete použít **najít** řízení k hledání v **Najít výsledky** seznamu.

### <a name="create-custom-search-folder-sets"></a>Vytvoří vlastní vyhledávání složky sady

Obor vyhledávání můžete definovat výběrem **zvolte složky výsledků hledání** tlačítko (to vypadá **...** ) vedle položky **Hledat v** pole. V **zvolte složky výsledků hledání** dialogové okno, můžete určit sadu složek hledání a specifikace můžete uložit tak, aby jej můžete znovu použít později.

> [!TIP]
> Pokud jste změnili jednotce vzdáleného počítače do místního počítače, můžete zadat složky, které se mají hledat ve vzdáleném počítači.

### <a name="create-custom-component-sets"></a>Vytvoří vlastní součást sady

Součást sady můžete definovat jako obor hledání tak, že zvolíte **upravit sadu součást vlastní** vedle položky **Hledat v** pole. Můžete zadat nainstalované rozhraní .NET nebo COM součásti, projektů sady Visual Studio, které jsou součástí vašeho řešení, nebo všechny sestavení nebo typ knihovny (*.dll*, *.tlb*, *.olb*, *.exe*, nebo *.ocx*). Chcete-li vyhledávat odkazy, vyberte **vypadat v odkazech na** pole.

## <a name="see-also"></a>Viz také

- [Použití regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md)
- [Refaktorovat kódu v sadě Visual Studio](../ide/refactoring-in-visual-studio.md)