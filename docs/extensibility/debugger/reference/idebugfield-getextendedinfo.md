---
title: IDebugField::GetExtendedInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugField::GetExtendedInfo
helpviewer_keywords:
- IDebugField::GetExtendedInfo method
ms.assetid: 46c0dd4d-4fd5-4efd-a908-71e4248e8e8d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ef431fbc3bf14124ee0ea08a2439c0473e958a91
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53945207"
---
# <a name="idebugfieldgetextendedinfo"></a>IDebugField::GetExtendedInfo
Tato metoda získá rozšířené informace o pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetExtendedInfo(   
   REFGUID guidExtendedInfo,  
   BYTE**  prgBuffer,  
   DWORD*  pdwLen  
);  
```  
  
```csharp  
int GetExtendedInfo(  
   ref Guid guidExtendedInfo,   
   IntPtr[] prgBuffer,   
   ref uint pdwLen  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidExtendedInfo`  
 [in] Vybere informace, které se mají vrátit. Platné hodnoty jsou:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`guidConstantValue`|Hodnota jako sekvence bajtů.|  
|`guidConstantType`|Typ jako typ podpisu.|  
  
 `prgBuffer`  
 [out] Vrátí rozšířené informace.  
  
 `pdwLen`  
 [out v] Vrátí velikost rozšířených informací v bajtech.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V současné době tato metoda vrátí pouze typem nebo hodnotou konstanty. Volající musí uvolnit vrácené ve vyrovnávací paměti `prgBuffer` volala modelu COM `CoTaskMemFree` – funkce (C++) nebo <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> (C#).  
  
## <a name="see-also"></a>Viz také  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)