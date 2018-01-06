---
title: BC Texture komprese Variant | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d0f5305-585b-4b01-bc9a-7a32d6e991da
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 13b97c4d9e90adf8b621100d6d2a68d11570e71d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="bc-texture-compression-variant"></a>BC Texture komprese Variant
Umožňuje blokovat kompresi na textury, které mají Pixelový formát, který se odlišuje od B8G8R8X8, B8G8R8A8 nebo R8G8B8A8.  
  
## <a name="interpretation"></a>Interpretace  
 Blokový komprese formáty jako BC1, BC2, a BC3 zabírají výrazně méně paměti, než nekomprimovaným formáty obrázků a proto využívat šířku pásma výrazně méně paměti. Ve srovnání s nekomprimované formátu, který používá 32 bitů na pixel, BC1 (dříve označované jako DXT1) dosahuje komprese 8:1 a 4:1, která patří dosahuje BC3 (dříve označované jako DXT5). Rozdíl mezi BC1 a BC3 je, že BC1 nepodporuje alfa kanál, zatímco BC3 podporuje kompresí bloku alfa kanálu. Navzdory vysoké komprese poměrům je pouze dílčí snížení kvality obrázku pro typické textury. Ale blokovat komprese určité druhy textury – například ty, které jsou důležité barvu variace v malých oblasti – může mít nepřijatelné výsledky.  
  
 Pokud vaše textury jsou vhodné pro blokový komprese a není nutné ideální věrnosti barvu, zvažte použití formátu kompresí bloku snížit využití paměti a využívat menší šířku pásma.  
  
## <a name="remarks"></a>Poznámky  
 Komprimovat textury ve formátu Blokový komprese při každém volání do `ID3DDevice::CreateTexture2D` vytvářející texture zdroje. Konkrétně jsou komprimované textury při:  
  
-   `D3D11_TEXTURE2D_DESC` Objekt předaný v `pDesc` popisuje neměnné shaderu prostředků, který je:  
  
    -   Člen BindFlags má pouze D3D11_BIND_SHADER_RESOURCE příznak nastavený.  
  
    -   Člen využití je nastavena na D3D11_USAGE_DEFAULT nebo D3D11_USAGE_IMMUTABLE.  
  
    -   Člen CPUAccessFlags nastavena na hodnotu 0 (žádný přístup procesoru).  
  
    -   Člen SamplerDesc má jeho Count – člen nastavena na hodnotu 1 (žádné více ukázka Anti-Aliasing (MSAA)).  
  
-   Počáteční data je určena k volání `CreateTexture2D`.  
  
 Tady jsou podporované zdrojové formáty a jejich formáty kompresí bloku.  
  
|Původním formátu (od)|Komprimované formátu (do)|  
|------------------------------|------------------------------|  
|`DXGI_FORMAT_B8G8R8X8_UNORM`|BC1 (dříve DXT1)|  
|`DXGI_FORMAT_B8G8R8X8_UNORM_SRGB`|BC1|  
|`DXGI_FORMAT_B8G8R8X8_TYPELESS`|BC1|  
|`DXGI_FORMAT_B8G8R8A8_UNORM`|BC3 (dříve DXT5)|  
|`DXGI_FORMAT_B8G8R8A8_UNORM_SRGB`|BC3|  
|`DXGI_FORMAT_B8G8R8A8_TYPELESS`|BC3|  
|`DXGI_FORMAT_R8G8B8A8_UNORM`|BC3|  
|`DXGI_FORMAT_R8G8B8A8_UNORM_SRGB`|BC3|  
|`DXGI_FORMAT_R8G8B8A8_TYPELESS`|BC3|  
  
 Pokud vaše texture má formát, který není uveden, textury se nemění.  
  
## <a name="restrictions-and-limitations"></a>Omezení a omezení  
 Někdy textury, které jsou vytvořeny pomocí varianta formátů obrázku B8G8R8A8 nebo R8G8B8A8 nepoužívejte ve skutečnosti alfa kanálu, ale neexistuje žádný způsob varianty vědět, jestli se používá nebo ne. Pokud chcete zachovat správnost v případě, že se používá alfa kanálu, varianta vždy kóduje tyto formáty do méně efektivní BC3 formátu. Může pomoci lépe pochopit potenciální výkon vykreslování vaší aplikace s Tato varianta pomocí varianta formátu B8G8R8X8 obrázku, pokud nepoužíváte alfa kanálu tak, aby varianta může používat další efektivní formát BC1 analýza grafických snímků.  
  
## <a name="example"></a>Příklad  
 Tento typ variant bloku zkomprimuje textury za běhu, před voláním `CreateTexture2D`. Nedoporučujeme tento přístup pro kód produkční, protože nekomprimované textury využívat více místa na disku a protože další krok může značně zvýšit časů načítání ve vaší aplikaci, protože vyžaduje významné Blokový komprese výpočetní prostředky ke kódování. Místo toho doporučujeme kompresi vaší textury offline pomocí editoru bitové kopie nebo bitové kopie procesoru, který je součástí vaší sestavení kanálu. Tyto přístupy snížit požadavky na místo na disku, eliminovat běhu režie ve vaší aplikaci a dovolit více času na zpracování, aby můžete zachovat nejlepší kvality obrázku.  
  
## <a name="see-also"></a>Viz také  
 [Texture půl/čtvrtletí dimenze typu Variant](half-quarter-texture-dimensions-variant.md)