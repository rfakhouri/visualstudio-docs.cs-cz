---
title: Konfigurace upozornění v jazyce Visual Basic | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors [Visual Basic], warnings
- run-time errors, warnings
- warnings, configuring
ms.assetid: 99cf4781-bd4d-47b4-91b9-217933509f82
caps.latest.revision: ''
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 65e290734a906f006f283bf3462d07389876375c
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="configuring-warnings-in-visual-basic"></a>Konfigurace upozornění v jazyce Visual Basic
[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Kompilátoru zahrnuje sadu upozornění na kód, který může způsobit chyby spuštění. Tyto informace můžete použít k zápisu čisticí, rychlejší a lepší kódu s menším počtem chyb. Například bude kompilátor vytvořit upozornění, když se uživatel pokusí o volají člena nepřiřazené objektové proměnné, vrátit z funkce bez nastavení návratovou hodnotu, nebo spuštění `Try` bloku s chybami v logika pro zachycení výjimky.  
  
 Někdy kompilátor poskytuje další logiku jménem uživatele, aby se uživatel může soustředit na na prováděné úloze, nikoli na předvídání možných chyb. V předchozích verzích [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], **možnost striktní** byla použita k omezení další logiku, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] poskytuje kompilátoru. Konfigurace upozornění umožňuje omezit tuto logiku podrobnější způsobem na úrovni jednotlivých upozornění.  
  
 Můžete přizpůsobit projektu a vypnout některé upozornění není vztahujících se k aplikaci při vypnutí některé upozornění na chyby. Tato stránka vysvětluje, jak zapnout jednotlivých upozornění zapnout a vypnout.  
  
## <a name="turning-warnings-off-and-on"></a>Zapnutí a zapněte upozornění  
 Existují dva různé způsoby konfigurace upozornění: můžete je nakonfigurovat pomocí **Návrhář projektu**, nebo můžete použít **/warnaserror** a **/nowarn** – možnosti kompilátoru .  
  
 **Zkompilovat** kartě **Návrhář projektu** stránce můžete zapnout upozornění zapnout a vypnout. Vyberte **zakázat všech upozornění** políčko zaškrtněte, chcete-li zakázat všech upozornění; vyberte **zpracování všech upozornění jako chyby** zachází všech upozornění jako chyby. Můžou být některé jednotlivých upozornění jako chyby nebo upozornění podle potřeby zobrazené tabulky.  
  
 Když **možnost striktní** je nastaven na **vypnout**, **možnost striktní** související upozornění nelze považovat nezávisle na sobě navzájem. Když **možnost striktní** je nastaven na **na**, přidružené upozornění jsou považovány za chyby, bez ohledu na co je jejich stav. Když **možnost striktní** je nastaven na **vlastní** zadáním `/optionstrict:custom` v kompilátoru příkazového řádku, **možnost striktní** můžou být zapnout nebo vypnout nezávisle.  
  
 **/Warnaserror** možnost příkazového řádku kompilátoru lze také použít k určení, zda upozornění jsou považovány za chyby. Seznam oddělený čárkami můžete přidat do této možnosti určíte, které upozornění mají být zpracovány jako chyby nebo upozornění pomocí + nebo -. V následující tabulce jsou dostupné možnosti.  
  
|Možnost příkazového řádku|Určuje|  
|--------------------------|---------------|  
|`/warnaserror+`|Zpracovává všechna upozornění jako chyby|  
|`/warnsaserror`-|Není považovat upozornění jako chyby. Toto nastavení je výchozí.|  
|`/warnaserror+:<warning list``>`|Konkrétní upozornění považovat za chyby, seřazené podle jejich identifikační číslo v seznamu odděleném čárkami r.|  
|`/warnaserror-:<warning list>`|Není považovat za konkrétní varování chyby, seřazené podle jejich identifikační číslo v seznamu odděleném čárkami.|  
|`/nowarn`|Neoznamovat upozornění.|  
|`/nowarn:<warning list>`|Neoznamovat zadaný upozornění, seřazené podle jejich identifikační číslo v seznamu odděleném čárkami.|  
  
 Seznam upozornění obsahuje identifikační čísla chyb upozornění, které by měly být považovány za chyby, které se dají použít s možností příkazového řádku pro konkrétní varování vypnutí a zapnutí. Pokud seznam upozornění obsahuje neplatné číslo, zobrazí se chybová zpráva.  
  
## <a name="examples"></a>Příklady  
 Tato tabulka příklady argumenty příkazového řádku popisuje, jaké jsou všechny argumenty.  
  
