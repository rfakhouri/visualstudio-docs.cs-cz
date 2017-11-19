---
title: "Analýza pokrytí kódu v testech pro ověření sestavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59c07d15-511e-4fd0-b398-bde9d5ed00d9
caps.latest.revision: "8"
ms.author: douge
manager: douge
ms.openlocfilehash: 3dab1fb335bf1fa7a51faf8f298208c18ec87dc5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
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
 [Použití pokrytí kódu k určení jak mnohem kódu se testuje](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
