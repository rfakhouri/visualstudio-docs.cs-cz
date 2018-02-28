---
title: IDebugAddress2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugAddress2
helpviewer_keywords:
- IDebugAddress2 interface
ms.assetid: b150e0ed-4ac0-4f8c-9732-4b3e54b9d243
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 43c112da892fadf95eb5a27880d82ec9d29419c7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugaddress2"></a>IDebugAddress2
Toto rozhraní poskytuje přístup k ID procesu, který vlastní objekt, jehož adresa je reprezentována toto rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugAddress2 : IDebugAddress  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje poskytovatele symbol pro stejný objekt, který implementuje [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní. Toto rozhraní poskytuje přístup k ID procesu, který vlastní objekt, který se vztahuje na tuto adresu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](/cpp/atl/queryinterface) k získání tohoto rozhraní z [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce vtable pořadí  
 Kromě metod zděděno z [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní, toto rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getprocessid –](../../../extensibility/debugger/reference/idebugaddress2-getprocessid.md)|Načte ID procesu, který vlastní objekt reprezentovaný tímto rozhraním.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Zprostředkovatel rozhraní symbol](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)