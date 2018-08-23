---
title: IDebugPointerObject::Dereference | Dokumentace Microsoftu
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
- IDebugPointerObject::Dereference
helpviewer_keywords:
- IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dd1c0652a8c1b165ae37756238c5615c4572c886
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676296"
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugPointerObject::Dereference](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugpointerobject-dereference).  
  
Získá odkazovaný objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT DeReference(   
   DWORD          dwIndex,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Dereference(  
   uint             dwIndex,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwIndex`  
 [in] Ukazuje jednoduchý bajtovým posunem od začátku objektu.  
  
 `ppObject`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt reprezentující objekt odkazovala na plus odsazení, pokud existuje.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby. Pokud tento objekt neodkazuje na jiný objekt, vrátí E_FAIL.  
  
## <a name="remarks"></a>Poznámky  
 Odkazovaný objekt může být jednoduchého typu nebo typu složitější například třídy nebo struktury.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)

