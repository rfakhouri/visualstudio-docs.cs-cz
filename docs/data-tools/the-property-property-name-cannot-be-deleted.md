---
title: "Vlastnost &lt;název vlastnosti&gt; nelze odstranit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 5bba0739a35dbc90c0c9141619c54b93f653d482
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted"></a>Vlastnost &lt;název vlastnosti&gt; nelze odstranit
Vlastnost \<název vlastnosti > nelze odstranit, protože je nastavený jako **diskriminátoru vlastnost** pro vztah dědičnosti mezi \<název třídy > a \<název třídy >  
  
 Vybranou vlastnost je nastavena jako **diskriminátoru vlastnost** pro vztah dědičnosti mezi třídami uvedené v chybové zprávě. Vlastnosti nelze odstranit, pokud se účastní konfiguraci dědičnosti mezi datových tříd.  
  
 Nastavte **diskriminátoru vlastnost** na jinou vlastnost třídy dat. Chcete-li povolit úspěšné odstranění požadované vlastnosti.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  V Návrháři relací objektů vyberte dědičnosti čáry propojující datové třídy uvedené v chybové zprávě.  
  
2.  Nastavte **diskriminátoru** vlastnost, která má jinou vlastnost.  
  
3.  Pokuste se znovu odstranit vlastnost.  
  
## <a name="see-also"></a>Viz také
[Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)