---
title: "Používání atributu IntelliSense | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.tools.intellisense
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
ms.assetid: 9fdb489b-8b46-4b92-9ccc-c8f8cc184081
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 149cb62f35ce4b1ce15ab939a0805bc63bfb6f26
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="using-intellisense"></a>Používání atributu IntelliSense
IntelliSense je obecný termín pro několik funkcí: seznamy členů, informace o parametrech, rychlé informace a dokončování slov. Tyto funkce umožňují získat další informace o kódu, který používáte, zachovat si přehled o parametrech, které píšete, a přidávat volání vlastností a metod s pomocí několika klávesových úhozů.  
  
 Mnoho aspektů technologie IntelliSense je specifických pro jazyk. Další informace o technologii IntelliSense pro různé jazyky naleznete v tématech uvedených v části Viz také.  
  
## <a name="list-members"></a>Vypsat členy  
 Po zadání znaku aktivační události se zobrazí seznam platný členy z typu (nebo obor názvů) (například dobu (`.`) ve spravovaném kódu nebo `::` v jazyce C++). Pokud budete pokračovat, zadejte znaky, je v seznamu vyfiltrován, aby obsahoval pouze členové, které začínají tyto znaky nebo kde začátku *žádné* slova v názvu začíná tyto znaky. IntelliSense také provede "camelCase" párování, takže první písmeno každého slova ve formátu camelCase můžete zadat jenom název člena můžete zobrazit shody.   
  
 Po výběru položky ji můžete vložit do kódu stisknutím klávesy TAB a zadáním mezery. Pokud vyberte položku a zadáte období, položka se zobrazí s uvedenou dobou, která vyvolá jiný seznam členů. Pokud vyberete položku, ale ještě před jejím vložením, zobrazí se rychlé informace pro položku.  
  
 V seznamu členů ikona vlevo představuje typ členu, například obor názvů, třídu, funkci nebo proměnnou. Seznam ikon, naleznete v části [zobrazení tříd a ikony v prohlížeči objekt](../ide/class-view-and-object-browser-icons.md). Seznam může být poměrně dlouhý a posouvat se v něm můžete stisknutím klávesy PAGE UP a PAGE DOWN.  
  
 ![Seznam členů v sadě Visual Studio](../ide/media/vs2015_intellisense.png "vs2015_Intellisense")  
  
 Můžete vyvolat **vypsat členy** funkce ručně zadáním CTRL + J, kliknutím na tlačítko **úpravy/IntelliSense/vypsat členy**, nebo kliknutím na tlačítko **vypsat členy** tlačítko na editoru panel nástrojů. Při vyvolání na prázdném řádku nebo mimo podporovaný rozsah zobrazí seznam symboly v globálním oboru názvů.  
  
 Chcete-li vypsat členy vypnout ve výchozím nastavení (tak to nezobrazí, dokud konkrétně vyvolat), přejděte na **Nástroje/možnosti/všechny jazyky** a zrušte výběr **automatický seznam členů**. Pokud chcete vypnout vypsat členy pouze pro konkrétní jazyk, přejděte k **Obecné** nastavení pro tento jazyk.  
  
 Můžete také změnit nastavení na režim návrhu, ve kterém je do kódu vložen pouze text, který zadáte. Například pokud zadáte identifikátor, který není uveden v seznamu, a stisknete klávesu TAB, v režimu ukončení by vstup nahradil zadaný identifikátor. K přepnutí mezi dokončení režim a režim návrhu, stiskněte CTRL + ALT + MEZERNÍK, nebo klikněte na tlačítko **režim dokončení úprav nebo IntelliSense nebo přepnutí**.  
  
