---
title: Varianta velikosti oblasti zobrazení 1 x 1 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3dbc3247-00f5-4644-8ff9-72e9febcf09a
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c0052a2d59dbcef1d7ea32eab789ab955750f3f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673690"
---
# <a name="1x1-viewport-size-variant"></a>Varianta velikosti oblasti zobrazení 1x1
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [varianta velikosti oblasti zobrazení 1 x 1](https://docs.microsoft.com/visualstudio/debugger/graphics/1x1-viewport-size-variant).  
  
Snižuje rozměry zobrazení na všechny cíle vykreslení na 1 × 1 pixelů.  
  
## <a name="interpretation"></a>interpretace  
 Menší zobrazení snižuje počet pixelů, které musí být označeno šedou barvou, ale nedojde k omezení počtu vrcholy, které je potřeba zpracovat. Nastavení rozměry zobrazení 1 x 1 pixelů efektivně eliminuje pixel stínování z vaší aplikace.  
  
 Pokud se tato varianta zobrazí zisk náročné na výkon, může to znamenat, že vaše aplikace spotřebovává příliš mnoho fillrate. To může znamenat, že na řešení, které jste zvolili, je příliš vysoká. pro cílovou platformu nebo že vaše aplikace stráví spoustu času stínování pixelů, které jsou přepsány později (overdraw). Tento výsledek naznačuje, že snižují velikost vašeho framebuffer nebo snižuje množství overdraw zlepší výkon vaší aplikace.  
  
## <a name="remarks"></a>Poznámky  
 Rozměry zobrazení se resetují na pixelech 1 × 1 po každém volání do `ID3D11DeviceContext::OMSetRenderTargets` nebo `ID3D11DeviceContext::RSSetViewports`.  
  
## <a name="example"></a>Příklad  
 Tato varianta možné reprodukovat pomocí kódu takto:  
  
```  
D3D11_VIEWPORT viewport;  
viewport.TopLeftX = 0;  
viewport.TopLeftY = 0;  
viewport.Width = 1;  
viewport.Height = 1;  
d3d_context->RSSetViewports(1, &viewport);  
```



