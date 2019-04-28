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
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62797616"
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
