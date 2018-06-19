---
title: VSG_NODEFAULT_INSTANCE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3d064f4a5b983058d9f1ad4428e2b37cf2e82dcf
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31473157"
---
# <a name="vsgnodefaultinstance"></a>VSG_NODEFAULT_INSTANCE
Definuje podle jeho přítomnosti zda výchozí instanci [VsgDbg – třída](vsgdbg-class.md) – třída – které poskytuje rozhraní zachytávání prostřednictvím kódu programu – pochází.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
#define VSG_NODEFAULT_INSTANCE  
```  
  
## <a name="value"></a>Hodnota  
 Preprocesor symbolů, která podle jeho přítomnosti nebo absenci Určuje, zda výchozí instanci `VsgDbg` třída je k dispozici. Pokud je definována tento symbol, pak žádný výchozí instanci systému `VsgDbg` je k dispozici – třída; výchozí instanci, jinak hodnota dodána a inicializovat před spuštěním programu.  
  
 Rozhraní zachytávání prostřednictvím kódu programu je zadaný prostřednictvím ukazatele, má globální obor, `g_pVsgDbg`.  
  
```  
VsgDbg *g_pVsgDbg;  
```  
  
## <a name="remarks"></a>Poznámky  
 Výchozí instance stačí často, ale rozhraní zachytávání prostřednictvím kódu programu uvnitř knihovny DLL použít, když zařízení D3D byla vytvořena mimo tuto knihovnu DLL, musíte vytvořit a spravovat vlastní instanci systému `VsgDbg` třídy. Pokud spravujete vlastní rozhraní pro zachytávání prostřednictvím kódu programu rozhraní API tímto způsobem, zakázat výchozí instanci definováním `VSG_NODEFAULT_INSTANCE` předejdete režijní náklady.  
  
 Pokud není zakázán výchozí instanci, je automaticky inicializován před program spustí a zničen automaticky při ukončení aplikace. Nemáte k inicializaci nebo explicitně Uninitialize – této instance.  
  
 Chcete-li zakázat výchozí instanci, je třeba definovat `VSG_NODEFAULT_INSTANCE` předtím, než zahrnete `vsgcapture.h` v programu.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak zakázat výchozí instanci:  
  
```  
// Define VSG_NODEFAULT_INSTANCE before including vsgcapture.h  
#define VSG_NODEFAULT_INSTANCE  
  
#include <vsgcapture.h>  
```