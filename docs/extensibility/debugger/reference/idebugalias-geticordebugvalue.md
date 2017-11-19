---
title: IDebugAlias::GetICorDebugValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAlias::GetICorDebugValue
helpviewer_keywords: IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 603f24f89463b9eb9f7c67ed3d05662870e41bf3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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