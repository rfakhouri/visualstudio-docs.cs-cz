---
title: Vlastnost &lt;název vlastnosti&gt; nelze odstranit, protože se účastní přidružení &lt;název přidružení&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5121d79e6db6bdef1deb0ee04540295b2a109f72
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>Vlastnost &lt;název vlastnosti&gt; nelze odstranit, protože se účastní přidružení &lt;název přidružení&gt;
Vybranou vlastnost je nastavena jako **vlastnosti přidružení** pro přidružení mezi třídami uvedené v chybové zprávě. Vlastnosti nelze odstranit, pokud se účastní přidružení mezi datových tříd.  
  
 Nastavte **vlastnosti přidružení** na jinou vlastnost třídy dat. Chcete-li povolit úspěšné odstranění požadované vlastnosti.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Vyberte řádek přidružení na Návrhář relací objektů, který se připojuje datové třídy uvedené v chybové zprávě.  
  
2.  Klikněte dvakrát na řádek otevřete **přidružení Editor** dialogové okno.  
  
3.  Odeberte vlastnost z **vlastnosti přidružení**.  
  
4.  Pokuste se znovu odstranit vlastnost.  
  
## <a name="see-also"></a>Viz také
[Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)