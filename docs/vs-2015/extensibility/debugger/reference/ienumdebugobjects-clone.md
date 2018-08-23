---
title: IEnumDebugObjects::Clone | Dokumentace Microsoftu
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
- IEnumDebugObjects::Clone
helpviewer_keywords:
- IEnumDebugObjects::Clone method
ms.assetid: cb7df109-d29a-4218-b900-6809091459dd
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 938fd48968cdb0b37402519f3afd7a902453a406
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677814"
---
# <a name="ienumdebugobjectsclone"></a>IEnumDebugObjects::Clone
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IEnumDebugObjects::Clone](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugobjects-clone).  
  
Tato metoda vrátí kopii objektu do aktuálního výčtu jako samostatný objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Clone(  
   IEnumDebugObjects** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugObjects ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí kopii objektu tento výčet jako samostatný objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kopírování výčet má stejného stavu jako původní v době, kdy tato metoda je volána. Ale tuto kopii a původní stavy jsou oddělené a je možné změnit individuálně.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)

