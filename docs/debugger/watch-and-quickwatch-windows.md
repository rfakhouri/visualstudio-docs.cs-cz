---
title: "Nastavovat sledování na proměnné v sadě Visual Studio | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 04/04/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.watch
helpviewer_keywords:
- debugging [Visual Studio], Watch window
- expressions [debugger], evaluating
- variables [debugger], evaluating
- expression evaluation
- registers, evaluating
- debugging [Visual Studio], expression evaluation
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0f5c518becd09f6b94fb598975caa913d150ac2a
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="set-a-watch-on-variables-using-the-watch-and-quickwatch-windows-in-visual-studio"></a>Nastavovat sledování na proměnné pomocí sledování a QuickWatch Windows v sadě Visual Studio
Při ladění, můžete použít **sledovat** a **QuickWatch** windows si chcete přehrát proměnné a výrazy.  Rozdíl je, že **sledovat** okno může zobrazit několika proměnných, při **QuickWatch** okno zobrazí jednu proměnnou najednou. 

Windows jsou k dispozici pouze během relace ladění. Otevřete **sledovat** okně zvolte **ladění > Windows > sledovat > sledování (1, 2, 3, 4)**). Chcete-li otevřít **QuickWatch** okně buď klikněte pravým tlačítkem na proměnnou a zvolte **QuickWatch** nebo zvolte **ladění > QuickWatch**.
  
## <a name="observing-a-single-variable-with-quickwatch"></a>Sledování jednu proměnnou s QuickWatch  
 Můžete použít **QuickWatch** okno sledovat jednu proměnnou. Například pokud máte následující kód:  
  
```CSharp
static void Main(string[] args)  
{  
    int a, b;  
    a = 1;  
    b = 2;  
    for (int i = 0; i < 10; i++)  
    {  
        a = a + b;  
    }   
}  
```  
  
 Proměnné v okně QuickWatch můžete sledovat následujícím způsobem:  
  
1.  Nastavit zarážky `a = a + b;` řádku.  
  
2.  Spusťte ladění. Provádění zastaví u zarážky.  
  
3.  Otevřete **QuickWatch** okno (klikněte pravým tlačítkem na `a`, zvolte **QuickWatch**, nebo vyberte `a` a stiskněte klávesu **SHIFT + F9**).

    Měli byste vidět proměnnou v **hodnoty** okno s hodnotou 1.

    ![QuickWatch Expression](../debugger/media/watchexpression.png "QuickWatchExpression")  

    Pokud chcete vyhodnotit výraz pomocí proměnné, přidejte výraz například `a + b` k **výraz** a klikněte na **přehodnocovat**. 
  
4.  Přidat proměnnou **sledovat** okna z **QuickWatch** kliknutím **Přidat kukátko**. 

    > [!NOTE]
    > **QuickWatch** okno je modální dialogové okno, takže nemůže pokračovat, ladění, dokud je otevřený.  
  
5.  Zavřít **QuickWatch** okno. Teď můžete pokračovat v ladění při zjistíte hodnotu v **sledovat** okno.  
  
## <a name="observing-variables-with-the-watch-window"></a>Sledování proměnné s okno kukátka  
 Můžete sledovat několika proměnných **sledovat** okno. Například pokud máte následující kód:  
  
```C++  
int main()
{
    int a, b, c;
    a = 1;
    b = 2;
    c = 0;

    for (int i = 0; i < 10; i++)
    {
        a++;
        b *= 2;
        c = a + b;
    }

    return 0;
}
  
```  
  
 Přidejte hodnoty proměnných tři do okna kukátka následujícím způsobem:  
  
1.  Nastavit zarážky `c = a + b;` řádku.  
  
2.  Spuštění ladění (**F5**). Provádění zastaví u zarážky.  
  
3.  Otevřete okno kukátka (**ladění > Windows > sledovat > sledovat 1**, nebo **CTRL + ALT + W, 1**).  
  
