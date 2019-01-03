---
title: IEEDataStorage::GetData | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEEDataStorage::GetData
helpviewer_keywords:
- IEEDataStorage::GetData
ms.assetid: 4d384039-73d4-40b4-ace6-a2474c546397
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8ed1788804fea7d10734de339d7b5a91d9cd168b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53936968"
---
# <a name="ieedatastoragegetdata"></a>IEEDataStorage::GetData
Načte zadaný počet bajtů z objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetData(  
   ULONG  dataSize,  
   ULONG* sizeGotten,  
   BYTE*  data  
);  
```  
  
```csharp  
int GetData(  
   uint     dataSize,  
   out uint sizeGotten,  
   byte[]   data  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dataSize`  
 [in] Počet bajtů k načtení ( `data` pole musí obsahovat nejméně tento počet bajtů).  
  
 `sizeGotten`  
 [out] Vrátí počet bajtů ve skutečnosti načíst.  
  
 `data`  
 [out v] Pole se vyplní požadovaná data.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Doporučené použití této metody je pro načtení všech bajtů dat do místního pole, protože neexistuje žádný způsob, jak přeskočit bajtů v procesu načítání. V tomto případě parametr `dataSize` by měla být hodnota vrácené [getsize –](../../../extensibility/debugger/reference/ieedatastorage-getsize.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)