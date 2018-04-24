---
title: Podmínky nástroje MSBuild | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, conditions
- conditions [MSBuild]
ms.assetid: 9d7aa308-b667-48ed-b4c9-a61e49eb0a85
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 221f8ceba5a82b25e78314579323f6a7d55cf984
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="msbuild-conditions"></a>Podmínky nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] podporuje konkrétní sadu podmínek, které lze použít kdekoli `Condition` atribut je povolen. Následující tabulka vysvětluje tyto podmínky.  
  
|Podmínka|Popis|  
|---------------|-----------------|  
|'`stringA`' == '`stringB`'|Vyhodnotí jako `true` Pokud `stringA` rovná `stringB`.<br /><br /> Příklad:<br /><br /> `Condition="'$(CONFIG)'=='DEBUG'"`<br /><br /> Jednoduchých uvozovek a jsou vyžadovány pro jednoduché alfanumerické řetězce nebo logické hodnoty. Jednoduché uvozovky jsou však nutná pro prázdné hodnoty.|  
|'`stringA`' != '`stringB`'|Vyhodnotí jako `true` Pokud `stringA` se nerovná `stringB`.<br /><br /> Příklad:<br /><br /> `Condition="'$(CONFIG)'!='DEBUG'"`<br /><br /> Jednoduchých uvozovek a jsou vyžadovány pro jednoduché alfanumerické řetězce nebo logické hodnoty. Jednoduché uvozovky jsou však nutná pro prázdné hodnoty.|  
|\<, >, \<=, >=|Vyhodnotí číselné hodnoty operandy. Vrátí `true` Pokud relační vyhodnocení má hodnotu true. Operandy se musí vyhodnotit desetinné nebo hexadecimální číslo. Hexadecimální číslice musí začínat řetězcem "0 x". **Poznámka:** v XML znaky `<` a `>` , je nutné uvést. Symbol `<` je reprezentován jako `&lt;`. Symbol `>` je reprezentován jako `&gt;`.|  
|Existuje ('`stringA`')|Vyhodnotí jako `true` Pokud soubor nebo složku s názvem `stringA` existuje.<br /><br /> Příklad:<br /><br /> `Condition="!Exists('$(builtdir)')"`<br /><br /> Jednoduchých uvozovek a jsou vyžadovány pro jednoduché alfanumerické řetězce nebo logické hodnoty. Jednoduché uvozovky jsou však nutná pro prázdné hodnoty.|  
|HasTrailingSlash('`stringA`')|Vyhodnotí jako `true` Pokud zadaný řetězec obsahuje buď koncové zpětné lomítko (\\) nebo předávat lomítko (/).<br /><br /> Příklad:<br /><br /> `Condition="!HasTrailingSlash('$(OutputPath)')"`<br /><br /> Jednoduchých uvozovek a jsou vyžadovány pro jednoduché alfanumerické řetězce nebo logické hodnoty. Jednoduché uvozovky jsou však nutná pro prázdné hodnoty.|  
|!|Vyhodnotí jako `true` Pokud je výsledkem operand `false`.|  
|A|Vyhodnotí jako `true` Pokud oba operandy vyhodnocení `true`.|  
|Nebo|Vyhodnotí jako `true` Pokud je alespoň jeden z operandy výsledkem `true`.|  
|()|Seskupování mechanismus, který se vyhodnocuje `true` Pokud vyhodnocení výrazů nachází v `true`.|  
|$if$ (% výrazu) $else$, $endif$|Kontroluje, zda zadaný `%expression%` odpovídá s řetězcovou hodnotou obsahující parametr předaný vlastní šablony. Pokud `$if$` podmínka vyhodnocena jako `true`, pak jeho příkazy jsou spuštění, jinak hodnota `$else$` se kontroluje podmínku. Pokud `$else$` podmínka je `true`, pak jeho příkazy jsou spuštění, jinak hodnota `$endif$` podmínky ukončení vyhodnocení výrazu.<br /><br /> Příklady využití najdete v tématu [Visual Studio nebo položka projektu šablony parametr logiku](http://stackoverflow.com/questions/6709057/visual-studio-project-item-template-parameter-logic).|  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Podmíněné konstrukce](../msbuild/msbuild-conditional-constructs.md)   
 [Návod: Vytvoření souboru projektu MSBuild od začátku](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)
