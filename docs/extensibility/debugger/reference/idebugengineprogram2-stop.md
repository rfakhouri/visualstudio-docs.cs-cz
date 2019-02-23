---
title: IDebugEngineProgram2::Stop | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineProgram2::Stop
helpviewer_keywords:
- IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b3cb9627ba11bdec5729383bd6a31e4a338f3ef9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686766"
---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
Zastaví všechna vlákna spuštěná v rámci tohoto programu.

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
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda je volána, když je tento program laděn v prostředí s více programu. Když je obdržena událostí ukončení z některé aplikace, tato metoda je volána v této aplikaci. Implementace této metody by měla být asynchronní; To znamená, že ne všechna vlákna by měl být musí být zastaven předtím, než tato metoda vrátí hodnotu. Implementace této metody může být stejně jednoduché jako volání funkce [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) metody v této aplikaci.

 Žádná událost ladění je odeslaný v odpovědi na tuto metodu.

## <a name="see-also"></a>Viz také
- [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)
- [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)