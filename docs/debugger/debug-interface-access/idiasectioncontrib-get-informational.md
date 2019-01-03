---
title: Idiasectioncontrib::get_informational – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_informational method
ms.assetid: 5351e89f-7db1-4f8e-9e57-2dd1c74002e0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e582849fe392a77b48a8c83664c98fedb8037f5f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53987625"
---
# <a name="idiasectioncontribgetinformational"></a>IDiaSectionContrib::get_informational
Získá příznak označující, zda oddíl obsahuje komentáře nebo podobné informace.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_informational(  
   BOOL* pRetVal  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` Pokud oddíl obsahuje komentáře nebo jiné informace; v opačném případě vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V části .directive obvykle obsahuje informace.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)