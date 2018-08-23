---
title: IDebugPortEx2::GetPortProcessId | Dokumentace Microsoftu
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
- IDebugPortEx2::GetPortProcessId
helpviewer_keywords:
- IDebugPortEx2::GetPortProcessId
ms.assetid: be85be66-47e6-415f-b0ca-24599aa5f13c
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d0364810c3538c37fcbb9d598d94c521b4024c51
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633340"
---
# <a name="idebugportex2getportprocessid"></a>IDebugPortEx2::GetPortProcessId
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugPortEx2::GetPortProcessId](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportex2-getportprocessid).  
  
Získá ID procesu portu samotný.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetPortProcessId (   
   DWORD* pdwProcessId  
);  
```  
  
```csharp  
int GetPortProcessId (   
   out uint pdwProcessId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwProcessId`  
 [out] Vrátí ID procesu fyzického portu samotný.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V modulu runtime Win32 například tato metoda obvykle volá funkci Win32 `GetCurrentProcessId` získat ID procesu fyzické.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)

