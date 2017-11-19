---
title: "Analyzátor jazyka starší verze služby a skener | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsers, language services [managed package framework]
- language services [managed package framework], Parsers
ms.assetid: 1ac3de27-a23b-438d-9593-389e45839cfa
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 30453237dcd95607a4f3524f115d16bc1cf4859a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="legacy-language-service-parser-and-scanner"></a>Analyzátor jazyka starší verze služby a skener
Analyzátor jsou srdcem služba jazyka. Třídy jazyka spravované Framework balíčku (MPF) vyžadují analyzátoru jazyka pro výběr informací o kódu se zobrazí. Analyzátor odděluje text do lexikální tokenů a pak identifikuje těchto tokenů podle typu a funkce.  
  
## <a name="discussion"></a>Diskusní  
 Toto je metoda C#.  
  
```csharp  
namespace MyNamespace  
{  
    class MyClass  
    {  
        public void MyFunction(int arg1)  
        {  
            int var1 = arg1;  
        }  
    }  
}  
```  
  
 V tomto příkladu jsou tokeny slova a interpunkčních znamének. Druhy tokeny jsou následujícím způsobem.  
  
|Název tokenu|Typ tokenu|  
|----------------|----------------|  
|obor názvů, třídy, veřejné, void, int|klíčové slovo|  
|=|– operátor|  
|{ } ( ) ;|Oddělovač|  
|MyNamespace, MyClass, MyFunction, arg1, var1|identifikátor|  
|MyNamespace|– obor názvů|  
|MyClass|třída|  
|MyFunction|– metoda|  
|arg1|parametr|  
|var1|místní proměnné|  
  
 Role Analyzátor je identifikace tokenů. Některé tokenů může mít více než jeden typ. Poté, co analyzátor má označený tokeny, služba jazyka můžete použít informace, které poskytují užitečné funkce, jako je zvýraznění syntaxe složených závorek odpovídající a činnosti IntelliSense.  
  
## <a name="types-of-parsers"></a>Typy analyzátory  
 Analyzátor jazyka služby není stejný jako analyzátor používá jako součást kompilátor. Tento druh analyzátor však musí používat skener a analyzátor, stejným způsobem jako kompilátoru analyzátor.  
  
-   Skener slouží k identifikaci typy tokenů. Tyto informace slouží pro zvýraznění syntaxe a rychle identifikace tokenu typy, které můžou aktivovat jiné operace, například závorky. Tento skener je reprezentována <xref:Microsoft.VisualStudio.Package.IScanner> rozhraní.  
  
-   Analyzátor se používá k popisu funkce a obor tokenů. Tyto informace se používá v operacích IntelliSense pro identifikaci prvků jazyka, jako je například metody, proměnné, parametry a deklarace a pro poskytování seznam členů a podpisy metoda na základě kontextu. Tento analyzátor slouží také najít odpovídající element dvojice jazyků, jako je například složené závorky a kulaté závorky. Tento analyzátor přistupuje prostřednictvím <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda v <xref:Microsoft.VisualStudio.Package.LanguageService> třídy.  
  
 Jak implementovat skeneru a analyzátor jazyka služby je na vás. K dispozici několik prostředků které popisují, jak analyzátory fungují a jak psát vlastní analyzátor. Kromě toho jsou k dispozici několik bezplatná a komerční produkty, které pomoci při vytváření analyzátor.  
  
### <a name="the-parsesource-parser"></a>Analyzátor ParseSource  
 Na rozdíl od analyzátor, který se používá jako součást kompilátor (kde tokeny se převedou na některé forma spustitelného kódu) je možné volat služby analyzátor jazyka mnoha různých důvodů a v mnoha různých kontextech. Jak implementovat tuto metodu v <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda v <xref:Microsoft.VisualStudio.Package.LanguageService> třída závisí na vás. Je důležité mít na paměti, <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda může být volána v vlákna na pozadí.  
  
