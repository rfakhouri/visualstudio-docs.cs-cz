---
title: Informace o parametrech, seznam členů a rychlé informace
ms.date: 05/25/2018
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 7ff6db60e9d6df092e3189f03e1410c41a799235
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54981893"
---
# <a name="intellisense-in-visual-studio"></a>Technologie IntelliSense v sadě Visual Studio

Technologie IntelliSense je podpora dokončování kódu, která zahrnuje celou řadu funkcí: Seznam členů, informace o parametrech, rychlé informace a dokončit slovo. Tyto funkce umožňují získat další informace o kód, který používáte, udržovat přehled o parametrech zadávání textu a přidávat volání vlastností a metod s pomocí několika klávesových úhozů.

Mnoho aspektů technologie IntelliSense je specifických pro jazyk. Další informace o technologii IntelliSense pro různé jazyky, naleznete v tématech uvedených v [viz také](#see-also) oddílu.

## <a name="list-members"></a>Vypsat členy

Po zadání znaku aktivační události se zobrazí seznam platných členů z typu (nebo oboru názvů) (například, období (`.`) ve spravovaném kódu nebo `::` v jazyce C++). Pokud budete pokračovat v zadávání znaků, v seznamu jsou vyfiltrované pouze členové, kteří začínají danými znaky nebo kde začátku *jakékoli* slova v rámci název začíná znaky. Technologie IntelliSense také provádí "camelCase" párování, takže první písmeno každého slova ve formátu camelCase můžete jednoduše zadat v členu názvu zobrazíte výsledky.

Po výběru položky ji můžete vložit do kódu stisknutím klávesy **kartu** nebo a zadáním mezery. Pokud vyberte položku a zadáte období, položka se zobrazí s uvedenou dobou, která vyvolá jiný seznam členů. Pokud vyberete položku, ale ještě před jejím vložením, zobrazí se rychlé informace pro položku.

V seznamu členů ikona vlevo představuje typ členu, například obor názvů, třídu, funkci nebo proměnnou. Seznam ikon naleznete v tématu [ikony zobrazení třídy a prohlížeče objektů](../ide/class-view-and-object-browser-icons.md). Seznam může být poměrně dlouhé, takže můžete stisknout **PgUp** a **Page Down** přesunout nahoru nebo dolů v seznamu.

![Seznam členů sady Visual Studio](../ide/media/vs2015_intellisense.png)

Můžete vyvolat **seznam členů** funkce ručně zadáním pomocí **Ctrl**+**J**zvolíte možnost **upravit**  >  **IntelliSense** > **seznam členů**, nebo kliknutím **seznam členů** tlačítko na panelu nástrojů editoru. Při vyvolání na prázdném řádku nebo mimo podporovaný rozsah zobrazí seznam symboly v globálním oboru názvů.

Chcete-li vypnout členy seznamu ve výchozím nastavení (tak, že se nezobrazí, pokud nejsou konkrétně vyvolány), přejděte na **nástroje** > **možnosti** > **všechny jazyky**a zrušte zaškrtnutí možnosti **automatický seznam členů**. Pokud chcete vypnout funkci vypsat členy pouze pro určitý jazyk, přejděte **Obecné** nastavení pro daný jazyk.

Můžete také změnit nastavení na režim návrhu, ve kterém je do kódu vložen pouze text, který zadáte. Například, pokud zadáte identifikátor, který se nenachází v seznamu a stiskněte klávesu **kartu**, při dokončení by režimu položka nahradil zadaný identifikátor. Chcete-li přepnout mezi doplňovacím režimem a režimem návrhu, stiskněte **Ctrl**+**Alt**+**místo**, nebo zvolte **upravit**  >  **IntelliSense** > **přepnout režim dokončení**.

## <a name="parameter-info"></a>Informace o parametrech

Informace o parametru poskytují informace o počtu, názvech a typech parametrů vyžadovaných metodou, atributem parametru obecného typu (v jazyce C#) nebo šablonou (v jazyce C++).

Parametr tučně označuje další parametr, který je vyžadován při zadávání funkce. Pro přetížené funkce můžete použít **nahoru** a **dolů** klávesy se šipkami zobrazíte alternativní informace o parametru pro přetížení funkce.

![Informace o parametrech](../ide/media/vs2015_param_info.png)

Když opatřujete poznámkami funkce a parametry s komentáři XML dokumentace, komentáře se zobrazí jako informace o parametru. Další informace najdete v tématu [komentářů ke kódu XML zadat](reference/generate-xml-documentation-comments.md).

Informace o parametrech lze vyvolat ručně kliknutím **upravit** > **IntelliSense** > **informace o parametru**, stisknutím klávesy **Ctrl**  + **Shift**+**místo**, nebo kliknutím **informace o parametru** tlačítko na panelu nástrojů editoru.

## <a name="quick-info"></a>Rychlé informace

Rychlé informace zobrazí úplnou deklaraci pro libovolný identifikátor ve vašem kódu.

![Visual Studio Quick Info](../ide/media/vs2015_quick_info.png)

Vyberete-li člena v **seznam členů** , rychlé informace zobrazí se také pole.

![Informace o parametrech ve C&#35; souboru kódu](../ide/media/vs2015_paraminfo.png)

Rychlé informace lze vyvolat ručně kliknutím **upravit** > **IntelliSense** > **rychlé informace**, stisknutím klávesy **Ctrl** + **můžu**, nebo kliknutím **rychlé informace** tlačítko na panelu nástrojů editoru.

Pokud je funkce přetížena, technologie IntelliSense nemusí zobrazit informace pro všechny formy přetížení.

Můžete vypnout rychlé informace pro kód C++ tak, že přejdete do **nástroje** > **možnosti** > **textový Editor** > **C / C++** > **Upřesnit**a nastavení **automatické rychlé informace** k `false`.

## <a name="complete-word"></a>Dokončit slovo

Jakmile zadáte dostatečný počet znaků pro odstranění dvojznačnosti termínu funkce dokončit slovo dokončí zbytek proměnné, příkazu nebo název funkce. Dokončit slovo můžete vyvolat kliknutím **upravit** > **IntelliSense** > **dokončit slovo**, stisknutím klávesy **Ctrl** + **Místo**, nebo kliknutím **dokončit slovo** tlačítko na panelu nástrojů editoru.

## <a name="intellisense-options"></a>Možnosti technologie IntelliSense

Možnosti technologie IntelliSense jsou standardně povoleny. Chcete-li je vypnout, vyberte **nástroje** > **možnosti** > **textový Editor** a zrušte zaškrtnutí možnosti **informace o parametrech**nebo **automatický seznam členů** Pokud nechcete, aby funkci vypsat členy.

## <a name="troubleshoot-intellisense"></a>Řešení potíží s IntelliSense

Možnosti technologie IntelliSense nemusí v určitých případech fungovat podle očekávání.

**Kurzor je pod chybě s kódem.** Nebudete moct používat technologii IntelliSense, pokud neúplné funkce nebo jiná chyba v kódu nad kurzorem existuje, protože nemusí být možné zpracovat prvky kódu technologie IntelliSense. Tento problém lze vyřešit okomentováním odpovídajícího kódu.

**Kurzor je v komentáři kódu.** Technologii IntelliSense nelze použít, pokud je kurzor v komentáři ve zdrojovém souboru.

**Kurzor je v řetězcovém literálu.** Technologii IntelliSense nelze použít, pokud je kurzor v uvozovkách okolo literálu řetězce, jako v následujícím příkladu:

```cpp
MessageBox( hWnd, "String literal|")
```

**Automatické možnosti jsou vypnuté.** Ve výchozím nastavení funguje technologie IntelliSense automaticky, ale lze je vypnout. Použít funkci IntelliSense můžete i v případě, že je zakázáno automatické dokončování.

## <a name="see-also"></a>Viz také:

- [Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md)
- [C# IntelliSense](../ide/visual-csharp-intellisense.md)
- [JavaScript IntelliSense](../ide/javascript-intellisense.md)
- [Zápis a Refaktorujte kód (C++)](/cpp/ide/writing-and-refactoring-code-cpp)
- [Zadat komentářů ke kódu XML](reference/generate-xml-documentation-comments.md)