4.  Přidat `a` proměnné na první řádek, `b` proměnné na druhý řádek a `c` proměnné na třetí řádek.

    Proměnné můžete přidat klepnutím na prázdný řádek a zadat název proměnné.
  
5.  Pokračovat, ladění (stiskněte **F11** posunut ladicího programu).  
  
 Měli byste vidět změna jako iteraci v rámci hodnoty proměnné `for` smyčky.  
  
 Pokud programujete v nativním kódu, může někdy potřebovat k určení kontextu název proměnné nebo výrazy, které obsahují název proměnné. Kontext je funkce, zdrojový soubor a modulu, kde se nachází na proměnnou. Pokud máte k vyfiltrování kontextu, můžete použít operátor syntaxe kontextu. Další informace najdete v tématu [kontextu – operátor (C++)](../debugger/context-operator-cpp.md).  
  
## <a name="observing-expressions-with-the-watch-window"></a>Sledování výrazy s okno kukátka  
 Nyní Pojďme výraz místo toho zkuste použít. Můžete přidat libovolný platný výraz rozpoznáno ladicího programu.  
  
 Například pokud máte kód uvedené v předchozí části, můžete získat průměr ze tří hodnot takto:  
  
 ![Watch Expression](../debugger/media/watchexpression.png "WatchExpression")  
  
 Obecně platí, pravidla pro vyhodnocení výrazů v **sledovat** okna jsou stejné jako pravidla pro vyhodnocení výrazů v jazyce kódování. Pokud výraz obsahuje chybu syntaxe, můžete očekávat ke stejné chybě kompilátoru, která zobrazí se v editoru kódu. Tady je příklad:  
  
 ![Watch Expression Error](../debugger/media/watchexpressionerror.png "WatchExpressionError")  
  
##  <a name="bkmk_refreshWatch"></a>Aktualizace hodnot sledování, které jsou zastaralé.  
 V některých případech může zobrazit aktualizace ikona (šipka cyklické) Pokud je výrazu vyhodnoceného v **sledovat** okno.  Například, pokud máte vyhodnocení vlastnosti vypnutý (**nástroje > Možnosti > ladění > povolit vyhodnocení vlastnosti a jiná volání funkce implicitní**), a máte následující kód:  
  
```CSharp  
static void Main(string[] args)  
{  
    List<string> list = new List<string>();  
    list.Add("hello");  
    list.Add("goodbye");  
}  
  
```  
  
 Pokud nastavovat sledování na `Count` vlastnost seznamu, měli byste vidět nějak takto:  
  
 ![RefreshWatch](../debugger/media/refreshwatch.png "RefreshWatch")  
  
 Předchozí obrázek zobrazuje chybu nebo hodnotu, která je zastaralá. Obecně můžete kliknutím na ikonu Aktualizovat hodnotu, ale v některých případech může nechcete obnovit. Nejdřív je potřeba vědět, proč nebyl vyhodnotit hodnotu.  
  
 Pokud nastavíte ukazatel myši na ikonu, popisek poskytuje informace o Proč tento výraz nebyl vyhodnocen.  Pokud se zobrazí circling šipky, tento výraz nebyl vyhodnocen pro jednu z následujících důvodů:  
  
-   Došlo k chybě, protože výraz byl vyhodnocovaný. Například pravděpodobně došlo k vypršení časového limitu, nebo proměnnou může byla mimo rozsah.  
  
