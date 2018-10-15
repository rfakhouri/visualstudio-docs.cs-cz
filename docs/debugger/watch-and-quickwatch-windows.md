---
title: Nastavení sledování u proměnných v sadě Visual Studio | Dokumentace Microsoftu
ms.custom: H1Hack27Feb2017
ms.date: 10/11/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad08799c0dce3792e096291dfaf62d52e2515df4
ms.sourcegitcommit: 48bc8492973e93612e5afaba3b47d0f98aecf97c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2018
ms.locfileid: "49325013"
---
# <a name="set-a-watch-on-variables-using-the-watch-and-quickwatch-windows-in-visual-studio"></a>Nastavení sledování u proměnných v oknech kukátka a Rychlé kukátko v sadě Visual Studio

Při ladění, můžete použít **Watch** a **QuickWatch** windows ke sledování proměnných a výrazů.  Rozdíl je, že **Watch** okno může zobrazit několik proměnných, zatímco **QuickWatch** okně zobrazí najednou jednu proměnnou.

Systému windows jsou k dispozici pouze během relace ladění. Otevřete **Watch** okně zvolte **ladění** > **Windows** > **Watch**a klikněte na tlačítko **Sledovat 1**, **sledovat 2**, **podívejte se na 3**, nebo **podívejte se 4**. Chcete-li otevřít **QuickWatch** okna, buď klikněte pravým tlačítkem na proměnnou a zvolte **QuickWatch**, nebo prostě vybrat **ladění** > **QuickWatch** .

## <a name="observe-variables-with-the-watch-window"></a>Sledujte proměnné okno kukátka

Můžete sledovat více než jednu proměnnou s **Watch** okna. Pokud například máte následující kód:

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

Hodnoty, přidejte do tří proměnných **Watch** okno následujícím způsobem:

1. Vyberte `c = a + b;` řádku.

2. Nastavení zarážky (výběrem **ladění** > **Přepnout zarážku** nebo stiskněte F9).

3. Spusťte ladění (F5). Provádění zastaví na zarážce.

4. Otevřít **Watch** okno (výběrem **ladění** > **Windows** > **Watch**  >   **Kukátko 1**, nebo stisknutím klávesy Ctrl + Alt + W, 1).

5. Vyberte prázdný řádek a zadejte proměnnou `a`. Potom to samé udělá proměnných `b` a `c`.

   ![Sledujte proměnné](../debugger/media/watchvariables.png "WatchVariables")

6. Pokračujte v ladění pomocí klávesy F11 podle potřeby k přechodu ladicí program.

Měli byste vidět změny jako iteraci v rámci hodnoty proměnné `for` smyčky.

Pokud programujete v nativním kódu, může někdy potřebovat kvalifikovat kontext názvu proměnné nebo výraz, který má název proměnné. Kontext je funkce, zdrojový soubor a modul, kde je umístěna proměnná. Pokud máte kvalifikovat kontext, můžete použít syntaxi kontextového operátoru. Další informace najdete v tématu [kontextový operátor (C++)](../debugger/context-operator-cpp.md).

## <a name="observe-expressions-with-the-watch-window"></a>Sledujte výrazy s okna kukátka

Teď si vyzkoušíme použití výrazu místo. Můžete přidat libovolný platný výraz rozpoznán v ladicím programu.

Například pokud máte kód uvedený v předchozí části, můžete získat průměrem tří hodnot s použitím tento výraz:

![Výraz Watch](../debugger/media/watchexpression.png "WatchExpression")

Pravidla pro vyhodnocování výrazů v **Watch** okna jsou obecně stejná jako pravidla pro vyhodnocování výrazů v kódovací jazyk. Pokud výraz obsahuje chybu syntaxe, očekávají stejný chybu kompilátoru, která se zobrazí v editoru kódu. Tady je příklad:

![Podívejte se na Chyba výrazu](../debugger/media/watchexpressionerror.png "WatchExpressionError")

## <a name="bkmk_refreshWatch"></a> Aktualizace hodnot sledování, které jsou zastaralé

Ikona Aktualizovat (kruhovou šipku) může zobrazit při vyhodnocování výrazu v **Watch** okna. Pokud jste vypnuli vyhodnocení vlastností (výběrem **nástroje** > **možnosti** > **ladění**  >   **Obecné**, pak vymazat **povolit vyhodnocování vlastností a jiných implicitních volání funkcí**), a jste napsali následující kód:

```csharp
static void Main(string[] args)
{
    List<string> list = new List<string>();
    list.Add("hello");
    list.Add("goodbye");
}

```

By měl vypadat přibližně jako na následujícím obrázku je-li nastavení sledování u `Count` vlastnost seznamu:

![RefreshWatch](../debugger/media/refreshwatch.png "RefreshWatch")

Předchozí obrázek znázorňuje chybu nebo hodnotu, která je zastaralá. Hodnota je obecně aktualizovat tak, že vyberete ikonu, ale v některých případech může být nechcete ho aktualizovat. Nejdřív je potřeba vědět, proč nebyl vyhodnocen hodnotu.

