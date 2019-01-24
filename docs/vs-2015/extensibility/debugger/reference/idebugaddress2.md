---
title: IDebugAddress2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugAddress2
helpviewer_keywords:
- IDebugAddress2 interface
ms.assetid: b150e0ed-4ac0-4f8c-9732-4b3e54b9d243
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 23fb27643a209e870165e521d63079a3b6c650eb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54765665"
---
# <a name="idebugaddress2"></a>IDebugAddress2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní poskytuje přístup k ID procesu, který je vlastníkem objektu, jehož adresu reprezentované tímto rozhraním.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugAddress2 : IDebugAddress  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Poskytovatel symbolů implementuje na stejný objekt, který implementuje toto rozhraní [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní. Toto rozhraní poskytuje přístup k ID procesu, který vlastní objekt, který se vztahuje na tuto adresu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) získat z tohoto rozhraní [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce vtable pořadí  
 Kromě metod zděděných z [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní, toto rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetProcessID](../../../extensibility/debugger/reference/idebugaddress2-getprocessid.md)|Načte ID procesu, který vlastní objekt reprezentovaný tímto rozhraním.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
