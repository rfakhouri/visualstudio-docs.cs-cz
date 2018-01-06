---
title: "Mapy MIP generování Variant | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b4b3583-0b01-4f5d-aacb-3f96d19111d9
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f6b7773562ed7b09ca00f7fc471b7ee2924c0181
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="mip-map-generation-variant"></a>Mapy MIP generování Variant
Umožňuje mapy mip na textury, které nejsou vykreslení cíle.  
  
## <a name="interpretation"></a>Interpretace  
 Mapy MIP primárně používají k vyloučení aliasy artefakty v textury v rámci minimalizace předem výpočtu menší verze textury. I když tyto další textury využívat grafické paměti – o 33 procent víc než původní texture – jsou také efektivnější protože z jejich útoku vyhovuje v mezipaměti texture GPU a její obsah dosáhnout vyšší využití.  
  
 Pro 3D scény doporučujeme mapy mip při paměti je k dispozici pro uložení Další textury, protože zvyšují výkon vykreslování a bitové kopie kvality.  
  
 Pokud tato varianta ukazuje značné zvýšení výkonu, znamená to, že používáte textury bez povolení mapy mip a tím není maximální využití z mezipaměti texture.  
  
## <a name="remarks"></a>Poznámky  
 Mapy MIP generace je nucen při každém volání do `ID3D11Device::CreateTexture2D` vytvářející texture zdroje. Konkrétně musí generování mip mapy při objekt D3D11_TEXTUR2D_DESC předaná `pDesc` popisuje neměnné shaderu prostředků, který je:  
  
-   Člen BindFlags má pouze D3D11_BIND_SHADER_RESOURCE příznak nastavený.  
  
-   Člen využití je nastavena na D3D11_USAGE_DEFUALT nebo D3D11_USAGE_IMMUTABLE.  
  
-   Člen CPUAccessFlags nastavena na hodnotu 0 (žádný přístup procesoru).  
  
-   Člen SampleDesc má jeho Count – člen nastavena na hodnotu 1 (žádné více ukázka Anti-Aliasing (MSAA)).  
  
-   Člen MipLevels nastavena na hodnotu 1 (žádné existující mip map).  
  
 Pokud zadaný počáteční data aplikací, formát texture musí podporovat mapy mip automatické generování – určeného D3D11_FORMAT_SUPPORT_MIP_AUTOGEN – Pokud je ve formátu BC1, BC2 nebo BC3; jinak se nemění textury a žádné mapy mip jsou generovány, pokud je zadaná počáteční data.  
  
 Pokud mapy mip byly automaticky generovány pro texturou, zavolá na `ID3D11Device::CreateShaderResourceView` jsou upraveny při přehrávání používat řetězu mip během texture vzorkování.  
  
## <a name="example"></a>Příklad  
 **Mip mapy generování** variant lze reprodukovat pomocí kódu takto:  
  
```  
D3D11_TEXTURE2D_DESC texture_description;  
  
// ...  
  
texture_description.MipLevels = 0; // generate a full mipchain  
  
std::vector<D3D11_SUBRESOURCE_DATA> initial_data(num_mips);  
  
for (auto&& mip_level : initial_data)  
{  
    // fill mip_level with the application-supplied initial data  
}  
  
d3d_device->CreateTexture2D(&texture_description, initial_data.data(), &texture)  
```  
  
 Chcete-li vytvořit texture, který má úplný řetězec mip, nastavte `D3D11_TEXTURE2D_DESC::MipLevels` na hodnotu 0. Počet úrovní mip z úplné mip řetězce, které je floor(log2(n) + 1), kde n je největší dimenze textury.  
  
 Nezapomeňte, že pokud zadáte počáteční data pro `CreateTexture2D`, je třeba zadat objekt D3D11_SUBRESOURCE_DATA pro každou úroveň mip.  
  
> [!NOTE]
>  Pokud chcete zadat vlastní mip úrovně obsah, místo aby generovala je automaticky, musíte vytvořit vaší textury pomocí image editor, který podporuje mapované mip textury a potom načíst soubor a předat mip úrovní `CreateTexture2D`.  
  
## <a name="see-also"></a>Viz také  
 [Texture půl/čtvrtletí dimenze typu Variant](half-quarter-texture-dimensions-variant.md)