> [!CAUTION]
>  <xref:Microsoft.VisualStudio.Package.ParseRequest> Struktura obsahuje odkaz na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> objektu. To <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> objekt nelze použít ve vlákně na pozadí. Ve skutečnosti mnoho ze základních tříd sady MPF nelze použít ve vlákně na pozadí. Patří mezi ně <xref:Microsoft.VisualStudio.Package.Source>, <xref:Microsoft.VisualStudio.Package.ViewFilter>, <xref:Microsoft.VisualStudio.Package.CodeWindowManager> třídy a jiné třídě, která přímo nebo nepřímo komunikuje s zobrazení.  
  
 Tento analyzátor obvykle analyzuje celý zdrojový soubor první čas se označuje jako nebo když analýzy důvodu hodnotu <xref:Microsoft.VisualStudio.Package.ParseReason> je zadána. Následující volání <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda zpracování malou část toho kód Analyzovaná a mohou být provedeny mnohem rychleji pomocí výsledky předchozí operace úplnou analýzu. <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> Metoda komunikuje výsledky analýzy operace prostřednictvím <xref:Microsoft.VisualStudio.Package.AuthoringSink> a <xref:Microsoft.VisualStudio.Package.AuthoringScope> objekty. <xref:Microsoft.VisualStudio.Package.AuthoringSink> Objekt se používá ke shromažďování informací z určitého důvodu analýzy, například informace o rozsahy odpovídajících složených závorek nebo metoda podpisy, které mají seznamy parametrů. <xref:Microsoft.VisualStudio.Package.AuthoringScope> Poskytuje kolekce deklarace a metoda podpisy a také podporu přejít na rozšířených upravit možnost (**přechod na definici**, **přejít na deklaraci**, **přejděte na Referenční**).  
  
### <a name="the-iscanner-scanner"></a>Skener IScanner  
 Musíte také implementovat skener, který implementuje <xref:Microsoft.VisualStudio.Package.IScanner>. Ale vzhledem k tomu, že tento skener funguje na základě řádek po řádku prostřednictvím <xref:Microsoft.VisualStudio.Package.Colorizer> třídy, je obvykle jednodušší implementaci. Na začátku každého řádku, MPF dává <xref:Microsoft.VisualStudio.Package.Colorizer> hodnota sloužící jako proměnné stavu, který je předán skeneru třídy. Na konci každého řádku vrátí skeneru proměnnou aktualizovaný stav. Sady MPF ukládá do mezipaměti tyto informace stav pro každý řádek tak, aby skeneru můžete spustit analýza z jakékoli řádku bez nutnosti spouštět na začátku zdrojový soubor. Tato rychlá kontrola jeden řádek umožňuje editoru k poskytnutí zpětné vazby rychlé uživateli.  
  
## <a name="parsing-for-matching-braces"></a>Analýza pro odpovídající složené závorky  
 Tento příklad zobrazuje tok řízení pro odpovídající pravé složené závorce, který má uživatel zadal. V tomto procesu skener, který se používá pro zabarvení slouží také k určení typu token a zda token můžete aktivovat operace porovnání závorek. Pokud je nalezen aktivační událost, <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda je volána k vyhledání odpovídajících složených závorek. Nakonec se zvýrazněnou dva složené závorky.  
  
 I když složené závorky se používají v názvech aktivační události a analyzovat z důvodů, tento proces se neomezuje na skutečné složené závorky. Jakýkoli pár znaků, které zadaných jako odpovídající spárujte je podporována. Mezi příklady patří (a), \< a >, a [a].  
  
 Předpokládejme, že služba jazyk podporuje odpovídající složené závorky.  
  
1.  Uživatel zadá uzavírací složená závorka (}).  
  
2.  Na pozici kurzoru ve zdrojovém souboru se vloží složené závorky a kurzor je rozšířená o jednu.  
  
3.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Metoda v <xref:Microsoft.VisualStudio.Package.Source> třída je volán s typem složená závorka.  
  
4.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Volání metod <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> metoda v <xref:Microsoft.VisualStudio.Package.Source> třídy se získat token na pozici těsně před aktuálním umístěním kurzoru. Tento token odpovídá typu pravé složené závorce).  
  
    1.  <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> Volání metod <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> metodu <xref:Microsoft.VisualStudio.Package.Colorizer> objekt, který chcete získat všechny tokeny na aktuálním řádku.  
  
    2.  <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> Volání metod <xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> metodu <xref:Microsoft.VisualStudio.Package.IScanner> objekt s textem aktuálního řádku.  
  
    3.  <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> Metoda opakovaně volá <xref:Microsoft.VisualStudio.Package.IScanner.ScanTokenAndProvideInfoAboutIt%2A> metodu <xref:Microsoft.VisualStudio.Package.IScanner> objekt, který chcete shromažďovat všechny tokeny z aktuálního řádku.  
  
    4.  <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> Metoda volá metodu privátní <xref:Microsoft.VisualStudio.Package.Source> třídy získat token, který obsahuje požadované poloze a předává v seznamu tokenů získané z <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> metoda.  
  
