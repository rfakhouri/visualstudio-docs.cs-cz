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
ms.openlocfilehash: b3a896e64e048a5104bca84b726c730d4d9d524a
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
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
[Návrhář relací objektů zprávy](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)