---
title: Zobrazení struktury kódu pomocí zobrazení tříd, volání hierarchie, prohlížeče objektů a definice kódu – okno
ms.date: 05/18/2018
ms.topic: conceptual
f1_keywords:
- vs.documentoutline.window
- vs.objectbrowser
- vs.classview
- VS.CodeDefinitionView
- VS.CodeDefinitionWindow
- vs.componentpicker
- vs.callbrowser
helpviewer_keywords:
- document outline window
- Visual Studio, object browser
- call hierarchy
- Visual Studio, document outline window
- code definition window [Visual Studio]
- Visual Studio, class view
- Visual Studio, call hierarchy window
- class view
- object browser
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e535ca76fd7b85d8267c0c002ffc8090430c5f0d
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55926369"
---
# <a name="view-the-structure-of-code-using-different-tool-windows"></a>Zobrazení struktury kódu pomocí různá okna nástrojů

Můžete zkontrolovat třídy a jejich členy v sadě Visual Studio pomocí různá okna nástrojů, včetně **zobrazení tříd**, **hierarchie volání**, **prohlížeče objektů**a **Code Definition** (pouze C++). Kód v projektech Visual Studio, součásti rozhraní .NET Framework, komponenty modelu COM, dynamické knihovny (DLL), můžete zkontrolovat těchto oknech nástrojů a knihoven (vyrovnávací paměti TLB) typů.

Můžete také použít **Průzkumníka řešení** pro přechod na typy a členy v projektech, hledání pro symboly, Zobrazit metody hierarchie volání, najít odkazy na symboly a další, aniž byste museli přepínat mezi více oken nástrojů.

Pokud máte Visual Studio Enterprise edition, můžete použít *map kódu* vizualizovat strukturu kódu a jeho závislosti napříč celé řešení. Další informace najdete v tématu [mapování závislostí pomocí map kódu](../modeling/map-dependencies-across-your-solutions.md).

## <a name="class-view-visual-basic-c-c"></a>Zobrazení tříd (Visual Basic, C# a C++)

**Zobrazení tříd** se zobrazí jako součást **Průzkumníka řešení** a jako samostatném okně. **Zobrazení tříd** zobrazuje prvky aplikace. V horním podokně se zobrazí obory názvů, typy, rozhraní, výčty a třídy a dolním podokně zobrazí členy, které patří typ vybraný v horním podokně. Pomocí tohoto okna můžete přesunout do definice členů ve zdrojovém kódu (nebo **prohlížeče objektů** Pokud element je definován vně vašeho řešení).

Není nutné k sestavení projektu, chcete-li zobrazit jeho prvky v **zobrazení tříd**. V okně se aktualizují při úpravě kódu ve vašem projektu.

Můžete přidat kód do vašeho projektu výběrem uzel projektu a zvolením **přidat** tlačítko Otevřít **přidat novou položku** dialogové okno. Kód se přidá do samostatného souboru.

Pokud váš projekt se změnami do správy zdrojového kódu, každý **zobrazení tříd** prvek zobrazuje ikonu, která určuje stav zdrojového kódu souboru. Příkazy společné zdrojového kódu, jako **rezervovat**, **vrátit se změnami**, a **získat nejnovější verzi** jsou také k dispozici v místní nabídce pro element.

### <a name="class-view-toolbar"></a>Panel nástrojů pro třídy zobrazení

**Zobrazení tříd** nástrojů obsahuje následující příkazy:

|||
|-|-|
|**Nová složka**|Vytvoří virtuální složku nebo podsložku, ve kterém můžete uspořádat často používaných elementy. Jsou uložené v aktivním řešení (*.suo*) soubor. Po přejmenování nebo odstranění elementu v kódu, může zobrazit ve virtuální složce jako uzel k chybě. Chcete-li tento problém, odstraňte uzel chyby. Pokud jste přejmenovali element, můžete jej přesunout z hierarchie projektu do složky znovu.|
|**Zpět**|Přejde na dříve vybrané položky.|
|**Vpřed**|Přejde na další vybranou položku.|
|**Zobrazit Diagram tříd** (kódové projekty pouze spravované)|K dispozici při vyberte obor názvů nebo typ v **zobrazení tříd**. Pokud je vybraná oboru názvů, třídy diagram znázorňuje všechny typy v ní. Když vyberete typ, diagram tříd se zobrazí pouze typu.|

### <a name="class-view-settings"></a>Zobrazení tříd – nastavení

