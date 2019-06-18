---
title: Postup použití testu CTest jazyka C++
ms.date: 05/01/2019
ms.topic: conceptual
ms.author: mblome
manager: jillfra
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 0b6c4eb391014342a18ec3fe56a03a651463105c
ms.sourcegitcommit: d4920babfc3d24a3fe1d4bf446ed3fe73b344467
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/17/2019
ms.locfileid: "67160079"
---
# <a name="how-to-use-ctest-for-c-in-visual-studio-2017-and-later"></a>Postup použití testu CTest pro C++ v sadě Visual Studio 2017 a novější

CMake (která zahrnuje CTest) je integrována do integrovaného vývojového prostředí sady Visual Studio ve výchozím nastavení jako součást sady **Desktop Development with C++** pracovního vytížení. Pokud je potřeba nainstalovat na svém počítači, spusťte program Instalační program sady Visual Studio, klikněte na tlačítko **Desktop Development with C++**  tlačítko a pak klikněte na **změnit**. Vyberte  **C++ nástroje CMake pro Windows** v seznamu součástí úlohy.

## <a name="to-write-tests"></a>K psaní testů

Podpora CMake v sadě Visual Studio nezahrnuje projektu systému Visual Studio. Proto zápisu a nakonfigurujte testy CTest, stejně jako v jakémkoli prostředí CMake. Další informace o používání CMake v sadě Visual Studio najdete v tématu [projekty CMake v sadě Visual Studio](/cpp/build/cmake-projects-in-visual-studio).

## <a name="to-run-tests"></a>Ke spuštění testů

CTest je plně integrována s **Průzkumník testů** a podporuje také rozhraní testování částí Googlu a Boost. Tyto architektury jsou zahrnuté ve výchozím nastavení jako komponentu **Desktop Development with C++** pracovního vytížení. Nicméně pokud provádíte upgrade projektu ze starší verze sady Visual Studio, budete muset nainstalovat tyto architektury pomocí programu Instalační program sady Visual Studio.

Následující obrázek znázorňuje výsledky CTest spouštět pomocí rozhraní Google Test:

![CTest pomocí rozhraní Google Test v sadě Visual Studio](media/ctest-test-explorer.png)

Pokud používáte CTest, ale ne Google nebo Boost adaptérů, uvidíte výsledky na úrovni CTest namísto jednotlivých testovací metoda úroveň. Můžete ladit a procházení po kroku jen CTest spustitelné soubory, ale trasování zásobníku na jednotlivé testy nejsou podporovány.

Následující obrázek znázorňuje výsledky CTest spouštět pomocí rozhraní Google Test:

![CTest pomocí rozhraní Google Test v sadě Visual Studio 2017](media/ctest-test-explorer.png)

Pokud používáte CTest, ale ne Google nebo Boost adaptérů, uvidíte výsledky na úrovni CTest namísto jednotlivých testovací metoda úroveň. Můžete ladit a procházení po kroku jen CTest spustitelné soubory, ale trasování zásobníku na jednotlivé testy nejsou podporovány.

## <a name="see-also"></a>Viz také:

- [Zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md)
