---
title: IDebugProcess2::Detach | Dokumentace Microsoftu
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
- IDebugProcess2::Detach
helpviewer_keywords:
- IDebugProcess2::Detach
ms.assetid: ee2b9084-2db1-4e49-a1d9-387284b7c3f8
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1895c146f557e0c3ba79bd84970b99fc663cc891
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668085"
---
# <a name="idebugprocess2detach"></a>IDebugProcess2::Detach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProcess2::Detach](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess2-detach).  
  
Ladicí program z tohoto procesu se odpojí odpojíte všechny programy v procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Detach(   
   void   
);  
```  
  
```csharp  
int Detach();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Všechny programy a procesu pokračovat v běhu, ale už nejsou součástí relace ladění. Po odpojení operace dokončena, žádné další ladění, bude odeslána události pro tento proces (a jeho programy).  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

