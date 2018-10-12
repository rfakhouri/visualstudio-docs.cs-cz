---
title: IDebugEngineProgram2::Stop | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEngineProgram2::Stop
helpviewer_keywords:
- IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0bd5312d611d261b6b0912edbd45c49fe07d2024
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49235882"
---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Zastaví všechna vlákna spuštěná v rámci tohoto programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Stop(   
   void   
);  
```  
  
```csharp  
int Stop();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána, když je tento program laděn v prostředí s více programu. Když je obdržena událostí ukončení z některé aplikace, tato metoda je volána v této aplikaci. Implementace této metody by měla být asynchronní; To znamená, že ne všechna vlákna by měl být musí být zastaven předtím, než tato metoda vrátí hodnotu. Implementace této metody může být stejně jednoduché jako volání funkce [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) metody v této aplikaci.  
  
 Žádná událost ladění je odeslaný v odpovědi na tuto metodu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)

