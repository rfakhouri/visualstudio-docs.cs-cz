---
title: "Jak používat CTest jazyka C++ v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
author: mikeblome
ms.openlocfilehash: 989f2b06df55fd0927863fe7e5603d3d0ec90b06
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="how-to-use-ctest-for-c-in-visual-studio"></a>Jak používat CTest jazyka C++ v sadě Visual Studio
CMake (která zahrnuje CTest) je integrována do prostředí Visual Studio IDE jako součást sady **Develoment plochy s jazykem C++** zatížení. Který jej nainstaluje na váš počítač, spusťte instalační program Visual Studio a najít [CMake nástrojů pro Visual C++](/cpp/ide/cmake-tools-for-visual-cpp) v seznamu součástí pracovního vytížení.

Podpora CMake v sadě Visual Studio nezahrnuje systému projektu sady Visual Studio. Proto zápisu a konfigurace CTest testů, stejně jako v jakémkoli CMake prostředí. V tématu [CMake nástrojů pro Visual C++](/cpp/ide/cmake-tools-for-visual-cpp) pro další informace o používání CMake v sadě Visual Studio.

**Visual Studio 2017 verze 15,5** CTest není aktuálně integrovat **Průzkumníka testů**. Testy můžete spustit z hlavní nabídky CMake nebo v místní nabídce na **CMakeLists.txt** souboru v **Průzkumníku řešení**. Výsledky testů jsou směrované sady Visual Studio **výstup – okno**.

![Testy CTest](media/cpp-cmake-run-tests.png "CTest spustit testy")


## <a name="see-also"></a>Viz také
[Zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md)


  







