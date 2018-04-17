---
title: Zkoumání hranice | Nástroj pro testování Microsoft IntelliTest Developer | Microsoft Docs
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Exploration bounds
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: f152f128fed04abee44ca8c57c89b9f1c2f12ae6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="exploration-bounds"></a>Zkoumání hranice

**PexSettingsAttributeBase** je abstraktní základní třída pro rozsah nastavení jako atributy. V tématu [nastavení vodopádu](settings-waterfall.md) přehled nastavení v IntelliTest.

Nastavení můžete upravit pomocí pojmenovaných vlastností tohoto a jeho odvozené atributy:

```
[PexClass(MaxRuns = 10)]
public partial class FooTest {...}
```

* **Omezení řešení hranice**
  * [MaxConstraintSolverTime](#maxconstraintsolvertime) -počet sekund [Řešitel omezení](input-generation.md#constraint-solver) má ke zjištění vstupních hodnot, které způsobí, že provádění nové a jinou cestu k provést.
  * [MaxConstraintSolverMemory](#maxconstraintsolvermemory) – velikost v megabajtech, [Řešitel omezení](input-generation.md#constraint-solver) může použít ke zjištění vstupy.<p />
* **Zkoumání cesta hranice**
  * [MaxBranches](#maxbranches) – maximální počet větví, které mohou být přijata podél jednoho spuštění cesty.
  * [MaxCalls](#maxcalls) – maximální počet volání provedené během jednoho spuštění cestu.
  * [MaxStack](#maxstack) -maximální velikost zásobníku kdykoli během jednoho spuštění cestu, měřeno jako počet snímků aktivního volání.
  * [MaxConditions](#maxconditions) – maximální počet podmínky přes vstupních hodnot, které během jednoho spuštění cesta se může ověřit.<p />
* **Zkoumání hranice**
  * [MaxRuns](#maxruns) – maximální počet spuštění, které se pokusí během zkoumání.
  * [MaxRunsWithoutNewTests](#maxrunswithoutnewtests) – maximální počet po sobě jdoucích běží bez nový test se vygenerované.
  * [MaxRunsWithUniquePaths](#maxrunswithuniquepaths) – maximální počet spustí s jedinečný provádění cesty, které se pokusí během zkoumání.
  * [MaxExceptions](#maxexceptions) – maximální počet výjimky, které lze najít pro kombinaci všechny zjištěné provádění cesty.<p />
* **Nastavení generování kódu sady testů**
  * [TestExcludePathBoundsExceeded](#testexcludepathboundsexceeded) – Pokud je to pravda, provádění cesty, které překročit žádné hranice cesta ([MaxCalls](#maxcalls), [MaxBranches](#maxbranches), [MaxStack](#maxstack), [ MaxConditions](#maxconditions)) se ignorují.
  * [TestEmissionFilter](#testemissionfilter) -Určuje, které okolností by měl IntelliTest emitování testy.
  * [TestEmissionBranchHits](#testemissionbranchhits) -Určuje, kolik testů IntelliTest vysílá.

<a name="maxconstraintsolvertime"></a>
## <a name="maxconstraintsolvertime"></a>MaxConstraintSolverTime

Počet sekund [Řešitel omezení](input-generation.md#constraint-solver) má k výpočtu vstupních hodnot, které způsobí, že cesta spuštění nové a jiné mají být provedeny. To je možnost z **PexSettingsAttributeBase** a jeho odvozených typů.

Čím hlouběji této IntelliTest jsou zde popsány cesty spuštění programu, složitější stát omezení systémy, které IntelliTest sestavení z toku řízení a tok dat programu. V závislosti na vaší časového omezení můžete nastavit tuto hodnotu umožňující IntelliTest provést více nebo méně času cesty zjišťování nové spuštění.

Z důvodu pro vypršení časového limitu je obvykle IntelliTest se snaží najít řešení pro systém omezení, která nemá řešení, ale nemá žádné informace o této skutečnosti. Vzhledem k tomu, že toto je nejběžnější případ vypršení časového limitu, nemusí mít smysl zvýšit hranice.

<a name="maxconstraintsolvermemory"></a>
## <a name="maxconstraintsolvermemory"></a>MaxConstraintSolverMemory

Počet MB, [Řešitel omezení](input-generation.md#constraint-solver) má k výpočtu vstupních hodnot, které způsobí, že cesta spuštění nové a jiné mají být provedeny. To je možnost z **PexSettingsAttributeBase** a jeho odvozených typů.

Jsou zde popsány podrobněji IntelliTest cesty spuštění programu, tím složitější stát omezení systémy, které IntelliTest sestavení z toku řízení a tok dat programu. V závislosti na dostupné paměti v počítači můžete nastavit tuto hodnotu umožňující IntelliTest pro řešení složitější systémy omezení.

Z důvodu pro vypršení časového limitu je obvykle IntelliTest se snaží najít řešení pro systém omezení, která nemá řešení, ale nemá žádné informace o této skutečnosti. Vzhledem k tomu, že toto je nejčastější příčina situaci nedostatku paměti, nemusí mít smysl zvýšit hranice.

<a name="maxbranches"></a>
## <a name="maxbranches"></a>MaxBranches

Maximální počet větví, které mohou být přijata podél jednoho spuštění cesty.

Motivace za tento zkoumání vázaný je omezit délku žádné provádění cestu, která IntelliTest prozkoumá během [vstupní generování](input-generation.md). Konkrétně zabraňuje IntelliTest stal reagovat, pokud program přejde do nekonečné smyčce.

Každé větve podmíněného a nepodmíněné spuštění a sledované kódu se počítá směrem tento limit, včetně větve, které nezávisí na vstupy parametrizované testu.

Například následující kód využívá větve v pořadí 100:

```
for (int i=0; i<100; i++) { }
```

<a name="maxcalls"></a>
## <a name="maxcalls"></a>MaxCalls

Maximální počet volání provedené během jednoho spuštění cestu.

Motivace za tento zkoumání vázaný je omezit délku žádné provádění cestu, která IntelliTest prozkoumá během [vstupní generování](input-generation.md). Konkrétně zabraňuje IntelliTest stal reagovat, pokud program volá rekurzivní metoda libovolný počet dobu, což by způsobilo přetečení zásobníku, která IntelliTest nelze obnovit z.

Každé volání (přímé, nepřímé, virtuální, přechod) ke spuštění a sledované kódu se počítá směrem toto omezení.

<a name="maxstack"></a>
## <a name="maxstack"></a>MaxStack

Maximální velikost zásobníku kdykoli během jednoho spuštění cestu, počet snímků aktivního volání.

Motivace za tento zkoumání vázaný je k omezení velikosti zásobníku žádné provádění cestu, která IntelliTest prozkoumá během [vstupní generování](input-generation.md). Konkrétně ho nemohou IntelliTest používat všechny dostupné zásobníku místa, což by způsobilo přetečení zásobníku, která IntelliTest nelze obnovit z.

<a name="maxconditions"></a>
## <a name="maxconditions"></a>MaxConditions

Číslo emaximum podmínek přes vstupních hodnot, které během jednoho spuštění cesta se může ověřit.

Motivace za tento zkoumání vázaný je omezit složitosti žádné provádění cestu, která IntelliTest prozkoumá během [vstupní generování](input-generation.md). Každý struktura, která závisí na vstupy parametrizované testu se počítá směrem toto omezení.

Každá cesta zahrnovat následující kód například využívá n + 1 podmínky:

```
[PexMethod]
void ParameterizedTest(int n) 
{
     for (int i=0; i<n; i++) { // conditions are "0<n", "1<n", ..., "!(n<n)"
          ...
     }
     for (int i=0; i<100; i++) { // irrelevant for MaxConditions, since conditions do not depend on input
          ...
     }
}
```

<a name="maxruns"></a>
## <a name="maxruns"></a>MaxRuns

Tý emaximum počet spuštění, které IntelliTest pokusí během průzkum testu.

Motivace za tento zkoumání vázaný je jakýkoli kód, který bude obsahovat smyčky nebo rekurze může mít libovolný počet spuštění cesty, a proto musí být omezená během IntelliTest [vstupní generování](input-generation.md). 

Dvě nastavení **MaxRuns** a **MaxRunsWithUniquePaths** souvisejí s následujícím způsobem: 

* IntelliTest bude volat metodu parametrizované testovací až **MaxRuns** časy se jiný testovací vstupy.
* Pokud spuštěného kódu je deterministická, bude se IntelliTest trvat cestu k provádění různých pokaždé, když. 
  Za určitých podmínek však může spustit kód podle cesta k provádění, která již přijal před, s různými vstupy. 
* IntelliTest počty kolik jedinečný provádění cesty najde; Toto číslo je omezena **MaxRunsWithUniquePaths** možnost.

<a name="maxrunswithoutnewtests"></a>
## <a name="maxrunswithoutnewtests"></a>MaxRunsWithoutNewTests

Maximální počet po sobě jdoucích běží bez nový test se vygenerované.

Při IntelliTest často najdete mnoho zajímavé vstupy testovací během krátké doby, po chvíli ji nebude možné najít žádné další nové testování vstupy a bude generovat žádné další testy jednotek. Tato možnost konfigurace umístí vázaný na počet po sobě jdoucích pokusů, které může provádět IntelliTest bez generování nového testu. Po dosažení zastaví průzkum. 

<a name="maxrunswithuniquepaths"></a>
## <a name="maxrunswithuniquepaths"></a>MaxRunsWithUniquePaths

Maximální počet jedinečných cesty, které IntelliTest bude vhodné zvážit během zkoumání.

Motivace za tento zkoumání vázaný je, že žádný kód obsahující smyčky nebo rekurze může mít libovolný počet spuštění cesty, a proto musí být IntelliTest omezené během [vstupní generování](input-generation.md).

Dvě nastavení **MaxRuns** a **MaxRunsWithUniquePaths** souvisejí s následujícím způsobem: 

* IntelliTest bude volat metodu parametrizované testovací až **MaxRuns** časy se jiný testovací vstupy.
* Pokud spuštěného kódu je deterministická, bude se IntelliTest trvat cestu k provádění různých pokaždé, když. 
  Za určitých podmínek však může spustit kód podle cesta k provádění, která již přijal před, s různými vstupy. 
* IntelliTest počty kolik jedinečný provádění cesty najde; Toto číslo je omezena **MaxRunsWithUniquePaths** možnost.

<a name="maxexceptions"></a>
## <a name="maxexceptions"></a>MaxExceptions

Maximální počet výjimky, které může dojít k před zkoumání je zastaveno.

Motivace za tento zkoumání vázaný se ukončit zkoumání kódu, který obsahuje celou řadu chyb.
Pokud IntelliTest najde příliš mnoho chyb v kódu, zkoumání je zastavena.

<a name="testexcludepathboundsexceeded"></a>
## <a name="testexcludepathboundsexceeded"></a>TestExcludePathBoundsExceeded

Provádění cesty, které překročí nakonfigurovanou cesta hranice [MaxCalls](#maxcalls), [MaxBranches](#maxbranches), [MaxStack](#maxstack), a [MaxConditions](#maxconditions) jsou ignorovány.

Motivace za tento zkoumání vázaný je řešení (pravděpodobně) neukončující testy. Když IntelliTest dosáhne zkoumání vázán, jako [MaxCalls](#maxcalls), [MaxBranches](#maxbranches), [MaxStack](#maxstack), nebo [MaxConditions](#maxconditions), předpokládá že test nebudou proces neukončující a později na nezpůsobí k přetečení zásobníku.
Takové testovacích případů může představovat problémy na jiných systémů testů a tento atribut poskytuje způsob, jak zabránit IntelliTest generování testovacích případů pro potenciálně neukončující procesy nebo testovacích případů, které způsobí, že k přetečení zásobníku.

<a name="testemissionfilter"></a>
## <a name="testemissionfilter"></a>TestEmissionFilter

Označuje typy testů, které by měl emitování IntelliTest. Možné hodnoty jsou:

* **Všechny** -emitování testy pro vše, včetně předpokladů porušení.
* **FailuresAndIncreasedBranchHits** (výchozí) – emitování testů pro všechny chyby při jedinečný, a kdykoli testovacího případu zvyšuje pokrytí řízený [TestEmissionBranchHits](#testemissionbranchhits).
* **FailuresAndUniquePaths** – emitování testů pro všechny chyby IntelliTest najde, a také pro každý vstupní testu, která způsobí jedinečný provádění cestu.
* **Selhání** -emitování testy pouze chyby.

<a name="testemissionbranchhits"></a>
## <a name="testemissionbranchhits"></a>TestEmissionBranchHits

V závislosti na aktuální [TestEmissionFilter](#testemissionfilter) nastavení, IntelliTest vydá nové testovacích případů při pokrývaly větve v programu, který nebyl před zahrnuté.

**TestEmissionBranchHits** nastavení určuje, pokud IntelliTest právě zvažte, zda byla na všech zahrnutých větve (**TestEmissionBranchHits = 1**), pokud se test pokrýt ho jednou nebo dvakrát ( **TestEmissionBranchHits = 2**), a tak dále.

**TestEmissionBranchHits = 1** způsobí velmi malé testovací sadu, která bude zahrnovat všechny větve IntelliTest může dosáhnout. Na konkrétní sadě testů také zahrnuje všechny základní bloky a příkazy, které bylo dosaženo. 

Výchozí hodnota pro tuto možnost je **TestEmissionBranchHits = 2**, který generuje více výrazovou testovací sadu, která je také lepší vhodnější zjišťování budoucí regrese chyb.

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
