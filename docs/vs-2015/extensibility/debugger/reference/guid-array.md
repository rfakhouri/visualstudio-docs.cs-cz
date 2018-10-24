---
title: GUID_ARRAY | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GUID_ARRAY structure
ms.assetid: 9e12500c-2c1c-49b1-a0ba-e08366c97eb8
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 048674fb1b024b5a4d7fa602a4757d81347c769b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49812254"
---
# <a name="guidarray"></a>GUID_ARRAY
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Popisuje celou řadu jedinečné identifikátory pro dostupné ladicí stroj.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
typedef struct tagGUID_ARRAY  
{  
   DWORD dwCount;  
   GUID *Members;  
} GUID_ARRAY;  
```  
  
```csharp  
public struct GUID_ARRAY  
{  
   public uint dwCount;  
   public Guid Members;  
}  
```  
  
## <a name="terms"></a>Podmínky  
 dwCount  
 Počet jedinečných identifikátorů v poli.  
  
 Členové  
 Pole, které obsahuje jedinečné identifikátory.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je vrácený [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)

