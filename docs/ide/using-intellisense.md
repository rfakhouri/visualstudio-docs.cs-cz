---
title: "Používání atributu IntelliSense | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.tools.intellisense
helpviewer_keywords:
- IntelliSense, Complete Word
- IntelliSense, completion mode
- parameter information
- IntelliSense, List Members
- Quick Info
- Parameter Info
- IntelliSense [Visual Studio]
- IntelliSense, suggestion mode
- IntelliSense, Parameter Info
- IntelliSense, customizing
- Complete Word
- IntelliSense
- List Members
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 42e34f5933d06bf9021ff8e0cab5b12f316ef52e
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="using-intellisense"></a>Používání atributu IntelliSense

IntelliSense je obecný termín pro několik funkcí: seznamy členů, informace o parametrech, rychlé informace a dokončování slov. Tyto funkce umožňují získat další informace o kódu, který používáte, zachovat si přehled o parametrech, které píšete, a přidávat volání vlastností a metod s pomocí několika klávesových úhozů.

Mnoho aspektů technologie IntelliSense je specifických pro jazyk. Další informace o technologii IntelliSense pro různé jazyky, najdete v tématech uvedených v [viz také](#see-also) části.

## <a name="list-members"></a>Vypsat členy

Po zadání znaku aktivační události se zobrazí seznam platný členy z typu (nebo obor názvů) (například dobu (`.`) ve spravovaném kódu nebo `::` v jazyce C++). Pokud budete pokračovat, zadejte znaky, je v seznamu vyfiltrován, aby obsahoval pouze členové, které začínají tyto znaky nebo kde začátku *žádné* slova v názvu začíná tyto znaky. IntelliSense také provede "camelCase" párování, takže první písmeno každého slova ve formátu camelCase můžete zadat jenom název člena můžete zobrazit shody.

Po výběru položky, můžete jej přidat do vašeho kódu stisknutím **kartě** nebo zadáním mezerou. Pokud vyberte položku a zadáte období, položka se zobrazí s uvedenou dobou, která vyvolá jiný seznam členů. Pokud vyberete položku, ale ještě před jejím vložením, zobrazí se rychlé informace pro položku.

V seznamu členů ikona vlevo představuje typ členu, například obor názvů, třídu, funkci nebo proměnnou. Seznam ikon, naleznete v části [zobrazení tříd a ikony v prohlížeči objekt](../ide/class-view-and-object-browser-icons.md). V seznamu může být poměrně dlouho, můžete stisknout **PgUp** a **Page Down** přesunout nahoru nebo dolů v seznamu.

![Seznam členů v sadě Visual Studio](../ide/media/vs2015_intellisense.png "vs2015_Intellisense")

Můžete vyvolat **vypsat členy** funkce ručně zadáním **CTRL** + **J**, výběrem možnosti **upravit**  >  **IntelliSense** > **vypsat členy**, nebo výběrem **vypsat členy** tlačítka na panelu nástrojů editoru. Při vyvolání na prázdném řádku nebo mimo podporovaný rozsah zobrazí seznam symboly v globálním oboru názvů.

Chcete-li vypsat členy vypnout ve výchozím nastavení (tak to nezobrazí, dokud konkrétně vyvolat), přejděte na **nástroje** > **možnosti** > **všechny jazyky**a zrušte výběr **automatický seznam členů**. Pokud chcete vypnout vypsat členy pouze pro konkrétní jazyk, přejděte k **Obecné** nastavení pro tento jazyk.

Můžete také změnit nastavení na režim návrhu, ve kterém je do kódu vložen pouze text, který zadáte. Například zadejte identifikátor, který se nenachází v seznamu a stiskněte klávesu **kartě**, při dokončení by režimu položku nahradit identifikátor typu. Chcete-li přepnout mezi dokončení režim a režim návrhu, stiskněte **Ctrl** + **Alt** + **MEZERNÍK**, nebo zvolte **upravit**  >  **IntelliSense** > **přepnout režim dokončení**.

## <a name="parameter-info"></a>Informace o parametrech

Informace o parametru poskytují informace o počtu, názvech a typech parametrů vyžadovaných metodou, atributem parametru obecného typu (v jazyce C#) nebo šablonou (v jazyce C++).

Parametr tučně označuje další parametr, který je vyžadován při zadávání funkce. Pro přetížené funkce můžete použít klávesy se šipkami nahoru a dolů a zobrazit tak alternativní informace o parametru pro přetížení funkce.

![Parameter Info](../ide/media/vs2015_param_info.png "VS2015_param_Info")

Když opatřujete poznámkami funkce a parametry s komentáři XML dokumentace, komentáře se zobrazí jako informace o parametru. Další informace najdete v tématu [zadávání komentářů ke kódu XML](../ide/supplying-xml-code-comments.md).

Informace o parametrech můžete vyvolat ručně tak, že zvolíte **upravit** > **IntelliSense** > **informace o parametrech**, stisknutím klávesy **Ctrl**   +  **Shift** + **místo**, nebo výběrem **informace o parametrech** tlačítka na panelu nástrojů editoru.

## <a name="quick-info"></a>Rychlé informace

Rychlé informace zobrazí úplnou deklaraci pro libovolný identifikátor ve vašem kódu.

![Visual Studio Quick Info](../ide/media/vs2015_quick_info.png "VS2015_Quick_info")

Když vyberete člena z **vypsat členy** pole, se také zobrazí rychlé informace.

![Informace o parametrech v a C &#35; souboru kódu](../ide/media/vs2015_paraminfo.png "VS2015_ParamInfo")

Rychlé informace můžete vyvolat ručně tak, že zvolíte **upravit** > **IntelliSense** > **rychlé informace**, stisknutím klávesy **Ctrl**  +  **I**, nebo výběrem **rychlé informace** tlačítka na panelu nástrojů editoru.

Pokud je funkce přetížena, technologie IntelliSense nemusí zobrazit informace pro všechny formy přetížení.

Můžete vypnout rychlé informace pro C++ – kód přechodem na **nástroje** > **možnosti** > **textového editoru** > **C / C++** > **Upřesnit**a nastavení **automaticky rychlé informace** k `false`.

## <a name="complete-word"></a>Dokončit slovo

Dokončení Word dokončí zbytek proměnnou, příkaz nebo název funkce po zadání dostatečný počet znaků k rozlišení termín. Dokončení Word můžete vyvolat výběrem **upravit** > **IntelliSense** > **dokončení Word**, stisknutím klávesy **Ctrl**  +  **Místo**, nebo výběrem **dokončení Word** tlačítka na panelu nástrojů editoru.

## <a name="intellisense-options"></a>Možnosti technologie IntelliSense

Možnosti technologie IntelliSense jsou standardně povoleny. Chcete-li je vypnout, vyberte **nástroje** > **možnosti** > **textového editoru** a zrušte výběr **informace o parametrech**nebo **automatický seznam členů** Pokud nechcete, aby funkci seznamu členů.

## <a name="troubleshooting-intellisense"></a>Řešení potíží technologie IntelliSense

Možnosti technologie IntelliSense nemusí v určitých případech fungovat podle očekávání.

**Kurzor je pod chybě s kódem.** Není možné použít technologii IntelliSense, pokud neúplná funkce nebo jiná chyba existuje v kódu výše kurzor, protože nemusí být schopen analyzovat elementy kódu technologie IntelliSense. Tento problém lze vyřešit okomentováním odpovídajícího kódu.

**Kurzor se nachází v komentář ke kódu.** IntelliSense nelze použít, pokud kurzor se nachází v komentáře ve zdrojovém souboru.

**Kurzor se nachází v řetězcový literál.** IntelliSense nelze použít, pokud kurzor se nachází v uvozovkách řetězcový literál, jako v následujícím příkladu:

```cpp
MessageBox( hWnd, "String literal|")
```

**Možnosti automatického jsou vypnuté.** Ve výchozím nastavení IntelliSense funguje automaticky, ale můžete ji zakázat. Použít funkci IntelliSense můžete i v případě, že je zakázáno automatické dokončování.

## <a name="see-also"></a>Viz také

[Specifické pro jazyk Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md)  
[C# IntelliSense](../ide/visual-csharp-intellisense.md)  
[JavaScript IntelliSense](../ide/javascript-intellisense.md)  
[Psaní a refaktoring kódu (C++)](/cpp/ide/writing-and-refactoring-code-cpp)  
[Zadávání komentářů ke kódu XML](../ide/supplying-xml-code-comments.md)
