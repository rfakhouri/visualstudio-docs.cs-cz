---
title: Spuštění testů jednotek jako 64bitový proces | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.assetid: d23a9ee7-58e3-4e8b-a38c-b2207ea73fea
caps.latest.revision: 27
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6b8dd75f7d293ee4e7dc412b2ff8f1983d936e3a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446258"
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>Spuštění testování částí v podobě 64bitového procesu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud máte 64bitový počítač, můžete spustit testy jednotky a zaznamenat informace o pokrytí kódu jako 64bitový proces.  
  
## <a name="running-a-unit-test-as-a-64-bit-process"></a>Spuštění testování částí jako 64bitový proces  
  
#### <a name="to-run-a-unit-test-as-a-64-bit-process"></a>Spuštění testování částí jako 64bitový proces  
  
1. Pokud váš kód nebo testů byly kompilovány jako 32-bit/x86, ale chcete nyní spustit jako 64bitový proces, znovu zkompilovat jako **jakýkoli procesor**, nebo volitelně jako **64-bit**.  
  
    > [!TIP]
    > Pro maximální flexibilitu byste měli kompilovat testovací projekty s **jakýkoli procesor** konfigurace. Poté můžete spouštět na 32 a 64 64bitových agentech. Neexistuje žádná výhoda pro kompilaci testovacích projektů s **64-bit** konfigurace.  
  
2. V nabídce sady Visual Studio zvolte **testovací**, klikněte na tlačítko **nastavení**a klikněte na tlačítko **architekturu procesoru**. Zvolte **x64** spustit testy jako 64bitový proces.  
  
     \- nebo –  
  
     Zadejte `<TargetPlatform>x64</TargetPlatform>` v souboru s příponou .runsettings. Výhodou této metody je, že můžete zadat skupiny nastavení v různých souborů a rychle přepínat mezi různými nastaveními. Můžete také kopírovat nastavení mezi řešeními. Další informace najdete v tématu [konfigurace testů jednotek s použitím souboru .runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).  
  
## <a name="see-also"></a>Viz také  
 [Spouštění testů jednotek pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)   
 [Testování částí kódu](../test/unit-test-your-code.md)   
 [Zadání nastavení testu pro testy Visual Studia](http://msdn.microsoft.com/library/0c15317e-80c6-4317-aed3-82b8e15e3901)
