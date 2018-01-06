---
title: "Informace o parametrech v Service2 jazyk starší verze | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliSense, Parameter Info tool tip
- language services [managed package framework], IntelliSense Parameter Info
- Parameter Info (IntelliSense), supporting in language services [managed package framework]
ms.assetid: a117365d-320d-4bb5-b61d-3e6457b8f6bc
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 69c65fa2691f71b3bb7f115b771a0de83d543f03
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="parameter-info-in-a-legacy-language-service"></a>Informace o parametrech ve službě jazyk starší verze
Informace o parametrech IntelliSense je popisek, který se zobrazí podpis metody, když uživatel zadá seznam parametrů počáteční znak (obvykle otevřené závorky) pro seznam parametrů metody. Protože každý parametr zadán, a je zadán parametr oddělovače (obvykle čárkou), popisek je aktualizována na další parametr tučným písmem.  
  
 Třídy spravované balíčků framework (MPF) poskytuje podporu pro správu informace o parametrech popisek. Analyzátor musí zjistit parametr start parametru v dalším kroku, a parametr koncové znaky ale musíte zadat seznam metoda podpisů a jejich přidružené parametry.  
  
 Starší verze jazyka služby jsou implementovány jako součást VSPackage, ale novější způsob implementace funkce služby jazyk je použití MEF rozšíření. Další informace naleznete v tématu [rozšíření pro Editor a služby, jazyk](../../extensibility/extending-the-editor-and-language-services.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat co nejdříve editoru nové rozhraní API. Tím zvýšit výkon služby jazyk a umožňují využívat výhod nových funkcí editoru.  
  
## <a name="implementation"></a>Implementace  
 Analyzátor měli nastavit hodnotu aktivační událost <xref:Microsoft.VisualStudio.Package.TokenTriggers> nastavená, pokud najde parametr seznamu úvodní znak (často otevřené závorky). Je potřeba nastavit <xref:Microsoft.VisualStudio.Package.TokenTriggers> aktivovat, pokud najde parametr oddělovače (často čárkou). To způsobí, že informace o parametrech popisek, který se aktualizovat a zobrazit další parametr tučným písmem. Analyzátor měli nastavit hodnotu aktivační událost <xref:Microsoft.VisualStudio.Package.TokenTriggers> při Pokud najde parametr seznamu koncový znak (často zavřít závorky).  
  
 <xref:Microsoft.VisualStudio.Package.TokenTriggers> Aktivační událost hodnota zahájí volání <xref:Microsoft.VisualStudio.Package.Source.MethodTip%2A> metoda, která volá <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> metoda analyzátor pomocí analýzy důvodu <xref:Microsoft.VisualStudio.Package.ParseReason>. Když analyzátor zjistí, že identifikátor před seznam parametrů počáteční znak název rozpoznaný metody, vrátí odpovídající metoda podpisy v seznamu <xref:Microsoft.VisualStudio.Package.AuthoringScope> objektu. Pokud nebyly nalezeny žádné metoda podpisy, zobrazí se informace o parametrech popisek podpisem první v seznamu. Tento popis je pak aktualizovat, protože je zadán více podpis. Pokud je zadán parametr seznamu koncový znak, odebere se ze zobrazení informace o parametrech popisek.  
  
> [!NOTE]
>  Chcete, aby je ve správném formátu popisek informace o parametrech, je nutné přepsat vlastnosti na <xref:Microsoft.VisualStudio.Package.Methods> třída k poskytování požadované znaky. Základní <xref:Microsoft.VisualStudio.Package.Methods> třída předpokládá C# – styl podpis metody. Najdete v článku <xref:Microsoft.VisualStudio.Package.Methods> třídy pro informace o tom, jak to lze provést.  
  
## <a name="enabling-support-for-the-parameter-info"></a>Povolení podpory pro informace o parametrech  
 Pro podporu popisy tlačítek informace o parametrech, musíte nastavit `ShowCompletion` s názvem parametru <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> k `true`. Služba jazyka čte hodnotu této položky registru z <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> vlastnost.  
  
 Kromě toho <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ParameterInformation%2A> musí být nastavena na `true` pro informace o parametrech popisek zobrazený.  
  
### <a name="example"></a>Příklad  
 Zde je příklad zjednodušené detekovat znaky seznamu parametr a nastavení odpovídající aktivačních událostí. V tomto příkladu je pouze pro ilustraci. Předpokládá, že skener obsahuje metodu `GetNextToken` který identifikuje a vrátí tokeny z řádku textu. Ukázkový kód jednoduše nastaví aktivačních událostí, vždy, když se zobrazí správný druh znak.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestScanner : IScanner  
    {  
        private Lexer lex;  
        private const char parameterListStartChar = '(';  
        private const char parameterListEndChar   = ')';  
        private const char parameterNextChar      = ',';  
  
        public bool ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo,  
                                                   ref int state)  
        {  
            bool foundToken = false  
            string token = lex.GetNextToken();  
            if (token != null)  
            {  
                foundToken = true;  
                char c = token[0];  
                if (Char.IsPunctuation(c))  
                {  
                    tokenInfo.Type = TokenType.Operator;  
                    tokenInfo.Color = TokenColor.Keyword;  
                    tokenInfo.EndIndex = index;  
  
                    if (c == parameterListStartChar)  
                    {  
                        tokenInfo.Trigger |= TokenTriggers.ParameterStart;  
                    }  
                    else if (c == parameterListNextChar)  
                    {  
                        tokenInfo.Trigger |= TokenTriggers.ParameterNext;  
                    else if (c == parameterListEndChar)  
                    {  
                        tokenInfo.Trigger |= TokenTriggers.ParameterEnd;  
                    }  
                }  
            return foundToken;  
        }  
    }  
}  
```  
  
## <a name="supporting-the-parameter-info-tooltip-in-the-parser"></a>Podpora popisek parametr informace o analyzátoru  
 <xref:Microsoft.VisualStudio.Package.Source> Třída provádí některé předpoklady o obsah <xref:Microsoft.VisualStudio.Package.AuthoringScope> a <xref:Microsoft.VisualStudio.Package.AuthoringSink> třídy, když se zobrazí a aktualizovat informace o parametrech popisek.  
  
-   Je zadána analyzátor <xref:Microsoft.VisualStudio.Package.ParseReason> Pokud je zadán parametr seznamu úvodní znak.  
  
-   V umístění <xref:Microsoft.VisualStudio.Package.ParseRequest> objekt je ihned po počáteční seznam parametrů znak. Analyzátor musí shromažďovat podpisy k dispozici na všech deklarací metody, které pozice a uložit je do seznamu ve vaší verzi <xref:Microsoft.VisualStudio.Package.AuthoringScope> objektu. Tento seznam obsahuje název metody, metoda typu (nebo návratový typ) a seznam možných parametrů. Tento seznam je později hledán podpis metody nebo podpisy zobrazíte v popisu tlačítka informace o parametrech.  
  
 Analyzátor musí pak analyzovat řádku určeného <xref:Microsoft.VisualStudio.Package.ParseRequest> objekt získat název metody, který vkládáte, a také jak daleko podél uživatel je v zadáte parametry. Toho dosahuje pomocí předání název metody, která <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartName%2A> metodu <xref:Microsoft.VisualStudio.Package.AuthoringSink> objekt a potom volání <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartParameters%2A> metoda spouštění seznam parametrů znak analyzovat, volání <xref:Microsoft.VisualStudio.Package.AuthoringSink.NextParameter%2A> metoda při seznam parametrů Další znak je Analyzovaná a nakonec volání <xref:Microsoft.VisualStudio.Package.AuthoringSink.EndParameters%2A> metoda, pokud je parametr seznamu koncový znak je analyzována. Výsledky volání těchto metod jsou používány <xref:Microsoft.VisualStudio.Package.Source> třída aktualizovat informace o parametrech popisek správně.  
  
### <a name="example"></a>Příklad  
 Tady je na řádku textu, které může uživatel zadat. Čísla pod na řádku uveďte, který krok je provedenou analyzátor na této pozici v řádku (za předpokladu, že analýzy přesune zleva doprava). Zde předpokladem je, že všechno před řádek již analýze metoda signatury, včetně podpis metody "testfunc".  
  
```  
testfunc("a string",3);  
     ^^          ^ ^  
     12          3 4  
```  
  
 Kroky, které analyzátor přijímá jsou uvedeny níže:  
  
1.  Volání analyzátor <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartName%2A> s textem "testfunc".  
  
2.  Volání analyzátor <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartParameters%2A>.  
  
3.  Volání analyzátor <xref:Microsoft.VisualStudio.Package.AuthoringSink.NextParameter%2A>.  
  
4.  Volání analyzátor <xref:Microsoft.VisualStudio.Package.AuthoringSink.EndParameters%2A>.