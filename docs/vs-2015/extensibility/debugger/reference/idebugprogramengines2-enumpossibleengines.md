---
title: IDebugProgramEngines2::EnumPossibleEngines | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
helpviewer_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
ms.assetid: 993d70a4-f6a5-4e47-a603-0b162b9fde00
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 971c4d44cc5b12460b9f715a60537687665b0e1d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677681"
---
# <a name="idebugprogramengines2enumpossibleengines"></a>IDebugProgramEngines2::EnumPossibleEngines
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProgramEngines2::EnumPossibleEngines](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines).  
  
Vrátí GUID pro všechny možné ladění motorů (DE), které můžete ladit tento program.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] Počet identifikátorů GUID DE vrátit. Také určuje maximální velikost `rgguidEngines` pole.  
  
 `rgguidEngines`  
 [out v] Pole DE identifikátory GUID pro vyplnění.  
  
 `pceltEngines`  
 [out] Vrátí skutečný počet DE identifikátory GUID, které jsou vráceny.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí [C++] `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` nebo [C#] 0x8007007A, pokud vyrovnávací paměť není dostatečně velký.  
  
## <a name="remarks"></a>Poznámky  
 Aby bylo možné zjistit, kolik motory existuje jsou, volejte tuto metodu jednou se `celtBuffer` parametr nastaven na hodnotu 0 a `rgguidEngines` parametr nastaven na hodnotu null. Vrátí `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` (0x8007007A pro jazyk C#) a `pceltEngines` parametr vrací potřebná velikost vyrovnávací paměti.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)

