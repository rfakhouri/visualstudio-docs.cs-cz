---
title: "Jak používat CTest jazyka C++ v sadě Visual Studio | Microsoft Docs"
ms.date: 11/07/2017
ms.technology: vs-ide-test
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 602240df366d9ee978f632a8693bae3de21fcedf
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-use-ctest-for-c-in-visual-studio"></a>Jak používat CTest jazyka C++ v sadě Visual Studio

CMake (která zahrnuje CTest) je integrována do prostředí Visual Studio IDE ve výchozím nastavení jako součást sady **Develoment plochy s jazykem C++** zatížení. Pokud potřebujete k instalaci na váš počítač, otevřete Visual Studio instalačního programu, klikněte na **upravit** tlačítko a potom zkontrolujte [CMake nástrojů pro Visual C++](/cpp/ide/cmake-tools-for-visual-cpp) v seznamu součástí pracovního vytížení.

## <a name="to-write-tests"></a>Zápis testů

Podpora CMake v sadě Visual Studio nebude zahrnovat systému projektu sady Visual Studio. Proto zápisu a konfigurace CTest testů, stejně jako v jakémkoli CMake prostředí. Další informace o používání CMake v sadě Visual Studio najdete v tématu [CMake nástrojů pro Visual C++](/cpp/ide/cmake-tools-for-visual-cpp).

## <a name="to-run-tests-visual-studio-2017-version-156"></a>Ke spuštění testů (Visual Studio 2017 verze 15,6 operací)

V aplikaci Visual Studio 2017 verze 15,6 operací, CTest jsou plně integrované s **Průzkumníka testů** a také podporuje testování rozhraní Google i nárůst částí. Tyto architektury jsou zahrnuté ve výchozím nastavení jako komponenty ve **Develoment plochy s jazykem C++** zatížení. Ale pokud provádíte upgrade projektu ze starší verze sady Visual Studio, může musíte nainstalovat tyto architektury pomocí programu Instalační program Visual Studio.

Následující obrázek znázorňuje výsledky CTest, spustí pomocí Google Test framework:

![CTest s Google Test Framework v VS2017 15,6 operací](media/ctest-test-explorer.png "CTest a Google testů v testovací Explorer")

Pokud používáte CTest, ale není Google nebo nárůst adaptérů, zobrazí výsledky na úrovni CTest místo jednotlivých testů metoda úroveň. Můžete ladit a procházení po kroku jen CTest spustitelné soubory, ale trasování zásobníku na jednotlivé testy nejsou podporovány.

## <a name="to-run-tests-visual-studio-2017-version-155"></a>Ke spuštění testů (Visual Studio 2017 verze 15,5)

V **Visual Studio 2017 verze 15,5**, CTest není integrovaná s **Průzkumníka testů**. Testy můžete spustit z hlavní nabídky CMake nebo v místní nabídce na **CMakeLists.txt** souboru v **Průzkumníku řešení**. Výsledky testů jsou směrované sady Visual Studio **výstup – okno**.

![Spuštění testů CTest 15,5 VS2017](media/cpp-cmake-run-tests.png "CTest spuštění testů v 15,5")

## <a name="see-also"></a>Viz také

[Zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md)