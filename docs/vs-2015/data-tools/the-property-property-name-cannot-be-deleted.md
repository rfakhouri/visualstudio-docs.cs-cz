---
title: Vlastnost &lt;název vlastnosti&gt; nelze odstranit | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f9d3533f2eb6cfb5bc2e3a68370f48daa4acfc1e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54752325"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted"></a>Vlastnost &lt;název vlastnosti&gt; nelze odstranit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Vlastnost \<název vlastnosti > nejde odstranit, protože je nastaven jako vlastnost diskriminátoru dědičnosti mezi \<název třídy > a \<název třídy >  
  
 Vybraná vlastnost je nastavena jako **vlastnost diskriminátoru** dědičnosti mezi třídami uvedené v chybové zprávě. Vlastnosti nelze odstranit, pokud se účastníte v konfiguraci dědičnosti mezi třídami data.  
  
 Nastavte **vlastnost diskriminátoru** různé vlastnosti třídy dat umožňující úspěšné odstranění sady požadovanou vlastnost.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  V Návrháři relací objektů vyberte čáru dědičnosti, která se připojuje datové třídy uvedené v chybové zprávě.  
  
2.  Nastavte **diskriminátoru** vlastnost na jinou vlastnost.  
  
3.  Zkuste znovu odstranit vlastnost.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Konfigurace dědičnosti pomocí Návrháře relací objektů](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)   
 [Dědičnost datových tříd (Návrhář O/R)](../data-tools/data-class-inheritance-o-r-designer.md)   
 [Návod: Vytvoření tříd LINQ to SQL pomocí dědičnosti jedné tabulky (Návrhář relací objektů)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)