Popis obsahuje informace o proč výraz nebyl vyhodnocen, pokud přejdete na ikonu. Pokud se zobrazí circling šipky, výraz nebyl vyhodnocen pro jednu z následujících důvodů:

- Jak jsou vyhodnocovalo výrazu došlo k chybě. Například pravděpodobně došlo k vypršení časového limitu nebo mohly být proměnná mimo rozsah.

- Má výraz volání funkce, které může způsobit vedlejší účinek v aplikaci (viz [vedlejší efekty a výrazy](#bkmk_sideEffects) části).

- Jste vypnuli jste automatické hodnocení vlastností a implicitní funkce volá ladicím programem (výběrem **nástroje** > **možnosti** > **ladění**  >  **Obecné**, pak vymazat **povolit vyhodnocování vlastností a jiných implicitních volání funkcí**). Výraz nejde vyhodnotit automaticky potom.

Pokud chcete aktualizovat hodnotu, vyberte ikonu aktualizace nebo stisknutím klávesy MEZERNÍK. Ladicí program se pokusí o opětovné vyhodnocení výrazu. Na ikonu aktualizace může zobrazit, protože byl vypnut automatické hodnocení vlastností a jiných implicitních volání funkcí. Ladicí program v tomto případě můžete vyhodnotit výraz.

Ikona se může zobrazit, který je kroužek s dvěma vlnovkou řádky, které se podobají vlákna. Tato ikona znamená, že ladicí program nevyhodnocuje výraz z důvodu možných závislosti mezi vlákny. Jinými slovy vyhodnocování kód vyžaduje ostatní vlákna v aplikaci dočasně spustit. Pokud jste v režimu přerušení, zastaví se obvykle všechna vlákna ve vaší aplikaci. Umožňuje spustit dočasně jiných vláken může mít neočekávané účinky na stav programu a způsobí, že se ladicí program ignorovat události, například zarážky a výjimky vyvolané na tato vlákna.

## <a name="bkmk_sideEffects"></a> Vedlejší efekty a výrazy

Hodnocení některých výrazů může změnit hodnotu proměnné nebo jinak ovlivnit stav programu. Například vyhodnocení následujícího výrazu změní hodnotu `var1`:

```csharp
var1 = var2
```

Tento kód může způsobit, že [vedlejší účinek](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\)). Vedlejší efekty můžou ztížit ladění tak, že změníte způsob, jakým pracuje váš program.

Výraz má vedlejší účinky je vyhodnocen pouze jednou, při prvním zadání. Další hodnocení jsou zakázána. Toto chování můžete přepsat ručně tak, že vyberete ikonu aktualizace, která se zobrazí vedle hodnoty.

Chcete-li vypnout automatické vyhodnocování funkcí je jedním ze způsobů, aby všechny vedlejší účinky (výběrem **nástroje** > **možnosti** > **ladění**  >  **Obecné**, pak vymazat **povolit vyhodnocování vlastností a jiných implicitních volání funkcí**).

Při hodnocení vlastnosti nebo implicitních volání funkcí je vypnutý, můžete vynutit pomocí vyhodnocení **ac** modifikátor formátu (pro jenom v C#). Zobrazit [v jazyce C# specifikátory formátu](../debugger/format-specifiers-in-csharp.md).

## <a name="bkmk_objectIds"></a> Pomocí ID objektů v okně kukátko (C# a Visual Basic)

Někdy budete chtít sledovat chování s určitým objektem. Můžete například chtít sledovat objekt odkazuje místní proměnné po této proměnné je nepřejdou mimo rozsah. V jazyce C# a Visual Basic, můžete vytvořit ID objektů pro konkrétní instance typů odkazů a používat **Watch** okno a podmínky zarážky. ID objektu je generována modulem common language runtime (CLR) ladění služeb a přidružená k objektu.

> [!NOTE]
> ID objektů vytvořit slabé odkazy, které není brání objekt uvolněn z paměti. Jsou platné pouze pro aktuální relaci ladění.

Následující kód vytvoří jednu metodu `Person` pomocí místní proměnné, ale chcete zjistit, co `Person`jeho název je v jiné metody:

```csharp
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
    static List<Person> _people = new List<Person>();
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

Můžete přidat odkaz na daný `Person` objekt **Watch** okno následujícím způsobem:

1. Vyberte řádek kódu, který vyvolá se, že objekt se vytvořil.

2. Nastavení zarážky (výběrem **ladění** > **Přepnout zarážku** nebo stiskněte F9).

3. Spusťte ladění.

4. Při provádění zastaví na zarážce, otevřete **lokální** okno (výběrem **ladění** > **Windows** > **místníchhodnot**), klikněte pravým tlačítkem na proměnnou a vyberte **Ujistěte se, ID objektu**.

   Měli byste vidět znak dolaru (**$**) plus číslo v **lokální** okna, která je ID objektu.

   > [!NOTE]
   > Pokud chcete zobrazit vlastnosti objektu, například `Person.Name`, je nutné povolit vyhodnocování vlastností výběrem **nástroje** > **možnosti**  >   **Ladění** > **Obecné**, potom nastavení **povolit vyhodnocování vlastností a jiných implicitních volání funkcí**.

5. Přidat ID objektu **Watch** okna tak, že kliknete pravým tlačítkem na znak dolaru a číslo, pak výběrem **Přidat kukátko**.

6. Nastavte zarážku, ve které chcete sledovat chování objektu.  V předchozím kódu, která by byla `DoSomething()` metody.

7. Pokračujte v ladění. Při provádění zastaví v `DoSomething()` metody **Watch** v okně se zobrazí `Person` objektu.

## <a name="use-registers-in-the-watch-window-c-only"></a>Použijte registry v okně kukátko (pouze C++)

Můžete přidat názvy registrů a názvy proměnných pomocí  **$ \<zaregistrovat&nbsp;název >** nebo  **@ \<zaregistrovat&nbsp;name >** při ladění nativního kódu. Další informace najdete v tématu [Pseudoproměnné](../debugger/pseudovariables.md).

## <a name="dynamic-view-and-the-watch-window"></a>Dynamické zobrazení a okno kukátka

Použít dynamické některé skriptovací jazyky (například JavaScript nebo Python) nebo [duck zadáním](https://en.wikipedia.org/wiki/Duck_typing), a objekty, které je obtížné sledovat v oknech ladění normální, protože podpora jazyků .NET (ve verzi 4.0 a novější), může mít runtime vlastnosti a metody, které nelze zobrazit.

**Watch** okno zobrazit dynamický objekt, který je vytvořena z typu, který implementuje <xref:System.Dynamic.IDynamicMetaObjectProvider> rozhraní. Když tento objekt se zobrazí, přidá ladicí program speciální **dynamického zobrazení** podřízený uzel název objektu, pokud otevřete **automatické hodnoty** okno (výběrem **ladění**  >  **Windows** > **automatické hodnoty**). Tento uzel zobrazuje dynamické členy dynamického objektu, ale neumožňuje úpravy hodnot členů.

Vložit nové kukátko. proměnné, která přetypovává objekt na dynamický objekt:

1. Klikněte pravým tlačítkem na podřízený uzel **dynamického zobrazení**.
2. Zvolte **Přidat kukátko**. Potom `object.name` stane `((dynamic) object).name`.

Vyhodnocování členů **dynamického zobrazení** může mít vedlejší účinky. Vysvětlení, jaké jsou vedlejší účinky, najdete v článku [vedlejší efekty a výrazy](#bkmk_sideEffects) oddílu. Pro jazyk C#, ladicí program nebude automaticky přehodnotit hodnoty zobrazené **dynamického zobrazení** po kroku na nový řádek kódu. V jazyce Visual Basic přidávají výrazy **dynamického zobrazení** se automaticky aktualizují.

Pokyny o tom, jak aktualizovat **dynamického zobrazení** hodnoty, najdete v článku [hodnot aktualizovat sledování, které jsou zastaralé](#bkmk_refreshWatch) oddílu.

Pokud chcete zobrazit pouze **dynamického zobrazení** pro objekt, můžete použít **dynamické** ve specifikátoru formátu **Watch** okno:

- C#: `ObjectName, dynamic`
- Visual Basic: `$dynamic, ObjectName`

**Dynamického zobrazení** také rozšiřuje možnosti ladění pro objekty COM. Pokud ladicí program získá objekt modelu COM, který je obalen **System.__ComObject**, přidá **dynamického zobrazení** uzlu pro objekt.

## <a name="observe-a-single-variable-or-expression-with-quickwatch"></a>Podívejte se jednu proměnnou nebo výraz s QuickWatch

Můžete použít **QuickWatch** okno dodržovat jednu proměnnou. Pokud například máte následující kód:

```csharp
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

Proměnnou můžete sledovat **QuickWatch** okno následujícím způsobem:

1. Nastavit zarážku na `a = a + b;` řádku.

2. Spusťte ladění. Provádění zastaví na zarážce.

3. Vyberte proměnnou `a`.

4. Zvolte **ladění** > **QuickWatch** nebo stiskněte klávesu **Shift + F9**. **QuickWatch** zobrazí se okno. V **hodnotu** pole `a` proměnné se zobrazí s hodnotou 1.

   ![Rychlé kukátko proměnné](../debugger/media/quickwatchvariable.png "QuickWatchVariable")

   Vyhodnotit výraz, který používá proměnné, zadejte výraz `a + b` k **výraz** pole a klikněte na tlačítko **přehodnotit**.

   ![Výraz QuickWatch](../debugger/media/quickwatchexpression.png "QuickWatchExpression")

   K přidání proměnné nebo výraz, který se **Watch** okna z **QuickWatch**, zvolte **Přidat kukátko**.

   > [!NOTE]
   > **QuickWatch** je okno oknem modální dialogové okno, takže nelze pokračovat v ladění, dokud je otevřen.

5. Zavřít **QuickWatch** okna. Teď můžete pokračovat v ladění při sledování hodnotu v **Watch** okna.

## <a name="see-also"></a>Viz také:

[Okno ladicího programu](../debugger/debugger-windows.md)
