---
title: Varianta velikosti oblasti zobrazení 1 x 1 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3dbc3247-00f5-4644-8ff9-72e9febcf09a
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 74e3bc706cb2df12aacddf9fbb77dec598bfc17a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157557"
---
# <a name="1x1-viewport-size-variant"></a>Varianta velikosti oblasti zobrazení 1x1
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
