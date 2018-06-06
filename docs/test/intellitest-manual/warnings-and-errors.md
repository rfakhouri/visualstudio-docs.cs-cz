---
title: Chyby a varování | Nástroj pro testování Microsoft IntelliTest Developer
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: reference
helpviewer_keywords:
- IntelliTest, Warnings and errors
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 75cda2b45137d982038587ee1dcb73661b77f0df
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815792"
---
# <a name="warnings-and-errors"></a>Upozornění a chyby

## <a name="warnings-and-errors-by-category"></a>Upozornění a chyby podle kategorie

* **Hranice**
  * [MaxBranches překročen](#maxbranches-exceeded)
  * [MaxConstraintSolverTime překročen](#maxconstraintsolvertime-exceeded)
  * [MaxConditions překročen](#maxconditions-exceeded)
  * [MaxCalls překročen](#maxcalls-exceeded)
  * [MaxStack překročen](#maxstack-exceeded)
  * [MaxRuns překročen](#maxruns-exceeded)
  * [MaxRunsWithoutNewTests překročen](#maxrunswithoutnewtests-exceeded)<p />

* **Omezení řešení**
  * [Nelze upřesnění řešení](#cannot-concretize-solution)<p />

* **Domény**
  * [Potřebujete pomoc při sestavování objektu](#help-construct)
  * [Potřebujete další pomoc k vyhledání typů](#help-types)
  * [Použitelné typ uhádnout](#usable-type-guessed)<p />

* **Spuštění**
  * [Neočekávaná chyba při zkoumání](#unexpected-exploration)
  * [Targetinvocationexception –](#targetinvocationexception)<p />

* **Instrumentace**
  * [Uninstrumented metodu s názvem](#uninstrumented-method-called)
  * [Externí metodu s názvem](#external-method-called)
  * [Uninstrumentable metodu s názvem](#uninstrumentable-method-called)
  * [Testovatelnosti problém](#testability-issue)
  * [Omezení](#limitation)<p />

* **Překladač**
  * [Neshoda zjištěnou volání](#observed-call-mismatch)
  * [Hodnota uložená v statické pole](#value-static-field)

<a name="maxbranches-exceeded"></a>
## <a name="maxbranches-exceeded"></a>MaxBranches překročen

Délka cesty žádné spuštění, který je zde popsány během omezuje IntelliTest [vstupní generování](input-generation.md). Tato funkce zabraňuje IntelliTest stal reagovat, když se program dostane do nekonečné smyčce.

Každé větve podmíněného a nepodmíněné spuštění a sledované kódu se počítá směrem tento limit, včetně větve, které nezávisí na vstupy z [testování částí parametrizované](test-generation.md#parameterized-unit-testing).

Například následující kód využívá větve v pořadí 100:

```csharp
for (int i=0; i<100; i++) { }
```

Můžete upravit **MaxBranches** možnost atributu odvozené od **PexSettingsAttributeBase**, jako například [PexClass](attribute-glossary.md#pexclass) nebo [PexMethod](attribute-glossary.md#pexmethod) . Následující příklad odebere efektivně to vázaný:

```csharp
[PexMethod(MaxBranches=int.MaxValue)]
public void MyTest(...) {
    // ....
}
```

Můžete také nastavit **TestExcludePathBoundsExceeded** možnost k informování IntelliTest jak obecně k řešení těchto problémů.

V testovací kód, můžete použít [PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue) Ignorovat omezení vygenerovaných podmínku cyklu:

```csharp
for (int i=0; 
    PexSymbolicValue.Ignore(i<100); // IntelliTest will 'forget' about this path condition
    i++) 
{ }
```

<a name="maxconstraintsolvertime-exceeded"></a>
## <a name="maxconstraintsolvertime-exceeded"></a>MaxConstraintSolverTime překročen

Používá IntelliTest [Řešitel omezení](input-generation.md#constraint-solver) k výpočtu nový test vstupy. Omezení řešení může být časově velmi náročná proces, takže IntelliTest umožňuje nakonfigurovat hranice – konkrétně **MaxConstraintSolverTime**.

Mnoho aplikací výrazně zvýšit časový limit nebude mít za následek lepší pokrytí. Důvodem je, většina vypršení časových limitů jsou způsobeny omezení systémy, které mají žádná řešení. IntelliTest však nemusí být schopní určit, že je nekonzistentní bez pokusu o všechna možná řešení, které způsobí vypršení časového limitu.

<a name="maxconditions-exceeded"></a>
## <a name="maxconditions-exceeded"></a>MaxConditions překročen

Délka cesty žádné spuštění, který je zde popsány během omezuje IntelliTest [vstupní generování](input-generation.md). Tato funkce zabraňuje IntelliTest stal reagovat, když se program spustí nekonečnou smyčku.

Každý struktura, která závisí na vstupy z [testování částí parametrizované](test-generation.md#parameterized-unit-testing) se počítá směrem toto omezení.

Například každá cesta zahrnovat následující kód využívá **n + 1** podmínky:

```csharp
[PexMethod]
void ParameterizedTest(int n) {
    // conditions are "0<n", "1<n", ..., "!(n<n)"
    for (int i=0; i<n; i++)
    { ... }

    // irrelevant for MaxConditions, since conditions do not depend on input
    for (int i=0; i<100; i++) 
    { ... }
}
```

Můžete upravit **MaxConditions** možnost atributu odvozené od **PexSettingsAttributeBase**, jako například [PexClass](attribute-glossary.md#pexclass) nebo [PexMethod](attribute-glossary.md#pexmethod). Příklad:

```csharp
[PexMethod(MaxConditions=10000)]
void ParameterizedTest(int n) {
    // ...
}
```

Můžete také nastavit **TestExcludePathBoundsExceeded** možnost k informování IntelliTest postupy obecně řešení těchto problémů.

Můžete použít [PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue) Ignorovat omezení vygenerovaných podmínku cyklu:

```csharp
[PexMethod]
void ParameterizedTest(int n) {
    int nshadow = PexSymbolicValue.Ignore(n); // IntelliTest looses track of 'n'

    // irrevelant for MaxConditions, since nshadow is not related to input
    for (int i=0; i<nshadow; i++)  
    {...}
}
```

<a name="maxcalls-exceeded"></a>
## <a name="maxcalls-exceeded"></a>MaxCalls překročen

Délka cesty žádné spuštění, který je zde popsány během omezuje IntelliTest [vstupní generování](input-generation.md). Tato funkce zabraňuje IntelliTest stal reagovat, kdy přestane program spustí nekonečnou smyčku.

Každé volání (přímé, nepřímé, virtuální, nebo přejít) ke spuštění a sledované kódu se počítá směrem tento limit.

Můžete upravit **MaxCalls** možnost atributu odvozené od **PexSettingsAttributeBase**, jako například [PexClass](attribute-glossary.md#pexclass) nebo [PexMethod](attribute-glossary.md#pexmethod). Následující příklad odebere efektivně to vázaný:

```csharp
[PexMethod(MaxCalls=int.MaxValue)]
public void MyTest(...) {
    // ....
}
```

Můžete také nastavit **TestExcludePathBoundsExceeded** možnost k informování IntelliTest postupy obecně řešení těchto problémů.

<a name="maxstack-exceeded"></a>
## <a name="maxstack-exceeded"></a>MaxStack překročen

IntelliTest omezuje velikost zásobníku volání žádné provádění cesty, která je zde popsány během [vstupní generování](input-generation.md). Tato funkce zabraňuje IntelliTest ukončení, když dojde k přetečení zásobníku.

Můžete upravit **MaxStack** možnost atributu odvozené od **PexSettingsAttributeBase**, jako například [PexClass](attribute-glossary.md#pexclass) nebo [PexMethod](attribute-glossary.md#pexmethod). Následující příklad odebere efektivně tuto mez (nedoporučuje se):

```csharp
[PexMethod(MaxStack=int.MaxValue)]
public void MyTest(...) {
    // ....
}
```

Můžete také nastavit **TestExcludePathBoundsExceeded** možnost k informování IntelliTest postupy obecně řešení těchto problémů.

<a name="maxruns-exceeded"></a>
## <a name="maxruns-exceeded"></a>MaxRuns překročen

IntelliTest omezuje počet spuštění cesty, které se zde popsány během [vstupní generování](input-generation.md). Tato funkce zajišťuje, že IntelliTest ukončí, pokud program obsahuje smyčky nebo rekurze.

Nemusí být případ, že pokaždé, když IntelliTest používá parametrizované test s konkrétní vstupy, vysílá nového testovacího případu. V tématu [TestEmissionFilter](exploration-bounds.md#testemissionfilter) Další informace.

Můžete upravit **MaxRuns** možnost atributu odvozené od **PexSettingsAttributeBase**, jako například [PexClass](attribute-glossary.md#pexclass) nebo [PexMethod](attribute-glossary.md#pexmethod). Následující příklad odebere efektivně tuto mez (nedoporučuje se):

```csharp
[PexMethod(MaxRuns=2000)]
public void MyTest(...) {
    // ....
}
```

<a name="maxrunswithoutnewtests-exceeded"></a>
## <a name="maxrunswithoutnewtests-exceeded"></a>MaxRunsWithoutNewTests překročen

IntelliTest omezuje počet spuštění cesty, které se zde popsány během [vstupní generování](input-generation.md). Tato funkce zajišťuje, že IntelliTest ukončí, pokud program obsahuje smyčky nebo rekurze.

Nemusí být případ, že pokaždé, když IntelliTest používá parametrizované test s konkrétní vstupy, vysílá nového testovacího případu. V tématu [TestEmissionFilter](exploration-bounds.md#testemissionfilter) Další informace.

Při IntelliTest často najde mnoho zajímavé vstupy testovací původně, se může není – po chvíli - emitování žádné další testy. Tato možnost řídí, jak dlouho IntelliTest může nadále pokoušet najít další relevantní testovací vstup.

Můžete upravit **MaxRunsWithoutNewTests** možnost atributu odvozené od **PexSettingsAttributeBase**, jako například [PexClass](attribute-glossary.md#pexclass) nebo [PexMethod](attribute-glossary.md#pexmethod). Následující příklad odebere efektivně tuto mez (nedoporučuje se):

```csharp
[PexMethod(MaxRunsWithoutNewTests=2000)]
public void MyTest(...) {
    // ....
}
```

<a name="cannot-concretize-solution"></a>
## <a name="cannot-concretize-solution"></a>Nelze upřesnění řešení

Tato chyba je často důsledkem dřívější chybě. Používá IntelliTest [Řešitel omezení](input-generation.md#constraint-solver) určit nový test vstupy. V některých případech testování vstupy navrhovaná [Řešitel omezení](input-generation.md#constraint-solver) jsou neplatné. To může dojít, když:

* určitá omezení nejsou známá.
* Pokud jsou hodnoty vytvořen uživatelem definované způsobem, příčinou chyby v uživatelském kódu
* Některé typy související se situací mají inicializace logiku není řízené IntelliTest (například třídy COM)

<a name="help-construct"></a>
## <a name="need-help-to-construct-object"></a>Potřebujete pomoc při sestavování objektu

IntelliTest [generuje testovací vstupy](input-generation.md), a některých vstupních hodnot může být objektů s poli. Zde IntelliTest pokusí generovat instance třídy, která obsahuje pole, privátní a předpokládá, že zajímavé chování programu se stane, když tento soukromé pole má určitou hodnotu. 

Ale když to je možné pomocí reflexe, IntelliTest není výroby objektů s hodnotami libovolného pole. Místo toho v těchto případech se spoléhá na uživatele k zadání pomocných parametrů o tom, jak použít veřejné metody třídy k vytvoření objektu a převeďte ho do stavu, kde jeho soukromé pole má požadovanou hodnotu.

Čtení [vytváření instancí existujících tříd](input-generation.md#existing-classes) se dozvíte, jak může pomoci IntelliTest vytvořit zajímavé objekty. 

<a name="help-types"></a>
## <a name="need-help-to-find-types"></a>Potřebujete další pomoc k vyhledání typů

IntelliTest [generuje testovací vstupy](input-generation.md) pro jakýkoli typ rozhraní .NET. Zde IntelliTest se pokusí vytvořit instanci, která je odvozena z abstraktní třídy nebo implementuje abstraktní rozhraní a IntelliTest není znám žádný typ, který splňuje všechny požadavky. 

IntelliTest pomůžete tak, že odkazuje na jeden nebo více typů, které odpovídají omezení. Obvykle jednu z následujících atributů pomůže:

* **PexUseTypeAttribute**, který odkazuje na konkrétní typ.

  Například pokud IntelliTest hlásí, že IT oddělení "není znám všechny typy přiřaditelné k **System.Collections.IDictionary**", můžete ji připojením následující **PexUseTypeAttribute** k testovací (nebo k třídě přípojka):

  ```csharp
  [PexMethod]
  [PexUseType(typeof(System.Collections.Hashtable))]
  public void MyTest(IDictionary[] dictionaries) { ... }
  ```

* **Atribut úrovně sestavení**

  ```csharp
  [assembly: PexUseType(typeof(System.Collections.Hashtable))]
  ```

<a name="usable-type-guessed"></a>
## <a name="usable-type-guessed"></a>Použitelné typ uhádnout

IntelliTest [generuje testovací vstupy](input-generation.md) pro všechny typy .NET. Když se typ abstraktní nebo rozhraní, musíte zvolit IntelliTest konkrétní implementaci tohoto typu. Chcete-li tuto volbu, musí vědět, jaké typy neexistuje. 

Když se zobrazí toto upozornění, it indiicates, IntelliTest hledá na některé z odkazovaných sestaveních a najít typ implementace, ale není jisti, zda měla by používat typ, nebo pokud jsou vhodnější typy k dispozici jinde. IntelliTest jednoduše zvolit typ, který hledá Slíbení.

Aby se zabránilo toto upozornění, můžete buď přijmout IntelliTest na typ Volba nebo pomůže IntelliTest přidáním odpovídající pomocí jiné typy [PexUseType](attribute-glossary.md#pexusetype).

<a name="unexpected-exploration"></a>
## <a name="unexpected-failure-during-exploration"></a>Neočekávaná chyba při zkoumání

Při prohlížení testu byla zachycena neočekávanou výjimku.

Prosím [to hlásit jako chyby](#report-bug).

<a name="targetinvocationexception"></a>
## <a name="targetinvocationexception"></a>Targetinvocationexception –

V uživatelském kódu došlo k výjimce. Zkontrolujte trasování zásobníku a odebrat chybě ve vašem kódu.

<a name="uninstrumented-method-called"></a>
## <a name="uninstrumented-method-called"></a>Uninstrumented metodu s názvem

IntelliTest [generuje testovací vstupy](input-generation.md) systémem monitorování na spuštění programu. Je nutné příslušný kód je tak, aby IntelliTest můžete monitorovat své chování správně instrumentovány.

Toto upozornění se zobrazí, když kód instrumentovaného volá metody v jiné, uninstrumented sestavení. Pokud chcete IntelliTest prozkoumat interakce obou, musí také instrumentace jiné sestavení (nebo její části).

<a name="external-method-called"></a>
## <a name="external-method-called"></a>Externí metodu s názvem

IntelliTest [generuje testovací vstupy](input-generation.md) pomocí monitorování výkonu aplikací .NET. IntelliTest nelze vygenerovat smysluplný testovací vstupy pro kód, který není napsán v jazyce .NET.

Toto upozornění se zobrazí, když kód instrumentovaného volá metodu nespravované, nativní, která IntelliTest nelze analyzovat. Pokud chcete IntelliTest prozkoumat interakce obou, musí se model metodu nespravované.

<a name="uninstrumentable-method-called"></a>
## <a name="uninstrumentable-method-called"></a>Uninstrumentable metodu s názvem

IntelliTest [generuje testovací vstupy](input-generation.md) pomocí monitorování výkonu aplikací .NET. Existují však některé metody, že technických důvodů IntelliTest nelze monitorovat. Například IntelliTest nelze monitorovat statického konstruktoru.

Toto upozornění se zobrazí, když kód instrumentovaného volá metodu, která IntelliTest nelze monitorovat. 

<a name="testability-issue"></a>
## <a name="testability-issue"></a>Testovatelnosti problém

IntelliTest [generuje testovací vstupy](input-generation.md) systémem monitorování na spuštění programu. Vstupy relevantní testovací to může generovat jenom když deterministická program a při řídí chování relevantní testovací vstupy.

Toto upozornění se zobrazí proto, že během provádění testovacího případu, byla volána metoda buď chová nedeterministicky nebo komunikuje s prostředím. Příklady jsou metody **System.Random** a **System.IO.File**. Pokud chcete IntelliTest vytvořit smysluplný testovací vstupy, musí se model metody, které IntelliTest flags jako testovatelnosti problémy.

<a name="limitation"></a>
## <a name="limitation"></a>Omezení

IntelliTest [generuje testovací vstupy](input-generation.md) pomocí [Řešitel omezení](input-generation.md#constraint-solver).
Existují však některé operace, které jsou nad rámec [Řešitel omezení](input-generation.md#constraint-solver).
Aktuálně patří mezi ně:

* operace s nejvíce plovoucí desetinnou (jenom některé lineární aritmetické operace je podporována na plovoucí desetinnou čárkou)
* převody mezi čísla s plovoucí desetinnou a celá čísla
* všechny operace v **System.Decimal** typu

Toto upozornění se zobrazí při spuštění kódu provádí operaci, nebo volá metodu, která IntelliTest nemůže interpretovat. 

<a name="observed-call-mismatch"></a>
## <a name="observed-call-mismatch"></a>Neshoda zjištěnou volání

IntelliTest [generuje testovací vstupy](input-generation.md) systémem monitorování na spuštění programu. IntelliTest však nemusí být schopen monitorovat všechny pokyny. Například ho nelze monitorovat nativního kódu a kód, který není instrumentována ji nelze monitorovat.

Když IntelliTest nelze monitorovat kódu, nemůže generovat testovací vstupních hodnot, které jsou relevantní pro tento kód.
Často IntelliTest nemá informace o fakt metodu ji nelze monitorovat, dokud vrátí volání této metody. Příčinu toto upozornění je však:

* IntelliTest monitorovat některé kód, který spustil volání pro metodu uninstrumented
* Uninstrumented metoda volá metodu, která je instrumentovány
* IntelliTest monitoruje instrumentovaného metodu, která byla volána 

IntelliTest nebude vědět, co se uninstrumented zprostředkující metoda, proto nemusí být schopen generovat testovací vstupních hodnot, které jsou relevantní pro vnořené instrumentovaného volání.

<a name="value-static-field"></a>
## <a name="value-stored-in-static-field"></a>Hodnota uložená v statické pole

IntelliTest systematičtěji můžete určit [relevantní testovací vstupy](input-generation.md) pouze při testování jednotka je deterministická; jinými slovy, vždy chová stejným způsobem jako pro stejný testovací vstupy. Konkrétně to znamená, že test nechat systému ve stavu, který umožňuje znovu provést testu.
V ideálním případě testování částí neměli měnit žádný globální stav, ale všechny interakce s globals by měl být mocked.

Toto upozornění označuje, že byl změněn statické pole; To může být test chovat nedeterministicky.

V některých případech je přijatelné změna statického pole:

* Když způsobí, že testovací vstupy instalační program nebo čištění kód vrátit změnu
* Když toto pole je zahájeno pouze jednou, a hodnota nemění později

<a name="report-bug"></a>

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
