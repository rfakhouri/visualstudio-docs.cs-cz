---
title: VSG_NODEFAULT_INSTANCE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a460110c56775723a3ab1a2933868e4508c18562
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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