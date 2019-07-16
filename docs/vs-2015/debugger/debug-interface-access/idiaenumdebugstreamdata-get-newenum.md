---
title: Idiaenumdebugstreamdata::get__newenum – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreamData::get__NewEnum method
ms.assetid: 023b3e31-0fc9-478d-88e8-af2ce762f322
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0f98152cf680da4b3993a069957caa8c186d2912
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198540"
---
# <a name="idiaenumdebugstreamdatagetnewenum"></a>IDiaEnumDebugStreamData::get__NewEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> verzi výčet.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí `IUnknown` rozhraní zastupující <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> verzi výčet.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
