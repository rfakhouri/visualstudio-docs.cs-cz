---
title: "16bpp vykreslení cílový formát Variant | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b22ad9-5ad0-4161-809a-9b518eb924bf
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ed6ee80d2c12a135b2679ce115ef490c8c617da
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="16bpp-render-target-format-variant"></a>16bpp vykreslení cílový formát Variant
Nastaví Pixelový formát k DXGI_FORMAT_B5G6R5_UNORM pro všechny cíle vykreslení a zpět vyrovnávací paměti.  
  
## <a name="interpretation"></a>Interpretace  
 Cíl vykreslení nebo back vyrovnávací paměti se většinou používá formát 32bpp (32 bitů na pixel) jako je například B8G8R8A8_UNORM. formáty 32bpp může využívat velké množství paměti šířky pásma. Protože B5G6R5_UNORM formát je 16bpp formátu, který je poloviční velikost 32bpp formátů, použití zbavit nároků na paměť šířky pásma, ale za cenu věrnosti snížené barev.  
  
 Pokud tato varianta ukazuje velké výkonnější, pravděpodobně to znamená, že vaše aplikace využívá příliš mnoho paměti šířky pásma. Zvýšení výkonu mohou zejména projevit při PROFILOVANÉHO rámečku vykazuje významné množství overdraw nebo obsahuje velké množství prolnutí alfa.  
  
 Pokud druhy scény, které jsou generovány aplikace nevyžadují reprodukci zachováním barev, nevyžadují vykreslení cíl, který má být alfa kanálu a často neobsahují smooth přechody – které jsou náchylné k řazení do pásem artefakty pod snížené barev přesnost – zvažte použití formátu cílové vykreslení 16bpp ke snížení využití šířky pásma paměti.  
  
 Pokud na pozadí, které jsou generovány ve vaší aplikaci vyžadují reprodukci zachováním barev nebo alfa kanálu nebo smooth přechody jsou společné, vezměte v úvahu další strategie ke snížení využití šířky pásma paměti – například snižuje množství overdraw nebo prolnutí alfa Při zmenšení framebuffer nebo úprava texture prostředky využívat menší šířku pásma paměti povolení komprese nebo snížením jejich dimenzí. Obvyklým způsobem je nutné zvážit poměrem kvality pocházející s žádným z těchto optimalizace bitovou kopii.  
  
 Pokud vaše aplikace by využívat přepnutí na 16bpp back vyrovnávací paměti, ale je součástí vašeho řetězce odkládacího souboru, je třeba provést další kroky, protože DXGI_FORMAT_B5G6R5_UNORM není podporované back vyrovnávací paměti formát pro swap řetězy vytvořily s použitím `D3D11CreateDeviceAndSwapChain` nebo `IDXGIFactory::CreateSwapChain`. Místo toho je nutné vytvořit cíl B5G6R5_UNORM formát vykreslení pomocí `CreateTexture2D` a vykreslování na který místo. Potom před voláním přítomné v řetězu vaší odkládacího souboru, zkopírujte, cíl vykreslení do přípravné vyrovnávací paměti odkládacího souboru řetězu kreslení přes celou obrazovku quad s cílem vykreslení jako texturou zdroje. Přestože je toto na další krok, který bude využívat šířku pásma některé paměti, většinu operací vykreslování bude využívat menší šířku pásma, protože mají vliv na cíl vykreslení 16bpp; Pokud to umožňuje ušetřit větší šířku pásma, než je spotřebovávají kopírování cíl vykreslení do odkládacího souboru řetězu přípravné vyrovnávací paměti, je lepší výkon vykreslování.  
  
 Grafický procesor architektury, které používají vedle sebe vykreslování techniky můžete zobrazit výkon významné výhody ve formátu framebuffer 16bpp protože větší část framebuffer můžete začlenit v mezipaměti místní framebuffer každou dlaždici. Vedle sebe vykreslování architektury se někdy nacházejí v grafickými procesory v mobilních mobilní telefony a tablety počítače; zřídka nacházet mimo tento volné místo.  
  
## <a name="remarks"></a>Poznámky  
 Formát vykreslení cílového obnoví DXGI_FORMAT_B5G6R5_UNORM při každém volání do `ID3D11Device::CreateTexture2D` vytvářející cíl vykreslení. Konkrétně je formát přepsat při objekt D3D11_TEXTURE2D_DESC předaná pDesc popisuje cíl vykreslení; To je:  
  
-   Člen BindFlags má nastaven příznak D3D11_BIND_REDNER_TARGET.  
  
-   Člen BindFlags má příznak D3D11_BIND_DEPTH_STENCIL vymazán.  
  
-   Člen využití je nastavena na D3D11_USAGE_DEFAULT.  
  
## <a name="restrictions-and-limitations"></a>Omezení a omezení  
 Vzhledem k tomu, že formát B5G6R5 nemá alfa kanálu, není tato varianta zachován alfa obsah. Pokud vaše aplikace vykreslování vyžaduje alfa kanálu v cílovém vykreslování, nelze právě přepnout do formátu B5G6R5.  
  
## <a name="example"></a>Příklad  
 **Cílový formát vykreslení 16bpp** variant lze reprodukovat pro vykreslení cíle vytvořily s použitím `CreateTexture2D` pomocí kódu takto:  
  
```  
D3D11_TEXTURE2D_DESC target_description;  
  
target_description.BindFlags = D3D11_BIND_RENDER_TARGET;  
target_description.Format = DXGI_FORMAT_B5G6R5_UNORM;  
d3d_device->CreateTexture2D(&target_description, nullptr, &render_target);  
```