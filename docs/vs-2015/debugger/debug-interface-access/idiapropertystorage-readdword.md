---
title: IDiaPropertyStorage::ReadDWORD | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadDWORD
ms.assetid: 5f4c034e-a9d3-4560-94b5-ede524741439
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e92b74fc1165adf359614e354ab60f3fc118e34b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62538821"
---
# <a name="idiapropertystoragereaddword"></a>IDiaPropertyStorage::ReadDWORD
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Přečte `DWORD` hodnoty v sadu vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT ReadDWORD (   
   PROPID id,  
   DWORD* pValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `id`  
 [in] Identifikátor vlastnosti pro čtení (`PROPID` je definována v WTypes.h jako `ULONG`).  
  
 `pValue`  
 [out] Vrátí hodnotu vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_INVALIDARG` Pokud vlastnost není typu `DWORD`.  
  
## <a name="remarks"></a>Poznámky  
 A `DWORD` je definován Windows jako 32bitové celé číslo bez znaménka.  
  
## <a name="see-also"></a>Viz také  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
