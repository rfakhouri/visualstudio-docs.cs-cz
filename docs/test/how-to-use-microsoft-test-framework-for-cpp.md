---
title: "Použít Microsoft jednotka testování Framework pro C++ v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d08de69-c32e-4f0b-89aa-75347b15fb82
caps.latest.revision: "11"
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 37356782854b9bbc45787fea727643f6d244f04d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="use-the-microsoft-unit-testing-framework-for-c-in-visual-studio"></a>Použít Microsoft jednotka testování Framework pro C++ v sadě Visual Studio 

Ve výchozím nastavení je zahrnuta Microsoft Unit Testing Framework pro C++ **vývoj plochy s jazykem C++** zatížení. 

##  <a name="separate_project"></a>Zápis testů jednotek v samostatných projektu  
Obvykle spuštění testovacího kódu v jeho vlastní projektu ve stejném řešení jako kód, který chcete testovat. Nastavit a konfigurovat nový projekt testu najdete v tématu [zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md).

##  <a name="same_project"></a>Zápis testů částí ve stejném projektu  
V některých případech, například při testování-exportované funkce v knihovně DLL může být potřeba vytvořit testů ve stejném projektu s programem, který testujete. Zápis testů částí ve stejném projektu:
  
1.  Změnit vlastnosti projektu zahrnuje hlavičky a soubory knihovny, které jsou požadovány pro testování jednotky.  
  
    1.  V Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu pro program, testování a pak vyberte **vlastnosti | Vlastnosti konfigurace | Adresáře VC ++**.  
  
    3.  Klikněte na šipku dolů ve následující řádky a zvolte  **<Edit>**  :  
  
        |||  
        |-|-|  
        |**Zahrnout adresáře**|**$(VCInstallDir)UnitTest\include;$(IncludePath)**|  
        |**Adresáře knihovny**|**$(VCInstallDir)UnitTest\lib;$(LibraryPath)**|  
  
2.  Přidejte soubor testování částí C++:  
  
    -   Klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a zvolte **přidat | Nová položka | Testování částí C++**.  

## <a name="write-the-tests"></a>Zápis testů
Všechny soubory sada s třídami test musí zahrnovat "CppUnitTest.h" a máte pomocí příkazu pro `using namespace Microsoft::VisualStudio::CppUnitTestFramework`. Testovacího projektu je již nakonfigurován pro vás. Zahrnuje také definici oboru názvů a TEST_CLASS s TEST_METHOD, abyste mohli spustit. Můžete upravit název oboru názvů, jakož i názvy v závorkách v makrech třídy a metody.

Speciální makra jsou definovány pro inicializaci testovací moduly, třídy a metody a pro čištění resoures při dokončení testů. Tyto makra generovat kód, který se spustí před prvním přístupu třída nebo metoda a po spuštění poslední test. Další informace najdete v tématu [inicializovat a čištění](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#Initialize_and_cleanup).

Použít statické metody v [Assert](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#general_asserts) třídy definují podmínky testu. Použití [protokolovacího nástroje](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#logger) třída pro psaní zprávy a pokuste se **výstup – okno**. Přidání atributů k testování metody
  
## <a name="run-the-tests"></a>Spouštění testů  
  
1.  Na **Test** nabídce zvolte **Windows**, **Průzkumníka testů**.  
2. Pokud všechny testy nejsou zobrazeny v okně, sestavte projekt test kliknutím pravým tlačítkem na jeho uzlu v **Průzkumníku řešení** a výběr **sestavení** nebo **znovu sestavit**.
  
2.  V Průzkumníku testu zvolte **spustit všechny**, nebo vyberte konkrétní testy, kterou chcete spustit. Klikněte pravým tlačítkem myši na test pro další možnosti, včetně spuštění v režimu ladění se zarážkami povolena.
3. V **výstup – okno** zvolte **testy** v rozevírací dolů zobrazení zprávy zapsané podle `Logger` třídy:
 
  ![Okno výstup C++ zobrazující zkušebních zpráv](media/cpp-test-output-window.png "výstup – okno")

## <a name="define-traits-to-enable-grouping"></a>Definování vlastnosti umožňující seskupení
Můžete definovat vlastnosti na testovací metody, které vám umožní kategorií a skupin testů v **testování Explorer**. Můžete definovat výšku, použijte `TEST_METHOD_ATTRIBUTE` makro. Například můžete definovat výšku s názvem `TEST_MY_TRAIT`:  
  
```cpp  
#define TEST_MY_TRAIT(traitValue) TEST_METHOD_ATTRIBUTE(L"MyTrait", traitValue)  
```  
  
 Použití definované znak v testů částí:  
  
```  
BEGIN_TEST_METHOD_ATTRIBUTE(Method1)  
    TEST_OWNER(L"OwnerName")  
    TEST_PRIORITY(1)  
    TEST_MY_TRAIT(L"thisTraitValue")  
END_TEST_METHOD_ATTRIBUTE()  
  
TEST_METHOD(Method1)  
{     
    Logger::WriteMessage("In Method1");  
    Assert::AreEqual(0, 0);  
}  
```  
  
### <a name="c-trait-attribute-macros"></a>Makra atribut znak C++  
  Následující předdefinované vlastnosti, které se nacházejí v `CppUnitTest.h`. Další informace najdete v tématu [The Microsoft Unit Testing Framework pro C++ referenční dokumentace rozhraní API](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md).

|– Makro|Popis|  
|-----------|-----------------|  
|`TEST_METHOD_ATTRIBUTE(attributeName, attributeValue)`|Makro TEST_METHOD_ATTRIBUTE použijte k definování výšku.|  
|`TEST_OWNER(ownerAlias)`|Pomocí předdefinovaných znak vlastníka můžete určit vlastníka zkušební metody.|  
|`TEST_PRIORITY(priority)`|Pomocí předdefinovaných znak Priority relativní priority přiřadit zkušební metody.|  
  
  
## <a name="see-also"></a>Viz také
[Rychlý začátek: Vývoj řízený testy s použitím Průzkumníka testů](../test/quick-start-test-driven-development-with-test-explorer.md)