**Zobrazení tříd – nastavení** tlačítko na panelu nástrojů má následující nastavení:

|||
|-|-|
|**Zobrazit základní typy**|Zobrazí se základní typy.|
|**Zobrazit odvozené typy**|Zobrazí se odvozené typy.|
|**Zobrazit skryté typy a členy**|Skryté typy a členy (není určená pro klienty) se zobrazí ve světle šedý text.|
|**Zobrazit veřejné členy**|Veřejné členy se zobrazí.|
|**Zobrazit chráněné členy**|Chráněné členy jsou zobrazeny.|
|**Zobrazit soukromé členy**|Soukromé členy jsou zobrazeny.|
|**Zobrazit ostatní členy**|Jiné druhy členů jsou zobrazeny, včetně interní (nebo typu Friend v jazyce Visual Basic) členy.|
|**Zobrazit zděděné členy**|Zděděné členy jsou zobrazeny.|
|**Zobrazit metody rozšíření**|Metody rozšíření jsou zobrazeny.|

### <a name="class-view-shortcut-menu"></a>Třídy zobrazení místní nabídky

V místní nabídce **zobrazení tříd** může obsahovat následující příkazy, v závislosti na druhu vybraný projekt:

|||
|-|-|
|**Přejít k definici**|Najde definici elementu ve zdrojovém kódu nebo v **prohlížeče objektů**, pokud element není definována v otevřeném projektu.|
|**Procházet definici**|Zobrazí vybrané položky **prohlížeče objektů**.|
|**Najít všechny odkazy**|Vyhledá položku aktuálně vybraný objekt a zobrazí výsledky v **výsledky hledání** okna.|
|**Typ filtru** (spravovaných jenom kód)|Zobrazí vybraný typ nebo obor názvů. Filtr můžete odebrat výběrem **vymazat najít** (**X**) vedle **najít** pole.|
|**kopírování**|Zkopíruje plně kvalifikovaný název položky.|
|**Seřadit podle abecedy**|Obsahuje typy a členy abecedně podle názvu.|
|**Seřadit podle typu člena**|Obsahuje typy a členy v pořadí podle typu (tak, aby předcházet rozhraní třídy, rozhraní předcházet delegáty a metody předcházet vlastnosti).|
|**Seřadit podle přístupu ke členu**|Seznamy, typy a členy v pořadí podle přístupu zadejte, jako jsou veřejné a privátní.|
|**Seskupit podle typu člena**|Seřadí typy a členy do skupin podle typu objektu.|
|**Přejděte do deklarace** (pouze v kódu jazyka C++)|Zobrazí deklarace typu nebo člena ve zdrojovém kódu, pokud je k dispozici.|
|**Přejít k definici**|Zobrazuje definici typu nebo člena ve zdrojovém kódu, pokud je k dispozici.|
|**Přejít na odkaz**|Pokud je k dispozici, zobrazí odkaz na typ nebo člen ve zdrojovém kódu.|
|**Zobrazit hierarchii volání**|Zobrazí vybrané metody v **hierarchie volání** okna.|

## <a name="call-hierarchy-window-visual-basic-c-c"></a>Hierarchie volání – okno (Visual Basic, C#, C++)

**Hierarchie volání** okno zobrazuje, kde je volán dané metody nebo vlastnosti. Obsahuje také seznam metod, které jsou volány z této metody. Můžete zobrazit více úrovní grafu volání, která zobrazuje volající / volaný vztahy mezi metodami v zadaném oboru.

Můžete zobrazit **hierarchie volání** okno výběrem – metoda (nebo vlastnost nebo konstruktor) v editoru a pak zvolením **zobrazit hierarchii volání** v místní nabídce. Zobrazení by měl vypadat podobně jako na následujícím obrázku:

![Hierarchie volání – okno v sadě Visual Studio](../ide/media/multiplenodes.png)

Pomocí rozevíracího seznamu na panelu nástrojů můžete určit rozsah hierarchii: řešení, aktuálním projektu nebo aktuální dokument.

V hlavním podokně se zobrazí volání do a z metody a **lokalit volání** podokně se zobrazí umístění vybraného volání. Pro členy, kteří jsou virtuální nebo abstraktní **název metody přepsání** uzel se objeví. Pro členy rozhraní **název metody implementuje** uzel se objeví.

