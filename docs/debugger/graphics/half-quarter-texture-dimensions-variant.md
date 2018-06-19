---
title: Texture půl čtvrtletí Dimensions Variant | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 282e9bbb-51aa-4cd0-8e5c-0901268c29e5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b19a7c8444264300bdb819152769f1760d4a4d3e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31481837"
---
# <a name="halfquarter-texture-dimensions-variant"></a>Texture půl/čtvrtletí dimenze typu Variant
Snižuje dimenze texture na textury, které nejsou vykreslení cíle.  
  
## <a name="interpretation"></a>Interpretace  
 Menší textury zabírají méně paměti a proto využívat menší šířku pásma paměti a snížení nároků na na grafický procesor texture mezipaměti. Jejich nižší úrovně podrobností však může způsobit snížené bitové kopie kvality, zejména v případě, že už zobrazit úzce v 3D scény nebo zobrazit v části zvětšení.  
  
 Pokud tato varianta zobrazuje velké výkonnější, mohlo znamenat, že vaše aplikace využívá příliš velkou šířku pásma, paměti, používá textury mezipaměti neefektivnímu nebo obojí. Můžete také určit, že vaše textury zabírají další grafické paměti, než je k dispozici, což způsobí, že textury k stránkování paměti systému.  
  
 Pokud vaše aplikace využívá příliš mnoho paměti šířky pásma nebo používá mezipaměť texture neefektivnímu, zvažte zmenšení velikosti vašeho textury, ale až poté, co byste zvážit povolení mapy mip textury vhodné. Jako menší textury mapované mip textury využívat menší šířku pásma paměti – i když jejich zabírají více paměti grafického procesoru – a zvýšení využití mezipaměti, ale nemáte snížit texture podrobností. Mapy mip doporučujeme vždy, když je využití paměti vyšší nezpůsobí textury k stránkování paměti systému.  
  
 Pokud vaše textury zabírají další grafické paměti, než je k dispozici, zvažte zmenšení velikosti textury, ale až poté, co byste zvážit kompresi textury vhodné. Podobně jako menší textury komprimované textury zabírají méně paměti a snížení nároků na stránku pro systémové paměti, ale jejich věrnosti barva se snižuje. Komprese není vhodné pro všechny textury, v závislosti na jejich obsah – například ty, které jsou důležité barvu variace v malých oblasti – ale pro mnoho textury komprese můžete zachovat lepší celkovou kvalitu obrazu než snižuje jejich velikost.  
  
## <a name="remarks"></a>Poznámky  
 Texture dimenze jsou omezeny na každé volání `ID3D11Device::CreateTexture2D` vytvářející texture zdroje. Konkrétně jsou omezeny texture dimenzí, když objekt D3D11_TEXTURE2D_DESC předaná `pDesc` popisuje texture, který se používá v vykreslování; který je:  
  
-   Člen BindFlags má pouze D3D11_BIND_SHADER_RESOURCE příznak nastavený.  
  
-   Člen MiscFlags nemá příznak D3D11_RESOURCE_MISC_TILE_POOL nebo nastaven příznak D3D11_RESOURCE_MISC_TILED (vedle sebe prostředky nejsou po změně velikosti).  
  
-   Formát texture je podporovaný jako cíl vykreslení – určeného D3D11_FORMAT_SUPPORT_RENDER_TARGET – což je vyžadováno pro zmenšení velikosti texture. Formáty BC1, BC2 a BC3 jsou také podporovány, i když některé funkce nejsou podporovány jako vykreslení cíle.  
  
 Pokud je zadaný počáteční data aplikací, škáluje Tato varianta předtím, než se vytvoří textury texture data, která mají správnou velikost. Pokud je zadaný počáteční data ve formátu-komprimovaného bloku například BC1, BC2 nebo BC3, je dekódovat, škálovat a znovu kódovaný předtím, než se používá k vytvoření menších texture. (Povaha Blokový komprese znamená, že proces velmi dekódovat škálování kódování téměř vždy způsobí nižší kvality obrázku, než když texturou-komprimovaného bloku se generují z škálovat verzi texture, který nebyl dříve zakódován.)  
  
 Pokud mapy mip jsou povolené pro textury, varianta snižuje počet úrovní mip odpovídajícím způsobem – jeden méně při škálování poloviční velikost nebo dvě méně při škálování velikost čtvrtletí.  
  
## <a name="example"></a>Příklad  
 Tento typ variant změní textury za běhu před voláním `CreateTexture2D`. Nedoporučujeme tento přístup pro kód produkční, protože plné velikosti textury využívat více místa na disku, a protože další krok může prodloužit dobu načítání ve vaší aplikaci – hlavně pro komprimovaný textury vyžadující významné výpočetní prostředky ke kódování. Místo toho doporučujeme změnit velikost vašeho textury do offline režimu, a to pomocí editoru bitové kopie nebo bitové kopie procesoru, který je součástí vašeho kanálu sestavení. Tyto přístupy snížit požadavky na místo na disku a eliminovat režii runtime v aplikaci a dovolit více času na zpracování, aby při zmenšení nebo kompresi vaší textury můžete zachovat nejlepší kvalitu obrazu.  
  
## <a name="see-also"></a>Viz také  
 [Mapy MIP generování Variant](mip-map-generation-variant.md)   
 [Varianta komprese textur BC](bc-texture-compression-variant.md)