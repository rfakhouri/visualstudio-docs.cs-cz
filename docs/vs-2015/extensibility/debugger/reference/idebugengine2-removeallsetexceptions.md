---
title: IDebugEngine2::RemoveAllSetExceptions | Dokumentace Microsoftu
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
- IDebugEngine2::RemoveAllSetExceptions
helpviewer_keywords:
- IDebugEngine2::RemoveAllSetExceptions
ms.assetid: 165fbe89-802d-4d99-85ca-c10fd6cccc09
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 09951fb3f19866b5efd3dc1511ef465907efb398
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629453"
---
# <a name="idebugengine2removeallsetexceptions"></a>IDebugEngine2::RemoveAllSetExceptions
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugEngine2::RemoveAllSetExceptions](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugengine2-removeallsetexceptions).  
  
Odebere seznam výjimek, integrovaném vývojovém prostředí má nastavit pro konkrétní architekturu za běhu nebo jazyk.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT RemoveAllSetExceptions(   
   REFGUID guidType  
);  
```  
  
```csharp  
int RemoveAllSetExceptions(   
   ref Guid guidType  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidType`  
 [in] Identifikátor GUID pro jazyk nebo identifikátor GUID pro ladicí stroj, který je specifický pro architekturu za běhu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Výjimky odebrat touto metodou byly nastavené zásadami předchozích volání [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) metody.  
  
 Chcete-li odebrat určité výjimky, zavolejte [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)

