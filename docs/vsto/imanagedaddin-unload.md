---
title: IManagedAddin::Unload
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Unload method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 296502aa461688c34152d86ee21aab5f2c83ecb4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640490"
---
# <a name="imanagedaddinunload"></a>IManagedAddin::Unload
  Volá se bezprostředně před spravované Add-in VSTO je uvolněna.

## <a name="syntax"></a>Syntaxe

```csharp
HRESULT Unload();
```

## <a name="return-value"></a>Návratová hodnota
 Hodnota HRESULT, která označuje, zda metoda byla úspěšně dokončena.

## <a name="remarks"></a>Poznámky
 Tato metoda není volána aktuální verze sady Microsoft Office. Tato metoda je vyhrazená pro budoucí použití.

## <a name="see-also"></a>Viz také:
- [Imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md)
- [IManagedAddin::Load](../vsto/imanagedaddin-load.md)
