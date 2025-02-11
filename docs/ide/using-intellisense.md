---
title: Informace o parametrech, seznam členů a rychlé informace
ms.date: 05/25/2018
ms.topic: conceptual
f1_keywords:
- vc.tools.intellisense
helpviewer_keywords:
- Quick info
- Parameter info
- Complete word
- List members
- IntelliSense [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 32e62131b2a66052ad4712b434c7b6f2b89065d0
ms.sourcegitcommit: 9fc8b144d4ed1c46aba87c0b7e1d24454e0eea9d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2019
ms.locfileid: "68493290"
---
# <a name="intellisense-in-visual-studio"></a>IntelliSense v aplikaci Visual Studio

IntelliSense je podpora dokončování kódu, která zahrnuje několik funkcí: Seznam členů, informace o parametrech, rychlé informace a dokončování slov. Tyto funkce vám pomůžou získat další informace o kódu, který používáte, sledovat parametry, které píšete, a přidávat volání vlastností a metod s pouze několika klávesami.

Mnoho aspektů technologie IntelliSense je specifických pro jazyk. Další informace o technologii IntelliSense pro různé jazyky naleznete v tématech uvedených v části [Viz také](#see-also) .

## <a name="list-members"></a>Vypsat členy

Po zadání spouštěcího znaku (například tečka (`.`) ve spravovaném kódu nebo `::` v C++) se zobrazí seznam platných členů z typu (nebo oboru názvů). Pokud budete pokračovat v zadávání znaků, seznam bude filtrován tak, aby zahrnoval pouze členy, které začínají těmito znaky, nebo kde začátek *libovolného* slova v rámci názvu začíná znaky. Technologie IntelliSense také provádí párování "ve stylu CamelCase Case", takže můžete pouze zadat první písmeno každého slova ve stylu CamelCase-použita v názvu člena, aby se zobrazily shody.

Po výběru položky ji můžete vložit do kódu stisknutím klávesy **TAB** nebo zadáním mezery. Pokud vyberte položku a zadáte období, položka se zobrazí s uvedenou dobou, která vyvolá jiný seznam členů. Pokud vyberete položku, ale ještě před jejím vložením, zobrazí se rychlé informace pro položku.

V seznamu členů ikona vlevo představuje typ členu, například obor názvů, třídu, funkci nebo proměnnou. Seznam ikon naleznete v tématu [zobrazení tříd a prohlížeč objektů ikony](../ide/class-view-and-object-browser-icons.md). Seznam může být poměrně dlouhý, takže stisknutím **Page Up** a **Page Down** se můžete v seznamu pohybovat nahoru nebo dolů.

![Seznam členů sady Visual Studio](../ide/media/vs2015_intellisense.png)

Funkci vypsat **členy** můžete vyvolat ručně zadáním **kombinace kláves CTRL**+**J**, výběrem možnosti **Upravit** > **členy seznamu** **IntelliSense** > nebo výběrem **členů seznamu.** tlačítko na panelu nástrojů editoru. Při vyvolání na prázdném řádku nebo mimo podporovaný rozsah zobrazí seznam symboly v globálním oboru názvů.

Chcete-li vypnout členy seznamu ve výchozím nastavení (takže se nezobrazí, pokud není výslovně vyvoláno), vyberte možnost **nástroje** > **Možnosti** > **všechny jazyky** a zrušte zaškrtnutí políčka **Členové automatických seznamů**. Pokud chcete vypnout seznam členů jenom pro určitý jazyk, přečtěte si **Obecné** nastavení daného jazyka.

Můžete také změnit nastavení na režim návrhu, ve kterém je do kódu vložen pouze text, který zadáte. Například pokud zadáte identifikátor, který není v seznamu a stiskněte klávesu **TAB**, v režimu dokončování by položka nahradila typový identifikátor. Chcete-li přepnout mezi režimem dokončení a režimem návrhu, stiskněte klávesu **CTRL**+**ALT +** +**MEZERNÍK**nebo zvolte možnost **Upravit** >  > režim dokončení přepínání**technologie IntelliSense**.

## <a name="parameter-info"></a>Informace o parametrech

Informace o parametru poskytují informace o počtu, názvech a typech parametrů vyžadovaných metodou, atributem parametru obecného typu (v jazyce C#) nebo šablonou (v jazyce C++).

Parametr tučně označuje další parametr, který je vyžadován při zadávání funkce. Pro přetížené funkce můžete použít klávesy se šipkami **nahoru** a **dolů** k zobrazení alternativních informací o parametrech pro přetížení funkce.

![Informace o parametrech](../ide/media/vs2015_param_info.png)

Když opatřujete poznámkami funkce a parametry s komentáři XML dokumentace, komentáře se zobrazí jako informace o parametru. Další informace najdete v tématu [zadání komentářů kódu XML](reference/generate-xml-documentation-comments.md).

Informace o parametrech lze vyvolat ručně kliknutímna možnost **Upravit** > **informace o parametrech** **technologie IntelliSense** > , stisknutím klávesy **CTRL**+**SHIFT**+nebo pomocí Výběr tlačítka **informace o parametru** na panelu nástrojů editoru.

## <a name="quick-info"></a>Rychlé informace

Rychlé informace zobrazí úplnou deklaraci pro libovolný identifikátor ve vašem kódu.

![Rychlé informace pro Visual Studio](../ide/media/vs2015_quick_info.png)

Když vyberete člena v poli **seznam členů** , zobrazí se také pole rychlé informace.

![Informace o parametrech v&#35; souboru kódu jazyka C](../ide/media/vs2015_paraminfo.png)

Rychlé informace můžete vyvolat ručně výběrem možnosti **Upravit** > **rychlé informace** **technologie IntelliSense** > , stisknutím **kombinace kláves CTRL +** +nebo výběrem tlačítka **rychlé informace** v editoru. pruhu.

Pokud je funkce přetížena, technologie IntelliSense nemusí zobrazit informace pro všechny formy přetížení.

C++ Rychlé informace pro kód můžete vypnout tak, že přejdete na **nástroje** > **Možnosti** > **textový editor** > **C/C++**  > **Upřesnit**a nastavíte **auto. Rychlé informace** pro `false`.

## <a name="complete-word"></a>Dokončit slovo

Po zadání dostatečného počtu znaků k odstranění nejednoznačného období dokončí aplikace slovo zbytek proměnné, příkazu nebo názvu funkce. Úplné slovo můžete vyvolat tak, že kliknete na tlačítko **Upravit** > **IntelliSense** > **hotové slovo**, stisknete klávesu **CTRL**+nebo kliknutím na tlačítko **kompletní slovo** na panel nástrojů editoru

## <a name="intellisense-options"></a>Možnosti technologie IntelliSense

Možnosti technologie IntelliSense jsou standardně povoleny. Chcete-li je vypnout, zvolte možnost **nástroje** >  > **textový editor** a zrušte výběr **informací o parametrech** nebo **Automatické seznamy členů** , pokud nechcete, aby funkce členové seznamu byly.

## <a name="intellisense-icons"></a>Ikony IntelliSense
Ikony v technologii IntelliSense mohou vyjádřit další význam s modifikátory ikon. Jedná se o hvězdičky, srdce a zámky nad ikonou objektu, který předává chráněné, interní nebo soukromé, v uvedeném pořadí.

|    Ikona    |    Usnadnění    |    Popis    |
|------------|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| ![Modifikátor veřejných ikon](../ide/media/intellisensePublicNoModifier.png)       |    Veřejná třída    |    Přístup není omezen.   |
| ![Modifikátor chráněné ikony](../ide/media/intellisenseProtectedModifier.png)       |    Chráněná třída    |    Přístup je omezen na obsahující třídu nebo typy odvozené z obsažené třídy.    |
| ![Modifikátor chráněné interní ikony](../ide/media/intellisenseProtectedInternalModifier.png)       |    Chráněná interní třída    |    Přístup je omezen na aktuální sestavení nebo typy odvozené z nadřazené třídy.    |
| ![Modifikátor interní ikony](../ide/media/intellisenseInternalModifier.png)       |    Internal – třída    |    Přístup je omezen na aktuální sestavení.    |
|![Modifikátor privátní ikony](../ide/media/intellisensePrivateModifier.png)        |    Soukromá třída    |    Přístup je omezen na obsahující třídu nebo typy odvozené z obsažené třídy v rámci aktuálního sestavení. (K dispozici od C# verze 7,2.)    |

## <a name="troubleshoot-intellisense"></a>Řešení potíží s technologií IntelliSense

Možnosti technologie IntelliSense nemusí v určitých případech fungovat podle očekávání.

**Kurzor je pod chybou kódu.** Je možné, že nebudete moci používat technologii IntelliSense, pokud v kódu nad kurzorem existuje nekompletní funkce nebo jiná chyba, protože technologie IntelliSense nemusí být schopna analyzovat prvky kódu. Tento problém lze vyřešit okomentováním odpovídajícího kódu.

**Kurzor je v komentáři kódu.** IntelliSense nemůžete použít, pokud je kurzor v komentáři ve zdrojovém souboru.

**Kurzor je v řetězcovém literálu.** IntelliSense nemůžete použít, pokud je kurzor v uvozovkách kolem řetězcového literálu, jako v následujícím příkladu:

```cpp
MessageBox( hWnd, "String literal|")
```

**Automatické možnosti jsou vypnuté.** Ve výchozím nastavení funguje technologie IntelliSense automaticky, ale můžete ji zakázat. Použít funkci IntelliSense můžete i v případě, že je zakázáno automatické dokončování.

## <a name="see-also"></a>Viz také:

- [Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md)
- [C# IntelliSense](../ide/visual-csharp-intellisense.md)
- [JavaScript IntelliSense](../ide/javascript-intellisense.md)
- [Zápis a refaktoring kódu (C++)](/cpp/ide/writing-and-refactoring-code-cpp)
- [Zadejte komentáře kódu XML](reference/generate-xml-documentation-comments.md)
