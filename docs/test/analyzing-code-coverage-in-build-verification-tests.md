---
title: "Analýza pokrytí kódu v testech pro ověření sestavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3f02166c89837dfd122ab8a8c71913c659ab1dd2
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/13/2018
---
# <a name="analyzing-code-coverage-in-build-verification-tests"></a>Analýza pokrytí kódu v testech pro ověření sestavení
Analýza pokrytí kódu v sadě Microsoft Visual Studio ukazuje, kolik z vašeho kódu se vykonávají automatizovaných testů. Další informace najdete v tématu [pomocí pokrytí kódu k určení jak mnohem kódu se testuje](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).  
  
 Při vrácení kódu se změnami jsou testy spuštěny na serveru sestavení společně se všemi dalšími testy ostatních členů týmu. (Pokud ještě již nastavit tuto možnost, přečtěte si téma [procesu sestavení spustit testy](http://msdn.microsoft.com/Library/d05743a1-c5cf-447e-bed9-bed3cb595e38).) Je užitečné k analýze pokrytí kódu ve službě sestavení vzhledem k tomu, který poskytuje nejnovější a komplexní přehled o pokrytí v celý projekt. Bude také zahrnovat automatizované systémové testy a jiné programové testy, které nejsou obvykle spustit na počítačích, vývoj.  
  
1.  V nástroji Team Explorer otevřete **sestavení**a potom přidat nebo upravit definici buildu.  
  
2.  Na **proces** rozbalte **automatizovaných testů**, **Test zdroje**, **spustit nastavení**. Nastavit **typ souboru parametrů běhu** k **Code pokrytí povoleno**.  
  
     Pokud máte více než jednu definici Zdroje testu, opakujte tento krok pro každou z nich.  
  
    -   *Ale neexistuje žádné pole s názvem **typ spuštění nastavení souboru**.*  
  
         V části **automatizovaných testů**, vyberte **testovací sestavení** a zvolte tlačítko se třemi tečkami **[...]**  na konci řádku. V **spuštění testu, přidat či upravit** dialogovém **Test Runner**, zvolte **Visual Studio Test Runner**.  
  
 ![Nastavení definici sestavení pro pokrytí kódu](../test/media/codecoverage-plaincc.png "CodeCoverage plainCC")  
  
 Po spuštění sestavení zobrazí výsledky pokrytí kódu v souhrnu sestavení.  
  
## <a name="see-also"></a>Viz také  
 [Použití pokrytí kódu k určení rozsahu testovaného kódu](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
