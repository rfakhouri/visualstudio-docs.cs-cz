---
title: "Spuštění testů jednotek v podobě procesu 64-bit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 36a33e9be37255e6bcf199e612a44f65ca243a1e
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>Spuštění testů jednotek v podobě 64bitového procesu
Pokud máte 64bitový počítač, můžete spustit testy jednotek a zachycení informací o pokrytí kódu jako 64bitový proces.  
  
## <a name="running-a-unit-test-as-a-64-bit-process"></a>Spuštění testů jednotek jako 64bitového procesu  
  
#### <a name="to-run-a-unit-test-as-a-64-bit-process"></a>Ke spuštění testů jednotek jako 64bitového procesu  
  
1.  Pokud byly jako 32-bit nebo x86 zkompilovat kód nebo testů, ale teď chcete spustit jako 64bitový proces, znovu zkompiluje je jako **libovolný procesor**, nebo volitelně jako **64-bit**.  
  
    > [!TIP]
    >  Flexibilní, by měl kompilovat testovací projekty s **libovolný procesor** konfigurace. Potom můžete spustit na 32 až 64 bit agenty. Neexistuje žádné výhody kompilace projektů testů pomocí **64-bit** konfigurace.  
  
2.  V sadě Visual Studio nabídce zvolte **Test**, zvolte **nastavení**a potom zvolte **architekturu procesoru**. Zvolte **x64** ke spuštění testů jako 64bitový proces.  
  
     \-nebo –  
  
     Zadejte `<TargetPlatform>x64</TargetPlatform>` v souboru .runsettings. Výhodou této metody je, že můžete zadat skupiny nastavení, v různých souborů a rychlé přepínání mezi různá nastavení. Můžete také zkopírovat nastavení mezi řešení. Další informace najdete v tématu [konfigurace testování částí s použitím souboru .runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).  
  
## <a name="see-also"></a>Viz také

[Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)  
[Testování částí kódu](../test/unit-test-your-code.md)  
