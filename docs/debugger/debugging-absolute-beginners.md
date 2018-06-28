---
title: Ladění kódu pro začátečníky absolutní
description: Pokud ladíte poprvé, přečtěte si několik Principy pomoc při spuštění aplikace v režimu ladění pomocí sady Visual Studio
ms.custom: ''
ms.date: 06/18/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e2b9bcfecb8bae70852aebf7503641a8c2a3f6cf
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057350"
---
# <a name="how-to-debug-for-absolute-beginners"></a>Postup ladění pro začátečníky absolutní

Bez nezdaří kód, který jsme zapsat jako vývojáři softwaru vždy neprovádí, co očekávali jsme na práci. Někdy se něco úplně jiné! Pokud k tomu dojde, dalším úkolem je zjistěte, proč a i když jsme mohou mít tendenci právě zachovat spuštěním v našem kódu, hodin, je mnohem snazší a efektivní používat nástroj pro ladění, nebo ladicího programu.

Ladicí program, není bohužel něco, co může magically odhalit všechny problémy nebo "chyb" v našem kódu. *Ladění* znamená pro spouštění vašeho kódu krok za krokem v ladicí nástroj jako Visual Studio, najít přesnou bod, kde jste udělali programování. Potom pochopit, jaké opravy, budete muset udělat ve vašem kódu a ladicí nástroje často umožní vám provádět dočasný změny, abyste mohli pokračovat, spuštění programu.

Efektivním použitím ladicí program je také odborností, která přebírá čas a další postup, ale je nakonec základní úloha pro každý vývojář softwaru. V tomto článku, zavést zásady základní ladění a budeme poskytují tipy, jak vám pomůžou začít.

## <a name="clarify-the-problem-by-asking-yourself-the-right-questions"></a>Vysvětlení problému tím, že požádá sami správné otázky

Pomáhá vysvětlení problému, který jste narazili teprve pak zkuste to opravit. Očekáváme, že jste již narazili na problém ve vašem kódu, jinak nebude možné zde pokoušíte zjistit, jak ho ladit! Ano než začnete, ladění, zkontrolujte, zda že jste zformulovali problému, který se snažíte vyřešit:

* Co očekává, že kód udělat?

* Co se stalo místo?

    Pokud jste spustili (výjimek) došlo k chybě při spuštění aplikace, který může být dobré! Výjimkou je neočekávané události došlo při spuštění kódu, obvykle chybu určitého druhu. Ladicí nástroj může trvat přesné místo v kódu, kde se vyskytla výjimka a může vám pomůže prozkoumat možné opravy.

    Pokud došlo k něco jiného, co je tento příznak problému? Máte už podezření kde došlo k tomuto problému v kódu? Například pokud váš kód zobrazí text, ale text je nesprávný, víte, buď vaše data jsou chybné nebo kód, který nastavení textu zobrazovaného má nějaký druh chyb. Pomocí procházení přes kód v ladicí program, můžete zkontrolovat každé změny do proměnných ke zjištění přesně, kdy a jak jsou přiřazeny nesprávné hodnoty.

## <a name="examine-your-assumptions"></a>Zkontrolujte předpokladů

Předtím, než můžete prozkoumat chyby nebo došlo k chybě, vezměte v úvahu předpokladů, které můžete očekávat, že určité výsledek provedeny. Skrytý nebo neznámé předpoklady můžete získat cestě identifikace problém i v případě, že hledáte vpravo na příčinu problému v ladicí program. Můžete mít dlouhý seznam možných předpoklady! Tady jsou jsou několik otázky sami vyzve předpokladů.

* Používáte správné rozhraní API (to znamená, v pravém objektu, funkce, metoda nebo vlastnost)? Rozhraní API, které používáte nemusí to, co si myslíte, že se nepodporuje. (Po byste zkontrolovat volání rozhraní API v ladicím programu, její opravu může vyžadovat cesty v dokumentaci k identifikaci správné rozhraní API.)

* Používáte rozhraní API správně? Možná použít právo rozhraní API ale nepoužili správné způsobem.

* Obsahuje kód žádné překlepům? Některé překlepy, jako je jednoduchý chybně napsané názvu proměnné, může být obtížné zjistit, zejména při práci s jazyky, které nevyžadují proměnné deklarovat, než jejich použití.

* Provést změnu kódu a předpokládají, že nemá vztah k problému, který se zobrazuje?

* Nebyla očekáváte objektu nebo proměnné tak, aby obsahovala určitou hodnotu (nebo typ hodnoty), se liší od co se skutečně stalo?

