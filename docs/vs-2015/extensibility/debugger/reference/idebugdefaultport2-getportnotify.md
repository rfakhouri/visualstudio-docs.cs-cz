---
title: IDebugDefaultPort2::GetPortNotify | Dokumentace Microsoftu
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
- IDebugDefaultPort2::GetPortNotify
helpviewer_keywords:
- IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0a0cd508f0eab1d4ffc0feea32de128c411bef6c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675400"
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugDefaultPort2::GetPortNotify](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdefaultport2-getportnotify).  
  
Tato metoda načte [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) rozhraní pro tento port.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetPortNotify(  
   IDebugPortNotify2** ppPortNotify  
);  
```  
  
```csharp  
int GetPortNotify(  
   out IDebugPortNotify2 ppPortNotify  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppPortNotify`  
 [out] [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Za normálních okolností `QueryInterface` metoda je volána při implementaci objektu [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) rozhraní získat [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) rozhraní. Nicméně existují okolnosti, ve kterých požadované rozhraní je implementováno na jiný objekt. Tato metoda skrývá situace a vrátí `IDebugPortNotify2` rozhraní z objektu nejvhodnější.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)

