---
title: IDebugClassField::DoesInterfaceExist | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugClassField::DoesInterfaceExist
helpviewer_keywords:
- IDebugClassField::DoesInterfaceExist method
ms.assetid: cc0c8642-1a76-4fda-a309-7018a34883c9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a7c4a09af356951e7e26b6c9b6b0af5922b9f53b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugclassfielddoesinterfaceexist"></a>IDebugClassField::DoesInterfaceExist
Určuje, zda určité rozhraní je definována v třídě.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DoesInterfaceExist(   
   LPCOLESTR pszInterfaceName  
);  
```  
  
```csharp  
int DoesInterfaceExist(  
   [In] string pszInterfaceName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszInterfaceName`  
 [v] Řetězec obsahující název rozhraní má být vyhledán.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK, vrátí hodnotu S_FALSE Pokud rozhraní neexistuje; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda platí získá výčet všech rozhraní a vyhledá v seznamu odpovídající rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)