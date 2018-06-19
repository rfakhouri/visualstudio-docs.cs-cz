---
title: IDebugAlias::GetICorDebugValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bfe0d8e4734c0d836b2dc6009fdedfa264720778
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099048"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
Načte rozhraní spravovaného kódu, který představuje hodnotu přidruženou tento alias.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetICorDebugValue(  
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetICorDebugValue(  
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppUnk`  
 [out] `IUnknown` rozhraní, které představuje hodnotu přidruženou tento alias. Toto rozhraní může být dotázán na `ICorDebugValue` rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tuto metodu lze použít pouze spravovaný hodnoty ( `ICorDebugValue` je k dispozici v rozhraní [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] a je definována v [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] SDK v souboru cordebug.idl).  
  
## <a name="see-also"></a>Viz také  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)