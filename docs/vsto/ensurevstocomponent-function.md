---
title: Ensurevstocomponent – funkce
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f99ccb4cb76f942852716abf1fcb0c0f280decbd
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621432"
---
# <a name="ensurevstocomponent-function"></a>Ensurevstocomponent – funkce
  Toto rozhraní API podporuje infrastrukturu sady Office a není určena pro použití přímo v kódu.

## <a name="syntax"></a>Syntaxe

```csharp
HRESULT EnsureVSTOComponent(
    IVSTProject *pProject
);
```

#### <a name="parameters"></a>Parametry

|Parametr|Popis|
|---------------|-----------------|
|*pProject*|Nepoužívejte.|

## <a name="return-value"></a>Návratová hodnota
 Pokud funkce uspěje, vrátí **S_OK**. Pokud funkce selže, vrátí kód chyby.
