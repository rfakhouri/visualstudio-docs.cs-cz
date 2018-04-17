---
title: 0 variant x-2 x-4 x MSAA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 668a6603-5082-4c78-98e6-f3dc871aa55b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09ec8c25a076fd9f74690b3be92715aa62b60f65
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="0x2x4x-msaa-variants"></a>0 x / 2 x / 4 x MSAA variant
Přepsání více ukázku vyhlazení (MSAA) nastavení na všech vykreslení cíle a řetězy prohodit.  
  
## <a name="interpretation"></a>Interpretace  
 Více ukázku vyhlazení zvyšuje visual kvality pomocí ukázky na víc umístění v každém bodě; vyšší úrovně MSAA využít další ukázky a bez MSAA, jenom jeden vzorek z centra pixelech. Povolení MSAA ve vaší aplikaci obvykle má mírný ale znatelné náklady v vykreslování výkon, ale u určité zatížení nebo v určitých grafickými procesory, může být měl s téměř žádný vliv.  
  
 Pokud vaše aplikace už má MSAA povolené, menší variant MSAA znamenat náklady relativní výkon, který způsobuje MSAA existující, vyšší úrovně. Konkrétně 0 x MSAA variant určuje relativní výkon vaší aplikace bez MSAA.  
  
 Pokud vaše aplikace již nemá MSAA povolené, 2 x MSAA a 4 x MSAA variant udávající náklady relativní výkon povolení je ve vaší aplikaci. Po přijatelně nízké náklady, zvažte povolení MSAA k vylepšení kvality obrázku vaší aplikace.  
  
> [!NOTE]
>  Váš hardware nemusí podporovat plně MSAA pro všechny formáty. Pokud některá z těchto variant dojde k omezení hardwaru, který nelze pracoval kolem, jeho sloupec v tabulce shrnutí výkonu je prázdné a vytváří chybovou zprávu.  
  
## <a name="remarks"></a>Poznámky  
 Ukázka počet a ukázkové kvality argumenty na volání přepsání těchto variant `ID3DDevice::CreateTexture2D` , vytvořit vykreslení cíle. Konkrétně se přepíšou těchto parametrů při:  
  
-   `D3D11_TEXTURE2D_DESC` Objekt předaný v `pDesc` popisuje cíl vykreslení; který je:  
  
    -   Člen BindFlags má buď D3D11_BIND_TARGET příznak nebo D3D11_BIND_DEPTH_STENCIL příznak nastavený.  
  
    -   Člen využití je nastavena na D3D11_USAGE_DEFAULT.  
  
    -   Člen CPUAccessFlags nastavena na hodnotu 0.  
  
    -   Člen MipLevels nastavena na hodnotu 1.  
  
-   Zařízení podporuje počet požadovaný vzorků (0, 2 nebo 4) a ukázkové kvality (0) pro požadovanou cílový formát (D3D11_TEXTURE2D_DESC::Format člen), určeného vykreslení `ID3D11Device::CheckMultisampleQualityLevels`.  
  
 Pokud D3D11_TEXTURE2D_DESC::BindFlags člen má nastaveny příznaky D3D_BIND_SHADER_RESOUCE nebo D3D11_BIND_UNORDERED_ACCESS, vytvoří se dvě verze textury; první má tyto příznaky vymazán pro použití jako cíl vykreslování a druhá je jiný MSAA texture, který má tyto příznaky zůstává nedotčeno tak, aby fungoval jako vyřešte vyrovnávací paměť pro první verzi. To je nezbytné, protože použití MSAA texture jako prostředek shaderu nebo pro neuspořádaný přístup, je pravděpodobně být platný – například shaderu funguje na něm by vygenerovat nesprávné výsledky, protože očekáváte texture bez MSAA. Pokud varianta vytvořil texture sekundární jiný MSAA, pak vždy, když je cíl vykreslení MSAA nenastavené v kontextu zařízení její obsah se překládají do jiných MSAA textury. Podobně vždy, když MSAA vykreslení cílový svázání jako prostředek shaderu, nebo se používá v zobrazení neuspořádaný přístup, texture přeložit jiný MSAA vázán místo.  
  
 Tyto variant také přepsat nastavení MSAA na všechny řetězy swap vytvořily s použitím `IDXGIFactory::CreateSwapChain`, `IDXGIFactory2::CreateSwapChainForHwnd`, `IDXGIFactory2::CreateSwapChainForCoreWindow`, `IDXGIFactory2::CreateSwapChainForComposition`, a `ID3D11CreateDeviceAndSwapChain`.  
  
 Projeví těchto změn je, že všechny vykreslování se provádí MSAA vykreslení cíl, ale pokud vaše aplikace používá jednu z těchto vykreslení cíle nebo vyrovnávací paměti odkládacího souboru řetězec jako zobrazení shaderu prostředku nebo zobrazení neuspořádaný přístup, a potom je vzorků dat z vyřešit , bez MSAA kopii cíl vykreslení.  
  
## <a name="restrictions-and-limitations"></a>Omezení a omezení  
 V Direct3D11 více než jiné MSAA textury omezeny MSAA textury. Například nelze volat `ID3D11DeviceContext::UpdateSubresource` na MSAA texture a volání `ID3D11DeviceContext::CopySubresourceRegion` selže, pokud počet vzorků a ukázkové kvalitu prostředku zdrojového a cílového prostředku se neshodují, které může dojít, když tato varianta přepíše nastavení MSAA jednoho prostředek, ale ne na druhou.  
  
 Zjistí-li přehrávání tyto druhy je v konfliktu, má usilovně replikovat zamýšlené chování, ale nemusí být možné přesně shodují své výsledky. Přestože neobvyklé to mít vliv na výkon těchto variant způsobem, který špatně rozpozná jejich dopadu, je možné – například když řízení toku v pixelech shaderu je dáno přesný obsah texturou – protože replikované textury nemusí mít identické obsah.  
  
## <a name="example"></a>Příklad  
 Tyto variant lze reprodukovat pro vykreslení cíle vytvořily s použitím `ID3D11Device::CreateTexture2D` pomocí kódu takto:  
  
```  
D3D11_TEXTURE2D_DESC target_description;  
target_description.BindFlags = D3D11_BIND_RENDER_TARGET;  
target_description.SampleDesc.Count = 4; // 4x MSAA, can be 2 or 0 instead  
target_description.SampleDesc.Quality = 0;  
d3d_device->CreateTexture2D(&target_description, nullptr, &render_target);  
```  
  
## <a name="example"></a>Příklad  
 Nebo pro swap řetězy vytvořily s použitím IDXGISwapChain::CreateSwapChain nebo D3D11CreateDeviceAndSwapChain pomocí kódu takto:  
  
```  
DXGI_SWAP_CHAIN_DESC chain_description;  
chain_description.SampleDesc.Count = 4; // 4x MSAA, can be 2 or 0 instead  
chain_description.SampleDesc.Quality = 0;  
  
// Call IDXGISwapChain::CreateSwapChain or D3D11CreateDeviceAndSwapChain, etc.  
```