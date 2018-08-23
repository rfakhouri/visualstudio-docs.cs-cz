---
title: IDebugArrayObject::GetElements | Dokumentace Microsoftu
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
- IDebugArrayObject::GetElements
helpviewer_keywords:
- IDebugArrayObject::GetElements method
ms.assetid: f6a6262f-5183-46ce-8a45-33ef46088b98
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 16e4ce5b705d55203a0c9b7da02655be91628064
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669951"
---
# <a name="idebugarrayobjectgetelements"></a>IDebugArrayObject::GetElements
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugArrayObject::GetElements](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayobject-getelements).  
  
Získá enumerátor všech prvků pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetElements(   
   IEnumDebugObjects** ppEnum  
);  
```  
  
```csharp  
int GetElements(  
   out IEnumDebugObjects ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md) objekt, který umožňuje vytváření výčtu přes všechny prvky.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Jako alternativu použijte [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) a [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) metody k iteraci v rámci prvků.  
  
## <a name="see-also"></a>Viz také  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)

