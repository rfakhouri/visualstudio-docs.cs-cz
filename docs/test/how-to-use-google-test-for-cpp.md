---
title: Jak používat Google Test pro C++
description: Použijte Google Test k vytvoření C++ testování částí v aplikaci Visual Studio.
ms.date: 05/06/2017
ms.topic: conceptual
ms.author: mblome
manager: markl
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 73f62e8b74864af0292a9cc3ab1eb325d679d2ea
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926752"
---
# <a name="how-to-use-google-test-for-c-in-visual-studio"></a>Jak používat Google Test pro C++ v sadě Visual Studio

V aplikaci Visual Studio 2017 a novějších jsou Google test integrovány do integrovaného vývojového prostředí sady Visual Studio jako výchozí součást **vývoje C++ desktopových** aplikací. Pokud chcete ověřit, jestli je nainstalovaný na počítači, otevřete instalační program sady Visual Studio a vyhledejte Google Test v seznamu součástí úlohy:

![Instalovat Google Test](media/cpp-google-component.png)

::: moniker range="vs-2019"

## <a name="add-a-google-test-project-in-visual-studio-2019"></a>Přidání projektu Google Test v aplikaci Visual Studio 2019

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na uzel řešení a vyberte možnost **Přidat** > **Nový projekt**.
2. Do vyhledávacího **C++** pole nastavte text na a zadejte **test** . V seznamu výsledků vyberte možnost **Google test projekt**.
3. Pojmenujte testovací projekt a klikněte na tlačítko **OK**.

![Nového projektu Google Test](media/vs-2019/cpp-gtest-new-project-vs2019.png)

::: moniker-end

::: moniker range="vs-2017"

## <a name="add-a-google-test-project-in-visual-studio-2017"></a>Přidání projektu Google Test v aplikaci Visual Studio 2017

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na uzel řešení a vyberte možnost **Přidat** > **Nový projekt**.
2. V levém podokně zvolte > **Visual C++**  **test** a potom v prostředním podokně zvolte **Google test projekt** .
3. Pojmenujte testovací projekt a klikněte na tlačítko **OK**.

![Nového projektu Google Test](media/cpp-gtest-new-project.png)

::: moniker-end

## <a name="configure-the-test-project"></a>Konfigurace testovacího projektu

V **testovací konfigurace projektu** zobrazeném dialogovém okně můžete nastavit projekt, kterou potřebujete otestovat. Když vyberete projekt, Visual Studio přidá odkaz na vybraný projekt. Pokud se rozhodnete žádný projekt, je třeba ručně přidat odkazy na projekty, které chcete testovat. Při volbě mezi statickým a dynamickým propojení binárních souborů Google testu, jaké jsou požadavky jsou stejné jako u každého programu C++. Další informace najdete v tématu [knihovny DLL v jazyce Visual C++](/cpp/build/dlls-in-visual-cpp).

![Konfigurace projektu Google Test](media/cpp-gtest-config.png)

## <a name="set-additional-options"></a>Nastavit další možnosti

V hlavní nabídce zvolte **nástroje** > **možnosti** > **testovací adaptér pro Google Test** můžete nastavit další možnosti. Viz dokumentace ke službě Google Test pro další informace o těchto nastaveních.

![Nastavení projektu Google Test](media/cpp-gtest-settings.png)

## <a name="add-include-directives"></a>Přidání direktiv

V testu *.cpp* přidejte všechny potřebné `#include` direktivy zviditelnit typy a funkce vaší aplikace k testovacímu kódu. Program je obvykle nahoru o jednu úroveň v hierarchii složek. Pokud zadáte `#include "../"` okno technologie IntelliSense se zobrazí a vám umožní vybrat úplná cesta k souboru hlaviček.

![Přidejte #include](media/cpp-gtest-includes.png)

## <a name="write-and-run-tests"></a>Psání a spouštění testů

Nyní jste připraveni pro zápis a spouštění testů Google. Najdete v článku [Úvod do Google Test](https://github.com/google/googletest/blob/master/googletest/docs/primer.md) informace o makra testu. Zobrazit [spouštění testů jednotek pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md) informace o zjišťování, spouštění a seskupení testů s použitím **Průzkumník testů**.

## <a name="see-also"></a>Viz také:

[Zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md)
