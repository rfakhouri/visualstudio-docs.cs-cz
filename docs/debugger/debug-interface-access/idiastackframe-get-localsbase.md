---
title: Idiastackframe::get_localsbase – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_localsBase method
ms.assetid: eb0bd73e-d92d-468e-a0b1-fbc279919f54
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cbe6dd1d5b72faea57ecb015b0da294798527c0b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838204"
---
# <a name="idiastackframegetlocalsbase"></a>IDiaStackFrame::get_localsBase
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Získá základní adresu lokální proměnné pro rámec.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_localsBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí základní adresu místní proměnné.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