**Hierarchie volání** okno nenajde metoda odkazy na skupinu, mezi které patří místa, kde se přidá jako obslužná rutina události metodu, nebo je přiřazená delegáta. Pokud chcete zjistit tyto odkazy, použijte **najít všechny odkazy** příkazu.

V místní nabídce **hierarchie volání** okno obsahuje následující příkazy:

|||
|-|-|
|**Přidat jako nový kořen**|Přidá zvolený uzel jako nový kořenový uzel.|
|**Odebrat kořen**|Odebere vybrané kořenový uzel v podokně se stromovým zobrazením.|
|**Přejít k definici**|Přejde na původní definice metody.|
|**Najít všechny odkazy**|Vyhledá v projektu všechny odkazy na vybrané metody.|
|**kopírování**|Zkopíruje vybraný uzel (ale ne jeho podřízené uzly).|
|**Aktualizace**|Aktualizuje informace.|

## <a name="BKMK_ObjectBrowser"></a> Prohlížeč objektů

**Prohlížeče objektů** okno zobrazuje popisy kód ve vašich projektech.

Můžete filtrovat komponenty, které chcete zobrazit pomocí rozevíracího seznamu v horní části okna. Vlastní komponenty mohou obsahovat spustitelné soubory spravovaného kódu, sestavení knihovny, knihovnách typů a *.ocx* soubory. Není možné přidat vlastní komponenty C++. Vlastní nastavení se ukládají do adresáře aplikace uživatele sady Visual Studio *%APPDATA%\Microsoft\VisualStudio\15.0\ObjBrowEX.dat*.

Levém podokně **prohlížeče objektů** ukazuje sestavení. Můžete rozbalit sestavení, které chcete zobrazit obory názvů, které obsahují a potom rozbalte obory názvů do zobrazení typů, které obsahují. Když vyberete typ, jeho členy (jako je například vlastnosti a metody) jsou uvedeny v pravém podokně. Pravém dolním podokně zobrazí podrobné informace o vybrané položce.

Konkrétní položku můžete vyhledat pomocí **hledání** pole v horní části okna. Hledání jsou malá a velká písmena. V levém podokně se zobrazí výsledky hledání. Vymazat hledání, zvolte **hledání vymazání** (**X**) vedle **hledání** pole.

**Prohlížeče objektů** sleduje provedené výběry kde se můžete dostat mimo váš výběr pomocí **vpřed** a **zpět** tlačítka na panelu nástrojů.

Můžete použít **prohlížeče objektů** výběrem položky (sestavení, oboru názvů, typ nebo člen) a zvolením přidat odkaz na sestavení k otevřenému řešení **přidat odkaz** tlačítko na panelu nástrojů.

### <a name="object-browser-settings"></a>Nastavení prohlížeče objektů

S použitím **nastavení prohlížeče objektů** tlačítko na panelu nástrojů můžete určit jednu z následujících zobrazení:

|||
|-|-|
|**Zobrazení oborů názvů**|V levém podokně zobrazí obory názvů spíše než fyzické kontejnery. Obory názvů uložená ve více fyzické kontejnery jsou sloučeny.|
|**Zobrazení kontejnerů**|Zobrazuje fyzické kontejnery spíše než obory názvů, v levém podokně. **Zobrazit obory názvů** a **kontejnery zobrazení** jsou vzájemně se vylučující nastavení.|
|**Zobrazit základní typy**|Zobrazí základních typů.|
|**Zobrazit odvozené typy**|Zobrazí odvozené typy.|
|**Zobrazit skryté typy a členy**|Zobrazí skryté typy a členy (není určená pro klienty), ve světle šedý text.|
|**Zobrazit veřejné členy**|Zobrazí veřejné členy.|
|**Zobrazit chráněné členy**|Zobrazí chráněné členy.|
|**Zobrazit soukromé členy**|Zobrazí privátní členy.|
|**Zobrazit ostatní členy**|Zobrazí jiné druhy členů, včetně interní (nebo typu Friend v jazyce Visual Basic) členy.|
|**Zobrazit zděděné členy**|Zobrazí zděděné členy.|
|**Zobrazit metody rozšíření**|Metody rozšíření se zobrazí.|

### <a name="object-browser-shortcut-menu-commands"></a>Objekt příkazy místní nabídky prohlížeče

V místní nabídce **prohlížeče objektů** může obsahovat následující příkazy, v závislosti na druhu položek vybraných:

