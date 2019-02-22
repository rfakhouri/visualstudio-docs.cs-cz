---
title: EndCapture | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 06084c3b-e065-49b6-968e-d578762fb871
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0ae024f0d91c980fa8e787b21c93d32a6431203e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695528"
---
# <a name="endcapture"></a>EndCapture
Končí zachycení interval, který byl spuštěn s `BeginCapture`.

## <a name="syntax"></a>Syntaxe

```C++
void EndCapture();
```

## <a name="remarks"></a>Poznámky
 Interval sběru obvykle zahrnuje podmnožinu jeden snímek, například když budete chtít zachytit grafické informace pouze o druh volání draw. Pokud interval zachytávání zahrnuje volání k dispozici, jsou zachyceny dvěma snímky informací grafiky. První snímek zahrnuje interval mezi volání `BeginCapture` a volání k dispozici; druhý snímek zahrnuje interval mezi první události rozhraní Direct3D po volání k dispozici a volání `EndCapture`.

 K zachycení intervalu, musíte připravit vaše aplikace k zachycení a zaznamenání grafických informací – to znamená, musí zavoláte [Init](init.md) prostřednictvím instance `VsgDbg` třídy před voláním `BeginCapture` nebo `EndCapture`.

## <a name="see-also"></a>Viz také
- [BeginCapture](begincapture.md)
- [CaptureCurrentFrame](capturecurrentframe.md)