---
title: "Bod, bilineární, Trilinear a volba Texture filtrování variant | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57d14fc9-b5f7-45ee-9717-48086886742d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cd601307ce635a4f4477f3d3ef3ea133f3981a3b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="point-bilinear-trilinear-and-anisotropic-texture-filtering-variants"></a>Bod, bilineární, Trilinear a volba Texture filtrování variant
Přepíše režim filtrování na příslušné texture vzorkovací body.  
  
## <a name="interpretation"></a>Interpretace  
 Různé metody vzorkování texture mají různé výkonu náklady a bitové kopie kvality. V pořadí podle zvýšit náklady – a zvýšení kvality visual – režim filtru:  
  
1.  Bod filtrování (nejlevnější, nejhorších visual kvality)  
  
2.  Bilineární filtrování  
  
3.  Trilinear filtrování  
  
4.  Volba filtrování (nejnákladnější, nejlépe visual kvality)  
  
 Pokud výkonu náklady na každý typ variant je důležité, nebo se zvyšuje s režimy filtrování náročných na další, můžete naváží jeho náklady s jeho vyšší bitové kopie kvality. Na základě posouzení konkrétních, může přijmout náklady na další výkonu zvýšit vizuální kvality, nebo může přijmout zmenšit visual kvality k dosažení vyšší obnovovací frekvence nebo získat výkonu, který můžete použít jiné způsoby.  
  
 Pokud zjistíte, že náklady na výkon je nepatrné nebo konstantní bez ohledu na režim filtrování – například v případě, že na grafický procesor, který jste cílení má celou řadu shaderu propustnost a paměti šířku pásma, zvažte použití volba filtrování k dosažení nejlepší bitové kopie Kvalita ve vaší aplikaci.  
  
## <a name="remarks"></a>Poznámky  
 Tyto variant přepsat stavy sampler na volání `ID3D11DeviceContext::PSSetSamplers` v režimu filtru sampler zadaný aplikace tedy jednu z těchto:  
  
-   `D3D11_FILTER_MIN_MAG_MIP_POINT`  
  
-   `D3D11_FILTER_MIN_MAG_POINT_MIP_LINEAR`  
  
-   `D3D11_FILTER_MIN_POINT_MAG_LINEAR_MIP_POINT`  
  
-   `D3D11_FILTER_MIN_POINT_MAG_MIP_LINEAR`  
  
-   `D3D11_FILTER_MIN_LINEAR_MAG_MIP_POINT`  
  
-   `D3D11_FILTER_MIN_LINEAR_MAG_POINT_MIP_LINEAR`  
  
-   `D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT`  
  
-   `D3D11_FILTER_MIN_MAG_MIP_LINEAR`  
  
-   `D3D11_FILTER_ANISOTROPIC`  
  
 V **bodu Texture filtrování** variant, režim filtru zadaná aplikace se nahradí `D3D11_FILTER_MIN_MAG_MIP_POINT`; v **bilineární filtrování Texture** variant, je nahrazen `D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT`; a v **Trilinear filtrování Texture** variant, je nahrazen `D3D11_FILTER_MIN_MAG_MIP_LINEAR`.  
  
 V **volba filtrování Texture** variant, režim filtru zadaná aplikace se nahradí `D3D11_FILTER_ANISOTROPIC`, a maximální Anisotropy je nastavena na 16.  
  
## <a name="restrictions-and-limitations"></a>Omezení a omezení  
 V Direct3D určuje úroveň funkcí 9.1 maximální anisotropy 2 x. Protože **volba filtrování Texture** variant pokusí použít 16 x anisotropy výhradně, přehrávání selže, pokud analýza snímků běží na úrovni funkcí bodech 9.1 zařízení. Moderní zařízení, které se vztahuje toto omezení zahrnují bázi ARM Surface RT a Windows 2 prostor pro tablety. Starší grafickými procesory, které se může stále v některých počítačích může mít vliv i, ale často se považuje za zastaralý a jsou stále neobvyklé.  
  
## <a name="example"></a>Příklad  
 **Bodu Texture filtrování** variant lze reprodukovat pomocí kódu takto:  
  
```  
D3D11_SAMPLER_DESC sampler_description;  
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_MIN_MAG_MIP_POINT;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```  
  
## <a name="example"></a>Příklad  
 **Bilineární filtrování Texture** variant lze reprodukovat pomocí kódu takto:  
  
```  
D3D11_SAMPLER_DESC sampler_description;   
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```  
  
## <a name="example"></a>Příklad  
 **Trilinear filtrování Texture** variant lze reprodukovat pomocí kódu takto:  
  
```  
D3D11_SAMPLER_DESC sampler_description;   
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_MIN_MAG_MIP_LINEAR;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```  
  
## <a name="example"></a>Příklad  
 **Volba filtrování Texture** variant lze reprodukovat pomocí kódu takto:  
  
```  
D3D11_SAMPLER_DESC sampler_description;   
  
// ... other sampler description setup ...  
  
sampler_description.Filter = D3D11_FILTER_ANISOTROPIC;  
sampler_description.MaxAnisotropy = 16;  
  
d3d_device->CreateSamplerState(&sampler_desc, &sampler);  
d3d_context->PSSetSamplers(0, 1, &sampler  
```