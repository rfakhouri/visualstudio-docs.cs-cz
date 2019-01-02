---
title: Bod, varianty bilineárního, Trilineárního a Anisotropního filtrování textur | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 57d14fc9-b5f7-45ee-9717-48086886742d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7185d9246eb66b1e6773caea8cf20441d463c1ce
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53858407"
---
# <a name="point-bilinear-trilinear-and-anisotropic-texture-filtering-variants"></a>Varianty bodového, bilineárního, trilineárního a anisotropního filtrování textur
Přepíše režim filtrování na odpovídající textury vzorkovače.  
  
## <a name="interpretation"></a>interpretace  
 Různé metody vzorkování textury mít náklady na jiný výkon a kvalita obrazu. V pořadí podle zvýšení nákladů – a zvýšení kvality – jsou režimy filtrování:  
  
1. Bod filtrování (kvalita nejlevnější, nejhorší visual)  
  
2. Varianty filtrování  
  
3. Trilineárního filtrování  
  
4. Anisotropního filtrování (kvalita nejdražší, nejlépe visual)  
  
   Pokud náklady na každý typ variant významné nebo hodnota se zvyšuje s režimy filtrování více náročné na prostředky, můžete zvážit její náklady podle jeho vyšší kvalitu obrazu. Založené na posouzení, byste mohli přijmout náklady na dodatečný výkon pro zvýšení kvality, nebo byste mohli přijmout sníží vizuální kvality, abyste dosáhli vyšší frekvence snímků nebo uvolnit výkonu, který vám pomůže jinými způsoby.  
  
   Pokud zjistíte, že je snížení výkonu zanedbatelný nebo konstantní bez ohledu na režim filtrování – například v případě, že GPU, který cílíte má celou řadu shaderu propustnost a paměti šířku pásma, zvažte použití anizotropní filtrování k dosažení nejlepší image Kvalita ve vaší aplikaci.  
  
## <a name="remarks"></a>Poznámky  
 Stavy vzorkování na volání přepsat tyto varianty `ID3D11DeviceContext::PSSetSamplers` v které režim filtru vzorkovače poskytované aplikací je jedna z následujících:  
  
- `D3D11_FILTER_MIN_MAG_MIP_POINT`  
  
- `D3D11_FILTER_MIN_MAG_POINT_MIP_LINEAR`  
  
- `D3D11_FILTER_MIN_POINT_MAG_LINEAR_MIP_POINT`  
  
- `D3D11_FILTER_MIN_POINT_MAG_MIP_LINEAR`  
  
- `D3D11_FILTER_MIN_LINEAR_MAG_MIP_POINT`  
  
- `D3D11_FILTER_MIN_LINEAR_MAG_POINT_MIP_LINEAR`  
  
- `D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT`  
  
- `D3D11_FILTER_MIN_MAG_MIP_LINEAR`  
  
- `D3D11_FILTER_ANISOTROPIC`  
  
  V **filtrování textur bodu** variant, režim filtru poskytované aplikací, který je nahrazen `D3D11_FILTER_MIN_MAG_MIP_POINT`; v **varianty filtrování textur** variant, je nahrazen `D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT`; a **Trilineárního filtrování textur** variant, je nahrazen `D3D11_FILTER_MIN_MAG_MIP_LINEAR`.  
  
  V **Anisotropního filtrování textur** variant, režim filtru poskytované aplikací, který je nahrazen `D3D11_FILTER_ANISOTROPIC`, a maximální počet Anisotropy je nastavena na 16.  
  
## <a name="restrictions-and-limitations"></a>Omezení a omezení  
 V rozhraní Direct3D určuje úroveň funkcí 9.1 maximální anisotropy 2 x. Vzhledem k tomu, **Anisotropního filtrování textur** variant pokusí použít 16 x anisotropy výhradně, přehrávání selže, když je analýza snímků spuštění na zařízení bodech 9.1 úroveň funkcí. Moderní zařízení, které jsou ovlivněny tohoto omezení patří založené na ARM Surface RT a Windows 2 Surface tablety. Starší grafickými procesory, které může být stále dostupné v některých počítačích může mít vliv i na, ale budete často považuje za zastaralé a je stále běžné.  
  
## <a name="example"></a>Příklad  
 **Filtrování textur bodu** variant možné reprodukovat pomocí kódu takto:  
  
```cpp
D3D11_SAMPLER_DESC sampler_description;  
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_MIN_MAG_MIP_POINT;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```  
  
## <a name="example"></a>Příklad  
 **Varianty filtrování textur** variant možné reprodukovat pomocí kódu takto:  
  
```cpp
D3D11_SAMPLER_DESC sampler_description;   
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```  
  
## <a name="example"></a>Příklad  
 **Trilineárního filtrování textur** variant možné reprodukovat pomocí kódu takto:  
  
```cpp
D3D11_SAMPLER_DESC sampler_description;   
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_MIN_MAG_MIP_LINEAR;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```  
  
## <a name="example"></a>Příklad  
 **Anisotropního filtrování textur** variant možné reprodukovat pomocí kódu takto:  
  
```cpp
D3D11_SAMPLER_DESC sampler_description;   
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_ANISOTROPIC;  
sampler_description.MaxAnisotropy = 16;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```
