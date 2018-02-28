---
title: "Výrazy v ladicím programu | Microsoft Docs"
ms.custom: 
ms.date: 02/07/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.expressions
helpviewer_keywords:
- expressions [debugger]
- debugging [Visual Studio], expressions
- expression evaluation, debugger evaluator
- native expression evaluation
- expression evaluators
- debugger, evaluating expressions
- debugging [Visual Studio], expression evaluation
- debugging [Visual Studio], variable evaluation
ms.assetid: 70f9b531-44c7-4d77-980d-5eddbf2bff41
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fd1a477a7d02171eecea51b26f796d9c958c09eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="expressions-in-the-visual-studio-debugger"></a>Výrazy v ladicím programu sady Visual Studio
Zahrnuje vyhodnocovače výrazů, které fungují při zadání výrazu v ladicím programu sady Visual Studio **QuickWatch** dialogové okno, **sledovat** okno, nebo **Immediate** okno. Vyhodnocovače výrazů jsou také v práci v **zarážky** okno a mnoho dalších místech ladicího programu.
  
 Následujících oddílech najdete podrobnosti o výrazy v různých jazycích.  
  
## <a name="f-expressions-are-not-supported"></a>F # výrazy nejsou podporovány.  
 F # výrazy nejsou rozpoznány. Pokud ladíte F # – kód, budete muset převede výrazech do jazyka C# – syntaxe před vstupem do ladicí program okno nebo dialogové okno pole výrazů. Když jste přeložit výrazy z F # pro C#, nezapomeňte mějte na paměti, že C# používá `==` operátor k testování rovnosti, zatímco F # používá jedné `=`.  
  
## <a name="c-expressions"></a>Výrazy jazyka C++  
 Informace o používání kontextu operátory s výrazy v jazyce C++ najdete v tématu [kontextu – operátor (C++)](../debugger/context-operator-cpp.md).  
  
### <a name="unsupported-expressions-in-c"></a>Nepodporované výrazy v jazyce C++  
  
#### <a name="constructors-destructors-and-conversions"></a>Konstruktory, destruktory a převody  
 Pro objekt, nelze volat konstruktor nebo destruktor, explicitně nebo implicitně. Následující výraz například explicitně volá konstruktor a výsledkem chybová zpráva:  
  
```C++  
my_date( 2, 3, 1985 )  
```  
  
 Pokud cílovým serverem převod je třída, nelze volat funkci pro převod. Takový převod zahrnuje vytváření objektu. Například pokud `myFraction` je instance `CFraction`, která definuje funkce operátor převodu `FixedPoint`, následující výraz vede k chybě:  
  
```C++  
(FixedPoint)myFraction  
```  
  
 Nelze volat nové nebo odstranit operátory. Například následující výraz není podporován:  
  
```C++  
new Date(2,3,1985)  
```  
  
#### <a name="preprocessor-macros"></a>Makra preprocesoru  
 Makra preprocesoru nejsou podporovány v ladicím programu. Například pokud konstanta `VALUE` je deklarován jako: `#define VALUE 3`, nemůžete použít `VALUE` v **sledovat** okno. K tomuto omezení vyhnout, měli byste nahradit `#define`je s výčty a funguje kdykoli je to možné.  
  
### <a name="using-namespace-declarations"></a>pomocí deklarace oborů názvů  
 Nemůžete použít `using namespace` deklarace.  Chcete-li získat přístup k název typu nebo proměnné mimo aktuální obor názvů, musíte použít plně kvalifikovaný název.  
  
### <a name="anonymous-namespaces"></a>Anonymní obory názvů  
 Anonymní obory názvů nejsou podporovány. Pokud máte následující kód, nelze přidat `test` do okna kukátka:  
  
```C++  
namespace mars   
{   
    namespace  
    {  
        int test = 0;   
    }   
}   
int main()   
{   
    // Adding a watch on test does not work.   
    mars::test++;   
    return 0;   
}  
  
```  
  
###  <a name="BKMK_Using_debugger_intrinisic_functions_to_maintain_state"></a>K zachování stavu používá ladicí program vnitřní funkce  
 Vnitřní funkce ladicího programu poskytnout způsob, jak volat určité funkce C/C++ ve výrazech beze změny stavu aplikace.  
  
 Vnitřní funkce ladicí program:  
  
-   Je zaručeno bezpečné: provádění vnitřní funkce ladicí program nebude proces, který je právě laděn poškozen.  
  
-   Jsou povoleny v všechny výrazy ve scénářích, kde vedlejší efekty a vyhodnocení funkce nejsou povoleny.  
  
-   Fungovat ve scénářích, kde nejsou možné, například minimální výpis ladění regulární funkce volání.  
  
 Vnitřní funkce ladicí program můžete také nastavit vyhodnocování výrazů pohodlnější. Například `strncmp(str, "asd")` je mnohem snazší zápisu v podmínce zarážek než `str[0] == 'a' && str[1] == 's' && str[2] == 'd'`. )  
  
