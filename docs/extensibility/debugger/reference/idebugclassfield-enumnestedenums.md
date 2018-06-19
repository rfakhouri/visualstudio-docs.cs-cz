---
title: IDebugClassField::EnumNestedEnums | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumNestedEnums
helpviewer_keywords:
- IDebugClassField::EnumNestedEnums method
ms.assetid: 90fd0cef-9145-4de6-91d4-6c881df39d6e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2ea28f2a455d3528f083ba2acb2e9e4ad8989319
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103026"
---
# <a name="idebugclassfieldenumnestedenums"></a>IDebugClassField::EnumNestedEnums
Vytvoří enumerátor pro vnořené výčty této třídy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumNestedEnums(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumNestedEnums(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objektu, který představuje seznam vnořených výčty. Vrátí hodnotu null, pokud nejsou žádné vnořené výčty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK nebo vrátí S_FALSE, pokud nejsou žádné vnořené výčty. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek výčtu je [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) objekt popisující vnořené výčtu.  
  
 Výčet deklarovat uvnitř třídy je považován za vnořené výčtu. Například uděleno:  
  
```  
class RootClass {  
   enum NestedEnum { EnumValue = 0 }  
};  
```  
  
 `EnumNestedEnums` Metoda by vrátit [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt, který obsahuje jeden [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) objekt, který reprezentuje `NestedEnum` výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)