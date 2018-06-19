---
title: Spuštění testů jednotek v podobě 64-bit procesu v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 2b6e44ae9b0587a044cb1a8a0d62db068dfc76d6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31966623"
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>Spuštění testů jednotek v podobě 64bitového procesu

Pokud máte 64bitový počítač, můžete spustit testy jednotek a zachycení informací o pokrytí kódu jako 64bitový proces.

## <a name="to-run-a-unit-test-as-a-64-bit-process"></a>Ke spuštění testů jednotek jako 64bitového procesu

1. Pokud byly jako 32-bit nebo x86 zkompilovat kód nebo testů, ale teď chcete spustit jako 64bitový proces, znovu zkompiluje je jako **libovolný procesor**, nebo volitelně jako **64-bit**.

    > [!TIP]
    > Flexibilní, zkompilovat testovací projekty s **libovolný procesor** konfigurace. Potom můžete spustit na 32bitové a 64bitové verze agentů. Neexistuje žádné výhody kompilace projektů testů pomocí **64-bit** konfigurace.

2. V sadě Visual Studio nabídce zvolte **Test**, zvolte **nastavení**a potom zvolte **architekturu procesoru**. Zvolte **x64** ke spuštění testů jako 64bitový proces.

   - nebo –

   Zadejte `<TargetPlatform>x64</TargetPlatform>` v *.runsettings* souboru. Výhodou této metody je, že můžete zadat skupiny nastavení, v různých souborů a rychlé přepínání mezi různá nastavení. Můžete také zkopírovat nastavení mezi řešení. Další informace najdete v tématu [konfigurace testování částí s použitím souboru .runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).

## <a name="see-also"></a>Viz také

- [Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)
- [Testování částí kódu](../test/unit-test-your-code.md)
