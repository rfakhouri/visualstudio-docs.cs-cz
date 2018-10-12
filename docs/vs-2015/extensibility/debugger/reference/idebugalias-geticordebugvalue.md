---
title: IDebugAlias::GetICorDebugValue | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c5e67bf2c470fc525b2d918a5f4ecb10b13ff8d0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49306277"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Načte rozhraní spravovaného kódu, které představuje hodnotu přidruženou k tento alias.  
  
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
 [out] `IUnknown` rozhraní, které představuje hodnotu přidruženou k tento alias. Toto rozhraní je možné zadávat dotazy pro `ICorDebugValue` rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tento postup se vztahuje jenom na spravované hodnoty ( `ICorDebugValue` je k dispozici v rozhraní [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] a je definován v [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] sady SDK v souboru cordebug.idl).  
  
## <a name="see-also"></a>Viz také  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)

