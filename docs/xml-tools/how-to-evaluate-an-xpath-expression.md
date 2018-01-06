---
title: "Postupy: vyhodnocení výrazu jazyka XPath | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8a0072df206fcdfc27966632e3801316bcfb7274
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-evaluate-an-xpath-expression"></a>Postupy: vyhodnocení výrazu jazyka XPath
Je možné vyhodnotit výraz XPath s **QuickWatch** dialogové okno. Výraz XPath musí být platná souladu s doporučením W3C XPath 1.0. Aktuální kontext XSLT – to znamená, `self::node()` uzlu **místní hodnoty –** okno – poskytuje kontext vyhodnocení pro výraz XPath.  
  
 Následující seznam popisuje, které funkce jsou podporovány při vyhodnocování výrazu jazyka XPath:  
  
-   Jsou podporovány integrované funkce jazyka XPath.  
  
-   Integrované funkce XSLT nejsou podporovány.  
  
-   Uživatelem definované funkce nejsou podporovány.  
  
> [!NOTE]
>  Následující postup používá belowAvg.xsl a books.xml soubory z [návod: ladění stylů XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md) tématu.  
  
### <a name="to-evaluate-an-xpath-expression"></a>Vyhodnocení výrazu jazyka XPath  
  
1.  Vložit zarážka v `xsl:if` počáteční značka.  
  
2.  Klikněte **ladění XSL** tlačítka na panelu nástrojů editoru XML.  
  
     Ladicí program spustí a dělí na `xsl:if` značky.  
  
3.  Klikněte pravým tlačítkem a vyberte **QuickWatch**.  
  
     **QuickWatch** se zobrazí dialogové okno.  
  
4.  Zadejte `./price/text()` v **výraz** pole z **QuickWatch** dialogové okno a klikněte na tlačítko **přehodnocovat**.  
  
     Cena na aktuální uzel adresáře se zobrazí v **hodnotu** pole.  
  
5.  Změnit výraz XPath pro `./price/text() < $bookAverage` a klikněte na tlačítko **přehodnocovat**.  
  
     **Hodnotu** pole ukazuje, že výraz XPath vyhodnocuje `true`.  
  
## <a name="see-also"></a>Viz také  
 [Ladění XSLT](../xml-tools/debugging-xslt.md)