5.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Metoda vyhledá token aktivační událost příznak <xref:Microsoft.VisualStudio.Package.TokenTriggers> na token, který je vrácen z <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> metoda; to znamená na token, který představuje pravé složené závorce).  
  
6.  Pokud aktivační událost příznak <xref:Microsoft.VisualStudio.Package.TokenTriggers> nenajde, <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> metoda v <xref:Microsoft.VisualStudio.Package.Source> třídy se nazývá.  
  
7.  <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> Metoda spustí operaci analýzy s hodnotou Důvod analýzy <xref:Microsoft.VisualStudio.Package.ParseReason>. Tuto operaci výsledku volání <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metodu <xref:Microsoft.VisualStudio.Package.LanguageService> třída. Pokud je povolena analýza asynchronní, volání na <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda proběhne vlákna na pozadí.  
  
8.  Při dokončení operace analýzy, obslužné rutiny interní dokončení (také známé jako metody zpětného volání) s názvem `HandleMatchBracesResponse` je volána <xref:Microsoft.VisualStudio.Package.Source> třídy. Toto volání se provádí automaticky pomocí <xref:Microsoft.VisualStudio.Package.LanguageService> základní třídy, ne podle analyzátor.  
  
9. `HandleMatchBracesResponse` Metoda získá seznam rozsahy z <xref:Microsoft.VisualStudio.Package.AuthoringSink> objekt, který je uložen v <xref:Microsoft.VisualStudio.Package.ParseRequest> objektu. (Je rozpětí <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> struktura, která určuje rozsah řádků a znaků ve zdrojovém souboru.) Tento seznam rozsahy obvykle obsahuje dva rozsahy, jednu pro počáteční a koncovou složené závorky.  
  
10. `HandleBracesResponse` Volání metod <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A> metodu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> objekt, který je uložen v <xref:Microsoft.VisualStudio.Package.ParseRequest> objektu. To ukazuje dané rozpětí.  
  
11. Pokud <xref:Microsoft.VisualStudio.Package.LanguagePreferences> vlastnost <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> je povoleno, `HandleBracesResponse` metoda získá text, který je zahrnut ve odpovídající značky span a zobrazuje prvních 80 znaků tohoto rozpětí ve stavovém řádku. To funguje nejlíp, pokud <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda obsahuje element jazyk, který doprovází odpovídající pár. Další informace najdete v tématu <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> vlastnost.  
  
12. V.  
  
### <a name="summary"></a>Souhrn  
 Odpovídající složené závorky operace je většinou omezují na jednoduchý páry elementů jazyka. Složitější prvky, jako jsou například odpovídající triples ("`if(...)`","`{`"a"`}`", nebo "`else`","`{`"a"`}`"), můžete mít zvýrazněná v rámci aplikace word dokončení operace. Například když je slovo "else" dokončení shody "`if`" může mít zvýrazněná příkaz. Kdyby řadu `if` / `else if` příkazy, všechny z nich může mít zvýrazněná pomocí mechanizmu stejné jako odpovídající složené závorky. <xref:Microsoft.VisualStudio.Package.Source> Základní třída již podporuje, následujícím způsobem: skeneru musí vrátit hodnotu tokenu aktivační událost <xref:Microsoft.VisualStudio.Package.TokenTriggers> kombinaci s hodnotou aktivační událost <xref:Microsoft.VisualStudio.Package.TokenTriggers> pro daný token, který je před pozice kurzoru.  
  
 Další informace najdete v tématu [odpovídající složené závorce ve službě jazyk starší](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md).  
  
