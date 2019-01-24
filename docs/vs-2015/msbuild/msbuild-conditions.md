---
title: Podmínky nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
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
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cd5fb6f70504fd89c0d08f7a8aa760b3c7b68323
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54758329"
---
# <a name="msbuild-conditions"></a>Podmínky nástroje MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] podporuje konkrétní sadu podmínek, které lze použít všude, kde `Condition` atribut je povolen. Následující tabulka vysvětluje tyto podmínky.  
  
|Podmínka|Popis|  
|---------------|-----------------|  
|'`stringA`' == '`stringB`'|Vyhodnotí jako `true` Pokud `stringA` rovná `stringB`.<br /><br /> Příklad:<br /><br /> `Condition="'$(CONFIG)'=='DEBUG'"`<br /><br /> Jednoduché uvozovky nejsou požadována pro jednoduché alfanumerické řetězce nebo logické hodnoty. Nicméně jednoduché uvozovky jsou povinné pro prázdné hodnoty.|  
|'`stringA`' != '`stringB`'|Vyhodnotí jako `true` Pokud `stringA` není roven `stringB`.<br /><br /> Příklad:<br /><br /> `Condition="'$(CONFIG)'!='DEBUG'"`<br /><br /> Jednoduché uvozovky nejsou požadována pro jednoduché alfanumerické řetězce nebo logické hodnoty. Nicméně jednoduché uvozovky jsou povinné pro prázdné hodnoty.|  
|\<, >, \<=, >=|Číselné hodnoty z operandů vyhodnotí. Vrátí `true` Pokud relační vyhodnocení má hodnotu true. Operandy musí vyhodnotit na desítkové nebo šestnáctkové číslo. Šestnáctková čísla musí začínat řetězcem "0 x". **Poznámka:**  V kódu XML znaky `<` a `>` musí být uvozeny řídicími znaky. Symbol `<` je vyjádřena jako `<`. Symbol `>` je vyjádřena jako `>`.|  
|Existuje ("`stringA`")|Vyhodnotí jako `true` Pokud soubor nebo složka s názvem `stringA` existuje.<br /><br /> Příklad:<br /><br /> `Condition="!Exists('$(builtdir)')"`<br /><br /> Jednoduché uvozovky nejsou požadována pro jednoduché alfanumerické řetězce nebo logické hodnoty. Nicméně jednoduché uvozovky jsou povinné pro prázdné hodnoty.|  
|HasTrailingSlash('`stringA`')|Vyhodnotí jako `true` Pokud zadaný řetězec obsahuje buď koncové zpětné lomítko (\\) nebo předávání znak lomítka (/).<br /><br /> Příklad:<br /><br /> `Condition="!HasTrailingSlash('$(OutputPath)')"`<br /><br /> Jednoduché uvozovky nejsou požadována pro jednoduché alfanumerické řetězce nebo logické hodnoty. Nicméně jednoduché uvozovky jsou povinné pro prázdné hodnoty.|  
|!|Vyhodnotí jako `true` Pokud operand je vyhodnocen jako `false`.|  
|A|Vyhodnotí jako `true` Pokud mají oba operandy `true`.|  
|Nebo|Vyhodnotí jako `true` Pokud se alespoň jeden z operandů vyhodnotí jako `true`.|  
|()|Seskupovací mechanismus, který se vyhodnotí `true` Pokud výrazy obsažené uvnitř `true`.|  
|$if$ (% výrazem %), $else$, $endif$|Kontroluje, zda zadaný `%expression%` shoduje s hodnotou řetězce parametr předaný vlastní šablony. Pokud `$if$` podmínka vyhodnocena jako `true`, pak jeho příkazy spuštění; v opačném případě `$else$` podmínka je zaškrtnuté políčko. Pokud `$else$` podmínka je `true`, pak jeho příkazy spuštění; v opačném případě `$endif$` podmínka ukončení vyhodnocení výrazu.<br /><br /> Příklady využití naleznete v tématu [Visual Studio projekt/položka šablony parametr logiky](http://stackoverflow.com/questions/6709057/visual-studio-project-item-template-parameter-logic).|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Podmíněné konstrukce](../msbuild/msbuild-conditional-constructs.md)   
 [Návod: Vytváření souboru projektu MSBuild od začátku](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)