* Znáte záměr kód? Je často je obtížné ladění někdo jiný kód. Pokud není kód, je možné, že možná budete muset něco dozvědět přesně co kód nemá předtím, než ho můžete efektivně ladit.

    > [!TIP]
    > Při psaní kódu, začněte v malém rozsahu a začněte s kódem, který funguje! (Dobrý ukázkový kód je užitečné sem.) V některých případech je snazší opravte sadu velké nebo složité kódu od malou část kódu, který ukazuje základní úlohy, kterou chcete dosáhnout. Potom můžete upravit nebo postupně, přidejte kód testování u každého bodu chyby.

Pomocí označování předpokladů, můžete snížit dobu potřebnou k vyhledání k problému v kódu. Může také snížit dobu potřebnou k vyřešení problému.

## <a name="step-through-your-code-in-debugging-mode-to-find-where-the-problem-occurred"></a>Krokovat kód při ladění režimu k nalezení, kde došlo k problému

Když spustíte obvykle aplikace, dochází k chybám a nesprávné výsledky pouze, po spuštění kódu. Program může také neočekávaně ukončí bez informací, proč.

Spuštění aplikace v rámci ladicí program, označované taky jako *režim ladění*, znamená, že ladicí program aktivně sleduje vše, co se děje jako program se spustí. Také umožňuje pozastavit aplikaci kdykoli zkontrolovat její stav a poté procházet kód řádek po řádku můžete sledovat všechny podrobnosti, jako Odehrává se.

V sadě Visual Studio, zadejte režim ladění pomocí **F5** (nebo **ladění** > **spustit ladění** příkazu nabídky nebo **spustit ladění**  tlačítko ![spustit ladění](../debugger/media/dbg-tour-start-debugging.png "spustit ladění")) na panelu nástrojů ladění. Pokud dojde k nějaké výjimky, Visual Studio pomocníka výjimka přejdete na přesný bod, kde výjimky došlo k chybě a poskytuje další užitečné informace.

Pokud jste neobdrželi výjimku, pravděpodobně máte vhodné místo pro vyhledání problému v kódu. To kde používáte *zarážky* pomocí ladicího programu, abyste měli o více pečlivě zkontrolujte v kódu. Zarážky jsou základní a nejjednodušší funkcí spolehlivého ladění. Zarážku označuje, kde Visual Studio pozastavit spuštěním kódu, můžete si prohlédněte hodnoty proměnných, nebo chování paměti nebo pořadí, ve kterém kód běží.

V sadě Visual Studio můžete rychle nastavit zarážky kliknutím na levém okraji vedle řádek kódu. Nebo umístěte kurzor na řádku a stiskněte klávesu **F9**.

Pro lepší znázornění tyto koncepty, budeme vás provede některé ukázkový kód, který už má několik chyb. Používáme C#, ale funkce ladění platí pro Visual Basic, C++, JavaScript, Python a jiné podporované jazyky.

### <a name="create-a-sample-app-with-some-bugs"></a>Vytvoření ukázkové aplikace (v některé chyby)

V dalším kroku vytvoříme aplikaci, která má několik chyb.

1. Musíte mít nainstalovanou sadu Visual Studio a buď. **NET vývoj aplikací** zatížení nebo. **NET jádra pro různé platformy vývoj** zatížení nainstalovaná, v závislosti na typ aplikace, které chcete vytvořit.

    Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

    Pokud potřebujete nainstalovat zatížení, ale už máte Visual Studio, klikněte na tlačítko **nástroje** > **funkcí a nástrojů pro získání**. Spustí se instalační program pro Visual Studio. Zvolte. **NET vývoj aplikací** (nebo. **NET jádra pro různé platformy vývoj**) pracovního vytížení, zvolte **upravit**.

1. Otevřete Visual Studio a zvolte **soubor** > **nový** > **projektu**.

1. Vyberte šablonu pro kód aplikace.

    Pro rozhraní .NET Framework v **nový projekt** dialogovém okně vyberte **Visual C#**, **Windows Desktop** z části nainstalovaných šablon a potom v prostředním podokně vyberte  **Konzole aplikace (rozhraní .NET Framework)**.

    Pro .NET Core v **nový projekt** dialogovém okně vyberte **Visual C#**, **.NET Core** z části nainstalovaných šablon a potom v prostředním podokně vyberte  **Konzole aplikace (.NET Core)**.

    Pokud nevidíte tyto šablony, je nutné nainstalovat příslušnou zatížení (viz dřívějších krocích).

1. V **název** zadejte **ConsoleApp FirstApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt konzoly, která se zobrazí v Průzkumníku řešení v pravém podokně.

