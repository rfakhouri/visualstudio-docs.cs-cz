---
title: Používání atributu DebuggerDisplay | Microsoft Docs
ms.custom: ''
ms.date: 08/09/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerDisplay attribute
- DebuggerDisplayAttribute class
ms.assetid: f4eb7c76-af4e-493b-9ab6-9cb05949d9b3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 054e66914172447e96e2977f81985c52430af115
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34573242"
---
# <a name="using-the-debuggerdisplay-attribute"></a>Používání atributu DebuggerDisplay
[DebuggerDisplayAttribute – třída](/dotnet/api/system.diagnostics.debuggerdisplayattribute) ovládací prvky zobrazení objektu, vlastnost nebo pole v proměnnými ladicího programu. Tento atribut lze použít pro typy, delegáti, vlastnosti, pole a sestavení.  
  
 `DebuggerDisplay` Atribut má jeden argument, což je řetězec, který se zobrazí ve sloupci Hodnota pro instance typu. Tento řetězec může obsahovat složené závorky (`{` a `}`). Text v páru složených závorek je vyhodnocena jako pole, vlastnost nebo metoda.  
  
 Pokud má třídu překryté `ToString()` metoda, ladicí program používá metodu přepsaného místo výchozího `{<typeName>}`. Proto pokud můžete přepsat `ToString()` metoda, ladicí program používá metodu přepsaného místo výchozího`{<typeName>}`, a není nutné používat `DebuggerDisplay`. Pokud používáte obě, `DebuggerDisplay` atribut má přednost před přepsané `ToString()` metoda.  
  
 Jestli vyhodnotí tomto implicitní ladicího programu `ToString()` volání závisí na nastavení uživatele **nástroje / Možnosti / ladění** dialogové okno. Visual Basic neimplementuje tomto implicitní `ToString()` vyhodnocení.  
  
> [!IMPORTANT]
>  Pokud **zobrazit nezpracované struktura objektů ve windows proměnné** je zaškrtnuté políčko v **nástroje/Možnosti / ladění** dialogové okno, pak se `DebuggerDisplay` atribut je ignorován.  
  
 V následující tabulce jsou uvedeny některé možné použití `DebuggerDisplay` atribut a příklad výstupy.  
  
|Atribut|Výstup ve sloupci Hodnota|  
|---------------|------------------------------------------------|  
|`[DebuggerDisplay("x = {x} y = {y}")]`<br /><br /> Použít na typ s pole `x` a `y`.|`x = 5 y = 18`|  
|`[DebuggerDisplay("String value is {getString()}")]`Syntaxe parametru se může lišit mezi jazyky. Proto ho používejte dát pozor.|`String value is [5, 6, 6]`|  
  
 `DebuggerDisplay` Můžete také přijímat pojmenované parametry.  
  
|Parametry|Účel|  
|----------------|-------------|  
|`Name`, `Type`|Tyto parametry mají vliv **název** a **typ** sloupce proměnné systému windows. (Je možné je nastavit na řetězců pomocí stejnou syntaxi jako konstruktoru.) Nadměrnému používání těchto tyto parametry, nebo jejich používání nesprávně, může způsobit matoucí výstup.|  
|`Target`, `TargetTypeName`|Určuje cílový typ. Pokud atribut se používá na úrovni sestavení.|  
  
 Soubor autoexp.cs používá atributu DebuggerDisplay na úrovni sestavení. Soubor autoexp.cs Určuje výchozí rozšíření, které sada Visual Studio používá pro objekty .NET. Můžete zkontrolovat soubor autoexp.cs příklady použití atributu DebuggerDisplay, nebo můžete upravit a kompilaci souboru autoexp.cs Chcete-li změnit výchozí rozšíření. Ujistěte se, že zálohování souboru autoexp.cs před zahájením úprav.  
  
 Pokud chcete vytvořit autoexp.cs, otevřete si příkazový řádek vývojáře pro VS2015 a spusťte následující příkazy  
  
```  
cd <directory containing autoexp.cs>  
csc /t:library autoexp.cs  
```  
  
 Změny autoexp.dll bude být zachyceny v další relaci ladění.  
  
## <a name="using-expressions-in-debuggerdisplay"></a>Použití výrazů v DebuggerDisplay  
 Přestože je možné použít výraz obecné mezi složené závorky v atributu DebuggerDisplay, tento postup se nedoporučuje.  
  
 Výraz Obecné v DebuggerDisplay má implicitní přístup k `this` ukazatele pro aktuální instancí třídy na typ cíle. Výraz nemá přístup k aliasy, místní hodnoty nebo ukazatele. Pokud výraz odkazuje na vlastnosti, atributy na tyto vlastnosti nejsou zpracovány. Například kódu C# `[DebuggerDisplay("Object {count - 2}")]` by zobrazit `Object 6` Pokud pole `count` byl 8.  
  
 Použití výrazů v DebuggerDisplay může vést k následujícím problémům:  
  
