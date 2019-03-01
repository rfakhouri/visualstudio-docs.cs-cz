---
title: Postup použití testu CTest jazyka C++
ms.date: 11/07/2017
ms.topic: conceptual
ms.author: mblome
manager: jillfra
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 6be079a5adfe52a7ac750f6713672dad50c7d2a4
ms.sourcegitcommit: 87d7123c09812534b7b08743de4d11d6433eaa13
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57222032"
---
# <a name="how-to-use-ctest-for-c-in-visual-studio"></a>Postup použití testu CTest jazyka C++ v sadě Visual Studio

CMake (která zahrnuje CTest) je integrována do integrovaného vývojového prostředí sady Visual Studio ve výchozím nastavení jako součást sady **Desktop Development with C++** pracovního vytížení. Pokud je potřeba nainstalovat na svém počítači, spusťte program Instalační program sady Visual Studio, klikněte na tlačítko **změnit** tlačítko a pak zkontrolujte [nástroje CMake pro Visual C++](/cpp/ide/cmake-tools-for-visual-cpp) v seznamu součástí úlohy.

## <a name="to-write-tests"></a>K psaní testů

Podpora CMake v sadě Visual Studio nezahrnuje projektu systému Visual Studio. Proto zápisu a nakonfigurujte testy CTest, stejně jako v jakémkoli prostředí CMake. Další informace o používání CMake v sadě Visual Studio najdete v tématu [nástroje CMake pro Visual C++](/cpp/ide/cmake-tools-for-visual-cpp).

## <a name="to-run-tests"></a>Ke spuštění testů

::: moniker range="vs-2017"

### <a name="visual-studio-2017-version-156-and-later"></a>Visual Studio 2017 verze 15.6 a novější

V sadě Visual Studio 2017 verze 15.6 a novější CTest je plně integrována s **Průzkumník testů** a podporuje také rozhraní testování částí Googlu a Boost. Tyto architektury jsou zahrnuté ve výchozím nastavení jako komponentu **Desktop Development with C++** pracovního vytížení. Nicméně pokud provádíte upgrade projektu ze starší verze sady Visual Studio, budete muset nainstalovat tyto architektury pomocí programu Instalační program sady Visual Studio.

Následující obrázek znázorňuje výsledky CTest spouštět pomocí rozhraní Google Test:

![CTest pomocí rozhraní Google Test v sadě Visual Studio 2017](media/ctest-test-explorer.png)

Pokud používáte CTest, ale ne Google nebo Boost adaptérů, uvidíte výsledky na úrovni CTest namísto jednotlivých testovací metoda úroveň. Můžete ladit a procházení po kroku jen CTest spustitelné soubory, ale trasování zásobníku na jednotlivé testy nejsou podporovány.

### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 verze 15.5

V sadě Visual Studio 2017 verze 15.5 není integrována CTest **Průzkumník testů**. Testy můžete spustit z hlavní nabídky CMake nebo v místní nabídce *CMakeLists.txt* ve **Průzkumníka řešení**. Výsledky testů jsou směrované na Visual Studio **okno výstup**.

![Testy CTest v sadě Visual Studio 2017 verze 15.5](media/cpp-cmake-run-tests.png)

::: moniker-end

::: moniker range=">=vs-2019"

CTest je plně integrována s **Průzkumník testů** a podporuje také rozhraní testování částí Googlu a Boost. Tyto architektury jsou zahrnuté ve výchozím nastavení jako komponentu **Desktop Development with C++** pracovního vytížení. Nicméně pokud provádíte upgrade projektu ze starší verze sady Visual Studio, budete muset nainstalovat tyto architektury pomocí programu Instalační program sady Visual Studio.

Následující obrázek znázorňuje výsledky CTest spouštět pomocí rozhraní Google Test:

![CTest pomocí rozhraní Google Test v sadě Visual Studio](media/ctest-test-explorer.png)

Pokud používáte CTest, ale ne Google nebo Boost adaptérů, uvidíte výsledky na úrovni CTest namísto jednotlivých testovací metoda úroveň. Můžete ladit a procházení po kroku jen CTest spustitelné soubory, ale trasování zásobníku na jednotlivé testy nejsou podporovány.

::: moniker-end

## <a name="see-also"></a>Viz také:

- [Zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md)