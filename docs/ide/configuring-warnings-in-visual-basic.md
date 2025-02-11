---
title: Konfigurace upozornění v jazyce Visual Basic
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- errors [Visual Basic], warnings
- run-time errors, warnings
- warnings, configuring
ms.assetid: 99cf4781-bd4d-47b4-91b9-217933509f82
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3ba037dd93c64fc15d8d540880d075ea7005685b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68924119"
---
# <a name="configuring-warnings-in-visual-basic"></a>Konfigurace upozornění v Visual Basic

[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Kompilátor obsahuje sadu upozornění na kód, který může způsobit chyby v době běhu. Tyto informace můžete použít k zápisu čisticího a rychlejšího kódu s méně chybami. Například kompilátor vytvoří upozornění, když se uživatel pokusí vyvolat člena nepřiřazené proměnné objektu, vrátit se z funkce bez nastavení návratové hodnoty nebo spustit `Try` blok s chybami v logice pro zachycení výjimek.

Někdy kompilátor poskytuje další logiku pro uživatele, aby se uživatel mohl soustředit na místo toho, aby se mohl zaměřit na úkol, nikoli na Předvídání možných chyb. V předchozích verzích systému [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]byla **možnost Option Strict** použita k omezení [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] další logiky, kterou poskytuje kompilátor. Konfigurace upozornění vám umožní omezit tuto logiku podrobněji na úrovni jednotlivých upozornění.

Můžete chtít přizpůsobit projekt a vypnout některá upozornění, která nejsou relevantní pro vaši aplikaci, a zároveň zapínat jiná upozornění na chyby. Tato stránka vysvětluje, jak zapnout a vypnout jednotlivá upozornění.

## <a name="turning-warnings-off-and-on"></a>Vypnutí a zapnutí upozornění
Existují dva různé způsoby konfigurace upozornění: můžete je nakonfigurovat pomocí **Návrháře projektu**, nebo můžete použít možnosti kompilátoru **/warnaserror** a **/nowarn** .

Na kartě **kompilovat** stránky **Návrháře projektu** můžete zapnout a vypnout upozornění. Zaškrtnutím políčka **Zakázat všechna upozornění** zakážete všechna upozornění. Pokud chcete považovat všechna upozornění za chyby, vyberte možnost **považovat všechna upozornění za chyby** . Některá jednotlivá upozornění je možné v zobrazené tabulce přepínat jako chyby nebo upozornění podle potřeby.

Pokud je **možnost Strict** nastavená na **vypnuto**, upozornění související s **možností Option Strict** nelze zpracovat nezávisle na sobě. Pokud je **možnost Strict** nastavená na **zapnuto**, jsou přidružená upozornění považována za chyby bez ohledu na jejich stav. Když je **možnost Strict** nastavená na **Custom** `/optionstrict:custom` zadáním příkazu v kompilátoru příkazového řádku, **možnost striktní** varování se dá zapnout nebo vypnout nezávisle.

Možnost příkazového řádku **/warnaserror** kompilátoru lze také použít k určení, zda jsou upozornění považována za chyby. Do této možnosti můžete přidat seznam oddělený čárkami a určit tak, která upozornění mají být považována za chyby nebo upozornění pomocí příkazu + nebo-. Následující tabulka popisuje možné možnosti.

|Možnost příkazového řádku|Určuje|
| - |---------------|
|`/warnaserror+`|Považovat všechna upozornění za chyby|
|`/warnsaserror`-|Nepovažujte za chyby jako upozornění. Toto nastavení je výchozí.|
|`/warnaserror+:<warning list``>`|Považovat specifická upozornění za chyby uvedené číslem ID chyby v seznamu r oddělené čárkami.|
|`/warnaserror-:<warning list>`|Nepovažujte specifická upozornění za chyby, která jsou uvedená číslem ID chyby v seznamu odděleném čárkami.|
|`/nowarn`|Nesestavovat upozornění.|
|`/nowarn:<warning list>`|Nesestavovat zadaná upozornění, uvedená číslem ID chyby v seznamu odděleném čárkami.|

Seznam upozornění obsahuje čísla ID chyby upozornění, která by měla být považována za chyby, které lze použít s možnostmi příkazového řádku pro zapnutí nebo vypnutí konkrétních upozornění. Pokud seznam upozornění obsahuje neplatné číslo, je hlášena chyba.

## <a name="examples"></a>Příklady
Tato tabulka příkladů argumentů příkazového řádku popisuje, co každý argument dělá.

|Argument|Popis|
|--------------|-----------------|
|`vbc /warnaserror`|Určuje, že všechna upozornění mají být považována za chyby.|
|`vbc /warnaserror:42024`|Určuje, že upozornění 42024 by mělo být považováno za chybu.|
|`vbc /warnaserror:42024,42025`|Určuje, že upozornění 42024 a 42025 by měla být považována za chyby.|
|`vbc /nowarn`|Určuje, že by neměla být hlášena žádná upozornění.|
|`vbc /nowarn:42024`|Určuje, že by se nemělo hlásit upozornění 42024.|
|`vbc /nowarn:42024,42025`|Určuje, že by se neměla hlásit upozornění 42024 a 42025.|

## <a name="types-of-warnings"></a>Typy upozornění
Následuje seznam upozornění, které můžete chtít považovat za chyby.

### <a name="implicit-conversion-warning"></a>Upozornění implicitního převodu
Vygenerováno pro instance implicitního převodu. Nezahrnují implicitní převody z vnitřního číselného typu na řetězec při použití `&` operátoru. Výchozí pro nové projekty jsou vypnuté.

ÚČET 42016

### <a name="late-bound-method-invocation-and-overload-resolution-warning"></a>Volání metody s pozdní vazbou a upozornění na rozlišení přetížení
Vygenerováno pro instance pozdní vazby. Výchozí pro nové projekty jsou vypnuté.

ÚČET 42017

### <a name="operands-of-type-object-warnings"></a>Operandy typu "Object" – upozornění
Vygenerováno, pokud dojde `Object` k operandům typu, které by vytvořily chybu s **možností Strict On**. Výchozí pro nové projekty jsou zapnuté.

ÚČET 42018 a 42019

### <a name="declarations-require-as-clause-warnings"></a>Deklarace vyžadují upozornění klauzule AS.
Vygenerováno při deklaraci proměnné, funkce nebo vlastnosti chybějící `As` klauzule by vytvořilo chybu s **možností Strict On**. Proměnné, které nemají přiřazený typ, se považují za typ `Object`. Výchozí pro nové projekty jsou zapnuté.

ÚČET 42020 (deklarace proměnné), 42021 (deklarace funkce) a 42022 (deklarace vlastnosti).

### <a name="possible-null-reference-exception-warnings"></a>Možná upozornění na výjimku null Reference
Vygenerováno při použití proměnné předtím, než jí byla přiřazena hodnota. Výchozí pro nové projekty jsou zapnuté.

ÚČET 42104, 42030

### <a name="unused-local-variable-warning"></a>Upozornění na nepoužitou místní proměnnou
Vygenerováno při deklaraci místní proměnné, ale nikdy se na ni neříká. Výchozí hodnota je zapnuto.

ÚČET 42024

### <a name="access-of-shared-member-through-instance-variable-warning"></a>Přístup ke sdílenému členu prostřednictvím upozornění na proměnnou instance
Vygenerováno při přístupu ke sdílenému členu prostřednictvím instance může mít vedlejší účinky nebo při přístupu ke sdílenému členu prostřednictvím proměnné instance není pravá strana výrazu nebo je předávána jako parametr. Výchozí pro nové projekty jsou zapnuté.

ÚČET 42025

### <a name="recursive-operator-or-property-access-warnings"></a>Rekurzivní operátor nebo upozornění na přístup k vlastnosti
Vygenerováno, když tělo rutiny používá stejný operátor nebo vlastnost, v níž je definována. Výchozí pro nové projekty jsou zapnuté.

ÚČET 42004 (operátor), 42026 (vlastnost)

### <a name="function-or-operator-without-return-value-warning"></a>Funkce nebo operátor bez upozornění na návratovou hodnotu
Vygenerováno v případě, že funkce nebo operátor nemá zadanou návratovou hodnotu. To zahrnuje vynechání `Set` pro implicitní místní proměnnou se stejným názvem jako funkce. Výchozí pro nové projekty jsou zapnuté.

ÚČET 42105 (funkce), 42016 (operátor)

### <a name="overloads-modifier-used-in-a-module-warning"></a>Modifikátor přetížení použitý v modulu upozornění
Vygenerováno při `Overloads` použití `Module`v. Výchozí pro nové projekty jsou zapnuté.

ÚČET 42028

### <a name="duplicate-or-overlapping-catch-blocks-warnings"></a>Duplicitní nebo překrývající se výstrahy catch Blocks
Vygenerováno `Catch` , když není blok nikdy dosažen z důvodu jeho vztahu `Catch` k jiným blokům, které byly definovány. Výchozí pro nové projekty jsou zapnuté.

ÚČET 42029, 42031

## <a name="see-also"></a>Viz také:

- [Typy chyb](/dotnet/visual-basic/programming-guide/language-features/error-types)
- [Zkusit... Zachytit... Finally – příkaz](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)
- [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn)
- [/warnaserror (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/warnaserror)
- [Stránka Kompilovat, Návrhář projektu (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md)
- [Upozornění kompilátoru, která jsou ve výchozím nastavení vypnutá](/cpp/preprocessor/compiler-warnings-that-are-off-by-default)