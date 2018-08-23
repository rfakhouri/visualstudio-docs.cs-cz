---
title: IDebugProcess3::Step | Dokumentace Microsoftu
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
- IDebugProcess3::Step
helpviewer_keywords:
- IDebugProcess3::Step
ms.assetid: 6ad9094c-27cc-4927-8a7c-1b4d97b2e436
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: db2f9ac59fcb72c7bc2a937dcba883eae8c26fe1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671174"
---
# <a name="idebugprocess3step"></a>IDebugProcess3::Step
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProcess3::Step](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess3-step).  
  
Způsobí, že proces kroku jedna instrukce nebo příkaz.  
  
> [!NOTE]
>  Tato metoda by měla být použita místo [krok](../../../extensibility/debugger/reference/idebugprogram2-step.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Step(  
   IDebugThread2* pThread,  
   STEPKIND       sk,  
   STEPUNIT       step,  
);  
```  
  
```csharp  
int Step(  
   IDebugThread2 pThread,   
   enum_STEPKIND sk,   
   enum_STEPUNIT step  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt představující vlákna se stupňovitým.  
  
 `sk`  
 [in] Jeden z [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) hodnoty.  
  
 `step`  
 [in] Jeden z [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) hodnoty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V případě, že je komunikace mezi vlákny ani synchronizaci vláken, ostatní vlákna v procesu měli spustit při krokování konkrétní vlákno.  
  
 **Upozornění** Neodesílat událostí ukončení nebo okamžité (synchronní) události, která [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování tohoto volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md)   
 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)