-   Vyhodnocení výrazů je nejvíce náročná operace v ladicím programu a výraz vyhodnotí pokaždé, když se zobrazí. To může způsobit problémy s výkonem v krokování kódu. Složitý výraz, který slouží k zobrazení hodnot v kolekci nebo seznam například může být velmi pomalé po velký počet elementů.  
  
-   Vyhodnocovací filtr výrazů jazyka aktuální rámec zásobníku a ne vyhodnocování jazyk, ve kterém byl zadán výraz se vyhodnotí výrazy. To může způsobit nepředvídatelné výsledky, když jsou různé jazyky.  
  
-   Vyhodnocení výrazu, můžete změnit stav aplikace. Výraz, který nastaví hodnotu vlastnosti, například mění hodnoty vlastností v provádění kódu.  
  
 Jeden způsob, jak snížit možné problémy vyhodnocení výrazu je tak, že vytvoříte privátní vlastnost, která provede operaci a vrátí řetězec. Debuggerdisplay – atribut pak můžete zobrazit hodnotu tohoto privátní vlastnosti. Následující příklad implementuje tento vzor:  
  
```csharp  
[DebuggerDisplay("{DebuggerDisplay,nq}")]  
public sealed class MyClass   
{      
    public int count { get; set; }      
    public bool flag { get; set; }      
    private string DebuggerDisplay  
   {         
        get  
        {  
             return string.Format("Object {0}", count - 2);  
        }      
    }  
}  
```  
", Nq" příponu informuje vyhodnocovací filtr výrazů k odebrání uvozovky, při zobrazení konečná hodnota (nq = žádné uvozovky). 
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak používat `DebuggerDisplay`, společně s `DebuggerBrowseable` a `DebuggerTypeProxy`. Při zobrazení v okně proměnné ladicí program, jako **sledovat** okně vyvolá rozšíření, která vypadá takto:  
  
|**Jméno**|**Hodnota**|**Typ**|  
|--------------|---------------|--------------|  
|Key|"tři"|objekt {řetězec}|  
|Hodnota|3|objekt {int}|  
  
```csharp  
[DebuggerDisplay("{value}", Name = "{key}")]  
internal class KeyValuePairs  
{  
    private IDictionary dictionary;  
    private object key;  
    private object value;  
    public KeyValuePairs(IDictionary dictionary, object key, object value)  
    {  
        this.value = value;  
        this.key = key;  
        this.dictionary = dictionary;  
    }  
  
    public object Key  
    {  
        get { return key; }  
        set  
        {  
            object tempValue = dictionary[key];  
            dictionary.Remove(key);  
            key = value;  
            dictionary.Add(key, tempValue);  
        }  
    }  
  
    public object Value  
    {  
        get { return this.value; }  
        set  
        {  
            this.value = value;  
            dictionary[key] = this.value;  
        }  
    }  
}  
  
[DebuggerDisplay("{DebuggerDisplay,nq}")]  
[DebuggerTypeProxy(typeof(HashtableDebugView))]  
class MyHashtable  
{  
    public Hashtable hashtable;  
  
    public MyHashtable()  
    {  
        hashtable = new Hashtable();    
    }
    
    private string DebuggerDisplay    {        get { return "Count = " + hashtable.Count); }    }  
  
    private class HashtableDebugView  
    {  
        private MyHashtable myhashtable;  
        public HashtableDebugView(MyHashtable myhashtable)  
        {  
            this.myhashtable = myhashtable;  
        }  
  
        [DebuggerBrowsable(DebuggerBrowsableState.RootHidden)]  
        public KeyValuePairs[] Keys  
        {  
            get  
            {  
                KeyValuePairs[] keys = new KeyValuePairs[myhashtable.hashtable.Count];  
  
                int i = 0;  
                foreach (object key in myhashtable.hashtable.Keys)  
                {  
                    keys[i] = new KeyValuePairs(myhashtable.hashtable, key, myhashtable.hashtable[key]);  
                    i++;  
                }  
                return keys;  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Používání atributu DebuggerTypeProxy](../debugger/using-debuggertypeproxy-attribute.md)   
 [Vytvořit vlastní zobrazení spravovaných objektů](../debugger/create-custom-views-of-dot-managed-objects.md)   
 [Specifikátory formátu v jazyce C#](../debugger/format-specifiers-in-csharp.md)   
 [Rozšíření ladění pomocí atributů zobrazení ladicího programu](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)
