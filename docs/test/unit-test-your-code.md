---
title: "Testování částí kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, unit tests
- unit tests, verifying code with
- testing code, automated tests
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: bafabb6755a5d3c8cf8f2b60b67a9dc0d7af9792
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="unit-test-your-code"></a>Testy jednotek kódu
Testování částí poskytnout vývojáři a testerům, sada rychlý způsob, jak hledat logické chyby v metody třídy v [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)], [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)], a [!INCLUDE[cpp_current_short](../misc/includes/cpp_current_short_md.md)] projekty.  
  
 Nástroje testování částí zahrnují:  
  
1.  **Test Explorer.** Průzkumník testů dovoluje spouštět testy částí a zobrazit jejich výsledky. Průzkumník testů může použít libovolné rozhraní testování částí, včetně rozhraní třetích stran, které má adaptér pro Průzkumníka.  
  
2.  **Částí Microsoft unit test framework pro spravovaný kód.** Rozhraní společnosti Microsoft pro testování částí spravovaného kódu je nainstalováno spolu se sadou Visual Studio a poskytuje rozhraní pro testování kódu rozhraní .NET.  
  
3.  **Částí Microsoft unit test framework pro C++.** Rozhraní Microsoft pro testování částí kódu v jazyce C++ je nainstalováno spolu se sadou Visual Studio a poskytuje rozhraní pro testování nativního kódu.  Google Test, Boost.Test a CTest architektury je také součástí sady Visual Studio a jsou k dispozici pro další test rozhraní adaptéry třetích stran. Další informace najdete v tématu [zápis testování částí pro C/C++](writing-unit-tests-for-c-cpp.md). 
  
4.  **Nástroje pro pokrytí kódu.** Množství kódu produktu, které testování částí kontroluje, je možné určit jedním příkazem v Průzkumníku testů.  
  
5.  **Microsoft Fakes izolace rámec.** Izolační rozhraní Microsoft Fakes může vytvořit zástupné třídy a metody pro produkční a systémový kód, které během testu vytváří závislosti v kódu. Implementací napodobenin delegátů pro funkci je možné kontrolovat chování a výstup závislého objektu.  
  
 Můžete také použít [IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md) prozkoumat ke generování testovacích datech a sada testů částí kódu .NET. Pro každý příkaz v kódu, je generována testovací vstup, spustí tento příkaz. Case analýzy se provádí pro každou podmíněného větve v kódu.  
  
## <a name="key-tasks"></a>Klíčové úkoly  
 V následujících tématech naleznete informace týkající se vytváření testování částí a sloužící k jeho lepšímu pochopení:  
  
|Úlohy|Související témata|  
|-----------|-----------------------|  
|**Rychlé zahájení práce a návody:** používat další jednotky testování v sadě Visual Studio z příklady kódu v následujících tématech.|-   [Návod: Vytváření a spouštění testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)<br />-   [Rychlé zahájení: Testování vývoj řízený testy pomocí Průzkumníka testů](../test/quick-start-test-driven-development-with-test-explorer.md)<br />-   [Přidání testů částí do stávajících aplikací C++](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)|  
|**Testování částí pomocí Průzkumníka testů:** zjistěte, jak můžete Průzkumníka testů pomocí vytvoření produktivní a efektivní testování částí.|-   [Testování částí](../test/unit-test-basics.md)<br />-   [Vytvoření projektu testování částí](../test/create-a-unit-test-project.md)<br />-   [Spouštění testů jednotek pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)<br />-   [Instalace systémů testů jednotek třetích stran](../test/install-third-party-unit-test-frameworks.md)<br />-   [Upgrade testu programového UI z produktu Visual Studio 2010](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)|  
|**Testování částí spravovaného kódu:**|-   [Zápis testů částí pro rozhraní .NET Framework s částí Microsoft Unit Test Framework pro spravovaný kód](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)|  
|**C++ – kód testování částí**|-   [Zápis testů částí pro C/C++ s Microsoft Unit Testing Framework pro C++](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)|  
|**Uzavírací testování částí**|-   [Izolace testovaného kódu pomocí zástupného rozhraní Microsoft](../test/isolating-code-under-test-with-microsoft-fakes.md)|  
|**Použijte pokrytí kódu k určení, jaké části kódu vašeho projektu se testuje pomocí testování částí:** Další informace o funkci pokrytí kódu [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)] testovací nástroje.|-   [Použití pokrytí kódu k určení jak mnohem kódu se testuje](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)|  
|**Analýzám přízvuk a výkonu pomocí zátěžových testů pro testy částí:** můžete vytvořit zátěžový test a přidejte testů jednotek do ní ke zjištění výkonu a vystavila zátěži problémy ve vaší aplikaci.|-   [Spouštění testování (služby VSTS a sady TFS)](/vsts/load-test/)|  
|**Nastavit a vynutit brány kvality:** vytvořením brány kvality vynutit spuštění testů, než se změnami kódu, abyste zajistili kvality kódu.|-   [Nastavit a vynutit brány kvality](http://msdn.microsoft.com/Library/bdc5666e-6cf0-45b2-a0a1-133c3f61e852)|  
|**Rozšíření jednotka typu testu:** funkce můžete přidat do vaší testy, které nemusí být v rámci testování jednotky. Například je možné přidat vlastnost testu, která specifikuje, zda má test běžet pod běžným uživatelem nebo ne. Nebo je možné rozšířit rozhraní přidáním atributů řádku do metody a použít data v tomto řádku uvnitř testu.|Ukázkový kód o tom, jak rozšířit jednotka test framework, naleznete v následujících [webu společnosti Microsoft](http://go.microsoft.com/fwlink/?LinkId=185591).|  
|**Nastavení možností otestování:** například můžete zadat, kde jsou uložené výsledky testů.|[Konfigurace testů částí s použitím souboru .runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)|  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting>  
 Popisuje obor názvů UnitTesting, který poskytuje atributy, výjimky, kontrolní výrazy a další třídy, které podporují testování částí.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Web>  
 Popisuje UnitTesting.Web názvů, který rozšiřuje obor názvů UnitTesting tím, že poskytuje podporu pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] a webové služby testování částí.  
  
## <a name="external-resources"></a>Externí zdroje  
  
### <a name="videos"></a>Videa  
 [Channel 9: Testování aplikace UWP vyvíjené v XAML částí](http://go.microsoft.com/fwlink/?LinkId=226285)  
  
### <a name="forums"></a>Diskuzní fóra  
 [Visual Studio Unit Testing](http://go.microsoft.com/fwlink/?LinkId=224477)  
  
### <a name="guidance"></a>Doprovodné materiály  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 2: testování částí: testování uvnitř](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
### <a name="reference"></a>Odkaz  
 [Index obsahu pro testování částí](http://go.microsoft.com/fwlink/?LinkID=254719)  
  
## <a name="see-also"></a>Viz také

[Zlepšení kvality kódu](/visualstudio/test/improve-code-quality)
