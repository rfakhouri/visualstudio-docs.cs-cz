---
title: 'Postupy: úprava bodu Pivot 3D modelu'
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: c20b4ec8-29f5-4ca5-bc39-d4548ca6f573
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d39d8a9406574f3e8959818051a70660042eab92
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-modify-the-pivot-point-of-a-3d-model"></a>Postupy: úprava bodu Pivot 3D modelu

Tento článek ukazuje, jak upravit pomocí editoru modelu *bodu otáčení* 3D modelu. Bod pivot je bod v prostor, který definuje matematické center objektu pro otáčení a škálování.

## <a name="modify-the-pivot-point-of-a-3d-model"></a>Úprava bodu pivot 3D modelu

Původ 3D model můžete upravit změnou jeho pivot bodu.

Ujistěte se, že **vlastnosti** okno a **sada nástrojů** jsou zobrazeny.

1.  Začátek s existující 3D modelu, například ten, který je popsaný v [postupy: vytvoření základního modelu 3D](../designers/how-to-create-a-basic-3-d-model.md).

2.  Zadejte režim pivot. Na **modelu Editor režimu** nástrojů, vyberte **Pivot režimu** tlačítko aktivovat pivot režimu. Pole se kolem **Pivot režimu** tlačítko, které označuje, že editoru modelu je nyní v režimu pivot. V režimu pivot operace jako je například překlad ovlivňují pivot bodu objektu místo strukturu objektu v místa na světě.

3.  Úprava pivot bodu objektu. V **vyberte** režimu, vyberte objekt a pak na **modelu prohlížeč** nástrojů, vyberte **přeložit** nástroj. Pole, který představuje bod pivot, zobrazí se na návrhovou plochu. Přesuňte pole k úpravě pivot bodu objektu.

     Přesunutím pole můžete přesunout pivot bod v všechny tři dimenze. Přeložit bodem pivot jednu osu, přesuňte na šipku, která odpovídá této osy. Pole a dvojice šipek, které změní na žlutou barvu, která má znamenat ose, která jsou ovlivněná překlad.

     Bod pivot můžete také zadat pomocí **Pivot překlad** vlastnost **vlastnosti** okno.

    > [!TIP]
    > Můžete zobrazit účinku nový bod pivot otáčení objektu. Otočení, použijte **otočit** nástroje nebo změnit **otočení** vlastnost.

Tady je model, který má bod upravené pivot:

![Model úklidové, který má bod upravené pivot](../designers/media/digit-modified-model.png "číslice upravit modelu")

## <a name="see-also"></a>Viz také

- [Postupy: vytvoření základní 3D modelu](../designers/how-to-create-a-basic-3-d-model.md)
- [Editor modelů](../designers/model-editor.md)