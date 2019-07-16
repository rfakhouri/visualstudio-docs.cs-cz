---
title: IDebugArrayObject::GetCount | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetCount
helpviewer_keywords:
- IDebugArrayObject::GetCount method
ms.assetid: 7931f3f7-033c-4bf8-8abd-95183952ebb0
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 35cce37afc389501386ffec7b75b934e7933bc98
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68197796"
---
# <a name="idebugarrayobjectgetcount"></a>IDebugArrayObject::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá počet elementů v poli.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[C++]  
HRESULT GetCount(   
   DWORD* pdwElements  
);  
```  
  
```  
[C#]  
int GetCount(  
   out uint pdwElements  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwElements`  
 [out] Vrátí počet.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda považuje všechny prvky objektu pole jednorozměrné pole, i když objekt pole je vícerozměrné. Mějme například pole `myarray[3][2][6]`, tato metoda vrátí 36 `pdwElements` parametru. Použití [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) metodu pro načtení jednotlivých prvků jeden po druhém.  
  
## <a name="see-also"></a>Viz také  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
