---
title: IDiaPropertyStorage::ReadLONG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadLONG
ms.assetid: 32054cbc-db55-4513-a1b4-de80e77aac8a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d162b8c92e5065f50e4bac63a1cd8681e18022d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiapropertystoragereadlong"></a>IDiaPropertyStorage::ReadLONG
Přečte `LONG` hodnoty v sadu vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT ReadDLONG (   
   PROPID id,  
   LONG*  pValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `id`  
 [v] Identifikátor vlastnosti čtení (`PROPID` je definována v WTypes.h jako `ULONG`).  
  
 `pValue`  
 [out] Vrátí hodnotu vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_INVALIDARG` Pokud vlastnost není typu `LONG`.  
  
## <a name="remarks"></a>Poznámky  
 A `LONG` je definována v systému Windows jako 32bitové celé číslo se znaménkem.  
  
## <a name="see-also"></a>Viz také  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)