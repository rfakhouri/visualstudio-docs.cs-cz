---
title: IDebugExtendedField::IsClosedType | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IsClosedType
- IDebugExtendedField::IsClosedType
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a566f5dc7d498a9b07d132abe35b279cbc83155d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627905"
---
# <a name="idebugextendedfieldisclosedtype"></a>IDebugExtendedField::IsClosedType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugExtendedField::IsClosedType](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugextendedfield-isclosedtype).  
  
Určuje, zda pole představuje uzavřený typ.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT IsClosedType(  
   void  
);  
```  
  
```csharp  
int IsClosedType();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je pole uzavřený typ, vrátí `S_OK`; v opačném případě vrátí `S_FALSE`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)

