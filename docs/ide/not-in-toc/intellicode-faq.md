---
title: IntelliCode otázek a odpovědí
ms.date: 07/12/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
ms.openlocfilehash: 79e18778eae231d16cf32c0fa68bcb6f5564b09d
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/17/2018
ms.locfileid: "39079308"
---
# Visual Studio IntelliCode – nejčastější dotazy

Děkujeme za váš zájem o Visual Studio IntelliCode. Tento krátký – nejčastější dotazy se snad získali odpovědi na otázky, které máte uzavřeny.

## Q. Co je Visual Studio IntelliCode?

V sestavení 2018 společnost Microsoft oznámila Visual Studio IntelliCode, novou funkci, která rozšiřuje možnosti vývoje softwaru pomocí AI. IntelliCode pomáhá vývojářům a týmy kódu bez obav, najít problémy rychleji a zaměřit revize kódu.

Časná přehled jak IntelliCode jsme si ukázali, jak vylepšuje proces vývoje softwaru následujícími způsoby:

- Nabízí dokončování s ohledem na kontext kódu
- Provede vývojářům dodržovat vzory a styly jejich tým
- Vyhledá problémy kód obtížné catch
- Se zaměřuje revize kódu tím upozorňuje na oblasti, které jsou opravdu důležité.

Vývojáři najdou další informace a přihlášení si novinky a budoucích verzí private Preview v [ https://aka.ms/intellicode ](https://aka.ms/intellicode).

## Q. Co Visual Studio IntelliCode zákazníkům umožnit, aby dělat?

Visual Studio IntelliCode je celou řadu funkcí, které nabízí nová vylepšení produktivity prostřednictvím umělé inteligence (AI).

Mohou vývojáři [stažení experimentální rozšíření](https://go.microsoft.com/fwlink/?linkid=872707) pro Visual Studio 2017 verze 15.7 nebo novější. Rozšíření v současné době poskytuje:

- AI Vylepšená technologie IntelliSense, který bude předpovídat nejpravděpodobnější správné rozhraní API pro vývojáře, které chcete použít, ne jenom nabízí ten samý abecední seznam členů. Používá aktuální kontext kódu a vzory pro vývojáře k poskytování tohoto dynamického seznamu.

- Odvození stylu kódu a formátování konvence, která pomáhá zachovat kódu konzistentní vzhledem k aplikacím dynamicky vytvořením [souboru .editorconfig](../create-portable-custom-editor-options.md) z vašeho základu kódu pro definování formátů a stylů kódování. Tato konvence umožníte softwaru Visual Studio nabízí automatické styl a formát oprav vyčistit dokument.

Aktualizujeme rozšíření s více funkcemi v nadcházejících měsících.

## Q. Proč EditorConfig odvození předřaďte 1 k názvu souboru?

Známý problém nástroje rozšiřitelnost sady Visual Studio způsobí, že 1. Chcete-li předsunuto souboru .editorconfig při vytváření kliknutím pravým tlačítkem a vyberete **Přidat > Nová položka**. Soubory s názvem tímto způsobem nerozpoznala editorconfig procesoru v aplikaci Visual Studio. Tento problém je vyřešen ve verzi Visual Studio 2017 15,8 ve verzi Preview 4, ale do té doby můžete obejít tak, že odeberete 1 v **přidat novou položku** dialogového okna.

## Q. Proč nevidím moje EditorConfig konvence neprojevuje?
Existuje několik běžných příčin, že tento problém může nastat:

- V sadě Visual Studio 2017 verze starší než 15,8 ve verzi Preview 3, budete muset zavřít a znovu otevřít všechny otevřené dokumenty zobrazíte konvence v souboru EditorConfig vytvoříte projeví. Tento problém vyřešen ve verzi Preview 15,8 3 verze.
- Formátovacích úmluv nikdy zobrazí **seznam chyb** nebo jako "podtržení vlnovkou" ve vašem kódu. Může však být opraveno v sadě Visual Studio 2017 verze 15.8 pomocí nové rozšíření formátovat dokument (Ctrl + K, Ctrl + D) ve verzi Preview 3 nebo novější

## Q. Formátovat dokument není oprava Moje konvence stylu – proč?
Existuje několik běžných příčin, že tento problém může nastat:

- Je možné, že používáte Visual Studio 2017 verze 15.8 ve verzi Preview 3 nebo vyšší. Bude nutné tuto verzi použít rozšířený příkaz "Formát dokumentu" pro další kód vyčištění pro aktuální dokument.
- Opravy, styl, nemusí být výslovného souhlasu. Rozšířené možnosti opravit problémy podle úmluvy schopností ve formátu dokumentu pokrývá jenom fixní sadu problémy. Můžete změnit problémy, které jsou opravené v **možnosti nástrojů** pod **textový Editor > C# > Styl kódu > Formát > Obecné > Nastavení formátu dokumentu (Experiment)**. Všimněte si, že výchozí nastavení nelze vyřešit pomocí některé konvence stylu. Můžete přejít k těmto prostřednictvím **nástroje > Možnosti**. Například "Použije implicitní nebo explicitní typ předvolby" se spustí pravidla stylu týkajících se používání `var`.

## Q. Jaké konvence EditorConfig může Visual Studio IntelliCode odvodit?

V současné době je tato funkce je experimentální, takže nepodporujeme úplnou sadu konvence uvedené v [referenční příručka k nastavení stylu kódu](../editorconfig-code-style-settings-reference.md) ještě.

IntelliCode lze odvodit aktuálně následující konvence:

Konvence formátování:

-   csharp_space_between_method_declaration_parameter_list_parentheses
-   csharp_space_between_method_declaration_empty_parameter_list_parentheses
-   csharp_space_between_method_call_name_and_opening_parenthesis
-   csharp_space_between_method_call_parameter_list_parentheses
-   csharp_space_between_method_call_empty_parameter_list_parentheses
-   csharp_space_after_keywords_in_control_flow_statements
-   csharp_space_between_parentheses
-   csharp_space_after_cast
-   csharp_space_after_colon_in_inheritance_clause
-   csharp_space_before_colon_in_inheritance_clause
-   csharp_space_around_binary_operators
-   csharp_indent_switch_labels
-   csharp_indent_case_contents
-   csharp_indent_case_contents_when_block
-   csharp_indent_labels
-   csharp_preserve_single_line_blocks
-   csharp_preserve_single_line_statements
-   csharp_new_line_before_open_brace
-   csharp_new_line_before_else
-   csharp_new_line_before_catch
-   csharp_new_line_before_finally
-   csharp_new_line_before_members_in_object_initializers
-   csharp_new_line_before_members_in_anonymous_types
-   csharp_new_line_between_query_expression_clauses

Konvence stylu
-   csharp__new_line_before_catch
-   csharp_new_line_before_else
-   csharp_new_line_before_members_in_anonymous_types
-   csharp_new_line_before_members_in_object_initializers
-   csharp_new_line_before_finally_style
-   csharp_new_line_between_query_expression_clauses
-   csharp_prefer_braces_style
-   csharp_preferred_modifier_order_style
-   csharp_prefer_simple_default_expression
-   csharp_preserve_single_line_blocks
-   csharp_space_after_cast
-   csharp_space_after_keywords_in_control_flow_statements
-   csharp_space_between_method_call_parameter_list_parentheses
-   csharp_space_between_method_declaration_parameter_list_parentheses
-   csharp_space_between_parentheses
-   csharp_style_expression_bodied_accessors
-   csharp_style_expression_bodied_constructors
-   csharp_style_expression_bodied_indexers
-   csharp_style_expression_bodied_methods
-   csharp_style_expression_bodied_operators
-   csharp_style_expression_bodied_properties
-   csharp_style_inlined_variable_declaration
-   csharp_style_pattern_local_over_anonymous_function
-   csharp_style_pattern_matching_over_as_with_null_check
-   csharp_style_var_for_built_in_types
-   csharp_style_var_when_type_is_apparent
-   dotnet_sort_system_directives_first
-   dotnet_style_explicit_tuple_names
-   dotnet_style_object_initializer
-   dotnet_style_predefined_type_for_locals_parameters_members
-   dotnet_style_predefined_type_for_member_access
-   dotnet_style_prefer_inferred_anonymous_type_member_names
-   dotnet_style_qualification_for_event
-   dotnet_style_qualification_for_field
-   dotnet_style_qualification_for_method
-   dotnet_style_qualification_for_property
-   dotnet_style_require_accessibility_modifiers

## Q. Existují jiné funkcí produktů Visual Studio IntelliCode rozšíření?

Aktivně pracujeme na celou řadu vlastností, které jsme rádi veřejně sdílet, jakmile budou k dispozici. Můžete se zaregistrovat do novinky a aktualizace na [ https://aka.ms/intellicode ](https://aka.ms/intellicode) být první vědět, když máme k dispozici nové funkce.

## Otázka: co vlastně "s asistencí AI technologie IntelliSense" technologii IntelliCode lepší než regulární IntelliSense?

Seznam pro doplňování s IntelliCode, navrhuje, že s největší pravděpodobností Opravte rozhraní API pro vývojář, abyste mohli použít, nikoli jednoduchý abecedním seznamu členů. Používá aktuální kontext kódu pro vývojáře a vzory založené na vysoce kvalitní 2000, projekty, open source na Githubu každý s více než 100 hvězdiček, k poskytování tohoto dynamického seznamu. Výsledky tvoří modelu, který předpovídá největší pravděpodobností a nejdůležitější volání rozhraní API.

## Otázka: jak kvalitní jsou návrhy dokončení IntelliCode?

Zatím jste používali doporučení technologie IntelliCode interně v Microsoftu nechystáte nějakou dobu jsme přesvědčeni, že návrhy jsou užitečné. Nakonec, ověření bude v užitečnost těchto doporučení jsou pro vás psaní kódu. Rádi vám umožní poskytovat sady Visual Studio [IntelliCode rozšíření](https://go.microsoft.com/fwlink/?linkid=872707) try. Dejte nám vědět, jak to funguje pro vás a pošlete nám svůj názor. Také natrénujeme náš model založený na vybrat v našich doporučení a aktualizujeme rozšíření modelu zlepšuje.

> [!NOTE]
> Jsou shromažďovány žádné z uživatelského kódu. Zobrazit dotaz na [ochrany osobních údajů](#privacy).

## Q. Jaká je budoucnost IntelliCode?

Zkoumání jsme řadu způsobů, jak zlepšit produktivitu vývojářů pomocí AI a dalších pokročilé techniky. V Microsoft Build 2018 jsme vám ukázali počáteční přehled scénářů, ve kterém by se AI může pomoci vývojáři, ale existuje mnoho další! Nás zajímá výukové od vývojářů, které experimentovat s co jsme ukázali, tedy přihlašování novinky a aktualizace na [ https://aka.ms/intellicode ](https://aka.ms/intellicode).

## Q. Kolik to stojí?

Máme k dispozici žádná oznámení týkající se ceny v současné době.

## Q. Kdy IntelliCode vydáte?

Technologie IntelliSense s asistencí AI IntelliCode je aktuálně ve své první experimentální verzi preview. Budeme aktualizovat experimentální rozšíření a přidáme další možnosti v budoucnu. Máme k dispozici žádný plán finální verzi, ale Vítáme zpětnou vazbu od vývojářů, budeme poskytovat nejlepší prostředí je to možné. Můžete se zaregistrovat do novinky a aktualizace na [ https://aka.ms/intellicode ](https://aka.ms/intellicode).

## Q. Je toto prostředí k dispozici pouze v sadě Visual Studio a jazyka C#?

Prostředí se zobrazilo na 2018 sestavení v sadě Visual Studio 2017 na základ kódu C#. Ale Těšíme se v budoucnu rozšíření IntelliCode do více jazyků a nástrojů řady Visual Studio.

## Q. <a name="whynointellisense"/> Nejde zobrazit návrhy IntelliCode v mé C# editační rozhraní – co se děje?

IntelliCode návrhů se zobrazí v uživatelském rozhraní standardní technologie IntelliSense Visual Studio pro jazyk C#. Rozšíření, která přepsat toto uživatelské rozhraní zabránit návrhy IntelliCode "označený hvězdičkou" povolí, v horní části seznamu. Můžete ověřit, pokud rozšíření způsobují toto chování je vypnutím a technologie IntelliSense zkusit to znovu.

Pokud pro vás to nebude problém vyřešit, ohlaste prosím problém prostřednictvím sady Visual Studio [nahlásit problém](https://docs.microsoft.com/en-us/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) funkcí a zmiňovat IntelliCode v sestavě.

## Q. Jaké verze sady Visual Studio je nutné spustit tuto příponu?

Rozšíření Visual Studio IntelliCode je podporována v sadě Visual Studio 2017 verze 15.7 preview 5 a novější (všechny skladové položky). Instalace rozšíření se zastaví "Toto rozšíření není instalovat na žádného momentálně nainstalovaného produktu." Pokud nemáte nainstalované minimální požadovaná verze.

## Q. Je toto prostředí k dispozici pouze v angličtině?

IntelliCode je rozšíření ve verzi preview ještě dnes a nepovedlo se nemůžou dočkat, až k pochopení, jak užitečné tyto možnosti jsou určené pro širokou škálu zákazníků. Pokud vezmeme IntelliCode z verze preview, jistě popíšeme které národního prostředí nebo jazyk o podporu první a jak je aplikace zabalená, na základě vaší zpětné vazby.

## <a name="privacy"/> Otázka: a co o ochraně osobních údajů? Jsou moje kód posílají do cloudu? Jaké zákaznická data se posílá Microsoftu?

Vývojáři mohou prostředí Visual Studio IntelliCode jako rozšíření experimentální verzi preview ještě dnes. Účelem tohoto rozšíření je umožňující vývojářům otestovat IntelliCode možnosti a připomínky pro produktový tým.

Zachycení jsme některé anonymizovaná data o používání a hlášení chyb z rozšíření k vylepšení produktu. Žádný uživatelský kód se neodesílají do Microsoftu, ale můžeme shromažďovat informace o používání IntelliCode výsledky. Data obsahují pouze open source a .NET typy a členy, které jste vybrali ze seznamu navrhovaných IntelliCode. Vývojáři se můžou rozhodnout z celkového počtu [programu zlepšování zkušeností sady Visual Studio](../../ide/visual-studio-experience-improvement-program.md), který vypne shromažďování dat pro rozšíření IntelliCode příliš. V panelu nabídky vyberte **pomáhají** > **odeslat zpětnou vazbu** > **nastavení**. V **programu zlepšování zkušeností sady Visual Studio** dialogového okna, vyberte **Ne, nechci se zúčastnit** a pak vyberte **OK**.

IntelliCode rozšíření může pravidelně žádat developer průzkumu, který znovu jsou anonymní. Uživatelé mohou zaregistrovat do zprávy a budoucí privátní verze preview, ale nejsou aktuálně vyžaduje k tomu použít experimentální rozšíření.

Budoucí funkce může vyžadovat přístup ke službě, která bude vyžadovat registrace. Jakmile tyto funkce jsou připravené pro privátní verze preview budeme publikovat další podrobnosti.