|Oblast|Vnitřní funkce|  
|----------|-------------------------|  
|**Délka řetězce**|strlen –, wcslen –, strnlen –, wcsnlen –|  
|**Porovnání řetězců**|strcmp –, wcscmp –, stricmp –, _stricmp –, _strcmpi –, wcsicmp –, _wcscmpi, _wcsnicmp –, strncmp –, wcsncmp –, strnicmp –, wcsnicmp –|  
|**Hledání řetězců**|strchr –, wcschr –, strstr –, wcsstr –|  
|**Win32**|Funkce GetLastError(), TlsGetValue()|  
|**Windows 8**|WindowsGetStringLen() WindowsGetStringRawBuffer()<br /><br /> Tyto funkce vyžadují proces, který je právě laděn, aby byl spuštěn v systému Windows 8. Ladění výpisu soubory vytvořené ze zařízení se systémem Windows 8 také vyžaduje, aby sadě Visual Studio počítače s Windows 8. Ale pokud ladíte zařízení se systémem Windows 8 vzdáleně, sadě Visual Studio počítač může mít spuštěný systém Windows 7.|  
|**Různé**|__log2<br /><br /> Vrátí protokol základní 2 zadané celé číslo, zaokrouhlí na nejbližší menší celé číslo.|  
  
## <a name="ccli---unsupported-expressions"></a>C + +/ CLI - nepodporovaný výrazy  
  
-   Přetypování, které zahrnují ukazatele nebo uživatelem definované přetypování nejsou podporovány.  
  
-   Objekt porovnání a přiřazení nejsou podporovány.  
  
-   Přetížené operátory a přetížených funkcí nejsou podporovány.  
  
-   Zabalení a rozbalení nejsou podporovány.  
  
-   `Sizeof`operátor není podporován.  
  
## <a name="c---unsupported-expressions"></a>C# – Nepodporovaná výrazy  
  
### <a name="dynamic-objects"></a>Dynamické objekty  
 Proměnné můžete použít ve výrazech ladicího programu, které jsou zadány staticky jako dynamický. Pokud objekty, které implementují [IDynamicMetaObjectProvider rozhraní](http://msdn.microsoft.com/Library/e887a72d-ebe2-4253-a7e8-3d8d05154647) jsou vyhodnocovány v okně Sledování dynamického zobrazení přidání uzlu. Uzel dynamického zobrazení ukazuje členové objektu, ale neumožňuje úpravy hodnot členů.  
  
 Nejsou podporovány následující funkce dynamické objektů:  
  
-   Složené operátory `+=`, `-=`, `%=`, `/=`, a`*=`  
  
-   Mnoho přetypování, včetně číselné přetypování a argument typu přetypování  
  
-   Volání metod s více než dva argumenty  
  
-   Vlastnost mechanismy získání s více než dva argumenty  
  
-   Nastavením vlastností s argumenty  
  
-   Přiřazení k indexeru.  
  
-   Logické operátory `&&` a`||`  
  
### <a name="anonymous-methods"></a>Anonymní metody  
 Vytváření nového anonymní metody není podporováno.  
  
## <a name="visual-basic---unsupported-expressions"></a>Visual Basic – Nepodporovaná výrazy  
  
### <a name="dynamic-objects"></a>Dynamické objekty  
 Proměnné můžete použít ve výrazech ladicího programu, které jsou zadány staticky jako dynamický. Pokud objekty, které implementují [IDynamicMetaObjectProvider rozhraní](http://msdn.microsoft.com/Library/e887a72d-ebe2-4253-a7e8-3d8d05154647) jsou vyhodnocovány v okně Sledování dynamického zobrazení přidání uzlu. Uzel dynamického zobrazení ukazuje členové objektu, ale neumožňuje úpravy hodnot členů.  
  
 Nejsou podporovány následující funkce dynamické objektů:  
  
-   Složené operátory `+=`, `-=`, `%=`, `/=`, a`*=`  
  
-   Mnoho přetypování, včetně číselné přetypování a argument typu přetypování  
  
-   Volání metod s více než dva argumenty  
  
-   Vlastnost mechanismy získání s více než dva argumenty  
  
-   Nastavením vlastností s argumenty  
  
-   Přiřazení k indexeru.  
  
-   Logické operátory `&&` a`||`  
  
### <a name="local-constants"></a>Místní konstanty  
 Místní konstanty nejsou podporovány.  
  
### <a name="import-aliases"></a>Import aliasů  
 Import aliasů nejsou podporovány.  
  
### <a name="variable-declarations"></a>Deklarace proměnných  
 Nelze deklarovat explicitní nové proměnné v ladicím programu systému windows. Však můžete přiřadit nové implicitní proměnné uvnitř **Immediate** okno. Tyto proměnné implicitní jsou omezená na relaci ladění a nejsou přístupné mimo ladicí program. Například příkaz `o = 5` implicitně vytvoří novou proměnnou `o` a přiřadit hodnotu 5. Takovéto implicitní proměnné jsou typu **objekt** Pokud typu lze odvodit pomocí ladicího programu.  
  
### <a name="unsupported-keywords"></a>Nepodporované klíčová slova  
  
-   `AddressOf`  
  
-   `End`  
  
-   `Error`  
  
-   `Exit`  
  
-   `Goto`  
  
-   `On Error`  
  
-   `Resume`  
  
-   `Return`  
  
-   `Select/Case`  
  
-   `Stop`  
  
-   `SyncLock`  
  
-   `Throw`  
  
-   `Try/Catch/Finally`  
  
-   `With`  
  
-   Modul nebo Namespace úrovně klíčová slova, jako například `End Sub` nebo `Module`.  
  
## <a name="see-also"></a>Viz také  
 [Specifikátory formátu v jazyce C++](../debugger/format-specifiers-in-cpp.md)   
 [Context – operátor (C++)](../debugger/context-operator-cpp.md)   
 [Specifikátory formátu v jazyce C#](../debugger/format-specifiers-in-csharp.md)   
 [Pseudoproměnné](../debugger/pseudovariables.md)