1. V *Program.cs*, ve výchozím kódu nahraďte následujícím kódem:

    ```csharp
    using System;
    using System.Collections.Generic;
    
    namespace ConsoleApp_FirstApp
    {
        class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("Welcome to Galaxy News!");
                IterateThroughList();
                Console.ReadKey();
            }
    
            private static void IterateThroughList()
            {
                var theGalaxies = new List<Galaxy>
            {
                new Galaxy() { Name="Tadpole", MegaLightYears=400, GalaxyType=new GType('S')},
                new Galaxy() { Name="Pinwheel", MegaLightYears=25, GalaxyType=new GType('S')},
                new Galaxy() { Name="Cartwheel", MegaLightYears=500, GalaxyType=new GType('L')},
                new Galaxy() { Name="Small Magellanic Cloud", MegaLightYears=.2, GalaxyType=new GType('I')},
                new Galaxy() { Name="Andromeda", MegaLightYears=3, GalaxyType=new GType('S')},
                new Galaxy() { Name="Maffei 1", MegaLightYears=11, GalaxyType=new GType('E')}
            };
    
                foreach (Galaxy theGalaxy in theGalaxies)
                {
                    Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears + ",  " + theGalaxy.GalaxyType);
                }
    
                // Expected Output:  
                //  Tadpole  400,  Spiral 
                //  Pinwheel  25,  Spiral 
                //  Cartwheel, 500,  Lenticular
                //  Small Magellanic Cloud .2,  Irregular
                //  Andromeda  3,  Spiral
                //  Maffei 1,  11,  Elliptical
            }
        }
    
        public class Galaxy
        {
            public string Name { get; set; }
    
            public double MegaLightYears { get; set; }
            public object GalaxyType { get; set; }
    
        }
    
        public class GType
        { 
            public GType(char type)
            {
                switch(type)
                {
                    case 'S':
                        MyGType = Type.Spiral;
                        break;
                    case 'E':
                        MyGType = Type.Elliptical;
                        break;
                    case 'l':
                        MyGType = Type.Irregular;
                        break;
                    case 'L':
                        MyGType = Type.Lenticular;
                        break;
                    default:
                        break;
                }
            }
            public object MyGType { get; set; }
            private enum Type { Spiral, Elliptical, Irregular, Lenticular}
        }
    }
    ```

    Naše pro tento kód je cílem zobrazovaný název galaxy, vzdálenost galaxy a typ galaxy všechny v seznamu. K ladění, je důležité si uvědomit, záměr kódu. Tady je formát pro jeden řádek v seznamu, který má být zobrazena ve výstupu:

    *Název Galaxy*, *vzdálenost*, *galaxy typu*.

### <a name="run-the-app"></a>Spuštění aplikace

1. Stiskněte klávesu **F5** nebo **spustit ladění** tlačítko ![spustit ladění](../debugger/media/dbg-tour-start-debugging.png "spustit ladění") v panelu nástrojů ladění umístěny nad editoru kódu.

    Spuštění aplikace a neexistují žádné výjimky uvedené pro nás pomocí ladicího programu. Výstup, který se zobrazí v okně konzoly je však není co očekávat. Toto je očekávaný výstup:

    ```
    Tadpole  400,  Spiral 
    Pinwheel  25,  Spiral 
    Cartwheel, 500,  Lenticular
    Small Magellanic Cloud .2,  Irregular
    Andromeda  3,  Spiral
    Maffei 1,  Elliptical
    ```

    Ale toto místo vidíme:

    ```
    Tadpole  400,  ConsoleApp_FirstApp.GType 
    Pinwheel  25,  ConsoleApp_FirstApp.GType 
    Cartwheel, 500,  ConsoleApp_FirstApp.GType
    Small Magellanic Cloud .2,  ConsoleApp_FirstApp.GType
    Andromeda  3,  ConsoleApp_FirstApp.GType
    Maffei 1, 11,  ConsoleApp_FirstApp.GType
    ```

    Vyhledávání v výstup a na našem kódu, budeme vědět, že `GType` je název třídy, která ukládá galaxy typu. Snažíme se zobrazit skutečné galaxy typ (například "Spirála"), není název třídy!

### <a name="debug-the-app"></a>Ladění aplikace

