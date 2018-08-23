---
title: IDebugArrayObject::GetElement | Dokumentace Microsoftu
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
- IDebugArrayObject::GetElement
helpviewer_keywords:
- IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b02e13443735b2f4620c479495c8aab8af9b3108
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633229"
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugArrayObject::GetElement](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayobject-getelement).  
  
Získá prvek pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetElement(   
   DWORD          dwIndex,  
   IDebugObject** ppElement  
);  
```  
  
```csharp  
int GetElement(  
   [In] uint dwIndex,   
   out IDebugObject ppElement  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwIndex`  
 [in] Index prvku.  
  
 `ppElement`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní, které představuje element.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda považuje všechny prvky objektu pole jednorozměrné pole, i když objekt pole je vícerozměrné. Mějme například pole `myarray[3][2][6]` a `dwIndex` parametr 20, vrátí tato metoda element z `myarray[1][1][2]`a `dwIndex` parametr 21 vracel element z `myarray[1][1][3]`. Použití [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) metodou ke zjištění celkový počet prvků v poli.  
  
## <a name="see-also"></a>Viz také  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)

