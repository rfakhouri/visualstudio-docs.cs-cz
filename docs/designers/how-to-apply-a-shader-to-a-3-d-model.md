---
title: 'Postupy: použití shaderu 3D modelu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a3877bd6-abd8-4a9d-842c-6848b6c2f335
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08e1a6b8bab7e6336f764f871328e0d56ad0c2f2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917393"
---
# <a name="how-to-apply-a-shader-to-a-3d-model"></a>Postupy: použití shaderu 3D modelu

Tento článek ukazuje, jak použít editoru modelů pro aplikaci shaderu směrované grafu shaderu jazyk (DGSL) na 3D modelu.

## <a name="apply-a-shader-to-a-3d-model"></a>Platí pro 3D model shaderu

Můžete použít efekt shaderu 3D modelu umožnit zajímavé vzhled.

Než začnete, ujistěte se, že **vlastnosti** zobrazí se okno.

1. Začněte s 3D scény, který obsahuje jeden nebo více modelů. Pokud nemáte k dispozici vhodný 3D scény, vytvořit jak je popsáno v [postupy: vytvoření základního modelu 3D](../designers/how-to-create-a-basic-3-d-model.md). Také budete muset mít shaderu DGSL, které můžete použít k modelu. Pokud nemáte k dispozici vhodný shaderu, vytvořit jak je popsáno v [postupy: vytvoření základní shaderu barvu](../designers/how-to-create-a-basic-color-shader.md) a ujistěte se, že uložení do souboru než budete pokračovat.

2. V **vyberte** režimu, vyberte model, který chcete použít shaderu na a pak v **vlastnosti** okno v **Filename** vlastnost **vliv**  vlastnosti skupiny, zadejte shaderu DGSL, který chcete použít pro model.

Tady je model, který má za následek základní barvu na něho použít:

![3&#45;scény D, který ukazuje základní barevný efekt](../designers/media/digit-3d-model-effect.png)

Po instalaci shaderu k modelu, můžete otevřít ho v Návrháři shaderu výběrem modelu a pak v **vlastnosti** okno v **(rozšířené)** vlastnost **vliv**skupina vlastností, výběr se třemi tečkami (**...** ) tlačítko.

## <a name="see-also"></a>Viz také

- [Postupy: vytvoření základní 3D modelu](../designers/how-to-create-a-basic-3-d-model.md)
- [Postupy: Vytvoření shaderu základní barvy](../designers/how-to-create-a-basic-color-shader.md)
- [Editor modelů](../designers/model-editor.md)
- [Návrhář shaderů](../designers/shader-designer.md)