|||
|-|-|
|**Procházet definici**|Ukazuje primárního uzlu pro vybranou položku.|
|**Najít všechny odkazy**|Vyhledá položku aktuálně vybraný objekt a zobrazí výsledky v **výsledky hledání** okna.|
|**Filtrovat vůči typu**|Zobrazí vybraný typ nebo obor názvů. Filtr můžete odebrat výběrem **– Vymazat hledání** tlačítko.|
|**kopírování**|Zkopíruje plně kvalifikovaný název položky.|
|**odebrat**|Pokud je obor sadu vlastních komponent, odebere vybrané součásti z oboru.|
|**Seřadit podle abecedy**|Obsahuje typy a členy abecedně podle názvu.|
|**Seřadit podle typu objektu**|Obsahuje typy a členy v pořadí podle typu (tak, aby předcházet rozhraní třídy, rozhraní předcházet delegáty a metody předcházet vlastnosti).|
|**Seřadit podle přístupu k objektům**|Seznamy, typy a členy v pořadí podle přístupu zadejte, jako jsou veřejné a privátní.|
|**Seskupit podle typu objektu**|Seřadí typy a členy do skupin podle typu objektu.|
|**Přejděte do deklarace** (pouze projekty C++)|Zobrazí deklarace typu nebo člena ve zdrojovém kódu, pokud je k dispozici.|
|**Přejít k definici**|Zobrazuje definici typu nebo člena ve zdrojovém kódu, pokud je k dispozici.|
|**Přejít na odkaz**|Pokud je k dispozici, zobrazí odkaz na typ nebo člen ve zdrojovém kódu.|
|**Zobrazit hierarchii volání**|Zobrazí vybrané metody v **hierarchie volání** okna.|

## <a name="code-definition-window-c"></a>Code Definition – okno (C++)

**Definice kódu** okně zobrazí definici vybraného typu jazyka C++ nebo člen aktivního projektu. Tento typ nebo člen je vybrat v editoru kódu nebo v okně zobrazení kódu.

I když v tomto okně je jen pro čtení, můžete nastavit zarážky a záložky v ní. Chcete-li upravit definici zobrazený, zvolte **upravit definici** v místní nabídce. Tím se otevře zdrojový soubor v editoru kódu a přesune kurzor na řádek, kde začíná v definici.

> [!NOTE]
> Spouští se v sadě Visual Studio 2015 **definice kódu** okno jde použít jenom s kódem jazyka C++.

### <a name="code-definition-shortcut-menu"></a>Code Definition nabídku

V místní nabídce **definice kódu** okna může obsahovat následující příkazy:

|||
|-|-|
|**Rychlé akce a Refaktoringy**||
|**Přejmenovat**||
|**Generovat graf souborů zahrnutí**||
|**Náhled definice**||
|**Přejít k definici**|Najde definici (nebo definice pro částečné třídy) a zobrazí je v **výsledky hledání** okna.|
|**Přejít na deklaraci**||
|**Najít všechny odkazy**|Vyhledá odkazy na tento typ nebo člen v řešení.|
|**Zobrazit hierarchii volání**|Metoda se zobrazí **hierarchie volání** okna.|
|**Přepínač záhlaví / soubor kódu**||
|**Spuštění testů**|Pokud v projektu testů jednotek, spouští testy pro vybraný kód.|
|**Ladit testy**||
|**Zarážky**|Vloží zarážky (nebo zarážku s trasováním).|
|**Spustit ke kurzoru**|Spustí program v režimu ladění do umístění kurzoru.|
|**Fragment kódu**||
|**Vyjmout**, **kopírování**, **vložit**||
|**Poznámka**||
|**Sbalení**|Standardní příkazy sbalování.|
|**Znovu prohledat**||
|**Upravit definici**|Přesune kurzor do definice v okně kódu.|
|**Zvolit kódování**|Otevře **kódování** okna tak, že můžete nastavit kódování souboru.|

## <a name="document-outline-window"></a>Osnova dokumentu – okno

Můžete použít **Osnova dokumentu** okna ve spojení s návrháře zobrazení, jako je například Návrhář XAML stránky nebo Návrhář formulářů Windows nebo stránky HTML. Toto okno zobrazuje prvky ve stromovém zobrazení, aby mohli zobrazit logické struktury formuláře nebo stránky a najít ovládací prvky, které jsou hluboce vložené nebo skrytý.

## <a name="see-also"></a>Viz také:

- [Ikony zobrazení třídy a prohlížeče objektů](../ide/class-view-and-object-browser-icons.md)