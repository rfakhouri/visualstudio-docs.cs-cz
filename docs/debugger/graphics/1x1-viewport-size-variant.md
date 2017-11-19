---
title: "1 × 1 velikosti zobrazovacího okna Variant | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3dbc3247-00f5-4644-8ff9-72e9febcf09a
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 074cf7111108b7ae4f3b6866be19f0a12d3c429b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="1x1-viewport-size-variant"></a>1 × 1 velikosti zobrazovacího okna Variant
Snižuje dimenze zobrazení na všechny cíle vykreslování do 1 x 1 pixel.  
  
## <a name="interpretation"></a>Interpretace  
 Menší zobrazení snižuje počet pixelů, které musí být šedou barvou, ale není snížit počet vrcholy, které musí být zpracován. Nastavení zobrazení dimenzí 1 x 1 pixel efektivně eliminuje pixelů stínování z vaší aplikace.  
  
 Pokud tato varianta zobrazuje velké výkonnější, může to znamenat, že vaše aplikace využívá příliš mnoho fillrate. Může to znamenat, že rozlišení zvolili jste je příliš vysoká. pro cílovou platformu nebo který aplikace tráví déle stínování pixelů, které jsou přepsány později (overdraw). Tento výsledek naznačuje, že při snížení velikosti vašeho framebuffer nebo snižuje množství overdraw se zvýší výkon vaší aplikace.  
  
## <a name="remarks"></a>Poznámky  
 Dimenze zobrazení se obnoví do 1 x 1 pixel po každé volání `ID3D11DeviceContext::OMSetRenderTargets` nebo `ID3D11DeviceContext::RSSetViewports`.  
  
## <a name="example"></a>Příklad  
 Tento typ variant lze reprodukovat pomocí kódu takto:  
  
```  
D3D11_VIEWPORT viewport;  
viewport.TopLeftX = 0;  
viewport.TopLeftY = 0;  
viewport.Width = 1;  
viewport.Height = 1;  
d3d_context->RSSetViewports(1, &viewport);  
```