## <a name="parameter-info"></a>Informace o parametrech  
 Informace o parametru poskytují informace o počtu, názvech a typech parametrů vyžadovaných metodou, atributem parametru obecného typu (v jazyce C#) nebo šablonou (v jazyce C++).  
  
 Parametr tučně označuje další parametr, který je vyžadován při zadávání funkce. Pro přetížené funkce můžete použít klávesy se šipkami nahoru a dolů a zobrazit tak alternativní informace o parametru pro přetížení funkce.  
  
 ![Informace o parametrech](../ide/media/vs2015_param_info.png "VS2015_param_Info")  
  
 Když opatřujete poznámkami funkce a parametry s komentáři XML dokumentace, komentáře se zobrazí jako informace o parametru. Další informace najdete v tématu [zadávání komentářů ke kódu XML](../ide/supplying-xml-code-comments.md).  
  
 Informace o parametrech můžete vyvolat ručně kliknutím **upravit informace technologie IntelliSense a parametru**, zadáním CTRL + SHIFT + MEZERNÍK, nebo kliknutím **informace o parametrech** tlačítka na panelu nástrojů editoru.  
  
## <a name="quick-info"></a>Rychlé informace  
 Rychlé informace zobrazí úplnou deklaraci pro libovolný identifikátor ve vašem kódu.  
  
 ![Rychlé informace sadě Visual Studio](../ide/media/vs2015_quick_info.png "VS2015_Quick_info")  
  
 Když vyberete člena z **vypsat členy** pole, se také zobrazí rychlé informace.  
  
 ![Informace o parametrech v a C &#35; souboru kódu](../ide/media/vs2015_paraminfo.png "VS2015_ParamInfo")  
  
 Rychlé informace můžete vyvolat ručně kliknutím **IntelliSense/Edit/rychlé informace**, zadejte CTRL + I nebo kliknutím na **rychlé informace** tlačítka na panelu nástrojů editoru.  
  
 Pokud je funkce přetížena, technologie IntelliSense nemusí zobrazit informace pro všechny formy přetížení.  
  
 Rychlé informace vypnout v C++ můžete zapnout nastavením **nástroje / Možnosti / textového editoru nebo C/C + +/ rychlé informace Upřesnit/automaticky** k `false`.  
  
## <a name="complete-word"></a>Dokončit slovo  
 Jakmile zadáte dostatečný počet znaků pro odstranění dvojznačnosti termínu, funkce Dokončit slovo dokončí zbytek proměnné, příkazu nebo názvu funkce. Dokončení Word můžete vyvolat kliknutím **úpravy/IntelliSense/dokončit slovo**, zadejte CTRL + MEZERNÍK, nebo kliknutím na **dokončení Word** tlačítka na panelu nástrojů editoru.  
  
## <a name="intellisense-options"></a>Možnosti technologie IntelliSense  
 Možnosti technologie IntelliSense jsou standardně povoleny. Chcete-li je vypnout, klikněte na tlačítko **nástroje/Možnosti/textového editoru** a zrušte výběr **informace o parametrech** nebo **automatický seznam členů** Pokud nechcete, aby funkci seznamu členů.  
  
## <a name="troubleshooting-intellisense"></a>Řešení potíží technologie IntelliSense  
 Možnosti technologie IntelliSense nemusí v určitých případech fungovat podle očekávání.  
  
 **Kurzor je pod chybě s kódem.** Není možné použít technologii IntelliSense, pokud neúplná funkce nebo jiná chyba existuje v kódu výše kurzor, protože nemusí být schopen analyzovat elementy kódu technologie IntelliSense. Tento problém lze vyřešit okomentováním odpovídajícího kódu.  
  
 **Kurzor se nachází v komentář ke kódu.** IntelliSense nelze použít, pokud kurzor se nachází v komentáře ve zdrojovém souboru.  
  
 **Kurzor se nachází v řetězcový literál.** IntelliSense nelze použít, pokud kurzor se nachází v uvozovkách řetězcový literál, jako v následujícím příkladu:  
  
```  
MessageBox( hWnd, "String literal|")
```  
  
 **Možnosti automatického jsou vypnuté.** Ve výchozím nastavení IntelliSense funguje automaticky, ale můžete ji zakázat. Použít funkci IntelliSense můžete i v případě, že je zakázáno automatické dokončování.  
  
## <a name="see-also"></a>Viz také  
 [Specifické pro Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md)   
 [Visual C# IntelliSense](../ide/visual-csharp-intellisense.md)   
 [JavaScript IntelliSense](../ide/javascript-intellisense.md)   
 [Zadávání komentářů ke kódu XML](../ide/supplying-xml-code-comments.md)
