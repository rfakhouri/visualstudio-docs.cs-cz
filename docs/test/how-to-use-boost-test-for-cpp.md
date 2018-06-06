---
title: Jak používat Boost.Test jazyka C++ v sadě Visual Studio
ms.date: 01/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: eadcc8f2a3e50f9a23da3e3bbc6689c643904470
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751621"
---
# <a name="how-to-use-boosttest-for-c-in-visual-studio"></a>Jak používat Boost.Test jazyka C++ v sadě Visual Studio

V **Visual Studio 2017 verze 15,5** a novější, je adaptér testovací Boost.Test integrována do prostředí Visual Studio IDE jako součást sady **vývoj aplikací s jazykem C++** zatížení.

![Test adaptér Boost.Test](media/cpp-boost-component.png)

Pokud nemáte **vývoj aplikací s jazykem C++** zatížení nainstalovaná, otevřete **instalační program Visual Studio** a vyberte **upravit**. Vyberte **vývoj aplikací s jazykem C++** zatížení, klikněte **upravit** tlačítko.

## <a name="install-boost"></a>Instalace se skóre

Vyžaduje Boost.Test [nárůst](http://www.boost.org/)! Pokud nemáte nárůst nainstalována, doporučujeme použít Vcpkg Správce balíčků.

1. Postupujte podle pokynů v [Vcpkg: Správce balíčků C++ pro Windows](/cpp/vcpkg) k instalaci vcpkg (pokud ji nemáte).

1. Nainstalujte Boost.Test dynamická nebo statická knihovny:

    - Spustit **vcpkg nainstalovat nárůst testovací** k instalaci dynamickou knihovnu Boost.Test.

       -NEBO-

    - Spustit **vcpkg nainstalovat nárůst-test: x 86-windows-static** k instalaci se statickou knihovnou Boost.Test.

1. Spustit **vcpkg integrovat instalace** konfigurace Visual Studia s knihovnou a musí zahrnovat cest skóre hlavičky a binární soubory.

## <a name="add-the-item-template-visual-studio-2017-version-156-and-later"></a>Přidání šablony položky (Visual Studio 2017 verze 15.6 a novější)

1. Pokud chcete vytvořit soubor sada testů, klikněte pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a zvolte **přidat novou položku**.

   ![Šablony Boost.Test položky](media/boost_test_item_template.png)

1. Nový soubor obsahuje metodu testovacího vzorku. Sestavení projektu povolit **Průzkumníka testů** metodu zjišťování.

Varianta jedním záhlaví Boost.Test používá šablony položky, ale můžete upravit #include cestu na variant knihovny samostatné. Další informace najdete v tématu [direktivy začlenění přidat](#add_include_directives).

## <a name="create-a-test-project-visual-studio-2017-version-155"></a>Vytvoření projektu testování (Visual Studio 2017 verze 15,5)

V aplikaci Visual Studio 2017 verze 15,5 jsou k dispozici pro Boost.Test žádné předem nakonfigurovaná testovacího projektu nebo šablony položek. Proto musíte vytvořit a nakonfigurovat projekt konzolové aplikace pro uložení testy.

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel řešení a zvolte **přidat** > **nový projekt...** .

1. V levém podokně vyberte **Visual C++** > **Windows Desktop**a potom zvolte **konzolové aplikace pro Windows** šablony.

1. Pojmenujte projekt a zvolte **OK**.
1. Odstranit `main` funkce v souboru.

1. Pokud používáte verzi Boost.Test jedním záhlaví nebo dynamické knihovny, přejděte na [direktivy začlenění přidat](#add_include_directives). Pokud používáte verzi statickou knihovnu, budete muset provést některé další konfigurace:

   a. Chcete-li upravit soubor projektu, nejdřív uvolněte ji. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte možnost **uvolnit projekt**. Potom klikněte pravým tlačítkem na uzel projektu a zvolte **upravit < název\>VCXPROJ**.

   b. Přidejte dva řádky do **Globals** vlastnosti skupiny, jak je vidět tady:

    ```xml
    <PropertyGroup Label="Globals">
    ....
        <VcpkgTriplet>x86-windows-static</VcpkgTriplet>
        <VcpkgEnabled>true</VcpkgEnabled>
    </PropertyGroup>
    ```
   c. Uložte a zavřete \*VCXPROJ souboru a pak znovu načíst projekt.

   d. Chcete-li otevřít **stránky vlastností**, klikněte pravým tlačítkem na uzel projektu a vyberte možnost **vlastnosti**.

   d. Rozbalte položku **C/C++** > **generování kódu**a potom vyberte **Runtime Library**. Vyberte **/MTd** ladicí statické runtime knihovny nebo **/MT** knihovny statické runtime verze.

   f. Rozbalte položku **Linkeru > systému**. Ověřte, že **subsystému** je nastaven na **konzoly**.

   g. Zvolte **OK** zavřete stránky vlastností.

## <a name="add-include-directives"></a>Přidání direktivy začlenění

1. Testovací soubor, přidejte všechny potřeby `#include` direktivy chcete zviditelnit vašeho programu typy a funkce pro testovací kód. Tento program je obvykle jednu úroveň v hierarchii složek. Pokud zadáte `#include "../"`, zobrazí se okno technologie IntelliSense a umožňuje vybrat úplnou cestu k souboru záhlaví.

   ![Přidat # direktivy include](media/cpp-gtest-includes.png)

   Můžete použít samostatné knihovna se:

   ```cpp
   #include <boost/test/unit_test.hpp>
   ```

   Nebo použijte verzi jedním záhlaví s:

   ```cpp
   #include <boost/test/included/unit_test.hpp>
   ```

   Poté definujte `BOOST_TEST_MODULE`.

Následující příklad je dostatečný pro test zjistitelné v **testování Explorer**:

```cpp
#define BOOST_TEST_MODULE MyTest
#include <boost/test/included/unit_test.hpp\> //single-header
#include "../MyProgram/MyClass.h" // project being tested
#include <string>

BOOST_AUTO_TEST_CASE(my\_boost_test)
{
    std::string expected_value = "Bill";

    // assume MyClass is defined in MyClass.h
    // and get_value() has public accessibility
    MyClass mc;
    BOOST_CHECK(expected_value == mc.get_value());
}
```

## <a name="write-and-run-tests"></a>Zápis a spouštění testů
Nyní jste připraveni k zápisu a testy skóre. Najdete v článku [dokumentaci ke knihovně pro testování nárůst](http://www.boost.org/doc/libs/release/libs/test/doc/html/index.html) informace o testovací makra. V tématu [spouštění testů jednotek pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md) informace o zjišťování, spuštění a seskupení testů pomocí **Průzkumníka testů**.

## <a name="see-also"></a>Viz také:
[Zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md)
