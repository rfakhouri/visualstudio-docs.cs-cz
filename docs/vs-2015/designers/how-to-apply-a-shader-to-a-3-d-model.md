---
title: 'Postupy: použití shaderu na 3D Model | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3877bd6-abd8-4a9d-842c-6848b6c2f335
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 277711a0dd2a106c8770b2b7d720666589e65d86
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677730"
---
# <a name="how-to-apply-a-shader-to-a-3-d-model"></a>Postupy: Použití shaderu na 3D model
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: použití shaderu na 3D Model](https://docs.microsoft.com/visualstudio/designers/how-to-apply-a-shader-to-a-3-d-model).  
  
Tento dokument popisuje způsob použití Editoru modelů pro použití orientovaného grafu Shader Language (DGSL) shaderu na 3D model.  
  
 Tento dokument ukazuje, tato aktivita:  
  
-   Použití shaderu na 3D model  
  
## <a name="applying-a-shader-to-a-3-d-model"></a>Použití shaderu na 3D model  
 Použít efekt shaderu na 3D model nabízí zajímavé vzhled.  
  
 Než začnete, ujistěte se, že **vlastnosti** se zobrazí okno.  
  
#### <a name="to-apply-a-shader-to-a-3-d-model"></a>K použití shaderu na 3D model  
  
1.  Začněte s 3D scény, který obsahuje jeden nebo více modelů. Pokud nemáte k dispozici vhodný 3D scény, vytvořit jak je popsáno v [postupy: vytvoření základního 3D modelu](../designers/how-to-create-a-basic-3-d-model.md). Také musíte mít DGSL shader, který můžete použít pro model. Pokud nemáte k dispozici vhodný shaderu, vytvořit jak je popsáno v [postupy: vytvoření shaderu základní barvy](../designers/how-to-create-a-basic-color-shader.md) a ujistěte se, že jste jste ho uložili do souboru předtím, než budete pokračovat.  
  
2.  V **vyberte** režimu, vybrat model, který chcete použít shaderu na a pak v **vlastnosti** okno v **Filename** vlastnost **efekt**  skupiny vlastností zadejte DGSL shader, který má být použita k modelu.  
  
 Tady je model, který je použit efekt základní barvy:  
  
 ![3&#45;scény D, která demonstruje účinek základní barvy](../designers/media/digit-3d-model-effect.png "číslice 3D modelu efekt")  
  
 Po použití shaderu na model, lze jej otevřít v Návrháři shaderu tak, že vyberete model a pak v **vlastnosti** okno v **(rozšířené)** vlastnost **efekt**skupiny vlastností, vyberete symbol tří teček (**...** ) tlačítko.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření základního 3D modelu](../designers/how-to-create-a-basic-3-d-model.md)   
 [Postupy: vytvoření shaderu základní barvy](../designers/how-to-create-a-basic-color-shader.md)   
 [Editor modelů](../designers/model-editor.md)   
 [Návrhář shaderů](../designers/shader-designer.md)



