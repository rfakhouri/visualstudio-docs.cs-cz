---
title: IDebugCustomAttributeQuery2::EnumCustomAttributes | Dokumentace Microsoftu
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
- IDebugCustomAttributeQuery2::EnumCustomAttributes
helpviewer_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
ms.assetid: 94bfce74-aa3d-45f0-8e04-5715faf85217
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c516d85a11e6d4e85cf86cf56f740e2f2bf7cf84
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632676"
---
# <a name="idebugcustomattributequery2enumcustomattributes"></a>IDebugCustomAttributeQuery2::EnumCustomAttributes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugCustomAttributeQuery2::EnumCustomAttributes](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes).  
  
Získá enumerátor pro všechny vlastní atributy připojené k tomuto poli.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT EnumCustomAttributes(   
   IEnumDebugCustomAttributes** ppEnum  
);  
```  
  
```csharp  
int EnumCustomAttributes(  
   out IEnumDebugCustomAttributes ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) objekt představující seznam vlastních atributů; jinak vrátí hodnotu null, pokud neexistují žádné vlastní atributy.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu, vrátí hodnotu S_OK nebo S_FALSE, pokud nejsou žádné vlastní atributy v tomto poli. V opačném případě vrátí kód chyby;  
  
## <a name="remarks"></a>Poznámky  
 Pole může mít několik vlastních atributů.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)

