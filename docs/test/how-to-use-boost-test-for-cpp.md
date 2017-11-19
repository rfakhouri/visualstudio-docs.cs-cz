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
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6bfce4aa4153d8f01fa9ef6cd6dc0d4b08eedbc4
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="how-to-use-boosttest-for-c-in-visual-studio"></a>Jak používat Boost.Test jazyka C++ v sadě Visual Studio
V **Visual Studio 2017 verze 15,5** a novější, je Boost.Test integrována do prostředí Visual Studio IDE jako součást sady **Develoment plochy s jazykem C++** zatížení. Který jej nainstaluje na váš počítač, spusťte instalační program Visual Studio a najít **Boost.Test adaptér** v seznamu součástí úlohy:

![Nainstalujte nárůst Test](media/cpp-boost-component.png "nainstalovat Boost.Test jazyka C++")

## <a name="install-boost"></a>Instalace se skóre

 Vyžaduje Boost.Test [nárůst](http://www.boost.org/)! Pokud nemáte nárůst nainstalována, doporučujeme použít Vcpkg Správce balíčků. 

1. Postupujte podle pokynů v [Vcpkg: Správce balíčků C++ pro Windows](/cpp/vcpkg) k instalaci vcpkg (pokud ji nemáte).
2. Spustit `vcpkg install boost` k instalaci knihovny skóre.
3. Spustit `vcpkg integrate install` příkaz konfigurace Visual Studia s knihovnou a musí zahrnovat cest skóre hlavičky a binární soubory. 

## <a name="create-a-project-for-your-tests"></a>Vytvoření projektu testů
V aplikaci Visual Studio 2017 verze 15,5 jsou k dispozici pro Boost.Test žádné předem nakonfigurovaná testovacího projektu nebo šablony položek. Proto je nutné vytvořit projekt konzolové aplikace pro uložení testy. Test šablon pro Boost.Test jsou plánované pro zahrnutí v budoucí verzi sady Visual Studio. 

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel řešení a zvolte **přidat | Nový projekt**. 
2. V levém podokně vyberte **Windows Desktop** a potom zvolte **konzolové aplikace pro Windows** v prostředním podokně. 
3. Pojmenujte projekt a klikněte na tlačítko **OK**. 

## <a name="add-include-directives"></a>Přidání direktivy začlenění
Testovací soubor, přidejte všechny potřeby `#include` direktivy chcete zviditelnit vašeho programu typy a funkce pro testovací kód. Tento program je obvykle jednu úroveň v hierarchii složek. Pokud zadáte `#include "../"` okno technologie IntelliSense se zobrazí a umožňuje vybrat úplnou cestu k souboru záhlaví.

![Přidat # direktivy include](media/cpp-gtest-includes.png "přidat zahrnují direktivy pro test souboru")

Minimálně je potřeba zahrnout do [jedné hlavičce variantě Boost.Test](http://www.boost.org/doc/libs/1_48_0/libs/test/doc/html/utf/user-guide/usage-variants/single-header-variant.html) s `#include <path>/unit_test.hpp` a definovat `BOOST_TEST_MODULE`. Následující příklad je dostatečný pro test zjistitelné v **testování Explorer**:

```cpp
#include "stdafx.h"
#define BOOST_TEST_MODULE MyTest
#include <boost/test/included/unit_test.hpp>
#include "../MyProgram/MyClass.h" // project being tested
#include <string>

BOOST_AUTO_TEST_CASE(my_boost_test)
{
    std::string name = "Bill";
    MyClass mc(name);
    Assert::AreEqual();
    BOOST_CHECK(name == mc.GetName());
}
```

## <a name="write-and-run-tests"></a>Zápis a spouštění testů
Nyní jste připraveni k zápisu a testy skóre. Najdete v článku [dokumentaci ke knihovně pro testování nárůst](http://www.boost.org/doc/libs/1_38_0/libs/test/doc/html/index.html) informace o testovací makra. V tématu [spouštění testů jednotek pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md) informace o zjišťování, spuštění a seskupení testů pomocí **Průzkumníka testů**.

## <a name="see-also"></a>Viz také
[Zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md)


  