1. Pomocí aplikace stále běží zarážku kliknutím na levém okraji vedle možnosti `Console.WriteLine` volání metody v tomto řádku kódu.

    ```csharp
    foreach (Galaxy theGalaxy in theGalaxies)
        {
            Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears + ",  " + theGalaxy.GalaxyType);
    }    
    ```

    Když nastavíte zarážce, se zobrazí na levém okraji červené tečky.

    Protože vidíme problém ve výstupu, spustíme ladění pohledem na předchozí kód, který nastaví výstup v ladicím programu.

1. Klikněte na tlačítko **restartujte** ![restartujte aplikace](../debugger/media/dbg-tour-restart.png "RestartApp") tlačítka na panelu nástrojů Debug (**Ctrl** + **posunutí**   +  **F5**).

    Aplikace se pozastaví u zarážky, který nastavíte. Žlutý hightlighting označuje, kde je pozastaven ladicího programu (žlutý řádek kódu ještě spuštěna).

1. Najeďte myší `GalaxyType` rozbalte proměnné na pravé straně a potom nalevo od ikona klíče `theGalaxy.GalaxyType`. Uvidíte, že `GalaxyType` obsahuje vlastnost `MyGType`, a hodnota vlastnosti je nastavena na `Spiral`.

    ![Zkontrolujte proměnné](../debugger/media/beginners-inspect-variable.png)

    "Spirála" je ve skutečnosti správnou hodnotu, kterou jste očekávali tisk do konzoly! Proto je dobré počáteční, dostanete tuto hodnotu v tomto kódu při spuštění aplikace. V tomto scénáři se používá nesprávný rozhraní API. Nemůžeme se zobrazí, pokud jsme to opravit při běhu kódu v ladicím programu.

1. Ve stejný kód, při ladění stále, umístěte kurzor na konci `theGalaxy.GalaxyType` a změňte ji na `theGalaxy.GalaxyType.MyGType`. I když provedete tuto změnu, editoru kódu ukazuje, k chyba oznamující, že tento kód nelze zkompilovat.

    ![Chyba syntaxe](../debugger/media/beginners-edit.png)

1. Klikněte na tlačítko **upravit** v **upravit a pokračovat** okno se zprávou. Zobrazí chybovou zprávu nyní ve **seznam chyb** okno. Chyba znamená, že `'object'` neobsahuje definici `MyGType`.

    ![Chyba syntaxe](../debugger/media/beginners-no-definition.png)

    I když nemůžeme nastavit každý galaxy s objektem typu `GType` (který má `MGType` vlastnost), nemůže rozpoznat ladicí program `theGalaxy` objektu jako objekt typu `GType`. Co se děje? Chcete si můžete prohlédnout kód, který nastaví typ galaxy. Když to uděláte, můžete vidět, že `GType` třída výborný má vlastnost `MyGType`, ale něco není pravé. Chybová zpráva o `object` být potvrzením; k překladač jazyk zdá být objekt typu typ `object` místo objekt typu `GType`.

1. Procházení kódu, vztahuje k nastavení typu galaxy, zjistíte `GalaxyType` vlastnost `Galaxy` třída je zadán jako `object` místo `GType`.

    ```csharp
    public object GalaxyType { get; set; }     
    ```

1. Změna předchozí kód k tomuto:

    ```csharp
    public GType GalaxyType { get; set; }     
    ```

1. Klikněte na tlačítko **restartujte** ![restartujte aplikace](../debugger/media/dbg-tour-restart.png "RestartApp") tlačítka na panelu nástrojů Debug (**Ctrl** + **posunutí**   +  **F5**) znovu zkompiluje kódu a restartovat.

    Teď, když ladicí program pozastaví na `Console.WriteLine`, můžete podržet přes `theGalaxy.GalaxyType.MyGType`a zjistit, který je hodnota nastavena správně.

1. Odebrat zarážce kliknutím na kruh zarážek na levém okraji (nebo klikněte pravým tlačítkem myši a zvolte **zarážek** > **odstranit zarážek**) a potom stiskněte klávesu **F5** pokračujte.

    Aplikace běží a zobrazí výstup. Vypadá to, poměrně vhodné nyní, ale Všimněte si jednou z věcí; očekáván galaxy malé cloudu Magellanic objeví jako nestandardní galaxy ve výstupu konzoly, ale žádný typ galaxy vůbec zobrazí.

    ```
    Tadpole  400,  Spiral 
    Pinwheel  25,  Spiral 
    Cartwheel, 500,  Lenticular
    Small Magellanic Cloud .2,
    Andromeda  3,  Spiral
    Maffei 1,  Elliptical
    ```

1. Nastavte zarážky tento řádek kódu.

    ```csharp
    public GType(char type)
    ```

    Tento kód je, kde je typ galaxy nastaven, takže chceme využít bližší pohled na ho.

