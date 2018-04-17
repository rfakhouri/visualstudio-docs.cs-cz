---
title: Roslyn analyzátory a podporou kód knihovny pro ImmutableArrays | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 0b0afa22-3fca-4d59-908e-352464c1d903
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6ebafdd09e6fca0e1266c4eb03c4f6cb66554d06
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="roslyn-analyzers-and-code-aware-library-for-immutablearrays"></a>Roslyn analyzátory a podporou kód knihovny pro ImmutableArrays

[Platformy .NET kompilátoru](https://github.com/dotnet/roslyn) ("Roslyn") vám pomůže vytvořit kód využívající knihoven.  Knihovnu deklaracemi kódu poskytuje funkce, které můžete použít a nástrojů (Roslyn analyzátory) můžete v knihovně nejlepším způsobem, nebo aby nedocházelo k chybám.  Toto téma ukazuje, jak stavět skutečném světě Roslyn analyzátor zachycení běžných chyb při použití [System.Collections.Immutable](https://www.nuget.org/packages/System.Collections.Immutable) balíček NuGet.  Příklad také ukazuje, jak zajistit opravy kódu pro kód problém nalezen nástrojem analyzer.  Uživatelé vidí opravy kódu v sadě Visual Studio žárovky uživatelského rozhraní a provést opravu pro kód automaticky.

## <a name="getting-started"></a>Začínáme

Následující sestavení v tomto příkladu potřebujete:

* Visual Studio 2015 (není edice Express) nebo novější verze.  Můžete použít bezplatnou [Visual Studio Community Edition](https://www.visualstudio.com/products/visual-studio-community-vs)
* [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  Můžete také při instalaci sady Visual Studio, zkontrolovat Visual Studio Extensibility Tools v rámci běžných nástrojů k instalaci sady SDK ve stejnou dobu.  Pokud jste již nainstalovali Visual Studio, můžete taky nainstalovat tuto sadu SDK tak, že přejdete do hlavní nabídky **soubor &#124; nový &#124;projektu...** , výběr jazyka C# v levém navigačním podokně a pak vyberete rozšíření.  Pokud vyberete "**nainstalovat Visual Studio Extensibility Tools**" šablony projektu s popisem cesty, budete vyzváni ke stažení a instalace sady SDK.
* [Kompilátoru platformu .NET ("Roslyn") SDK](http://aka.ms/roslynsdktemplates).  Tuto sadu SDK můžete taky nainstalovat tak, že přejdete do hlavní nabídky **soubor &#124; nový &#124; projektu...** , výběrem možnosti **C#** v levém navigačním podokně a pak vyberete **rozšiřitelnost**.  Pokud vyberete "**stáhnout sadu SDK platformy .NET kompilátoru**" šablony projektu s popisem cesty, budete vyzváni ke stažení a instalace sady SDK.  Tato sada SDK zahrnuje [Roslyn syntaxe vizualizér](https://github.com/dotnet/roslyn/wiki/Syntax%20Visualizer).  Tato velmi užitečné nástroj pomáhá můžete zjistit, jaké typy modelu kódu je vhodné vyhledat ve vašem analyzátor.  Analyzátor infrastruktury volání do kódu pro konkrétní kód modelu typy, tak, aby váš kód pouze provede, když je to nutné a zaměřit pouze na Analýza relevantní kódu.

## <a name="whats-the-problem"></a>Co je problém?

Představte si ImmutableArray můžete poskytnout knihovny (například <xref:System.Collections.Immutable.ImmutableArray%601?displayProperty=fullName>) podporují.  C# vývojáři mají mnoha prostředí .NET pole.  Ale vzhledem k povaze ImmutableArrays a optimalizace postupy používané při implementaci intuitions vývojáře jazyka C#, že uživatelům své knihovny napsat kód, poškozený, jak je popsáno níže.  Uživatelé navíc nezobrazí jejich chyby do doby běhu, která není kvality prostředí, které se používají v sadě Visual Studio s rozhraním .NET.

Uživatelé se seznámíte s psaní kódu takto:

```csharp
var a1 = new int[0];
Console.WriteLine("a1.Length = { 0}", a1.Length);
var a2 = new int[] { 1, 2, 3, 4, 5 };
Console.WriteLine("a2.Length = { 0}", a2.Length);
```

Vytváření, aby uživatelé zadat další řádek kódu prázdné pole a pomocí syntaxe inicializátoru kolekce jsou velmi pro vývojáře v jazyce C#.  Však stejné zápis kódu pro ImmutableArray dojde k chybě za běhu:

```csharp
var b1 = new ImmutableArray<int>();
Console.WriteLine("b1.Length = { 0}", b1.Length);
var b2 = new ImmutableArray<int> { 1, 2, 3, 4, 5 };
Console.WriteLine("b2.Length = { 0}", b2.Length);
```

Kvůli implementaci ImmutableArray pomocí struktury zabalit podkladové úložiště dat je první chyba. Struktury musí být konstruktory bez parametrů, aby `default(T)` výrazy může vrátit struktury se všemi nula nebo hodnotu null členy.  Když přistoupí kód `b1.Length`, je null běhu dereference chyba, protože v struktura ImmutableArray neexistuje žádná základní pole úložiště.  Je správný způsob, jak vytvořit prázdný ImmutableArray `ImmutableArray<int>.Empty`.

Chyba s Inicializátory kolekcí se stane, protože metoda ImmutableArray.Add vrátí nové instance pokaždé, když ji volat.  Protože ImmutableArrays nikdy změnit, když přidáte nového elementu, zobrazí zpět nový objekt ImmutableArray (který může sdílet úložiště z důvodů výkonu s dříve existující ImmutableArray).  Protože `b2` odkazuje na první ImmutableArray před voláním `Add()` pětkrát, `b2` je výchozí ImmutableArray.  Dereference – Chyba volání délka na něm také dojde k chybě s hodnotou null.  Správný způsob k chybě při inicializaci ImmutableArray bez volání ručně přidat, je použít `ImmutableArray.CreateRange(new int[] {1, 2, 3, 4, 5})`.

## <a name="finding-relevant-syntax-node-types-to-trigger-your-analyzer"></a>Hledání typy uzlů relevantní syntaxe pro aktivaci vaší analyzátor

 Pokud chcete začít vytvářet nástroje analyzer, nejprve rozmyslete si, jaký typ SyntaxNode, budete muset vyhledat. Spusťte vizualizér syntaxe z nabídky **zobrazení &#124; ostatní okna &#124; Roslyn syntaxe vizualizér**.

Umístit editor vsuvka na řádek, který deklaruje `b1`.  Zobrazí se syntaxe vizualizér zobrazuje se v `LocalDeclarationStatement` uzel stromu syntaxe.  Tento uzel má `VariableDeclaration`, která naopak má `VariableDeclarator`, která naopak má `EqualsValueClause`a nakonec dojde `ObjectCreationExpression`.  Jako kliknete ve stromu syntaxe vizualizér uzlů, syntaxe v okně editoru označuje tak, aby zobrazovalo kód představuje tento uzel.  Názvy typů dílčí SyntaxNode odpovídat názvů používaných v gramatika C#.

## <a name="creating-the-analyzer-project"></a>Vytvoření projektu analyzátor

Z hlavní nabídky zvolte **soubor &#124; nový &#124; projektu...** .  V **nový projekt** dialogové okno, v části **C#** projekty v levém navigačním panelu zvolte rozšiřitelnost a v pravém podokně **analyzátor s opravte kód** projektu Šablona.  Zadejte název a potvrďte dialogové okno.

Šablona se otevře soubor DiagnosticAnalyzer.cs.  Zvolte tohoto editoru karta vyrovnávací paměti.  Tento soubor má třídu analyzátoru (vytvořen z názvu dáte projekt), je odvozena z `DiagnosticAnalyzer` (typ Roslyn rozhraní API).  Má novou třídu `DiagnosticAnalyzerAttribute` deklarace vaší Analyzátor je relevantní pro jazyk C#, aby kompilátor vyhledá a načte vaše analyzátor.

```csharp
[DiagnosticAnalyzer(LanguageNames.CSharp)]
public class ImmutableArrayAnalyzerAnalyzer : DiagnosticAnalyzer
{}
```

Můžete implementovat analyzátor jazyka Visual Basic, která je cílena kód C#, a naopak.  Je důležité v DiagnosticAnalyzerAttribute zvolit, jestli vaše analyzátor cílem jeden jazyk nebo obojí.  Složitější analyzátory, které vyžadují podrobné modelování jazyka, můžete vybrat jen jeden jazyk.  Pokud analyzátor, například kontroluje pouze názvy typů nebo názvy veřejných členů, je možné použít běžné model jazyk, který nabízí Roslyn napříč Visual Basic a C#.  Například FxCop varuje, že třída implementuje <xref:System.Runtime.Serialization.ISerializable>, ale nemá třídu <xref:System.SerializableAttribute> atribut je nezávislé na jazyku a funguje pro kód jazyka Visual Basic a C#.

## <a name="initalizing-the-analyzer"></a>Initalizing nástroje Analyzer

 Posuňte se dolů trochu v `DiagnosticAnalyzer` třída zobrazíte `Initialize` metoda.  Kompilátor volá tuto metodu při aktivaci analyzátor.  Tato metoda přebírá `AnalysisContext` objekt, který umožňuje vaší analyzátor získat na informace o kontextu a registrace zpětných volání pro události pro různé druhy kódu, které chcete analyzovat.

```csharp
public override void Initialize(AnalysisContext context) {}

```

Otevřete nový řádek v této metody a typu "kontextu." Chcete-li zobrazit seznam doplňování IntelliSense.  Zobrazí v seznamu dokončení mnoho `Register...` metody pro zpracování různé druhy událostí.  Například první z nich, `RegisterCodeBlockAction`, volání zpět do kódu pro blok, který je obvykle kód mezi složené závorky.  Registrace pro blok také volá zpět do kódu pro inicializátoru pole, hodnotě zadané do atribut nebo hodnota volitelný parametr.

Například `RegisterCompilationStartAction`, volání zpět na kód na začátku kompilace, což je užitečné, když je třeba shromáždit stavu přes mnoho míst.  Můžete vytvořit datové struktury, Řekněme, ke shromažďování všech symboly použité, a pokaždé, když je vaše Analyzátor zpětné volání pro některé syntaxe nebo symbol, můžete uložit informace o každé umístění v datovou strukturu.  Pokud jste zpětné volání z důvodu ukončuje kompilace, můžete analyzovat všechna místa, které jste uložili, například k hlášení jaké symboly kód používá z každé `using` příkaz.

Pomocí **syntaxe vizualizér**, jste se dozvěděli, že chcete volat, když kompilátor zpracovává ObjectCreationExpression.  Pomocí tohoto kódu nastavit zpětné volání:

```csharp
context.RegisterSyntaxNodeAction(c => AnalyzeObjectCreation(c),
                                 SyntaxKind.ObjectCreationExpression);
```

Je-li zaregistrovat pro uzel syntaxe a filtr pouze objekt vytvoření syntaxe uzly.  Podle konvence analyzátor autoři používat lambda při registraci akcí, které pomáhá chránit analyzátorů bezstavové akce.  Můžete použít funkci Visual Studio **generování před využitím** vytvořit `AnalyzeObjectCreation` metoda.  Tím se vytvoří správný typ kontext parametru pro vás příliš.

## <a name="setting-properties-for-users-of-your-analyzer"></a>Nastavení vlastností pro uživatele vaše analyzátor

Tak, aby vaše analyzátor objeví ve Visual Studiu správně, vyhledejte a upravte následující řádek kódu k identifikaci vaší analyzer:

```csharp
internal const string Category = "Naming";
```

Změna `"Naming"` k `"API Guidance"`.

Poté vyhledejte a otevřete `Resources.resx` souboru v projektu pomocí **Průzkumníku řešení**.  Umístit do popis pro analyzátor, název, atd.  Je-li změnit hodnotu pro všechny z nich k `"Don't use ImmutableArray<T> constructor"` teď.  Můžete použít a zadat řetězec formátování argumenty do řetězce ({0}, {1}, atd.) a novější při volání `Diagnostic.Create()`, můžete zadat `params` pole argumenty předávané.

## <a name="analyzing-an-object-creation-expression"></a>Analýza výraz vytvoření objektu

`AnalyzeObjectCreation` Metoda má jiný typ kontextu poskytl framework analyzátor kódu.  Metoda Initialize `AnalysisContext` umožňuje registrace zpětných volání akce nastavit vaše analyzátor.  `SyntaxNodeAnalysisContext`, Například má `CancellationToken` , které můžete předat kolem.  Pokud uživatel spustí zadáním v editoru, zruší Roslyn spuštěné analyzátorů uložte práci a zlepšíte výkon.  Další příklad má tento kontext uzlu vlastnost, která vrátí uzel syntaxe vytvoření objektu.

Získáte uzlu, který můžete předpokládat, jde o typ, pro který filtrovaná akce uzlu syntaxe:

```csharp
var objectCreation = (ObjectCreationExpressionSyntax)context.Node;
```

### <a name="launching-visual-studio-with-your-analyzer-the-first-time"></a>Visual Studio s vaší analyzátor při prvním spuštění

Spusťte sadu Visual Studio ve vytváření a spouštění vaší analyzátor (stiskněte **F5**).  Vzhledem k tomu, že počáteční projekt v **Průzkumníku řešení** je projekt VSIX, spouštění kódu buildy kódu a VSIX a poté spustí Visual Studio s této VSIX nainstalován.  Při spuštění sady Visual Studio tímto způsobem, spustí se odlišné podregistru tak, aby hlavní používání sady Visual Studio nebude mít vliv vaše testování instance při sestavování analyzátorů.  Při prvním spuštění tímto způsobem, Visual Studio nepodporuje několik inicializacích podobně jako když jste první spuštění sady Visual Studio po její instalaci.

Vytvoření projektu konzoly a pak zadejte kód pole do konzoly metodu hlavní aplikace:

```csharp
var b1 = new ImmutableArray<int>();
Console.WriteLine("b1.Length = {0}", b1.Length);
var b2 = new ImmutableArray<int> { 1, 2, 3, 4, 5 };
Console.WriteLine("b2.Length = {0}", b2.Length);
```

Řádky kódu s `ImmutableArray` mít podtržení vlnovkou, protože je potřeba získat neměnné balíček NuGet a přidejte `using` příkaz kódu.  Klikněte na tlačítko správné ukazatel na uzel projektu v **Průzkumníku řešení** a zvolte **spravovat balíčky NuGet...** .  Ve Správci NuGet do vyhledávacího pole zadejte "Immutable" a vyberte položku "System.Collections.Immutable" (nevybírejte "Microsoft.Bcl.Immutable") v levém podokně a stiskněte tlačítko instalovat v pravém podokně.  Instalace balíčku přidá odkaz na odkazy projektu.

Stále vidět red podtržení vlnovkou pod `ImmutableArray`, takže umístit pomocí kurzoru v identifikátor a stiskněte klávesu **CTRL +.** (tečka) se vyvolat nabídce navrhované opravy a vyberte, chcete-li přidat odpovídající `using` příkaz.

**Uložte a ukončete** druhou instanci sady Visual Studio teď můžete uvést do čistého stavu pokračujte.

## <a name="finishing-the-analyzer-using-edit-and-continue"></a>Dokončení pomocí analyzátoru upravit a pokračovat

V první instanci sady Visual Studio, nastavit zarážky na začátku vaše `AnalyzeObjectCreation` metoda stisknutím **F9** s pomocí kurzoru na prvním řádku.

Spuštění vaší Analyzátor znovu s **F5**a ve druhé instance sady Visual Studio znovu otevřete konzolu aplikace vytvořit čas poslední.

Vrátíte na první instance sady Visual Studio u zarážky, protože kompilátoru Roslyn viděli výraz vytvoření objektu a volat do vaší analyzátor.

**Získáte uzlu vytvoření objektu.** Krok přes řádek, který nastaví `objectCreation` proměnné stisknutím **F10**a v **hodnot proměnných** vyhodnocování výrazu `"objectCreation.ToString()"`.  Uvidíte, že proměnná ukazuje na uzel syntaxe je kód `"new ImmutableArray<int>()"`, právě co hledáte.

**Získat ImmutableArray < T\> typ objektu.** Je třeba zkontrolovat, jestli je typ vytváří ImmutableArray.  Nejdřív získat objekt, který reprezentuje tohoto typu.  Zaškrtnete typy použití sémantického modelu, abyste zajistili máte správný typ. a nemáte porovnat řetězec z ToString().  Zadejte následující řádek kódu na konci funkce:

```csharp
var immutableArrayOfTType =
    context.SemanticModel
           .Compilation
           .GetTypeByMetadataName("System.Collections.Immutable.ImmutableArray`1");
```

Obecné typy v metadata s backquotes (') a počet obecné parametry, které označíte.  Proto se nezobrazí "... ImmutableArray\<T > "v názvu metadat.

Sémantický model má celou řadu věcí užitečné v něm, která umožňují klást otázky týkající se symboly, tok dat, proměnné životnost, atd.  Roslyn odděluje syntaxe uzly od sémantického modelu z různých důvodů engineering (výkon, modelování chybný kód atd.).  Chcete kompilace modelu k vyhledání informací obsažených v odkazech na přesné porovnání.

Můžete přetáhnout žlutý provádění ukazatele na levé straně okna editoru.  Přetáhněte až po řádek, který nastaví `objectCreation` proměnnou a krok přes váš nový řádek kódu pomocí **F10**.  Pokud se ukazatel myši nad proměnnou `immutableArrayOfType`, najdete v článku jsme našli přesném typu v sémantického modelu.

**Získáte typ výrazu vytvoření objektu.** "Typ" se používá několika různými způsoby v tomto článku, ale to znamená, že pokud máte "nové Foo" výrazu, potřebujete získat model Foo.  Budete muset získat typ výrazu vytvoření objektu pro zkontrolujte, jestli je ImmutableArray\<T > typu.  Znovu použijte sémantického modelu k získání informací symbol pro typ symbolu (ImmutableArray) ve výrazu vytvoření objektu.  Zadejte následující řádek kódu na konci funkce:

```csharp
var symbolInfo = context.SemanticModel.GetSymbolInfo(objectCreation.Type).Symbol as INamedTypeSymbol;
```

Protože vaše Analyzátor je potřeba zpracovat neúplný nebo nesprávný kód v editoru vyrovnávací paměti (například je chybějící `using` příkaz), byste měli zkontrolovat pro `symbolInfo` se `null`.  Potřebujete získat pojmenovaného typu (INamedTypeSymbol) z objektu symbol informace k dokončení analýzy.

**Porovnejte typy.** Protože je otevřený obecný typ. t, který jsme hledáte a typ v kódu je konkrétní obecného typu, dotazovat informací o symbolu, pro jaký typ se vytvářejí na základě (otevřete obecného typu) a porovnání tohoto výsledek s `immutableArrayOfTType`.  Zadejte na konec metody:

```csharp
if (symbolInfo != null &&
    symbolInfo.ConstructedFrom.Equals(immutableArrayOfTType))
{}
```

**Sestavy diagnostiky.** Vytváření sestav diagnostiky je velmi snadné.  Můžete použít pravidlo vytvořena v šabloně projektu, která je definována před voláním metody inicializovat.  Vzhledem k této situaci v kódu je chyba, můžete změnit na řádek, který inicializovat pravidla nahrazení `DiagnosticSeverity.Warning` (zelený vlnovku) s `DiagnosticSeverity.Error` (červenou vlnovkou).  Zbývající pravidla inicializuje z prostředků, které jste upravili na začátku průvodce.  Potřebujete sestavu umístění vlnovka, což je umístění specifikace typu expresssion vytvoření objektu.  Tento kód v zadejte `if` bloku:

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, objectCreation.Type.GetLocation()));
```

Funkce by měl vypadat takto (například ve formátu jinak):

```csharp
private void AnalyzeObjectCreation(SyntaxNodeAnalysisContext context)
{
    var objectCreation = (ObjectCreationExpressionSyntax)context.Node;
    var immutableArrayOfTType =
        context.SemanticModel
               .Compilation
               .GetTypeByMetadataName(
                   "System.Collections.Immutable.ImmutableArray`1");
    var symbolInfo = context.SemanticModel.GetSymbolInfo(objectCreation.Type).Symbol as
        INamedTypeSymbol;
    if (symbolInfo != null &&
        symbolInfo.ConstructedFrom.Equals(immutableArrayOfTType))
    {
        context.ReportDiagnostic(
            Diagnostic.Create(Rule, objectCreation.Type.GetLocation()));
    }
}
```

Odeberte zarážce tak, aby v tématu pracujete analyzer (a zastavit vrácením první instance sady Visual Studio).  Přetáhněte provádění ukazatel na začátek metody a stiskněte klávesu **F5** pro pokračování v provádění.  Když přepnete zpět na druhou instanci sady Visual Studio, kompilátor začne znovu zkontrolujte kód a zavolá váš analyzátor.  Můžete zobrazit vlnovku pod `ImmutableType<int>`.

## <a name="adding-a-code-fix-for-the-code-issue"></a>Přidání "Kód oprava" pro problém v kódu

Než začnete, zavřete druhou instanci sady Visual Studio a ukončení ladění v první instance sady Visual Studio (kde vyvíjíte nástroje analyzer).

**Přidejte novou třídu.** Pomocí místní nabídky (ukazatel pravé tlačítko) vašeho projektu uzlu v Průzkumníku řešení a zvolte Přidat novou položku.  Přidejte třídu s názvem `BuildCodeFixProvider`.  Tato třída musí být odvozen z `CodeFixProvider`, a budete muset použít **CTRL +.** (tečka) k vyvolání kódu opravu, která přidá správný `using` příkaz.  Tato třída také musí být opatřena poznámkou `ExportCodeFixProvider` atribut a je nutné přidat `using` příkaz přeložit `LanguageNames` výčtu.  Měli byste soubor třídy v ji následujícím kódem:

```csharp
using Microsoft.CodeAnalysis;
using Microsoft.CodeAnalysis.CodeFixes;

namespace ImmutableArrayAnalyzer
{
    [ExportCodeFixProvider(LanguageNames.CSharp)]
    class BuildCodeFixProvider : CodeFixProvider
    {}

```

**Stub out odvozené členy.** Nyní, umístit editor vsuvka identifikátor `CodeFixProvider` a stiskněte klávesu **CTRL +.** (tečka) se zakázaným se implementace pro tato abstraktní základní třída.  Tím se vytvoří vlastnosti a metody pro vás.

**Implementujte vlastnost.** Vyplňte `FixableDiagnosticIds` vlastnosti `get` textu s následujícím kódem:

```csharp
return ImmutableArray.Create(ImmutableArrayAnalyzerAnalyzer.DiagnosticId);
```

Roslyn spojuje diagnostiky a opravy porovnáním tyto identifikátory, které jsou jenom řetězce.  Šablona projektu pro vás vygeneroval ID diagnostiky a můžete ho změnit.  Kód ve vlastnosti právě vrací ID třídy analyzátor.

**Metoda RegisterCodeFixAsync přebírá kontext.** Kontext je důležité, protože opravy kódu můžete použít pro více diagnostiky nebo může být více než jedno vydání na řádek kódu.  Pokud zadáte "context". v těle metody seznamu dokončení IntelliSense si ukážeme některé užitečné členy.  Není CancellationToken člena, který Pokud chcete zobrazit, pokud něco chce zrušit opravu můžete zkontrolovat.  Není členem dokumentu, který má spoustu užitečné členy a umožňuje vám přístup k projektu a řešení objekty modelu.  Je rozpětí člena, který je spuštění a end kód umístění zadaná při hlášené diagnostiky.

**Ujistěte se asynchronní metoda.** První věc, kterou je potřeba udělat je opravte deklarace generovaného metody být `async` metoda.  Neobsahuje opravu kódu stubbing se implementace abstraktní třída `async` – klíčové slovo to i v případě, že metoda vrátí `Task`.

**Získáte kořenu stromu syntaxe.** Chcete-li upravit kód, který potřebujete k vytvoření nového stromu syntaxe se změnami kódu oprava umožňuje.  Je nutné `Document` z kontextu volat `GetSyntaxRootAsync`.  Je to asynchronní metody, proto je neznámý práce získat stromu syntaxe, včetně získávání soubor z disku, jeho analýzu a vytváření že model kódu aplikace Roslyn pro ni.  Rozhraní Visual Studia, která by měla být přizpůsobivý během této doby, které pomocí `async` umožňuje.  Řádek kódu v metodě nahraďte následujícím textem:

```csharp
var root = await context.Document
                        .GetSyntaxRootAsync(context.CancellationToken);
```

**Najít uzel s problém.** Můžete předat podle kontextu rozpětí, ale uzlu, na který zjistíte, nemusí být kód, který budete muset změnit.  Značka span hlášené diagnostiky pouze zadaná pro identifikátor typu (kde vlnovka patřil), ale je třeba nahradit výraz vytvoření celý objekt, včetně `new` – klíčové slovo na začátku a na konci v závorkách.  Přidejte následující kód pro metodu (a použití **CTRL +.** Chcete-li přidat `using` příkaz pro `ObjectCreationExpressionSyntax`):

```csharp
var objectCreation = root.FindNode(context.Span)
                         .FirstAncestorOrSelf<ObjectCreationExpressionSyntax>();
```

**Zaregistrujte opravu žárovky uživatelského rozhraní vašeho kódu.** Při registraci kódu oprava Roslyn automaticky připojuje k sadě Visual Studio žárovky uživatelského rozhraní.  Koncoví uživatelé uvidí, mohou používat **CTRL +.** (period), když vaše analyzátor squiggles chybný `ImmutableArray<T>` použijte konstruktor.  Vzhledem k tomu, že poskytovatel opravy kódu pouze provede, když se vyskytl problém, předpokládejte, že máte výraz vytvoření objektu, který jste hledali.  Z kontextu parametru, můžete zaregistrovat nový kód opravu přidáním následující kód do konce `RegisterCodeFixAsync` metoda:

```csharp
context.RegisterCodeFix(
            CodeAction.Create("Use ImmutableArray<T>.Empty",
                              c => ChangeToImmutableArrayEmpty(objectCreation,
                                                               context.Document,
                                                               c)),
            context.Diagnostics[0]);
```

Je třeba umístit editor vsuvka identifikátor, `CodeAction`, pak použít **CTRL +.** (tečka) Chcete-li přidat odpovídající `using` pro tento typ příkazu.

Pak umístit pomocí kurzoru editoru v `ChangeToImmutableArrayEmpty` identifikátor a používání **CTRL +.** znovu ke generování tato metoda se zakázaným inzerováním za vás.

Tento poslední fragment kódu, který jste přidali zaregistruje kód opravu předáním `CodeAction` a diagnostiky ID druh problému nalezen.  V tomto příkladu není pouze ID diagnostiky, který poskytuje tento kód opraví, tak předáte na první prvek pole ID diagnostiky.  Když vytvoříte `CodeAction`, předáte jako text, který žárovky uživatelského rozhraní se má použít jako popis opravu kódu.  Můžete také předat ve funkci, která přijímá CancellationToken a vrací nový dokument.  Nový dokument má nové stromu syntaxe, která obsahuje vaše opravou kód, který volá `ImmutableArray.Empty`.  Tento fragment kódu použije lambda, takže můžete zavřít přes uzel objectCreation a dokumentu podle kontextu.

**Vytvořte nový stromu syntaxe.** V `ChangeToImmutableArrayEmpty` metoda, jejíž se zakázaným inzerováním jste vygenerovali dříve, zadejte na řádek kódu: `ImmutableArray<int>.Empty;`.  Pokud si zobrazit okno vizualizér syntaxe nástroje uvidíte, že tato syntaxe je SimpleMemberAccessExpression uzlu.  To je, co musí tuto metodu pro vytvoření a návrat do nového dokumentu.

První změnu `ChangeToImmutableArrayEmpty` je přidání `async` před `Task<Document>` protože generátory kódu nelze předpokládat, metoda by měla být asynchronní.

Zadejte text vložte následující kód tak, aby vaše metoda bude vypadat podobně jako následující:

```csharp
private async Task<Document> ChangeToImmutableArrayEmpty(
    ObjectCreationExpressionSyntax objectCreation, Document document,
    CancellationToken c)
{
    var generator = SyntaxGenerator.GetGenerator(document);
    var memberAccess =
        generator.MemberAccessExpression(objectCreation.Type, "Empty");
    var oldRoot = await document.GetSyntaxRootAsync(c);
    var newRoot = oldRoot.ReplaceNode(objectCreation, memberAccess);
    return document.WithSyntaxRoot(newRoot);
}
```

Je nutné uvést editoru pomocí kurzoru do `SyntaxGenerator` identifikátor a používání **CTRL +.** (tečka) Chcete-li přidat odpovídající `using` pro tento typ příkazu.

Tento kód používá `SyntaxGenerator`, který je typu velmi užitečná pro tvorbu nový kód.  Po získání generátor pro dokument, který má problém kódu `ChangeToImmutableArrayEmpty` volání `MemberAccessExpression`, předáním typ, který obsahuje člena chceme přístup a předáním název člena jako řetězec.

V dalším kroku kořene dokumentu načte metodu a protože to může zahrnovat libovolnou práce v případě, že obecné, kód čeká toto volání a předá token zrušení.  Roslyn kód – modely jsou neměnné, jako je práce s řetězec .NET; Při aktualizaci řetězec nového objektu řetězce můžete získat na oplátku.  Při volání `ReplaceNode`, se vraťte do nového kořenového uzlu.  Většina stromu syntaxe je sdílen (protože je neměnné), ale `objectCreation` uzlu se nahradí `memberAccess` uzlu a také všech nadřazených uzlů až kořen stromu syntaxe.

## <a name="trying-your-code-fix"></a>Při operaci kódu oprava

Nyní můžete stisknout **F5** k provedení vaší analyzátor v druhé instance Visual Studio.  Otevřete projekt konzoly, které jste používali před.  Teď byste měli vidět žárovky zobrazí, kde je výraz vytvoření nového objektu pro `ImmutableArray<int>`.  Pokud vyberete **CTRL +.** (období) pak se zobrazí kód opravit a bude zobrazit náhled rozdíl automaticky generovaného kódu v žárovky uživatelského rozhraní.  Roslyn to pro vás vytvoří.

**Tipu pro:** Spusťte druhou instanci sady Visual Studio a nevidíte žárovky s kódu oprava a pak budete muset vymazat mezipaměť součást Visual Studio.  Vymazání mezipaměti vynutí sady Visual Studio znovu zkontrolujte součásti, takže Visual Studio by pak vyzvedávat nejnovější komponenty.  Nejprve vypněte druhou instanci sady Visual Studio.  Potom v Průzkumníku Windows přejděte do vašeho adresáře uživatele (c:\users\\< userid\>) a najděte AppData\Local\Microsoft\VisualStudio\14.0Roslyn\\.  V tomto adresáři odstraňte adresář dílčí ComponentModelCache.  "14" změny na verzi pomocí sady Visual Studio.

## <a name="talk-video-and-finish-code-project"></a>Talk Video a dokončit projektu kódu

Zobrazí se v tomto příkladu vyvíjí a popsané v další [tento talk](http://channel9.msdn.com/events/Build/2015/3-725).  Talk ukazuje analyzátor pracovní a vás provede procesem vytváření ho.

Zobrazí všechny kód dokončení [zde](https://github.com/DustinCampbell/CoreFxAnalyzers/tree/master/Source/CoreFxAnalyzers).  Podsložek DoNotUseImmutableArrayCollectionInitializer a DoNotUseImmutableArrayCtor mít soubor C# pro hledání problémy a soubor C#, který implementuje opravy kódu, které se zobrazí v sadě Visual Studio žárovky uživatelského rozhraní.  Všimněte si, kód dokončení má trochu další abstrakce, aby se zabránilo načítání ImmutableArray\<T > opakovaně typ objektu.  Používá vnořené registrované akce Uložit objekt typu v kontextu, který je k dispozici vždy, když dílčích akcí (analyzovat vytvoření objektu a analyzovat kolekce inicializacích) provést.

## <a name="see-also"></a>Viz také

* [\\Talk \Build 2015](http://channel9.msdn.com/events/Build/2015/3-725)
* [Dokončený kód na Githubu](https://github.com/DustinCampbell/CoreFxAnalyzers/tree/master/Source/CoreFxAnalyzers)
* [Několik příkladů na Githubu, které jsou seskupeny do tři druhy analyzátorů](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)
* [Další dokumentace na webu GitHub operačních systémů](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
* [Pravidla FxCop implementuje pomocí analyzátorů Roslyn na Githubu](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)
