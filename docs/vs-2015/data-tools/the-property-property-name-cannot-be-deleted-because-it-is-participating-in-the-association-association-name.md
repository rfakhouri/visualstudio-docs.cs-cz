---
title: Vlastnost &lt;název vlastnosti&gt; nejde odstranit, protože se účastní asociace &lt;název přidružení&gt; | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 52dc1d42ab8fff879bd290fe1a9c9aa2ca0a08c0
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65700308"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>Vlastnost &lt;název vlastnosti&gt; nejde odstranit, protože se účastní asociace &lt;název přidružení&gt;
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vybraná vlastnost je nastavena jako **přidružení vlastnost** pro přidružení mezi třídami uvedené v chybové zprávě. Vlastnosti nelze odstranit, pokud se účastní asociace mezi datových tříd.  
  
 Nastavte **přidružení vlastnost** různé vlastnosti třídy dat umožňující úspěšné odstranění sady požadovanou vlastnost.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1. Vyberte Asociační čára na Návrháře relací objektů, která se připojuje datové třídy uvedené v chybové zprávě.  
  
2. Dvakrát klikněte na řádek otevřít **Editor asociace** dialogové okno.  
  
3. Odebere vlastnost z **vlastnosti přidružení**.  
  
4. Zkuste znovu odstranit vlastnost.  
  
## <a name="see-also"></a>Viz také  
 [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [Postupy: Vytvoření přidružení (vztah) mezi třídy LINQ to SQL (O/R Designer)](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)   
 [Návod: Vytvoření třídy LINQ to SQL (Návrhář O-R)](https://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)
