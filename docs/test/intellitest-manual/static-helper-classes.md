---
title: "Statické pomocné třídy | Nástroj pro testování Microsoft IntelliTest Developer | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Static helper classes
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: fe4c855f9fad611dd1131997a86143523f51a80e
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="static-helper-classes"></a>Statické pomocné třídy

Poskytuje sadu statickou pomocnou třídu, která lze použít při vytváření IntelliTest [parametrizovaných testů částí](test-generation.md#parameterized-unit-testing):

* [PexAssume](#pexassume): slouží k definici předpoklady pro vstupy a jsou užitečné pro filtrování nežádoucího vstupy
* [PexAssert](#pexassert): jednoduchý assertion třídu pro použití, pokud vaše testovací framework neposkytuje jeden
* [PexChoose](#pexchoose): proud další testovací vstupních hodnot, které spravuje IntelliTest
* [PexObserve](#pexobserve): konkrétní hodnoty a optionaly v protokolech, ověřuje je generovaného kódu

Některé třídy umožňují komunikovat s modulem reasoning IntelliTest na nižší úrovně:

* [PexSymbolicValue](#pexsymbolicvalue): nástroje zkontrolovat nebo změnit symbolický omezení proměnné

<a name="pexassume"></a>
## <a name="pexassume"></a>PexAssume

Statická třída používaná k express předpoklady, například [předběžné podmínky](test-generation.md#precondition)v [parametrizovaných testů částí](test-generation.md#parameterized-unit-testing).
Metody této třídy lze filtrovat nežádoucího testovací vstupy.

Pokud předpokládané podmínku nemá pro některé test vstup **PexAssumeFailedException** je vyvolána výjimka. To způsobí, že test bez upozornění ignorovat.

**Příklad**

Nebude zvažte následující parametrizované test **j = 0**:

```
public void TestSomething(int i, int j) {
     PexAssume.AreNotEqual(j, 0);
     int k = i/j;
     ...
}
```

**Poznámky**

Výše uvedený kód je téměř ekvivalentní:

```
     if (j==0)
          return;
```

Kromě toho, že selhání **PexAssume** výsledkem žádné testovací případy. U **Pokud** příkaz IntelliTest generuje samostatné testovacího případu tak, aby pokrývalo **pak** větev **Pokud** příkaz.

**PexAssume** také obsahuje specialzed vnořené třídy pro předpoklady na řetězec, pole a kolekce.

<a name="pexassert"></a>
## <a name="pexassert"></a>PexAssert

Statická třída používaná k express kontrolní výrazy, například [vstupních](test-generation.md#postcondition)v [parametrizovaných testů částí](test-generation.md#parameterized-unit-testing).

Pokud uplatňovaná podmínku nemá pro některé test vstup **PexAssertFailedException** je vyvolána, což způsobí, že test selhání.

**Příklad**

Následující vyhodnotí, že je absolutní hodnotu celé kladné:

```
public void TestSomething(int i) {
     int j = Maths.Abs(i);
     PexAssert.IsTrue(j >= 0);
     ...
}
```

<a name="pexchoose"></a>
## <a name="pexchoose"></a>PexChoose

Statické třídy, která poskytuje pomocného vstupní hodnoty do testu, který lze použít k implementaci [parametry Mocks](input-generation.md#parameterized-mocks).

**PexChoose** třída nepomůže při určení, zda testu předá nebo pro konkrétní vstupní hodnoty se nezdaří. **PexChoose** jednoduše poskytuje vstupní hodnoty, které jsou také označovány jako *volby*. Je stále až uživatelské omezit vstupní hodnoty a zapsat kontrolní výrazy, které definují, kdy testovací předá nebo selže.

**Režimy provozu**

**PexChoose** třídy mohou pracovat ve dvou režimech:

* Při IntelliTest provádí symbolický analysis test a kód otestované během [vstupní generování](input-generation.md), nástroje připojení vrátí libovolné hodnoty a IntelliTest sleduje použití každé hodnoty v testu a otestované kód. IntelliTest vygeneruje příslušné hodnoty pro aktivaci cesty jiný provádění v test a otestované kód.

* Generovaný kód pro konkrétní testovací případy Nastaví zprostředkovatele volba určitým způsobem, tak, aby opětovné spuštění testovacího případu bude provést konkrétní možnosti pro aktivaci konkrétní provádění cestu.

**Využití**

* Jednoduché volání **PexChoose.Value** vygenerovat novou hodnotu:

```
public int Foo() {
    return PexChoose.Value<int>("foo");
}
```

<a name="pexobserve"></a>
## <a name="pexobserve"></a>PexObserve

Statické třídy do protokolu pojmenovaných hodnot.

Pokud jsou zde popsány IntelliTest kód, **PexObserve** se používá k zaznamenání počítaný hodnoty pomocí jejich vyjádření formátovaný řetězec. Hodnoty jsou přidruženy k jedinečné názvy.

```
PexObserve.Value<string>("result", result);
```

**Příklad**

```
// product code
public static class MathEx {
     public static int Square(int value) { return value * value; }
}


// fixture
[TestClass]
public partial class MathExTests {
     [PexMethod]
     public int SquareTest(int a) {
        int result = MathEx.Square(a); 
        // storing result
        return result;
     }
}
```

<a name="pexsymbolicvalue"></a>
## <a name="pexsymbolicvalue"></a>PexSymbolicValue

Statická třída používaná Ignorovat omezení parametrů a tisknout symbolické informace spojené s hodnotami.

**Využití**

Za normálních okolností IntelliTest pokusí nepokrývají všechny cesty provádění kódu během provádění. Ale zejména v případě, že computing předpokladů a kontrolní výraz podmínky, by neměl prozkoumejte všechny možné případy.

**Příklad**

Tento příklad ukazuje implementaci **PexAssume.Arrays.ElementsAreNotNull** metoda. V metodě můžete ignorovat omezení na délce hodnota pole, aby se zabránilo IntelliTest pokusu o generování různé velikosti pole. Omezení se ignorují pouze sem. Pokud kód otestované pracuje odlišně pro různé pole délek, IntelliTest nelze generovat různých velikostí pole z omezení otestované kódu.

```
public static void AreElementsNotNull<T>(T[] value)
    where T : class
{
    PexAssume.NotNull(value);
    // the followings prevents the exploration of all array lengths
    int len = PexSymbolicValue.Ignore<int>(value.Length);

    // building up a boolean value as follows prevents exploration
    // of all combinations of non-null (instead, there are just two cases)
    bool anyNull = false;
    for (int i = 0; i < len; ++i)
        anyNull |= value[i] == null;

    // was any element null?
    if (anyNull)
        PexAssume.Fail("some element of array is a null reference");
}
```

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
