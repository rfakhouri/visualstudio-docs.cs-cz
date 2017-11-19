---
redirect_url: /visualstudio/test/how-to-use-microsoft-test-framework-for-cpp
ms.openlocfilehash: 7ab917a55d9a2d00a8d4635e2de45cd43cbe02f2
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="how-to-use-the-microsoft-unit-testing-framework-for-c"></a>Jak používat Microsoft Unit Testing Framework pro C++
Doporučujeme, než změníte existující aplikaci, ověřit, zda má dobrou pokrytí pomocí jednotkových testů. To vám dává jistotu, že chyby nebyly zavedeny vaše změny. Pokud aplikace již nemá testování částí, můžete je přidat pomocí postupů popsaných v tomto tématu. Toto téma popisuje postup přidání testování částí pro existující kód jazyka Visual C++, počínaje rozhodování o k testování kódu a pak vytváření, zápisu a nakonec spuštěním testů.  
  
## <a name="deciding-how-to-test-your-code"></a>Rozhodování o k testování kódu  
 Otevřít existující projekt C++ a zkontrolovat k rozhodování o tom, jak chcete přidat testování částí. Můžete chtít použít některé nástroje pro modelování, které pomáhají najdete v části závislosti v kódu a vám pomohou pochopit, jak interakci částí. Další informace najdete v tématu [vizualizace kódu](../modeling/visualize-code.md).  
  
 Doporučujeme vám, že oddělíte změny do malých úlohy. Před každým malého změnit, zápis testů částí aspektů chování, které zůstávají stejné. Tyto testy budou nadále předat po provedení změny. Například pokud chcete změnit řazení funkce tak, aby Seřadí seznam lidí, kteří podle příjmení místo podle křestní jméno, pak můžete napsat testů jednotek, která ověřuje, že všechny vstupní názvy se zobrazí ve výstupu. Po provedení změn, můžete přidat nové testy částí pro nové chování.  
  
 Pokud je to praktické, všech testů jednotek nebo měli použít pouze funkce, které byly exportovány. Ale pokud chcete změnit jenom malou část celou aplikaci, pak můžete chtít použít funkce, které nejsou exportována. Můžete například testy, které vyvolají interní funkce nebo testy, které nastavování a získávání hodnoty proměnných interní.  
  
 K testování kódu produktu, v závislosti na tom, zda poskytuje rozhraní, které chcete testovat několika způsoby. Vyberte jednu z následujících způsobů:  
  
 **Testy jednotek můžete volat jenom funkce, které byly exportovány z testovaného kódu:**  
 Přidáte samostatné testovacího projektu. K testovacímu projektu přidejte odkaz na projekt v rámci testu.  
  
 Přejděte na postup [k odkazování exportovaných funkcí z testovacího projektu](#projectRef).  
  
 **Jako soubor .exe je sestavena testovaného kódu:**  
 Přidáte samostatné testovacího projektu. Propojte objekt výstupní soubor.  
  
 Přejděte na postup [propojení testy na objekt nebo knihovna soubory](#objectRef).  
  
 **Testování částí musí používat privátní funkcí a dat a jako statické knihovny se dají vytvářet testovaného kódu:**  
 Změňte projekt testovaného tak, aby je kompilováno do souboru LIB. Přidáte samostatné testovací projekt, který odkazuje na projekt v rámci testu.  
  
 Tento přístup má výhodu povolení testy používat soukromé členy, ale při tom zachovat testy v samostatných projektu. Však nemusí být vhodný pro některé aplikace, kde musí mít knihovny DLL (.dll).  
  
 Přejděte na postup [změnit testovaného kódu na statickou knihovnu](#staticLink).  
  
 **Testování částí musí používat privátní členských funkcí a data, a kód musí být vytvořená jako dynamická knihovna (DLL):**  
 Přidání testů jednotek v projektu stejný jako kód produktu.  
  
 Přejděte na postup [přidání testů jednotek ve stejném projektu](#sameProject).  
  
## <a name="creating-the-tests"></a>Vytváření testů  
  
###  <a name="staticLink"></a>Chcete-li změnit testovaného kódu do statické knihovny  
  
-   Pokud testy musí používat členy, kteří nejsou exportována projektem testovaného a sestavení projektu testovaného jako dynamické knihovny, zvažte jeho převodem na statické knihovny.  
  
    1.  V Průzkumníku řešení klikněte na místní nabídky projektu testovaného, zvolte **vlastnosti**. Otevře se okno Vlastnosti projektu.  
  
    2.  Zvolte **vlastnosti konfigurace**, **Obecné**.  
  
    3.  Nastavit **typ konfigurace** k **statické knihovny (LIB)**.  
  
 Pokračujte postupem uvedeným [propojení testy na objekt nebo knihovna soubory](#objectRef).  
  
###  <a name="projectRef"></a>Chcete-li exportované funkce DLL z testovacího projektu  
  
-   Pokud projekt testovaného knihovny DLL, který exportuje funkce, které chcete testovat, můžete přidat odkaz na projekt kódu z testovacího projektu.  
  
    1.  Vytvoření projektu testování C++.  
  
        1.  Na **soubor** nabídce zvolte **nový**, **projektu**, **Visual C++, testovací**, **projektu testování částí C++**.  
  
    2.  V Průzkumníku řešení, vyberte v místní nabídce testovacího projektu **odkazy**. Otevře se okno Vlastnosti projektu.  
  
    3.  Vyberte **společných vlastností**, **Framework a odkazy na**a potom zvolte **přidat nový odkaz** tlačítko.  
  
    4.  Vyberte **projekty**a potom projekt, který má být testována.  
  
         Vyberte **přidat** tlačítko.  
  
    5.  Ve vlastnostech k testovacímu projektu přidejte do adresáře Include umístění projektu v rámci testu.  
  
         Zvolte **vlastnosti konfigurace**, **adresáře VC ++**, **adresáře souborů k zahrnutí**.  
  
         Zvolte **upravit**a poté přidejte adresáři záhlaví projektu v rámci testu.  
  
 Přejděte na [zápis testů částí](#addTests).  
  
###  <a name="objectRef"></a>Propojení testy na objekt nebo knihovna soubory  
  
-   Pokud testovaného kódu neexportuje funkce, které chcete testovat, můžete přidat výstup **.obj** nebo **.lib** soubor závislosti testovacího projektu.  
  
    1.  Vytvoření projektu testování C++.  
  
        1.  Na **soubor** nabídce zvolte **nový**, **projektu**, **Visual C++, testovací**, **projektu testování částí C++**.  
  
    2.  V Průzkumníku řešení, vyberte v místní nabídce testovacího projektu **vlastnosti**. Otevře se okno Vlastnosti projektu.  
  
    3.  Zvolte **vlastnosti konfigurace**, **Linkeru**, **vstup**, **Další závislosti**.  
  
         Zvolte **upravit**a přidejte názvy **.obj** nebo **.lib** soubory. Nepoužívejte názvy úplnou cestu.  
  
    4.  Zvolte **vlastnosti konfigurace**, **Linkeru**, **Obecné**, **adresáře další knihovny**.  
  
         Zvolte **upravit**a přidejte cestu k adresáři **.obj** nebo **.lib** soubory. Cesta je obvykle ve složce sestavení projektu v rámci testu.  
  
    5.  Zvolte **vlastnosti konfigurace**, **adresáře VC ++**, **adresáře souborů k zahrnutí**.  
  
         Zvolte **upravit**a poté přidejte adresáři záhlaví projektu v rámci testu.  
  
 Přejděte na [zápis testů částí](#addTests).  
  
###  <a name="sameProject"></a>Chcete-li přidat ve stejném projektu testování částí  
  
1.  Změnit vlastnosti projektu kódu produktu zahrnuje hlavičky a soubory knihovny, které jsou požadovány pro testování jednotky.  
  
    1.  V Průzkumníku řešení v místní nabídce projektu testovaného, vyberte možnost Vlastnosti. Otevře se okno Vlastnosti projektu.  
  
    2.  Zvolte **vlastnosti konfigurace**, **adresáře VC ++**.  
  
    3.  Úpravy adresáře Include a Library:  
  
        |||  
        |-|-|  
        |**Zahrnout adresáře**|**$(VCInstallDir)UnitTest\include;$(IncludePath)**|  
        |**Adresáře knihovny**|**$(VCInstallDir)UnitTest\lib;$(LibraryPath)**|  
  
2.  Přidejte soubor testování částí C++:  
  
    -   V Průzkumníku řešení v místní nabídce projektu, zvolte **přidat**, **nová položka**a potom zvolte **testování částí C++**.  
  
 Přejděte na [zápis testů částí](#addTests).  
  
##  <a name="addTests"></a>Zápis testů částí  
  
1.  Do každého souboru kód testu jednotek přidat `#include` příkaz pro záhlaví projektu v rámci testu.  
  
2.  Přidáte test třídy a metody k souborům kód testu jednotek. Příklad:  
  
    ```cpp  
    #include "stdafx.h"  
    #include "CppUnitTest.h"  
    #include "MyProjectUnderTest.h"  
    using namespace Microsoft::VisualStudio::CppUnitTestFramework;  
    namespace MyTest  
    {  
      TEST_CLASS(MyTests)  
      {  
      public:  
          TEST_METHOD(MyTestMethod)  
          {  
              Assert::AreEqual(MyProject::Multiply(2,3), 6);  
          }  
      };  
    }  
    ```  
  
 Další informace najdete v tématu [testování nativního kódu pomocí Průzkumníka testů částí](http://msdn.microsoft.com/en-us/8a09d6d8-3613-49d8-9ffe-11375ac4736c).  
  
## <a name="run-the-tests"></a>Spouštění testů  
  
1.  Na **Test** nabídce zvolte **Windows**, **Průzkumníka testů**.  
2. Pokud všechny testy nejsou zobrazeny v okně, sestavte projekt test kliknutím pravým tlačítkem na jeho uzlu v **Průzkumníku řešení** a výběr **sestavení** nebo **znovu sestavit**.
  
2.  V Průzkumníku testu zvolte **spustit všechny**, nebo vyberte konkrétní testy, kterou chcete spustit. Klikněte pravým tlačítkem myši na test pro další možnosti, včetně spuštění v režimu ladění se zarážkami povolena.
  
## <a name="see-also"></a>Viz také
[Rychlé zahájení: Testování vývoj řízený testy pomocí Průzkumníka testů](../test/quick-start-test-driven-development-with-test-explorer.md)

