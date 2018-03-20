---
title: "Zápis testů částí pro C/C++ v sadě Visual Studio | Microsoft Docs"
ms.date: 11/04/2017
ms.technology: vs-ide-test
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: ecb611d7ab816ed99e4bcce954466309f7436f76
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="write-unit-tests-for-cc-in-visual-studio"></a>Zápis testů částí pro C/C++ v sadě Visual Studio

Můžete napsat a spouštění testů jednotek C++ pomocí **Průzkumníka testů** okno, stejně jako u ostatních jazyků. Další informace o používání **Průzkumníka testů**, najdete v části [spouštění testů jednotek pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md).

> [!NOTE]
> Některé funkce, jako je například Live testování částí, programových testů uživatelského rozhraní a IntelliTest nejsou podporovány pro jazyk C++.

Visual Studio zahrnuje tyto architektury testovací C++ s žádné další položky ke stažení vyžaduje:

- Částí Microsoft Unit testování Framework pro C++
- Google Test
- Boost.Test
- CTest

Kromě nainstalované rozhraní můžete napsat vlastní test adaptéru pro libovolnou platformu chcete použít v sadě Visual Studio. Test adaptér můžete integrovat testování částí s **testování Explorer** okno. Několik adaptérů třetích stran, které jsou k dispozici na [Visual Studio Marketplace](https://marketplace.visualstudio.com). Další informace najdete v tématu [instalace systémů testů jednotek třetích stran](install-third-party-unit-test-frameworks.md).

**Visual Studio 2017 verze 15,5**

- **Adaptér testovací Google** je dodávána jako součást výchozí **vývoj aplikací s jazykem C++** zatížení. Má šablona projektu, který můžete přidat do řešení pomocí **přidat nový projekt** kontextové nabídky na uzlu řešení v **Průzkumníku řešení**a možnosti můžete nakonfigurovat přes **nástroje | Možnosti**. Další informace najdete v tématu [postupy: použití Google testu v sadě Visual Studio](how-to-use-google-test-for-cpp.md).

- **Boost.Test** je dodávána jako součást výchozí **vývoj aplikací s jazykem C++** zatížení. Je integrován se **Průzkumníka testů** ale v současné době není šablona projektu, proto je nutné jej ručně nakonfigurovat. Další informace najdete v tématu [postupy: použití Boost.Test v sadě Visual Studio](how-to-use-boost-test-for-cpp.md).

- **CTest** podpora je součástí [CMake Tools pro Visual Studio](/cpp/ide/cmake-tools-for-cpp) komponenta, která je součástí systému **vývoj aplikací s jazykem C++** zatížení. Ale CTest není ještě plně integrovaná s **Průzkumníka testů**. Další informace najdete v tématu [postupy: použití CTest v sadě Visual Studio](how-to-use-ctest-for-cpp.md).

**Visual Studio 2015 a starší**

Můžete si stáhnout Google testovací adaptér a rozšíření Boost.Test adaptéru na Visual Studio Marketplace v [testovací adaptér Boost.Test](https://marketplace.visualstudio.com/items?itemName=VisualCPPTeam.TestAdapterforBoostTest) a [adaptér testu pro Google Test](https://marketplace.visualstudio.com/items?itemName=VisualCPPTeam.TestAdapterforGoogleTest).

## <a name="basic-test-workflow"></a>Základní test pracovního postupu

Následující části vysvětlují základní kroky, které vám pomůžou začít s testování částí C++. Základní konfigurace je velmi podobný pro rozhraní Microsoft a testování Google. Boost.Test vyžaduje ruční vytvoření projektu testů.

### <a name="create-a-test-project"></a>Vytvoření projektu testů

Můžete definovat a spustit testy uvnitř jeden nebo více projektů testů, které jsou ve stejném řešení jako kód, který chcete testovat. Chcete-li přidat nový projekt testu do existujícího řešení, klikněte pravým tlačítkem na uzel řešení v **Průzkumníku řešení** a zvolte **přidat | Nový projekt**. Potom v levém podokně vyberte **testu sady Visual C++** a vyberte jeden z typů projektu z podokna center. Následující obrázek znázorňuje projektů testů, které jsou k dispozici, při zpracování **vývoj plochy s jazykem C++** zatížení je nainstalován:

![Testování projektů C++](media/cpp-new-test-project.png "C++ otestovat nové šablony projektů")

### <a name="create-references-to-other-projects-in-the-solution"></a>Vytvořit odkazy na další projekty v řešení

Chcete-li povolit testovacího kódu pro přístup k funkcím v projekt, který má být testována, přidejte do testovacího projektu odkaz na projekt. Klikněte pravým tlačítkem na uzel projektu testu v **Průzkumníku řešení** a zvolte **přidat | Referenční dokumentace**. Potom v dialogovém okně vyberte projekty, které chcete otestovat.

![Přidat odkaz](media/cpp-add-ref-test-project.png "C++ testovací přidat odkaz na projekty, které má být testována")

### <a name="add-include-directives-for-header-files"></a>Přidat #include pro soubory hlaviček

Dále v jednotky testovací soubor, přidejte `#include` direktivy pro všechny hlavičky souborů, které deklarovat typy a funkce, kterou chcete otestovat. Typ `#include "` a poté bude aktivovat IntelliSense, které vám pomohou zvolit. Opakujte pro všechny další záhlaví.

![Přidání direktivy začlenění](media/cpp-add-includes-test-project.png "C++ testovací přidat zahrnuje pro soubory hlaviček")

### <a name="write-test-methods"></a>Test metody zápisu

> [!NOTE]
> Tato část ukazuje syntaxi pro Microsoft Unit Testing Framework pro C/C++. Jsou zde uvedeny: [referenční dokumentace rozhraní API atributu Microsoft.VisualStudio.TestTools.CppUnitTestFramework](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md). Google Test dokumentaci najdete v tématu [Úvod do testovací Google](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md). Boost.Test, najdete v části [nárůst testovací knihovny: The Unit Test Framework](http://www.boost.org/doc/libs/1_46_0/libs/test/doc/html/utf.html).

Ve vašem projektu testovacího souboru má třída se zakázaným inzerováním a metoda definované pro vás jako příklad jak napsat testování kódu. Všimněte si, že podpisů používat TEST_CLASS a TEST_METHOD makra, které metody zjistitelnost z okna Průzkumníka testů.

![Přidání direktivy začlenění](media/cpp-write-test-methods.png "C++ testovací přidat zahrnuje pro soubory hlaviček")

TEST_CLASS a TEST_METHOD jsou součástí [Microsoft nativní testovací Framework]((microsoft-visualstudio-testtools-cppunittestframework-api-reference.md). **Testování Explorer** zjistí testovací metody v jiné podporované architektury podobným způsobem.

TEST_METHOD vrátí prázdnou hodnotu. Chcete-li vytvořit výsledků testů, použijte statických metod v `Assert` třídy proti očekávané skutečné výsledky testu. V následujícím příkladu se předpokládá `MyClass` má konstruktor, který, která má `std::string`. Abychom mohli otestovat, zda konstruktor inicializuje třídy podle očekávání takto:

```cpp
        TEST_METHOD(TestClassInit)
        {
            std::string name = "Bill";
            MyClass mc(name);
            Assert::AreEqual(name, mc.GetName());
        }
```
V předchozím příkladu, výsledek `Assert::AreEqual` volání Určuje, zda test bude provedeno úspěšně, nebo se nezdaří. Třída Assert obsahuje mnoho dalších metod pro porovnání očekává vs. skutečné výsledky.

Můžete přidat *vlastnosti* k testování metody k určení testovací vlastníky, prioritu a další informace. Pak můžete tyto hodnoty řadit a seskupovat testů v **Průzkumníka testů**. Další informace najdete v tématu [spouštění testů jednotek pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md).

### <a name="run-the-tests"></a>Spouštění testů

1. Na **Test** nabídce zvolte **Windows** > **Průzkumníka testů**. Následující obrázek znázorňuje testovacího projektu, jehož testy dosud nebyly spuštěny.

   ![Testování Explorer před spuštěním testů](media/cpp-test-explorer.png "C++ Průzkumníka testů")

   > [!NOTE]
   > CTest integrace s **Průzkumníka testů** dosud nejsou k dispozici. Spusťte testy CTest z hlavní nabídky CMake.

1. Pokud všechny testy nejsou zobrazeny v okně, sestavte projekt test kliknutím pravým tlačítkem na jeho uzlu v **Průzkumníku řešení** a výběr **sestavení** nebo **znovu sestavit**.

1. V Průzkumníku testu zvolte **spustit všechny**, nebo vyberte konkrétní testy, kterou chcete spustit. Klikněte pravým tlačítkem myši na test pro další možnosti, včetně spuštění v režimu ladění se zarážkami povolena. Okně se zobrazí po spuštění všechny testy, které testy předán a ty, které se nezdařilo:

![Po spuštění testů vyzkoušet Explorer](media/cpp-test-explorer-passed.png "C++ Průzkumníka testů po spuštění testů")

Zpráva pro neúspěšných testů, nabízí podrobnosti, které pomohou při určování příčin. Můžete kliknout pravým tlačítkem na test selhání a vyberte **ladění vybrané testy** krok prostřednictvím funkce, kde došlo k chybě.

Další informace o používání **Průzkumníka testů**, najdete v části [spouštění testů jednotek pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md).

Doporučené postupy související s testování částí, najdete v části [testování částí](unit-test-basics.md)

## <a name="see-also"></a>Viz také

[Testování částí kódu](unit-test-your-code.md)