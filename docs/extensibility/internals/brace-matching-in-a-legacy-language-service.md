---
title: Související závorky ve službě jazyk starší | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- brace matching
- language services [managed package framework], brace matching
ms.assetid: 4e3d0a70-f22f-49dd-92d8-edf48ab62b52
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c9df179d6f5b1bd6d7b9f2c827568b6954860b81
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131960"
---
# <a name="brace-matching-in-a-legacy-language-service"></a>Související závorky ve službě jazyk starší verze
Odpovídající složené závorce pomáhá vývojářům sledovat jazykové elementy, které se provést společně, jako je například kulaté závorky a složené závorky. Vývojář zadá pravé složené závorce, je označený levá složená závorka.  
  
 Dvě nebo tři společně se vyskytující prvky, jako páry a triples může odpovídat. Triples jsou sady tři společně se vyskytující prvky. V jazyce C#, například `foreach` příkaz formulářů triple: "`foreach()`","`{`", a "`}`". Všechny tři prvky se zvýrazní, když je zadán složená závorka.  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace o nový způsob implementace závorky, najdete v tématu [návod: zobrazení odpovídající složené závorky](../../extensibility/walkthrough-displaying-matching-braces.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat co nejdříve editoru nové rozhraní API. Tím zvýšit výkon služby jazyk a umožňují využívat výhod nových funkcí editoru.  
  
 <xref:Microsoft.VisualStudio.Package.AuthoringSink> Třída podporuje obě páry a triples s <xref:Microsoft.VisualStudio.Package.AuthoringSink.MatchPair%2A> a <xref:Microsoft.VisualStudio.Package.AuthoringSink.MatchTriple%2A> metody.  
  
## <a name="implementation"></a>Implementace  
 Služba jazyka musí identifikovat všechny odpovídající elementy v jazyce a vyhledejte všechny odpovídající páry. To se obvykle provádí implementací <xref:Microsoft.VisualStudio.Package.IScanner> zjištění odpovídající jazyk a pak pomocí <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda tak, aby odpovídaly elementy.  
  
 <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Metoda volá skeneru tokenizaci řádku a vrátíte se token těsně před pomocí kurzoru. Skeneru označuje, že element pár jazyk má byla nalezena nastavením hodnotu tokenu aktivační událost <xref:Microsoft.VisualStudio.Package.TokenTriggers> na aktuální tokenu. <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Volání metod <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> metoda, která volá <xref:Microsoft.VisualStudio.Package.LanguageService.BeginParse%2A> metoda s hodnotou Důvod analýzy <xref:Microsoft.VisualStudio.Package.ParseReason> najít odpovídající element jazyka. Když se najde odpovídající element jazyk, se zvýrazněnou obou elementů.  
  
 Úplný popis toho, jak psát složená závorka aktivuje zvýraznění závorek, najdete v části "Příklad analyzovat operace" v tématu [analyzátoru služby starší verze jazyka a skener](../../extensibility/internals/legacy-language-service-parser-and-scanner.md).  
  
## <a name="enabling-support-for-brace-matching"></a>Povolení podpory pro párování závorek  
 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> Atribut lze nastavit `MatchBraces`, `MatchBracesAtCaret`, a `ShowMatchingBrace` pojmenované parametry, které nastavit odpovídající vlastnosti <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídy. Uživatel můžete také nastavit vlastnosti předvoleb jazyka.  
  
|Položky registru|Vlastnost|Popis|  
|--------------------|--------------|-----------------|  
|`MatchBraces`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableMatchBraces%2A>|Umožňuje závorky|  
|`MatchBracesAtCaret`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableMatchBracesAtCaret%2A>|Umožňuje závorky jako přesune pomocí kurzoru.|  
|`ShowMatchingBrace`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A>|Označuje odpovídajících složených závorek.|  
  
## <a name="matching-conditional-statements"></a>Odpovídající podmíněné příkazy  
 Podmíněné příkazy, se může shodovat, jako `if`, `else if`, a `else`, nebo `#if`, `#elif`, `#else`, `#endif`, stejným způsobem jako odpovídající oddělovače. Můžete podtřídami <xref:Microsoft.VisualStudio.Package.AuthoringSink> třídy a zadejte metodu, která můžete přidat text zahrnuje i oddělovače do interní pole odpovídajících elementy.  
  
## <a name="setting-the-trigger"></a>Nastavení aktivační události  
 Následující příklad ukazuje, jak zjistit odpovídající závorky, složené závorky a hranatých závorkách a nastavení aktivační událost pro něj v skeneru. <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Metodu <xref:Microsoft.VisualStudio.Package.Source> třída zjišťuje aktivační události a volá analyzátor najít odpovídající pár (viz část "Hledání shodu" v tomto tématu). V tomto příkladu je pouze pro ilustraci. Předpokládá, že skener obsahuje metodu `GetNextToken` který identifikuje a vrátí tokeny z řádku textu.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestScanner : IScanner  
    {  
        private const string braces = "()[]{}";  
        private Lexer lex;  
  
        public bool ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo,  
                                                   ref int state)  
        {  
            bool foundToken = false;  
            string token = lex.GetNextToken();  
            if (token != null)  
            {  
                foundToken = true;  
                char firstChar = token[0];  
                if (Char.IsPunctuation(firstChar) && token.Length > 0)  
                {  
                    if (braces.IndexOf(firstChar) != -1)  
                    {  
                        tokenInfo.Trigger = TokenTriggers.MatchBraces;  
                    }  
                }  
            }  
            return foundToken;  
        }  
```  
  
## <a name="matching-the-braces"></a>Odpovídající složené závorky  
 Zde je příklad zjednodušené pro porovnávání {} elementy jazyka, () a [] a jejich rozpětí k přidání <xref:Microsoft.VisualStudio.Package.AuthoringSink> objektu. Tento přístup není doporučený postup k analýze zdrojového kódu; je pouze pro ilustraci.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class Parser  
    {  
         private IList<TextSpan[]> m_braces;  
         public IList<TextSpan[]> Braces  
         {  
             get { return m_braces; }  
         }  
         private void AddMatchingBraces(TextSpan braceSpan1, TextSpan braceSpan2)  
         {  
             if IsMatch(braceSpan1, braceSpan2)  
                 m_braces.Add(new TextSpan[] { braceSpan1, braceSpan2 });  
         }  
  
         private bool IsMatch(TextSpan braceSpan1, TextSpan braceSpan2)  
         {  
             //definition for matching here  
          }  
    }  
  
    public class TestLanguageService : LanguageService  
    {  
         Parser parser = new Parser();  
         Source source = (Source) this.GetSource(req.FileName);  
  
         private AuthoringScope ParseSource(ParseRequest req)  
         {  
             if (req.Sink.BraceMatching)  
             {  
                 if (req.Reason==ParseReason.MatchBraces)  
                 {  
                     foreach (TextSpan[] brace in parser.Braces)  
                     {  
                         req.Sink.MatchPair(brace[0], brace[1], 1);  
                     }  
                 }  
             }  
             return new TestAuthoringScope();  
         }  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Funkce služby starší verze jazyka](../../extensibility/internals/legacy-language-service-features1.md)   
 [Analyzátor a skener služby starší verze jazyka](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)