---
title: IDebugProgramEngines2::EnumPossibleEngines | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramEngines2::EnumPossibleEngines
helpviewer_keywords: IDebugProgramEngines2::EnumPossibleEngines
ms.assetid: 993d70a4-f6a5-4e47-a603-0b162b9fde00
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 81765959c0735080141ba8974387d592a461df25
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramengines2enumpossibleengines"></a>IDebugProgramEngines2::EnumPossibleEngines
Vrátí identifikátory GUID pro všechny možné ladění motory (DE), které můžete ladit tento program.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumPossibleEngines(   
   DWORD  celtBuffer,  
   GUID*  rgguidEngines,  
   DWORD* pceltEngines  
);  
```  
  
```csharp  
int EnumPossibleEngines(   
   uint      celtBuffer,  
   GUID[]    rgguidEngines,  
   ref DWORD pceltEngines  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celtBuffer`  
 [v] Počet identifikátory GUID DE vrátit. Také určuje maximální velikost `rgguidEngines` pole.  
  
 `rgguidEngines`  
 [ve out] Pole identifikátory GUID DE k vyplnění.  
  
 `pceltEngines`  
 [out] Vrátí skutečný počet DE identifikátory GUID, které jsou vráceny.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. Vrátí [C++] `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` nebo [C#] 0x8007007A, pokud vyrovnávací paměť není dostatečně velký.  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li zjistit, kolik modulů existuje jsou, volejte tuto metodu jednou s `celtBuffer` parametr nastaven na hodnotu 0 a `rgguidEngines` parametr nastaven na hodnotu null. Tento příkaz vrátí `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` (0x8007007A pro jazyk C#) a `pceltEngines` parametr vrátí potřebná velikost vyrovnávací paměti.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)