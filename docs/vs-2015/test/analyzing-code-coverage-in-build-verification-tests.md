---
title: Analýza pokrytí kódu v ověřovacích testech sestavení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 59c07d15-511e-4fd0-b398-bde9d5ed00d9
caps.latest.revision: 10
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1dc7dceeaf94ef94a46da6836fea95ac94e49db7
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65686467"
---
# <a name="analyzing-code-coverage-in-build-verification-tests"></a>Analýza pokrytí kódu v testech pro ověření sestavení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Analýza pokrytí kódu v sadě Microsoft Visual Studio se dozvíte, jak velká část kódu je testovány pomocí automatizovaných testů. Další informace najdete v tématu [pomocí pokrytí kódu k určení jak mnohem kódu je právě testováno](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).  
  
 Při vrácení kódu se změnami jsou testy spuštěny na serveru sestavení společně se všemi dalšími testy ostatních členů týmu. (Pokud jste ještě nenastavili to, přečtěte si téma [spuštění testů v procesu sestavení](https://msdn.microsoft.com/library/d05743a1-c5cf-447e-bed9-bed3cb595e38).) Je užitečné analyzovat pokrytí kódu na službě sestavení, protože, která poskytuje nejaktuálnější a nejsrozumitelnější obraz o pokrytí celého projektu. Takový postup bude také zahrnovat automatizované systémové testy a další kódované testy, které nejsou obvykle spouštěny na počítačích vývojářů.  
  
1. V Průzkumníku týmových projektů otevřete **sestavení**a poté přidejte nebo upravte definici sestavení.  
  
2. Na **procesu** stránce, rozbalte **automatizované testy**, **zdroj testu**, **parametrů běhu**. Nastavte **typ souboru parametrů běhu** k **povoleným pokrytím kódu**.  
  
    Pokud máte více než jednu definici Zdroje testu, opakujte tento krok pro každou z nich.  
  
   - <em>Ale neexistuje žádné pole s názvem **typ spustit nastavení souboru</em>*. *  
  
      V části **automatizované testy**vyberte **sestavení testu** a zvolte tlačítko se třemi tečkami **[...]**  na konci řádku. V **přidat/upravit testovací běh** dialogovém okně **nástroj Test Runner**, zvolte **Visual Studio Test Runner**.  
  
   ![Nastavení definice sestavení pro pokrytí kódu](../test/media/codecoverage-plaincc.png "CodeCoverage plainCC")  
  
   Když sestavení proběhne, zobrazí se výsledky pokrytí kódu v souhrnu sestavení.  
  
## <a name="see-also"></a>Viz také  
 [Použití pokrytí kódu k určení rozsahu testovaného kódu](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
