---
title: Vlastnost &lt;název vlastnosti&gt; nelze odstranit | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 22884e69c4802ec0bf699e383f0339d840f515e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628460"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted"></a>Vlastnost &lt;název vlastnosti&gt; nelze odstranit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vlastnost &lt;název vlastnosti&gt; nelze odstranit](https://docs.microsoft.com/visualstudio/data-tools/the-property-property-name-cannot-be-deleted).  
  
  
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
 [Návod: Vytvoření třídy LINQ to SQL s použitím dědičnosti jedné tabulky (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)

