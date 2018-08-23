---
title: IDebugObject2::GetBackingFieldForProperty | Dokumentace Microsoftu
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
- IDebugObject2::GetBackingFieldForProperty
helpviewer_keywords:
- IDebugObject2::GetBackingFieldForProperty method
ms.assetid: e72c6338-5573-4fad-8075-f3ade3435424
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b29b6eb411c511612b60faf271d23decd7370c12
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669737"
---
# <a name="idebugobject2getbackingfieldforproperty"></a>IDebugObject2::GetBackingFieldForProperty
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugObject2::GetBackingFieldForProperty](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject2-getbackingfieldforproperty).  
  
Získá pole nebo proměnné (pokud existuje), který může být zálohování vlastnost reprezentovaný tímto objektem.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetBackingFieldForProperty(  
   IDebugObject2** ppObject  
);  
```  
  
```csharp  
int GetBackingFieldForProperty(  
   out IDebugObject2 ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppObject`  
 [out] [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) objekt popisující pole zálohování.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) objekt představuje vlastnost třídy spravovaného kódu, to znamená, že metoda get a/nebo nastavení přístupového objektu. Tyto vlastnosti se obecně vyžadují proměnná obsahuje hodnotu manipulovat vlastnost. Tato proměnná je označována jako pole zálohování. Pokud tam není žádné pole zálohování pro objekt, ujistěte se, vrátí hodnotu null: některé volající nemusí věnovat pozornost návratovou hodnotu, ale místo toho bude vypadat zobrazíte, pokud byla vrácena hodnota null v `ppObject`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)

