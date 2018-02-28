---
title: IDebugProgram2::WriteDump | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgram2::WriteDump
helpviewer_keywords:
- IDebugProgram2::WriteDump
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 40fcd345a2a07a0ebdcf9e984b060cc81e946fc3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
Výpis zapisuje do souboru.  
  
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
 [v] Hodnota z [DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md) výčet, který určuje typ výpisu, například, prostě nebo long.  
  
 `pszDumpUrl`  
 [v] Adresa URL k výpisu k zápisu. Obvykle je to ve formě `file://c:\path\filename.ext`, ale může být libovolná platná adresa URL.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Výpis program by měl obvykle zahrnovat aktuální rámec zásobníku, zásobník samotný, seznam vláken v programu a které by mohly mít žádné paměti, která vlastní program.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)