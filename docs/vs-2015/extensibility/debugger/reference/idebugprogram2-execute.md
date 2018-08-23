---
title: IDebugProgram2::Execute | Dokumentace Microsoftu
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
- IDebugProgram2::Execute
helpviewer_keywords:
- IDebugProgram2::Execute
ms.assetid: f7205ce8-0ac6-4fcd-b6ec-b720b4fcaccf
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4223133cea40badb995b553032357267e21a948e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666329"
---
# <a name="idebugprogram2execute"></a>IDebugProgram2::Execute
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProgram2::Execute](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-execute).  
  
Dál spuštěním tohoto programu v zastaveném stavu. Vymazat všechny předchozí stav provádění (například krok), a program začne provádět znovu.  
  
> [!NOTE]
>  Tato metoda je zastaralá. Použití [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md) metoda místo.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Execute(  
   void  
);  
```  
  
```csharp  
int Execute();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když uživatel spustí provádění z zastaven jiným programem vlákno, tato metoda je volána v této aplikaci. Tato metoda je volána, i když uživatel vybere **Start** příkaz **ladění** nabídky v integrovaném vývojovém prostředí. Implementace této metody může být stejně jednoduché jako volání funkce [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md) metodu na aktuální vlákno v aplikaci.  
  
> [!WARNING]
>  Neodesílat událostí ukončení nebo okamžité (synchronní) události, která [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování tohoto volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Obnovení](../../../extensibility/debugger/reference/idebugthread2-resume.md)

