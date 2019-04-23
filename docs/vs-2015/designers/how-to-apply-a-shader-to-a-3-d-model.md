---
title: 'Postupy: Použití shaderu na 3D Model | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a3877bd6-abd8-4a9d-842c-6848b6c2f335
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a55c1e71242e59c04066c09efa2375c4bafc485b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60094774"
---
# <a name="how-to-apply-a-shader-to-a-3-d-model"></a>Postupy: Použití shaderu na 3D Model
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento dokument popisuje způsob použití Editoru modelů pro použití orientovaného grafu Shader Language (DGSL) shaderu na 3D model.  
  
 Tento dokument ukazuje, tato aktivita:  
  
- Použití shaderu na 3D model  
  
## <a name="applying-a-shader-to-a-3-d-model"></a>Použití shaderu na 3D model  
 Použít efekt shaderu na 3D model nabízí zajímavé vzhled.  
  
 Než začnete, ujistěte se, že **vlastnosti** se zobrazí okno.  
  
#### <a name="to-apply-a-shader-to-a-3-d-model"></a>K použití shaderu na 3D model  
  
1. Začněte s 3D scény, který obsahuje jeden nebo více modelů. Pokud nemáte k dispozici vhodný 3D scény, vytvořit jak je popsáno v [jak: Vytvoření základního 3D modelu](../designers/how-to-create-a-basic-3-d-model.md). Také musíte mít DGSL shader, který můžete použít pro model. Pokud nemáte k dispozici vhodný shaderu, vytvořit jak je popsáno v [jak: Vytvoření shaderu základní barvy](../designers/how-to-create-a-basic-color-shader.md) a ujistěte se, že jste jste ho uložili do souboru předtím, než budete pokračovat.  
  
2. V **vyberte** režimu, vybrat model, který chcete použít shaderu na a pak v **vlastnosti** okno v **Filename** vlastnost **efekt**  skupiny vlastností zadejte DGSL shader, který má být použita k modelu.  
  
   Tady je model, který je použit efekt základní barvy:  
  
   ![3&#45;scény D, která demonstruje účinek základní barvy](../designers/media/digit-3d-model-effect.png "číslice 3D modelu efekt")  
  
   Po použití shaderu na model, lze jej otevřít v Návrháři shaderu tak, že vyberete model a pak v **vlastnosti** okno v **(rozšířené)** vlastnost **efekt**skupiny vlastností, vyberete symbol tří teček (**...** ) tlačítko.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytvoření základního 3D modelu](../designers/how-to-create-a-basic-3-d-model.md)   
 [Postupy: Vytvoření shaderu základní barvy](../designers/how-to-create-a-basic-color-shader.md)   
 [Model Editor](../designers/model-editor.md)   
 [Návrhář shaderů](../designers/shader-designer.md)
