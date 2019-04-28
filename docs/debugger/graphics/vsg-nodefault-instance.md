---
title: VSG_NODEFAULT_INSTANCE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 304576391b2287aee7567b3ccc2e4514ce5cb2e8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62848459"
---
# <a name="vsgnodefaultinstance"></a>VSG_NODEFAULT_INSTANCE
Definuje jeho přítomnost, zda výchozí instanci [třída VsgDbg](vsgdbg-class.md) třídy – poskytující rozhraní zachytávání prostřednictvím kódu programu – pochází.

## <a name="syntax"></a>Syntaxe

```C++
#define VSG_NODEFAULT_INSTANCE
```

## <a name="value"></a>Value
 Preprocesoru symbol, který podle jeho přítomnost nebo absence Určuje, zda výchozí instanci `VsgDbg` třídy je k dispozici. Pokud tento symbol není definován, pak žádný výchozí instanci `VsgDbg` třídy je k dispozici; jinak je výchozí instance k dispozici a inicializován před spuštěním programu.

 Programové zachytávání rozhraní je k dispozici prostřednictvím ukazatele, který má globální obor, `g_pVsgDbg`.

```cpp
VsgDbg *g_pVsgDbg;
```

## <a name="remarks"></a>Poznámky
 Výchozí instance je často dostatečné, ale pokud chcete použít rozhraní zachytávání prostřednictvím kódu programu uvnitř knihovny DLL, po vytvoření zařízení D3D mimo tuto knihovnu DLL, musíte vytvořit a spravovat vlastní instance `VsgDbg` třídy. Pokud spravujete vlastní rozhraní pro zachytávání prostřednictvím kódu programu API tímto způsobem, zakázat výchozí instanci definováním `VSG_NODEFAULT_INSTANCE` , aby režijní náklady.

 Pokud není výchozí instancí zakázán, je automaticky inicializován před spuštěním vaší aplikace a automaticky je zničen při ukončení programu. Není nutné inicializovat nebo explicitně uninitialize této instance.

 Chcete-li zakázat výchozí instanci, je nutné definovat `VSG_NODEFAULT_INSTANCE` teprve potom zahrňte `vsgcapture.h` ve svém programu.

## <a name="example"></a>Příklad
 Tento příklad ukazuje, jak zakázat výchozí instanci:

```cpp
// Define VSG_NODEFAULT_INSTANCE before including vsgcapture.h
#define VSG_NODEFAULT_INSTANCE

#include <vsgcapture.h>
```
