---
title: "Postupy: úprava bodu Pivot 3D modelu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c20b4ec8-29f5-4ca5-bc39-d4548ca6f573
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1f0c356df742f279e60d81a060551530be49ac9d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-modify-the-pivot-point-of-a-3-d-model"></a>Postupy: Změna bodu otáčení 3D modelu
Tento dokument ukazuje, jak upravit pomocí editoru modelu *bodu otáčení* 3D modelu. Bod pivot je bod v prostor, který definuje matematické center objektu pro otáčení a škálování.  
  
 Tento dokument ukazuje této aktivity:  
  
-   Úprava pivot bodu objektu  
  
## <a name="modifying-the-pivot-point-of-a-3-d-model"></a>Úprava bodem pivot 3D modelu  
 Původ 3D model můžete upravit změnou jeho pivot bodu.  
  
 Ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.  
  
#### <a name="to-modify-the-pivot-point-of-a-3-d-model"></a>Chcete-li upravit bodem pivot 3D modelu  
  
1.  Začátek s existující 3D modelu, například ten, který je popsaný v [postupy: vytvoření základního modelu 3D](../designers/how-to-create-a-basic-3-d-model.md).  
  
2.  Zadejte režim pivot. Na **modelu Editor režimu** nástrojů, vyberte **Pivot režimu** tlačítko aktivovat pivot režimu. Pole se kolem **Pivot režimu** tlačítko, které označuje, že editoru modelu je nyní v režimu pivot. V režimu pivot operace jako je například překlad ovlivňují pivot bodu objektu místo strukturu objektu v místa na světě.  
  
3.  Úprava pivot bodu objektu. V **vyberte** režimu, vyberte objekt a pak na **modelu prohlížeč** nástrojů, vyberte **přeložit** nástroj. Pole, který představuje bod pivot, zobrazí se na návrhovou plochu. Přesuňte pole k úpravě pivot bodu objektu.  
  
     Přesunutím pole můžete přesunout pivot bod v všechny tři dimenze. Přeložit bodem pivot jednu osu, přesuňte na šipku, která odpovídá této osy. Pole a dvojice šipek, které změní na žlutou barvu, která má znamenat ose, která jsou ovlivněná překlad.  
  
     Bod pivot můžete také zadat pomocí **Pivot překlad** vlastnost **vlastnosti** okno.  
  
    > [!TIP]
    >  Můžete zobrazit účinku nový bod pivot otáčení objektu. Otočení, použijte **otočit** nástroje nebo změnit **otočení** vlastnost.  
  
 Tady je model, který má bod upravené pivot:  
  
 ![Model úklidové, který má bod upravené pivot](../designers/media/digit-modified-model.png "číslice upravit modelu")  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření základní 3D modelu](../designers/how-to-create-a-basic-3-d-model.md)   
 [Editor modelu](../designers/model-editor.md)