---
title: IDebugProgram2::WriteDump | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::WriteDump
helpviewer_keywords:
- IDebugProgram2::WriteDump
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f4fc77748e456a612130de4b8f814ea7ba491f22
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021842"
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
Výpis zapíše do souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT WriteDump(   
   DUMPTYPE  DumpType,  
   LPCOLESTR pszDumpUrl  
);  
```  
  
```csharp  
int WriteDump(   
   enum_DUMPTYPE  DumpType,  
   string         pszDumpUrl  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `DumpType`  
 [in] Hodnota z [DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md) výčet, který určuje typ s výpisem paměti, například řečeno nebo long.  
  
 `pszDumpUrl`  
 [in] Adresa URL s výpisem paměti pro zápis. Obvykle je to ve formě `file://c:\path\filename.ext`, ale mohou být jakákoliv platná adresa URL.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Výpis program obvykle zahrnuje aktuální rámec zásobníku, zásobník samotný seznam vlákna spuštěná v programu a pravděpodobně paměti, která vlastní program.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)