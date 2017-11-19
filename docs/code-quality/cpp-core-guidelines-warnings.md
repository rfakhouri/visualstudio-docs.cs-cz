---
title: "Pokyny pro základní C++ upozornění | Microsoft Docs"
ms.custom: 
ms.date: 08/10/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c83814a-f21d-4323-ad5f-13bac40d3e38
author: mblome
ms.author: mblome
manager: ghogen
ms.technology: vs-ide-code-analysis
ms.openlocfilehash: 65f4e7ed865a3a620d58b45580914d6e0b589660
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="using-the-c-core-guidelines-checkers"></a>Pomocí kameny základní pokyny pro C++
Základní pokyny C++ jsou přenosné sadu pokyny, pravidla a osvědčené postupy o kódování v jazyce C++ vytvořené odborníky C++ a návrháři. Visual Studio aktuálně podporuje podmnožinu tato pravidla v rámci jeho nástrojů pro analýzu kódu pro jazyk C++. Kameny platí základní jsou nainstalované ve výchozím nastavení v Visual Studio 2017 a [k dispozici jako balíčku NuGet pro Visual Studio 2015](#vs2015_corecheck).
  
## <a name="the-c-core-guidelines-project"></a>Pokyny k projektu C++ jádra  
 Vytvoření Bjarnem Stroustrupem a jinými uživateli pokyny základní C++ jsou návod, jak bezpečně a efektivně pomocí moderní verze jazyka C++. Podle pokynů zdůraznil statického typu zabezpečení a zabezpečení prostředků. Identifikovat způsoby, jak vyloučit nebo minimalizovat části nejvíce náchylné jazyka a navrhněte postupy, aby byl váš kód jednodušší a další původce spolehlivé způsobem. Tyto pokyny jsou zachována ve standardní C++ Foundation. Další informace najdete v dokumentaci [C++ základní pokyny](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)a přístup k souborům projektu C++ základní pokyny dokumentace [Githubu](https://github.com/isocpp/CppCoreGuidelines).  
  
## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>Povolit podle pokynů zkontrolujte základní C++ v analýza kódu  
 Analýza kódu v projektu můžete povolit výběrem **povolit analýza kódu při sestavování** zaškrtnout políčko **analýza kódu** části **stránky vlastností** dialogové okno pro váš projekt.  
  
 ![Stránka vlastností pro nastavení obecné analýzy kódu](../code-quality/media/cppcorecheck_codeanalysis_general.png "CPPCoreCheck_CodeAnalysis_General")  
  
 Zkontrolujte základní C++ pravidla jsou rozšíření sad výchozí pravidlo, které spustit, když je povolena analýza kódu. Protože C++ základní zkontrolujte pravidla jsou ve vývoji, některá pravidla jsou dobře známou a některé nemusí být připraven k použití na všechny kód, ale stále může být informativní. Pravidla jsou rozděleny do dvou skupin: bylo uvolněno a experimentální. Můžete zvolit, jestli se má spustit vydaná nebo experimentální pravidla ve vlastnostech projektu.  
  
 ![Stránka vlastností pro nastavení rozšíření analýzy kódu](../code-quality/media/cppcorecheck_codeanalysis_extensions.png "CPPCoreCheck_CodeAnalysis_Extensions")  
  
 Chcete-li povolit nebo zakázat sady pravidel C++ zkontrolujte jádra, otevřete **stránky vlastností** dialogové okno pro váš projekt. V části **vlastnosti konfigurace**, rozbalte položku **analýza kódu**, **rozšíření**. V rozevírací nabídce řízení vedle **povolit C++ základní zkontrolujte (vydané)** nebo **povolit C++ základní zkontrolujte (experimentální)**, zvolte **Ano** nebo **ne**. Zvolte **OK** nebo **použít** uložte provedené změny.  
  
## <a name="examples"></a>Příklady  
 Tady je příklad některých problémů, které můžete najít C++ základní zkontrolujte pravidla:  
  
```cpp  
// CoreCheckExample.cpp  
// Add CppCoreCheck package and enable code analysis in build for warnings.  
  
int main()  
{  
    int arr[10];           // warning C26494  
    int* p = arr;          // warning C26485  
  
    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1  
    {  
        int* q = p + 1;    // warning C26481 (suppressed)  
        p = q++;           // warning C26481 (suppressed)  
    }  
  
    return 0;  
}  
```  
  
 Tento příklad ukazuje několik upozornění, které můžete najít C++ základní zkontrolujte pravidla:  
  
-   C26494 je pravidlo Type.5: vždy inicializovat objekt.  
  
-   C26485 je pravidlo Bounds.3: decay žádné pole ukazatele.  
  
-   C26481 je pravidlo Bounds.1: Nepoužívejte aritmetika ukazatele. Místo nich se používá `span`.  
  
 Pokud sady pravidel C++ základní zkontrolujte analýzy kódu nainstalované a povolené při kompilaci tento kód, první dva upozornění jsou výstupem, ale třetí potlačeno. Toto je výstup sestavení z ukázkového kódu:  
  
```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------  
1>  CoreCheckExample.cpp  
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe  
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)  
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)  
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)  
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
```  
  
Pokyny pro základní C++ existují můžete napsat kód, lepší a bezpečnější. Pokud máte instanci, kde by neměl použito pravidlo nebo profil, je však snadno potlačit přímo v kódu. Můžete použít `gsl::suppress` atribut zachovat C++ základní zkontrolujte ze zjišťování a vytváření sestav nedodržení pravidla v následující blok kódu. Můžete označit jednotlivé příkazy k potlačení specifická pravidla. Celý rozsah profilu můžete potlačit i napsáním `[[gsl::suppress(bounds)]]` bez zahrnutí číslo konkrétní pravidlo.  

## <a name="supported-rule-sets"></a>Podporované sady pravidel
Při přidávání nové pravidel pro kontrolu C++ základní pokyny, může zvýšit počet upozornění, které jsou vytvářeny pro existující kód. Sady předdefinovaných pravidel můžete použít k filtrování které typy pravidel se povolit. Od verze Visual Studio 2017 verze 15.3 sady podporované pravidel jsou: 
  - **Vlastník ukazatel pravidla** vynutit [Správa prostředků kontroluje související s vlastníka<T> od základní pokynů C++](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

  - **Const pravidla** vynutit [související const kontroly od základní pokynů C++](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability).

  - **Nezpracovaná pravidla ukazatel** vynutit [Správa prostředků kontroluje související s nezpracovaná ukazatele od základní pokynů C++](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

  - **Jedinečný pravidla ukazatel** vynutit [Správa prostředků kontroluje související s typy pomocí sémantiky jedinečný ukazatel ze základní pokyny C++](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

  - **Rozsah pravidla** vynutit [hranice profil pokyny základní C++](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

  - **Zadejte pravidla** vynutit [typ profilu pokyny základní C++](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile).


 Můžete omezit upozornění na právě jednu nebo několik skupin. **Nativní minimální** a **nativní doporučená** pravidlo nastaví zahrnout C++ základní zkontrolujte pravidla kromě jiných PREfast kontroly. Pokud chcete zobrazit dostupné sady pravidel, otevřete dialogové okno Vlastnosti projektu, vyberte **Analysis\General kód**, otevřete rozevírací seznam v **sad pravidel** pole se seznamem a vybrat **zvolte více sad pravidel** . Další informace o použití sady pravidel v sadě Visual Studio najdete v tématu [pomocí sad pravidel k seskupování pravidel analýzy kódu](using-rule-sets-to-group-code-analysis-rules.md).

## <a name="macros"></a>Makra
 Nástroj pro kontrolu C++ základní pokyny součástí obsahuje soubor hlaviček, který definuje makra, které usnadňují potlačit celý kategorií upozornění v kódu:

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

Tyto makra odpovídají sady pravidel a rozšířit oddělených mezerami seznam čísel upozornění. Pomocí příslušné – Direktiva pragma konstrukce můžete nakonfigurovat efektivní sada pravidel, která je zajímavé pro projekt nebo část kódu. V následujícím příkladu se analýza kódu pouze upozornění na chybějící konstantní modifikátory:

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>Atributy
 Microsoft Visual C++ compiler má omezenou podporu pro GSL potlačit atribut.
Může sloužit k potlačení upozornění na výrazu a příkazy bloku uvnitř funkce.

```cpp
// Supress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Supress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{ 
    new int; 
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```  

## <a name="suppressing-analysis-by-using-command-line-options"></a>Potlačení analysis pomocí možnosti příkazového řádku
 Místo #pragmas můžete použít možnosti příkazového řádku na stránce vlastností souboru k potlačení upozornění pro projekt nebo jeden soubor. Chcete-li například zakázat upozornění 26400 pro soubor:
 
 1) Pravým tlačítkem na soubor v **Průzkumníku řešení**

 2) Zvolte **vlastnosti | C / C++ | Příkazový řádek**

 3) V **další možnosti** okně Přidat `/wd26400`.

 Můžete použít možnost příkazového řádku k dočasnému zakázání všechny analýzy kódu pro soubor zadáním `/analyze-`. Vznikne upozornění *D9025 přepsání '/ analyzovat' s ' / analyze – '*, který bude upozornění, abyste později znovu povolit analýza kódu.

 ## <a name="corecheck_per_file"></a>Povolení kontrolu C++ základní pokyny na soubory konkrétní projektu
Někdy může být užitečné proveďte zaměřené analýzy kódu a stále využívají prostředí Visual Studio IDE. Níže je ukázkový scénář, který můžete použít pro velké projekty ušetřit čas sestavení a usnadňují výsledky filtru.
1.  V příkazovém okně nastavený `esp.extension` a `esp.annotationbuildlevel` proměnné prostředí.
2.  Visual Studio spustíte z příkazového okna dědění tyto proměnné.
3.  Načtení projektu a otevřete jeho vlastnosti.
4.  Povolit analýza kódu, vyberte příslušné pravidlo sady, ale není rozšíření analýzy kódu.
5.  Přejděte na soubor, který chcete analyzovat pomocí kontrolu C++ základní pokyny a otevřete jeho vlastnosti.
6.  Zvolte **C / C++ \Command možnosti řádku** a přidejte`/analyze:plugin EspXEngine.dll`
7.  Zakázat použití předkompilovaných hlaviček (**C / C++ \Precompiled hlavičky**). To je nezbytné, protože modul rozšíření může pokus o čtení jeho interní informace z předkompilovaných hlaviček a pokud k tomu bylo kompilováno s možností výchozího projektu, nebude kompatibilní.
8.  Znovu sestavte projekt. Běžné PREFast kontroly měly být spuštěny na všechny soubory. Protože nástroj pro kontrolu C++ základní pokyny součástí není povolen ve výchozím nastavení, měli spustit pouze v souboru, který je konfigurován pro použití.

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>Jak používat nástroj pro kontrolu základní pokyny C++ mimo Visual Studio
Můžete vytvořit kontroly C++ základní pokyny v automatizovaných sestaveních.

### <a name="msbuild"></a>MSBuild
 Analýza nativního kódu kontrolu (nástroj PREfast) je integrovaná do prostředí nástroje MSBuild soubory vlastní cíle. Můžete použít vlastnosti projektu povolit a přidat C++ základní pokyny pro kontrolu, (která je založena na nástroj PREfast):

 ```xml
  <PropertyGroup>
    <EnableCppCoreCheck>true</EnableCppCoreCheck>
    <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>¬¬
    <RunCodeAnalysis>true</RunCodeAnalysis>
  </PropertyGroup>
```
Ujistěte se, že přidáte tyto vlastnosti před importem souboru Microsoft.Cpp.targets. Můžete vybrat konkrétní pravidlo sady nebo vytvořit vlastní sady pravidel nebo použít výchozí sadu pravidlo, které zahrnuje další PREfast kontroly.

Nástroj pro kontrolu C++ základní součástí lze spustit pouze na zadané soubory pomocí stejný přístup jako [dříve popisované](#coreckeck_per_file), ale pomocí nástroje MSBuild souborů. Proměnné prostředí lze nastavit pomocí `BuildMacro` položky:

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <ValueCppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

Pokud nechcete, aby k úpravě souboru projektu, můžete předat vlastnosti na příkazovém řádku:

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>Bez MSBuild projekty
Pokud používáte systém sestavení, která není závisí na MSBuild pořád se dá spustit nástroj pro kontrolu, ale budete muset Seznamte se s některé interní informace o modulu Konfigurace analýzy kódu (který není zaručeno, podporovaná v budoucnu).

Musíte používat správné parametry příkazového řádku pro kompilátor a nastavení pár proměnných prostředí. Je lepší, aby fungovaly v prostředí "nativní nástroje příkazového řádku" tak, že nemáte k vyhledání konkrétních cest pro kompilátor, zahrnout adresáře atd.

1.  **Proměnné prostředí**
  - `set esp.extensions=cppcorecheck.dll`Tato hodnota informuje modul načíst modul C++ základní pokyny.
  - `set esp.annotationbuildlevel=ignore`To zakáže logiku, která zpracovává poznámek SAL. Poznámky neovlivňuje analýza kódu v kontrola C++ základní pokyny, ale jejich trvá zpracování času (někdy mnoho času). Toto nastavení je volitelný, ale důrazně doporučujeme.
  - `set caexcludepath=%include%`Důrazně doporučujeme zakázat upozornění, které na standardní hlavičky. Můžete přidat více cest zde, například cestu k společné hlavičky ve vašem projektu.
2.  **Možnosti příkazového řádku**
  - `/analyze`Analýza kódu umožňuje (zvažte taky použití / analyze: pouze a / analyze: quiet).
  - `/analyze:plugin EspXEngine.dll`Tato možnost načte modul rozšíření analýzy kódu do nástroj PREfast. Tento modul se pak načte kontrolu C++ základní pokyny.



## <a name="use-the-guideline-support-library"></a>V knihovně obecné zásady podpory  
 Knihovna podpory platí usnadňuje postupujte podle pokynů jádra. GSL obsahuje definice, které umožňují náchylné konstrukce nahraďte bezpečnějších alternativ. Například můžete nahradit `T*, length` pár parametrů s `span<T>` typu. Je k dispozici na GSL [http://www.nuget.org/packages/Microsoft.Gsl](http://www.nuget.org/packages/Microsoft.Gsl). Knihovny je open source, takže můžete zobrazit zdroje, zadávání komentářů nebo přispívat. Projekt naleznete na adrese [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL).

 ## <a name="vs2015_corecheck"></a>Postupujte podle pokynů zkontrolujte základní C++ v projektech Visual Studio 2015  
  Pokud používáte Visual Studio 2015, sad pravidel C++ základní zkontrolujte analýzy kódu ve výchozím nastavení nenainstalují. Než můžete povolit C++ základní zkontrolujte nástrojů pro analýzu kódu v sadě Visual Studio 2015, musíte provést další kroky. Společnost Microsoft poskytuje podporu pro projekty Visual Studio 2015 pomocí balíčku Nuget. Balíček je s názvem Microsoft.CppCoreCheck a je k dispozici na [http://www.nuget.org/packages/Microsoft.CppCoreCheck](http://www.nuget.org/packages/Microsoft.CppCoreCheck). Tento balíček vyžaduje, že abyste měli aspoň nainstalovanou sadu Visual Studio 2015 s Update 1.  
  
 Balíček nainstaluje taky jiný balíček jako závislost, pouze záhlaví platí podpora knihovny (GSL). GSL je také k dispozici na webu GitHub na [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL).  

 Kvůli způsobu, kterým jsou načtena pravidel analýzy kódu je nutné nainstalovat balíček Microsoft.CppCoreCheck NuGet do každého projektu C++, který chcete zkontrolovat v sadě Visual Studio 2015.  
  
#### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Chcete-li přidat balíček Microsoft.CppCoreCheck do projektu v sadě Visual Studio 2015  
  
1.  V **Průzkumníku**, klikněte pravým tlačítkem na otevření místní nabídky projektu v řešení, které chcete přidat balíček do. Zvolte **spravovat balíčky NuGet** otevřete **Správce balíčků NuGet**.  
  
2.  V **Správce balíčků NuGet** vyhledejte Microsoft.CppCoreCheck.  
  
     ![Okno Správce balíčků Nuget ukazuje CppCoreCheck balíček](../code-quality/media/cppcorecheck_nuget_window.PNG "CPPCoreCheck_Nuget_Window")  
  
3.  Vyberte balíček Microsoft.CppCoreCheck a potom zvolte **nainstalovat** tlačítko Přidat pravidla do projektu.  
  
 Další soubor .targets MSBuild přidává balíček NuGet do projektu, která je volána, pokud povolíte analýza kódu v projektu. Tento soubor .targets přidá C++ základní zkontrolujte pravidla jako další rozšíření pro nástroj pro analýzu kódu sadě Visual Studio. Když je balíček nainstalován, můžete k povolení nebo zakázání pravidla vydaná a experimentální dialogové okno stránky vlastností.  
  
