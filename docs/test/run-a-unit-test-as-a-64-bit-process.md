---
title: "Spuštění testů jednotek v podobě 64-bit procesu v sadě Visual Studio | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: fa7b467be269466170962944e9fbf8bd3a9889f0
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
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
