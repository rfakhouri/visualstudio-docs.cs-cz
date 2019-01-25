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
ms.openlocfilehash: 68ef36185c193263db386a1e1f80877c0327440c
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54874338"
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
 [Imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Load](../vsto/imanagedaddin-load.md)  
