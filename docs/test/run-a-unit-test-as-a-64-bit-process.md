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
ms.assetid: d23a9ee7-58e3-4e8b-a38c-b2207ea73fea
caps.latest.revision: "25"
ms.author: douge
manager: douge
ms.openlocfilehash: bb22521dc0c4f4a1a824c3554ce37297a61108c5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
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
 [Spouštění testů jednotek pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)   
 [Testování částí kódu](../test/unit-test-your-code.md)   
 [Zadání nastavení testu pro testy Visual Studia](/devops-test-docs/test/specifying-test-settings-for-visual-studio-tests)
