---
title: Postup použití testu CTest jazyka C++
ms.date: 05/01/2019
ms.topic: conceptual
ms.author: mblome
manager: jillfra
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: fddb32ce75bf587ee78ca172fd4de2c31237a331
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225940"
---
# <a name="how-to-use-ctest-for-c-in-visual-studio-2017-and-later"></a>Postup použití testu CTest pro C++ v sadě Visual Studio 2017 a novější

CMake (která zahrnuje CTest) je integrována do integrovaného vývojového prostředí sady Visual Studio ve výchozím nastavení jako součást sady **Desktop Development with C++** pracovního vytížení. Pokud je potřeba nainstalovat na svém počítači, spusťte program Instalační program sady Visual Studio, klikněte na tlačítko **Desktop Development with C++**  tlačítko a pak klikněte na **změnit**. Zkontrolujte [nástroje CMake pro Visual C++ ](/cpp/ide/cmake-tools-for-visual-cpp) v seznamu součástí úlohy.

## <a name="to-write-tests"></a>K psaní testů

Podpora CMake v sadě Visual Studio nezahrnuje projektu systému Visual Studio. Proto zápisu a nakonfigurujte testy CTest, stejně jako v jakémkoli prostředí CMake. Další informace o používání CMake v sadě Visual Studio najdete v tématu [nástroje CMake pro Visual C++](/cpp/ide/cmake-tools-for-visual-cpp).

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