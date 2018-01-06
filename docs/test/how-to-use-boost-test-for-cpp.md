---
title: "Jak používat Boost.Test jazyka C++ v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0710a8-8e8a-4f6e-8415-5ab3eb830079
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b469ee739ebdc4f3cf61e8b5e578c676b5af5e24
ms.sourcegitcommit: 0614bdb0895b6e6f5b84ba4e1d9327802eca3a6b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/06/2018
---
# <a name="how-to-use-boosttest-for-c-in-visual-studio"></a>Jak používat Boost.Test jazyka C++ v sadě Visual Studio

V **Visual Studio 2017 verze 15,5** a novější, je adaptér testovací Boost.Test integrována do prostředí Visual Studio IDE jako součást sady **vývoj aplikací s jazykem C++** zatížení.

![Testovat adaptér Boost.Test](media/cpp-boost-component.png "Test adaptéru pro součást Boost.Test")

Pokud nemáte **vývoj aplikací s jazykem C++** zatížení nainstalovaná, otevřete **instalační program Visual Studio** a vyberte **upravit**. Vyberte **vývoj aplikací s jazykem C++** zatížení, klikněte **upravit** tlačítko.

## <a name="install-boost"></a>Instalace se skóre

Vyžaduje Boost.Test [nárůst](http://www.boost.org/)! Pokud nemáte nárůst nainstalována, doporučujeme použít Vcpkg Správce balíčků.

1. Postupujte podle pokynů v [Vcpkg: Správce balíčků C++ pro Windows](/cpp/vcpkg) k instalaci vcpkg (pokud ji nemáte).

1. Spustit `vcpkg install boost:x86-windows-static` k instalaci se statickou knihovnou skóre.

1. Spustit `vcpkg integrate install` příkaz konfigurace Visual Studia s knihovnou a musí zahrnovat cest skóre hlavičky a binární soubory.

## <a name="create-a-project-for-your-tests"></a>Vytvoření projektu testů

> [!NOTE]
> V aplikaci Visual Studio 2017 verze 15,5 jsou k dispozici pro Boost.Test žádné předem nakonfigurovaná testovacího projektu nebo šablony položek. Proto je nutné vytvořit projekt konzolové aplikace pro uložení testy. Test šablon pro Boost.Test jsou plánované pro zahrnutí v budoucí verzi sady Visual Studio.

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel řešení a zvolte **přidat** > **nový projekt...** .

1. V levém podokně vyberte **Visual C++** > **Windows Desktop**a potom zvolte **konzolové aplikace pro Windows** šablony.

1. Pojmenujte projekt a zvolte **OK**.

## <a name="link-and-configuration-boost-static-library-only"></a>Odkaz a konfigurace (pouze nárůst statické knihovny)

Konfigurace projektu ke spuštění testů Boost.Test.

1. Chcete-li upravit soubor projektu, nejdřív uvolněte ji. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte možnost **uvolnit projekt**. Potom klikněte pravým tlačítkem na uzel projektu a zvolte **upravit < název\>VCXPROJ**.

1. Přidejte dva řádky do **Globals** vlastnosti skupiny, jak je vidět tady:

    ```xml
    <PropertyGroup Label="Globals">
    ....
        <VcpkgTriplet>x86-windows-static</VcpkgTriplet>
        <VcpkgEnabled>true</VcpkgEnabled>
    </PropertyGroup>
    ```
1. Uložte a zavřete \*VCXPROJ souboru a pak znovu načíst projekt.

1. Chcete-li otevřít **stránky vlastností**, klikněte pravým tlačítkem na uzel projektu a vyberte možnost **vlastnosti**.

1. Rozbalte položku **C/C++** > **generování kódu**a potom vyberte **Runtime Library**. Vyberte `/MTd` ladicí statické runtime knihovny nebo `/MT` knihovny statické runtime verze.

1. Rozbalte položku **Linkeru > systému**. Ověřte, že **subsystému** je nastaven na **konzoly**.

1. Zvolte **OK** zavřete stránky vlastností.

## <a name="add-include-directives"></a>Přidání direktivy začlenění

1. Pokud dojde `main` fungovat v testovací soubor, odstraňte jej.

1. Testovací soubor, přidejte všechny potřeby `#include` direktivy chcete zviditelnit vašeho programu typy a funkce pro testovací kód. Tento program je obvykle jednu úroveň v hierarchii složek. Pokud zadáte `#include "../"`, zobrazí se okno technologie IntelliSense a umožňuje vybrat úplnou cestu k souboru záhlaví.

   ![Přidat # direktivy include](media/cpp-gtest-includes.png "přidat zahrnují direktivy pro test souboru")

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
Nyní jste připraveni k zápisu a testy skóre. Najdete v článku [dokumentaci ke knihovně pro testování nárůst](http://www.boost.org/doc/libs/1_38_0/libs/test/doc/html/index.html) informace o testovací makra. V tématu [spouštění testů jednotek pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md) informace o zjišťování, spuštění a seskupení testů pomocí **Průzkumníka testů**.

## <a name="see-also"></a>Viz také
[Zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md)