## <a name="parsing-for-colorization"></a>Analýza pro zabarvení  
 Barevné zdrojový kód je jednoduché, stačí určit typ tokenu a zpět barva informací o typu. <xref:Microsoft.VisualStudio.Package.Colorizer> Třída slouží jako zprostředkovatel mezi editoru a skeneru lze zadat barvu informace o každé token. <xref:Microsoft.VisualStudio.Package.Colorizer> Třídy používá <xref:Microsoft.VisualStudio.Package.IScanner> objekt při barevné řádku a také získat informace o stavu pro všechny řádky v zdrojový soubor. Do tříd služby jazykové sady MPF <xref:Microsoft.VisualStudio.Package.Colorizer> třída nemá přepsat, protože komunikuje s skeneru pouze prostřednictvím <xref:Microsoft.VisualStudio.Package.IScanner> rozhraní. Zadáte objektu, který implementuje <xref:Microsoft.VisualStudio.Package.IScanner> rozhraní přepsáním <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> metodu <xref:Microsoft.VisualStudio.Package.LanguageService> třídy.  
  
 <xref:Microsoft.VisualStudio.Package.IScanner> Skener je zadána řádek zdrojového kódu pomocí <xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> metoda. Volání <xref:Microsoft.VisualStudio.Package.IScanner.ScanTokenAndProvideInfoAboutIt%2A> metoda jsou opakována až do řádku vyčerpání tokenů získat další token v řádku. Sady MPF pro zabarvení, zpracovává všechny zdrojového kódu jako pořadí řádků. Skeneru proto musí být schopen zvládnout se zdrojem přicházející na to jako řádky. Kromě toho kterýkoli řádek se dá předat do skeneru kdykoli a pouze záruku je, že skeneru obdrží z řádku před řádek chystáte zkontrolovat proměnné stavu.  
  
 <xref:Microsoft.VisualStudio.Package.Colorizer> Třída slouží také k identifikaci tokenu aktivační události. Tyto triggery říct MPF, že konkrétní token můžete zahájit složitější operace, jako je například word dokončení nebo odpovídající složené závorky. Vzhledem k tomu, že určíte takové aktivační události musí být rychlé a v libovolném umístění se musí vyskytovat, skeneru je nejvhodnější pro tuto úlohu.  
  
 Další informace najdete v tématu [syntaxe barevné ve službě jazyk starší](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md).  
  
## <a name="parsing-for-functionality-and-scope"></a>Analýza pro funkce a obor  
 Analýza pro funkce a obor náročný více než jen identifikace typy tokenů, které se vyskytují. Analyzátor má k identifikaci pouze typ tokenu, ale také funkce, pro který se používá token. Například identifikátor je právě název, ale ve vašem jazyce, může být identifikátor název třídy, obor názvů, metoda nebo proměnnou, v závislosti na kontextu. Obecné typ tokenu může být identifikátor, ale identifikátor mohou mít i další významy, a to v závislosti na tom, co je a je-li definován. Toto identifikační vyžaduje analyzátor tak, aby měl více rozsáhlé znalosti o jazyce, který je při analýze. To je, kdy <xref:Microsoft.VisualStudio.Package.AuthoringSink> třída dodává. <xref:Microsoft.VisualStudio.Package.AuthoringSink> Třída shromažďuje informace o identifikátory, metody, odpovídající dvojice jazyků (například složené závorky a kulaté závorky) a jazyk triples (podobně jako dvojice jazyků s tím rozdílem, že existují tři části, například "`foreach()`" "`{`"a"`}`"). Kromě toho můžete přepsat <xref:Microsoft.VisualStudio.Package.AuthoringSink> třídy pro podporu identifikační kód, který je používán časná ověření zarážky tak, aby ladicí program nemá načíst, a **automobily** ladění okna, která zobrazuje místní parametry a proměnné automaticky při program je laděné a vyžaduje analyzátor k identifikaci příslušné místní proměnné a parametry kromě těch, které představuje ladicího programu.  
  
 <xref:Microsoft.VisualStudio.Package.AuthoringSink> Objekt předaný analyzátor jako součást <xref:Microsoft.VisualStudio.Package.ParseRequest> objekt a novou <xref:Microsoft.VisualStudio.Package.AuthoringSink> objekt je vytvořena pokaždé, když nový <xref:Microsoft.VisualStudio.Package.ParseRequest> je vytvořen objekt. Kromě toho <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda musí vrátit <xref:Microsoft.VisualStudio.Package.AuthoringScope> objektu, který slouží ke zpracování různých operací IntelliSense. <xref:Microsoft.VisualStudio.Package.AuthoringScope> Objekt udržuje seznam pro deklarace a seznam metod, buď z nich je vyplněný, v závislosti na důvod k analýze. <xref:Microsoft.VisualStudio.Package.AuthoringScope> Třídu, musí být implementována.  
  
## <a name="see-also"></a>Viz také  
 [Implementace služby jazyk starší verze](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [Přehled služby starší verze jazyka](../../extensibility/internals/legacy-language-service-overview.md)   
 [Syntaxe barevné ve službě jazyk starší verze](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)   
 [Související závorky ve službě jazyk starší verze](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)