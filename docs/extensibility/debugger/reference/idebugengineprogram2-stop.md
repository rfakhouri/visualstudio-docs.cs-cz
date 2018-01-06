---
title: IDebugEngineProgram2::Stop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngineProgram2::Stop
helpviewer_keywords: IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4004ca92b32e63565a71a3a6971ebb4ae073b9f9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
Zastaví všechny podprocesy spuštěné v této aplikaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Stop(   
   void   
);  
```  
  
```csharp  
int Stop();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána, když tento program je právě ladí v prostředí s více programu. Když je obdržena událost zastavit z jiným programem, tato metoda je volána v této aplikaci. Implementace této metody by měla být asynchronní; To znamená musí být všechny vláken muset zastavit před tato metoda vrátí hodnotu. Implementace této metody může být stejně jednoduché jako volání [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) metoda na tento program.  
  
 Žádné události ladění je odeslaný v odpovědi na tuto metodu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)