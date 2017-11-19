---
title: "Zkontrolujte proměnné v automobily a místní hodnoty – Windows | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 04/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.autos
- vs.debug.locals
helpviewer_keywords:
- debugger, variable windows
- debugging [Visual Studio], variable windows
ms.assetid: bb6291e1-596d-4af0-9f22-5fd713d6b84b
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2504807bd4717ec7f42ed059e7ef4d962c7441e4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="inspect-variables-in-the-autos-and-locals-windows-in-visual-studio"></a>Zkontrolovat proměnné v automobily a místní hodnoty – Windows v sadě Visual Studio
**Automobily** okno (při ladění, **CTRL + ALT + V, A**, nebo **ladění > Windows > automobily**) a **místní hodnoty –** okno (při ladění **CTRL + ALT + V, L**, nebo **ladění > Windows > místní hodnoty –**) jsou velmi užitečné, pokud chcete zobrazit hodnoty proměnné při ladění. **Místní hodnoty –** okno zobrazí proměnné, které jsou definovány v místní obor, což je obecně funkce nebo metoda, která je aktuálně spouštěna. **Automobily** okno se zobrazí proměnné používá kolem aktuálního řádku (místo, kde je zastavena ladicího programu). Přesně které proměnné zobrazení v tomto okně se liší v různých jazycích. V tématu [proměnné, které se zobrazí v okně automobily?](#bkmk_whatvariables) níže.  
  
Pokud potřebujete další informace o základní ladění, přečtěte si [Začínáme s ladicím programem](../debugger/getting-started-with-the-debugger.md).  
  
## <a name="looking-at-objects-in-the-autos-and-locals-windows"></a>Prohlížení objekty v systému windows automobily a lokální proměnné  
Pole a objekty jsou zobrazeny v systému windows automobily a místní hodnoty jako ovládacích prvků strom. Klikněte na šipku nalevo od názvu proměnné rozbalte zobrazení zobrazit pole a vlastnosti. Tady je příklad [FileStream](http://msdn.microsoft.com/Library/a8737776-e545-4867-91ed-51c7f031fa19) objekt v **místní hodnoty –** okno:  
  
![Místní hodnoty – & č. 45; FileStream](../debugger/media/locals-filestream.png "FileStream lokální proměnné")  
  
## <a name="bkmk_whatvariables"></a>Jaké proměnné se zobrazí v okně Automatické hodnoty?  
 Můžete použít **automobily** okno v kódu jazyka C#, Visual Basic a C++. **Automobily** okno nepodporuje jazyk JavaScript a F #.  
  
 V jazyce C# a Visual Basic **automobily** okně se zobrazí všechny proměnné použít na aktuální nebo předchozí řádek. Pokud například deklarovat čtyři proměnné a jejich nastavení následujícím způsobem:

```CSharp
    public static void Main()
    {
       int a, b, c, d;
       a = 1;
       b = 2;
       c = 3;
       d = 4;
    }
```

 Pokud nastavíte bod přerušení na řádku `c = 3`; a spusťte ladicí program, když se zastaví provádění **automobily** okno bude vypadat například takto:  

 ![Automatické hodnoty & č. 45; CSharp](../debugger/media/autos-csharp.png "automobily CSharp")  

 Všimněte si, že hodnota `c` je 0, protože řádek `c = 3` ještě nebyla spuštěna.  

 V jazyce C++ **automobily** okně se zobrazí proměnné používané aspoň tři řádky před aktuálního řádku (na řádku, kdy je zastavena spuštění). Pokud je deklarovat šesti proměnné:

```C++
    void main() {
        int a, b, c, d, e, f;
        a = 1;
        b = 2;
        c = 3;
        d = 4;
        e = 5;
        f = 6;
    }
```

 Pokud nastavíte bod přerušení na řádku `e = 5;` a spusťte ladicí program, když se zastaví provádění **automobily** okno bude vypadat například takto:  
  
 ![Automatické hodnoty & č. 45; Cplus](../debugger/media/autos-cplus.png "automobily Cplus")  
  
 Všimněte si, že proměnná e není inicializována, protože kód na řádku `e = 5;` ještě nebyla spuštěna.  
  
 Zobrazí se také návratové hodnoty funkce a metody za určitých okolností. V tématu [zobrazení návratových hodnot volání metod](#bkmk_returnValue) níže.  
  
##  <a name="bkmk_returnValue"></a>Zobrazení návratových hodnot volání metod  
 V rozhraní .NET a C++ kódu můžete zkontrolovat návratové hodnoty, když krok přes nebo mimo volání metody. Tato funkce je užitečná, pokud výsledek volání metody není uložen v místní proměnné, třeba když metoda se používá jako parametr nebo jako návratová hodnota jinou metodu.  
  
 Následující kód C# přidá vrácené hodnoty dvě funkce:  

```CSharp
static void Main(string[] args)  
{  
    int a, b, c, d;  
    a = 1;  
    b = 2;  
    c = 3;  
    d = 4;  
    int x = sumVars(a, b) + subtractVars(c, d);  
}  
  
private static int sumVars(int i, int j)  
{  
    return i + j;  
}  
  
private static int subtractVars(int i, int j)  
{  
    return j - i;  
}  
```

 Nastavit zarážky `int x = sumVars(a, b) + subtractVars(c, d);` řádku.  
  
 Spuštění ladění a při provádění dělí na první zarážky, stiskněte klávesu **F10 (Krokovat s přeskočením)**. Měli byste vidět následující **automobily** okno:  
  
 ![AutosReturnValueCSharp2](../debugger/media/autosreturnvaluecsharp2.png "AutosReturnValueCSharp2")  
  
## <a name="why-are-variable-values-sometimes-red-in-locals-and-autos-windows"></a>Proč jsou hodnoty proměnné někdy red v lokální a automobily windows?  
Můžete si všimnout, že hodnota proměnné je někdy red v **místní hodnoty –** a **automobily** systému windows. Toto jsou hodnoty proměnné, které se změnily od posledního vyhodnocení. Tato změna může být z předchozí relace, ladění, nebo protože byla hodnota změněna v okně.  
  
## <a name="changing-the-numeric-format-of-a-variable-window"></a>Změna numerického formátu oken okně proměnná  
Výchozí číselný formát je decimal, ale můžete ho změnit na hexadecimální. Klepněte pravým tlačítkem myši **místní hodnoty –** nebo **automobily** a vyberte **hexadecimální zobrazení**. Změna ovlivní všechny ladicího programu.  
  
## <a name="editing-a-value-in-a-variable-window"></a>Úpravy hodnotu v okně proměnná  
Můžete upravit hodnoty Většina proměnných, které se zobrazují v **automobily**, **místní hodnoty –**, **sledovat**, a **QuickWatch** systému windows. Informace o **sledovat** a **QuickWatch** windows, najdete v části [sledovat a QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md). Právě dvakrát klikněte na hodnotu, kterou chcete změnit a přidejte novou hodnotu.  
  
Výraz hodnoty, můžete zadat například `a + b`. Ladicí program přijme nejvíce platné výrazy jazyka.  
  
V nativním kódu C++ může mít pro kvalifikaci kontextu název proměnné. Další informace najdete v tématu [kontextu – operátor (C++)](../debugger/context-operator-cpp.md).  
 
Však postupujte opatrně při změně hodnoty. Mohlo dojít k některému z následujících problémů:  
  
-   Hodnocení některých výrazů může změnit hodnotu proměnné nebo jinak ovlivnit stav programu. Například vyhodnocení `var1 = ++var2` změní hodnotu `var1` a `var2`.  
  
     Výrazy, které mění data jsou uvedená tak, aby měl [vedlejší účinky](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\)), což může vést k neočekávaným výsledkům Pokud nejste vědět z nich. Ujistěte se, že rozumíte následky takové změny před jeho provedením.  
  
-   Úpravy hodnot s plovoucí desetinnou čárkou mohou díky převodu komponenty zlomku z desítkové do binární soustavy způsobit drobné nepřesnosti. I zdánlivě neškodné úpravy mohou v proměnné s plovoucí desetinnou čárkou způsobit změny některých nejméně významných bitů.  
  
## <a name="changing-the-window-context"></a>Změna kontextu okna  
Můžete použít **ladění umístění** nástrojů vyberte požadované funkce, vlákno nebo proces, který mění kontext pro proměnné systému windows. Nastavte zarážky a spuštění ladění. (Pokud se tento panel nástrojů nezobrazí, můžete ji povolit kliknutím v prázdné místo oblasti panelu nástrojů. Zobrazí seznam panelů nástrojů; Vyberte **ladění umístění**). Pokud je průchodu zarážkou, provádění zastaví a zobrazit nástrojů ladění umístění, které je dolní řádek na následujícím obrázku.
  
![DebugLocationToolbar](../debugger/media/debuglocationtoolbar.png "DebugLocationToolbar")   
  
## <a name="see-also"></a>Viz také  
 [Ladicího programu](../debugger/debugger-windows.md)
