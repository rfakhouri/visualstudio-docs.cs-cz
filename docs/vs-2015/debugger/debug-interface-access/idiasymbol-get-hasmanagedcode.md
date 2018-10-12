---
title: Idiasymbol::get_hasmanagedcode – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hasManagedCode method
ms.assetid: e40f82f5-88fe-4a9b-b594-3605f42773ec
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a7c1808644bf5bc26385bbd7c81d308680ce2f0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49262974"
---
# <a name="idiasymbolgethasmanagedcode"></a>IDiaSymbol::get_hasManagedCode
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Získá příznak označující, zda modul obsahuje spravovaný kód.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_hasManagedCode(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pFlag`  
 [out] Vrátí `TRUE` Pokud modul obsahuje spravovaný kód; v opačném případě vrátí `FALSE`, kód je nespravovaného kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost je k dispozici `SymTagCompilandDetails` typu symbolu (naleznete v tématu [compilanddetails –](../../debugger/debug-interface-access/compilanddetails.md)).  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Záhlaví:|dia2.h|  
|Verze:|Ve verzi 8.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)



