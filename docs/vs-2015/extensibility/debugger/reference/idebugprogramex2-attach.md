---
title: IDebugProgramEx2::Attach | Dokumentace Microsoftu
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
- IDebugProgramEx2::Attach
helpviewer_keywords:
- IDebugProgramEx2::Attach
ms.assetid: 33b22b2f-431e-4205-9441-d28a9c928c97
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1969f8d38cd52572f0d0c7cde603a1ea25c0e0be
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667650"
---
# <a name="idebugprogramex2attach"></a>IDebugProgramEx2::Attach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProgramEx2::Attach](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramex2-attach).  
  
Relaci připojení k programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason,  
   IDebugSession2*       pSession  
);  
```  
  
```  
[C#]  
int Attach(   
   IDebugEventCallback2 pCallback,  
   uint                 dwReason,  
   IDebugSession2       pSession  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který reprezentuje funkce zpětného volání, která odesílá události do připojeného ladicího stroje.  
  
 `dwReason`  
 [in] Hodnota z [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) výčet, který je popsaný i důvod pro operace připojení.  
  
 `pSession`  
 [in] Hodnota, která jednoznačně identifikuje relace, která se připojuje k programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Tato metoda by měla vrátit `E_ATTACH_DEBUGGER_ALREADY_ATTACHED` Pokud program je již připojen.  
  
## <a name="remarks"></a>Poznámky  
 Port, který obsahuje program můžete použít hodnotu v `pSession` k určení, které relace se pokouší připojit k programu. Například pokud port umožňuje pouze jednu ladicí relaci se připojit k procesu najednou, port, který můžete určit, pokud stejné relace je již připojena k jiné programy v procesu.  
  
> [!NOTE]
>  Předané rozhraní `pSession` je považován za pouze do souboru cookie, hodnotu, která jednoznačně identifikuje správce ladění relace připojení k tomuto programu; žádný z metod na zadané rozhraní není funkční.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)