|Argument|Popis|  
|--------------|-----------------|  
|`vbc /warnaserror`|Určuje, že všechna upozornění mají být považována za chyby.|  
|`vbc /warnaserror:42024`|Určuje, že upozornění 42024 měli považovat za chybu.|  
|`vbc /warnaserror:42024,42025`|Určuje, že varování 42024 a 42025 by měly být považovány za chyby.|  
|`vbc /nowarn`|Určuje, že by měly být uvedeny žádné upozornění.|  
|`vbc /nowarn:42024`|Určuje, že upozornění 42024 by neměly být hlášeny.|  
|`vbc /nowarn:42024,42025`|Určuje, že varování 42024 a 42025 by neměly být hlášeny.|  
  
## <a name="types-of-warnings"></a>Typy upozornění  
 Následuje seznam upozornění, které můžete chtít považovat za chyby.  
  
### <a name="implicit-conversion-warning"></a>Implicitní převod upozornění  
 Vygenerovaný pro instance implicitního převodu. Při použití nezahrnují implicitní převod z typu vnitřní čísel na řetězec `&` operátor. Výchozí pro nové projekty je vypnutý.  
  
 ID: 42016  
  
### <a name="late-bound-method-invocation-and-overload-resolution-warning"></a>Rozpoznání s pozdní vázán volání metody a přetížení řešení upozornění  
 Vygenerovaný pro instance dynamické vazby. Výchozí pro nové projekty je vypnutý.  
  
 ID: 42017  
  
### <a name="operands-of-type-object-warnings"></a>Operandy typu upozornění, objektu.  
 Generuje při operandy typu `Object` dojít k chybě, by vytvořit **možnost striktní na**. Výchozí pro nové projekty je zapnuto.  
  
 ID: 42018 a 42019  
  
### <a name="declarations-require-as-clause-warnings"></a>Deklarace vyžadovat jako upozornění – klauzule  
 Vygeneruje, když proměnné, funkce nebo postrádá vlastnost deklarace `As` klauzule by vytvořila chybu s **možnost striktní na**. Proměnné, které nemají typ přiřazenou jsou považovány za typ `Object`. Výchozí pro nové projekty je zapnuto.  
  
 ID: 42020 (deklarace proměnných), 42021 (deklarace funkcí) a 42022 (deklarace vlastnosti).  
  
### <a name="possible-null-reference-exception-warnings"></a>Upozornění výjimka možné odkazu s hodnotou null  
 Generuje při předtím, než byl přiřazen hodnotu proměnné. Výchozí pro nové projekty je zapnuto.  
  
 ID: 42104, 42030  
  
### <a name="unused-local-variable-warning"></a>Nepoužívané místní proměnné upozornění  
 Generovány, pokud je deklarovaná ale nikdy označuje místní proměnné. Výchozí hodnota je na.  
  
 ID: 42024  
  
### <a name="access-of-shared-member-through-instance-variable-warning"></a>Přístup sdíleného člena prostřednictvím instance upozornění pro proměnné  
 Generuje při přístupu k sdíleného člena prostřednictvím instance může mít vedlejší účinky, nebo když přístup sdíleného člena prostřednictvím instance proměnné není pravé straně výrazu nebo je předáván jako parametr. Výchozí pro nové projekty je zapnuto.  
  
 ID: 42025  
  
### <a name="recursive-operator-or-property-access-warnings"></a>Rekurzivní operátor nebo vlastnost přístup upozornění  
 Generovány, pokud text rutinu, která používá stejnou operátor nebo vlastnost, kterou je definována v. Výchozí pro nové projekty je zapnuto.  
  
 ID: 42004 (operátor), 42026 (vlastnost)  
  
### <a name="function-or-operator-without-return-value-warning"></a>Funkce nebo operátor bez vrátit hodnotu upozornění  
 Generovány, pokud funkce nebo operátor nemá návratovou hodnotu zadat. To zahrnuje vynechání `Set` implicitní místní proměnné se stejným názvem jako funkce. Výchozí pro nové projekty je zapnuto.  
  
 ID: 42105 (funkce), 42016 (operátor)  
  
### <a name="overloads-modifier-used-in-a-module-warning"></a>Modifikátor přetížení použitý v modulu upozornění  
 Generuje při `Overloads` je používán `Module`. Výchozí pro nové projekty je zapnuto.  
  
 ID: 42028  
  
### <a name="duplicate-or-overlapping-catch-blocks-warnings"></a>Duplicitní nebo překrývající se catch – bloky upozornění  
 Vygeneruje, když `Catch` bloku je přístupný z důvodu jeho vztahu k jiné `Catch` bloky, které byly definovány. Výchozí pro nové projekty je zapnuto.  
  
 ID: 42029, 42031  
  
## <a name="see-also"></a>Viz také  
 [Typy chyb](/dotnet/visual-basic/programming-guide/language-features/error-types)   
 [Try... Catch... Finally – příkaz](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn)   
 [/warnaserror (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/warnaserror)   
 [Stránka kompilovat, Návrhář projektu (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Upozornění kompilátoru, která jsou ve výchozím nastavení vypnuté](/cpp/preprocessor/compiler-warnings-that-are-off-by-default)