-   Výraz obsahuje volání funkce, které může spustit vedlejším účinkem v aplikaci (viz [vedlejší efekty a výrazy](#bkmk_sideEffects)).  
  
-   Automatické vyhodnocování vlastností a volání funkce implicitní ladicím programem vypnutý (**nástroje > Možnosti > ladění > povolit vyhodnocení vlastnosti a jiná volání funkce implicitní**), a výraz nesmí být automaticky vyhodnotit.  
  
 Chcete-li aktualizovat hodnotu, klikněte na ikonu aktualizace nebo stiskněte MEZERNÍK. Ladicí program se pokusí přehodnocovat výraz. Pokud se zobrazila ikonu aktualizace, protože Automatické vyhodnocení vlastností a jiná volání funkce implicitní byl vypnutý, můžete tento výraz vyhodnocen.  
  
 Pokud se zobrazí ikona, která je kruh dvě vlnovkami, které se podobají vláken, tento výraz nebyl vyhodnocen z důvodu potenciální závislosti mezi vlákny. Jinými slovy vyhodnocení kód vyžaduje jiná vlákna v dočasně spuštění vaší aplikace. Pokud jste v režimu pozastavení, zastaví se obvykle všechna vlákna ve vaší aplikaci. Povolení dalších podprocesů pro spuštění dočasně může mít neočekávané dopad na stav vašeho programu a způsobí, že ladicí program na události, jako je například zarážky a výjimky vydané v těchto vláknech ignorovat.  
  
##  <a name="bkmk_sideEffects"></a>Vedlejší efekty a výrazy  
 Hodnocení některých výrazů může změnit hodnotu proměnné nebo jinak ovlivnit stav programu. Například následující výraz vyhodnocení změní hodnotu `var1`:  
  
```  
var1 = var2  
```  
  
 Tento kód může způsobit [vedlejším účinkem](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\)). Vedlejší efekty můžete provést ladění obtížnější změnou s používáním vašeho programu.  
  
 Vyhodnotí výraz, který má vedlejší účinky jen jednou, když poprvé vstoupíte ho. Následné hodnocení jsou zakázány. Toto chování můžete přepsat ručně kliknutím na ikonu aktualizace, který se zobrazí vedle hodnota.  
  
 Chcete-li vypnout automatické funkce vyhodnocení je možné vyhnout všechny vedlejší efekty (**nástroje > Možnosti > ladění > povolit vyhodnocení vlastnosti a další funkce implicitní volání**).  
  
 Při vyhodnocení vlastnosti nebo volání funkce implicitní je vypnutý, můžete vynutit vyhodnocení pomocí **ac** formátu – modifikátor (pro jazyk C# pouze). V tématu [specifikátory v jazyce C# formátu](../debugger/format-specifiers-in-csharp.md).  
  
## <a name="bkmk_objectIds"></a>Pomocí ID objektů v okně sledovat (C# a Visual Basic)  

 Existují situace, kdy chcete pozorovat chování určitého objektu. Můžete například chtít sledovat objekt odkazuje místní proměnné po tuto proměnnou byla mimo rozsah. V jazyce C# a Visual Basic můžete vytvořit ID pro určité instance odkazové typy objektů a použít je v okně sledovat a v zarážek podmínky. ID objektu je generované common language runtime (CLR) ladění služeb a přidružená k objektu.  
  
> [!NOTE]
>  ID objektu vytvořte slabé odkazy a nezabrání objekt se uvolnění z paměti. Jsou platné pouze pro aktuální relaci ladění.  
  
 Následující kód vytvoří jednu metodu `Person` pomocí místní proměnné, ale chcete zjistit, co `Person`na název se jinou metodu:  
  
```CSharp  
class Person  
{  
    public Person(string name)  
    {  
        Name = name;  
    }  
    public string Name { get; set; }  
}  
  
public class Program  
{  
    List<Person> _people = new List<Person>();  
    public static void Main(string[] args)  
    {  
        MakePerson();  
        DoSomething();  
    }  
  
    private static void MakePerson()  
    {  
        var p = new Person("Bob");  
        _people.Add(p);  
    }  
  
    private static void DoSomething()  
    {  
        // more processing  
         Console.WriteLine("done");  
    }  
}  
  
```  
  
 Můžete přidat odkaz na daný `Person` objekt v **sledovat** okno následujícím způsobem:  
  
1.  Nastavte zarážky v kódu delší dobu, po vytvoření objektu.  
  
2.  Spuštění ladění a při spuštění, zastavení v zarážce, najděte proměnné v **místní hodnoty –** okně pravým tlačítkem a vyberte **Zkontrolujte ID objektu**.  
  
3.  Měli byste vidět  **$**  plus číslo **místní hodnoty –** okna, která reprezentuje ID objektu.  
  
4.  Přidejte do okna kukátka ID objektu.  
  
5.  Nastavte zarážky, kde chcete pozorovat chování objektu.  V předchozí kód, který by byl v `DoSomething()` metoda.  
  
6.  Pokračovat, ladění a při spuštění zastaví v `DoSomething()` metody **sledovat** v okně se zobrazí `Person` objektu.  
  
> [!NOTE]
>  Pokud chcete zobrazit vlastnosti objektu, například `Person.Name` v předchozím příkladu musí mít povoleno vyhodnocení vlastnosti.  
  
## <a name="using-registers-in-the-watch-window-c-only"></a>Pomocí registruje v okně sledovat (pouze C++)  
 Pokud jsou ladění nativního kódu, můžete přidat názvy registrace, jakož i názvy proměnných pomocí  **$ \<zaregistrovat název >** nebo  **@ \<zaregistrovat název >**.  Další informace najdete v tématu [Pseudovariables](../debugger/pseudovariables.md).  
  
## <a name="dynamic-view-and-the-watch-window"></a>Dynamické zobrazení a okno kukátka  
 Některé skriptovací jazyky (například JavaScript nebo Python) použít dynamické nebo [kachní zadáním](https://en.wikipedia.org/wiki/Duck_typing), a jazyky rozhraní .NET (ve verzi 4.0 a novější) podporují objekty, které je obtížné sledovat pomocí normální ladění systému windows, protože jejich může mít runtime vlastnosti a metody, které nelze zobrazit.  
  
 Pokud okno kukátka zobrazí objektu vytvořeny z typ, který implementuje [IDynamicMetaObjectProvider rozhraní](/dotnet/api/system.dynamic.idynamicmetaobjectprovider?view=netframework-4.7), ladicí program přidá speciální **dynamického zobrazení** uzlu **automobily**  zobrazení. Tento uzel obsahuje dynamické členy dynamický objekt, ale neumožňuje úpravu hodnoty členů.  
  
 Pokud kliknete pravým tlačítkem na všechny podřízené z **dynamického zobrazení** a zvolte **Přidat kukátko**, ladicí program vloží novou proměnnou sledovat který vrhá objekt pro dynamický objekt. Jinými slovy **název objektu** stane (**(dynamických) objektů). Název**.  
  
 Vyhodnocení členů **dynamického zobrazení** může mít vedlejší účinky. Vysvětlení, co jsou vedlejší účinky, najdete v článku [vedlejší efekty a výrazy](#bkmk_sideEffects). Pro jazyk C#, ladicího programu není přehodnocovat automaticky hodnoty zobrazené v **dynamického zobrazení** při krok na nový řádek kódu. V jazyce Visual Basic výrazy přidány prostřednictvím **dynamického zobrazení** jsou automaticky aktualizovat.  
  
 Pokyny o tom, jak aktualizovat hodnoty dynamického zobrazení najdete v tématu [aktualizace sledovat hodnoty, které jsou zastaralé](#bkmk_refreshWatch).  
  
 Pokud chcete zobrazit jenom **dynamického zobrazení** pro objekt, můžete použít **dynamické** formátovací řetězec:  
  
-   C#: **ObjectName, dynamické**  
  
-   Visual Basic:: **$dynamic ObjectName**  
  
 **Dynamického zobrazení** rovněž vylepšuje možnosti ladění COM – objekty. Pokud ladicí program nalezne objekt COM uzavřen do **System.__ComObject**, přidá **dynamického zobrazení** uzel pro objekt.  
  
## <a name="see-also"></a>Viz také  
 [Ladicího programu](../debugger/debugger-windows.md)
