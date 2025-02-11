---
title: Varianta komprese textur BC | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 2d0f5305-585b-4b01-bc9a-7a32d6e991da
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3a25411449c1b13b12f05819061847c252a76c9c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62848692"
---
# <a name="bc-texture-compression-variant"></a>Varianta komprese textur BC
Umožňuje zablokovat kompresi na textury, které mají žádnému pixelovému formátu, který je varianta B8G8R8X8, B8G8R8A8 nebo R8G8B8A8.

## <a name="interpretation"></a>interpretace
 Blokový komprese formáty, jako jsou BC1, BC2, a BC3 zabírat výrazně méně paměti, než nekomprimovaný formátů obrázku a proto spotřebovávají výrazně menší šířku pásma paměti. Ve srovnání s nekomprimovaný formát, který používá 32 bitů na pixel, BC1 (dříve označované jako DXT1) dosahuje komprese 8:1 a BC3 (dříve označované jako DXT5) dosahuje 4:1. Rozdíl mezi BC1 a BC3 je, že BC1 nepodporuje alfa kanál, zatímco BC3 podporuje komprimovaný alfa kanálu. Bez ohledu na vysoké Kompresní poměry je pouze dílčí snížení kvality obrázku pro typické textury. Ale blokovat komprese určité druhy textury – například ty, které mají významný barev ve malou oblast – může mít nepřijatelné výsledky.

 Pokud vaše textury jsou vhodné pro kompresi blokových a není nutné zdokonalujete barva věrností, zvažte použití formátu komprimovanými ke snížení využití paměti a využívat menší šířku pásma.

## <a name="remarks"></a>Poznámky
 Komprimovat textury s použitím komprese Blokový formát pro každé volání do `ID3DDevice::CreateTexture2D` , který vytváří zdrojovou texturu. Konkrétně jsou komprimovány textury při:

- `D3D11_TEXTURE2D_DESC` Objekt předaný v `pDesc` popisuje neměnné prostředek shaderu; který je:

  - Člen BindFlags má pouze D3D11_BIND_SHADER_RESOURCE příznak nastaven.

  - Využití člen je nastavený na D3D11_USAGE_DEFAULT nebo D3D11_USAGE_IMMUTABLE.

  - Člen CPUAccessFlags je nastavený na hodnotu 0 (žádný přístup procesoru).

  - Člen SamplerDesc má jeho Count – člen nastavena na hodnotu 1 (žádné více ukázka Anti-Aliasing (MSAA)).

- Nejsou k dispozici počáteční data volání `CreateTexture2D`.

  Tady jsou formáty podporované zdrojové a jejich komprimovanými formátů.

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

 Pokud vaše textury má formát, který není uveden, se nezmění textury.

## <a name="restrictions-and-limitations"></a>Omezení a omezení
 Někdy textury, které jsou vytvořeny pomocí varianta formátů obrázku B8G8R8A8 nebo R8G8B8A8 nepoužívejte skutečně alfa kanál, ale neexistuje žádný způsob, jak variant vědět, jestli se používá nebo ne. Zachování správnosti v případě, že se používá kanál alfa, varianty vždy kóduje tyto formáty méně efektivní BC3 formátu. Může pomoct lépe porozumět výkonu vaší aplikace potenciální vykreslování s Tato varianta pomocí varianta B8G8R8X8 formát obrázku, pokud nepoužíváte alfa kanál tak, aby varianty pomocí formátu efektivní informace BC1 analýza grafických snímků.

## <a name="example"></a>Příklad
 Tato varianta bloku komprimovat textury v době běhu, před voláním `CreateTexture2D`. Nedoporučujeme tento přístup pro produkční kód, protože nekomprimované textury využívat více místa na disku a další krok může významně zvýšit dobu načítání v aplikaci, protože založené na blocích komprese vyžaduje důležité výpočetní prostředky ke kódování. Namísto toho doporučujeme komprimovat vaše textury offline pomocí editoru obrázků nebo obrázků procesor, který je součástí vašeho kanálu sestavení. Tyto přístupy snížit požadavky na místo na disku, odstranění nároky ve vaší aplikaci za běhu a dovolit více času na zpracování, takže můžete zachovat nejlepší kvalitu obrazu.

## <a name="see-also"></a>Viz také
- [Varianta polovičních/čtvrtinových dimenzí textury](half-quarter-texture-dimensions-variant.md)