1. Klikněte na tlačítko **restartujte** ![restartujte aplikace](../debugger/media/dbg-tour-restart.png "RestartApp") tlačítka na panelu nástrojů Debug (**Ctrl** + **posunutí**   +  **F5**) k restartování.

    Ladicí program se pozastaví na řádek kódu, kde nastavit bod přerušení.  

1. Najeďte myší `type` proměnné. Zobrazí hodnotu `S` (následující kód znaku). Máte zájem hodnotu `I`, protože víte, který je nestandardní galaxy typu.

1. Stiskněte klávesu **F5** a najeďte myší `type` proměnné znovu. Tento krok opakujte, dokud neuvidíte hodnotu `I` v `type` proměnné.

    ![Zkontrolujte proměnné](../debugger/media/beginners-inspecting-data.png)

1. Nyní, stiskněte klávesu **F11** (**ladění** > **Krokovat s vnořením** nebo **Krokovat s vnořením** tlačítka na panelu nástrojů Debug).

    **F11** posune ladicí program (a spustí kód) jeden příkaz v čase. **F10** (**Krokovat s přeskočením**) je podobný příkaz a obě jsou velmi užitečné, když naučit se používat ladicí program.

1. Stiskněte klávesu **F11** dokud jej nezastavíte na řádek kódu `switch` příkaz na hodnotu "I". Zde najdete v části zrušte potíže způsobené překlepem. Očekáván kód, který přechodu na kde nastaví `MyGType` jako nepravidelné galaxy typ, ale ladicí program místo úplně přeskočí tento kód a pozastaví na `default` části `switch` příkaz.

    ![Najít překlepem](../debugger/media/beginners-typo.png)

    Prohlížení kódu, uvidíte překlepem v `case 'l'` příkaz. Měla by být `case 'I'`.

1. Klikněte na tlačítko v kódu pro `case 'l'`a nahraďte ho "malá"I".

1. Odebrat vaší zarážce a klikněte **restartujte** tlačítko restartujte aplikaci.

    Chyby jsou nyní opraveny a zobrazí se výstup očekáváte!

    Stisknutím libovolné klávesy ukončíte aplikace.

## <a name="summary"></a>Shrnutí

Pokud se problém, použijte ladicí program a [krok příkazy](../debugger/navigating-through-code-with-the-debugger.md) , jako **F10** a **F11** najít oblasti s problémem kódu.

> [!NOTE]
> Pokud je obtížné určit oblasti kódu, kde k problému dochází, nastavte zarážky v kódu, který běží před výskytem problému a pak použít příkazy krok, dokud neuvidíte problém manifestu. Můžete také použít [tracepoints](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints) protokolu zprávy pro **výstup** okno. Pomocí prohlížení zprávy zaznamenané (a vašeho povšimnutí zprávy, které ještě neprotokolovaly!), můžete často izolovat oblasti s problémem kódu. Možná budete muset tento postup opakujte několikrát zúžit zaměření.

Až najdete oblasti kódu s problémem, použijte ladicí program k prozkoumání. Chcete-li zjistit příčinu problému, zkontrolujte kód problém při spuštění aplikace v ladicím programu:

* [Zkontrolujte proměnné](../debugger/view-data-values-in-data-tips-in-the-code-editor.md) a zkontrolujte, zda obsahují typ hodnoty, které se musí obsahovat. Pokud zjistíte chybná hodnota, zjistit, kde byla nastavena chybná hodnota (najít, kde byla nastavena hodnota, budete pravděpodobně potřebovat restartovat ladicího programu, podívejte se na [zásobník volání](../debugger/how-to-use-the-call-stack-window.md), nebo obojí).

* Zkontrolujte, jestli vaše aplikace spouští kód, který jste očekávali. (Například v ukázkové aplikaci očekávali jsme kód pro příkaz switch postup nastavení typu galaxy nepravidelné, ale aplikace přeskočen kód z důvodu překlepem.)

> [!TIP]
> Ladicí program slouží k pomůže vám zjistit případné chyby. Ladicí nástroj můžete najít chyby *pro vás* pouze v případě, že zná záměr kódu. Nástroj můžete pouze vědět záměr kódu, pokud vás jako na vývojáři express tento záměr. Zápis [testování částí](../test/improve-code-quality.md) je, jak můžete udělat.

## <a name="next-steps"></a>Další kroky

V tomto článku když jste se naučili několik obecné koncepty ladění. Potom můžete spustit naučit, jak k ladění pomocí sady Visual Studio.

> [!div class="nextstepaction"]
> [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)
