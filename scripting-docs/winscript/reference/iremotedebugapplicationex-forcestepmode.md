---
title: IRemoteDebugApplicationEx:ForceStepMode | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:ForceStepMode
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:ForceStepMode
ms.assetid: 83e69a3e-e4c9-4ddd-b01b-1820e4177a03
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04a2c700d2cac4bcdc845ebf442de29863e87deb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62934638"
---
# <a name="iremotedebugapplicationexforcestepmode"></a>IRemoteDebugApplicationEx:ForceStepMode

Vynutí ladicí program v režimu krokování.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT ForceStepMode(
   IRemoteDebugApplicationThread*  pStepThread
);
```

### <a name="parameters"></a>Parametry

`pStepThread`

[in] Vlákno pro sledování ladění procesu krok. Pokud má hodnotu null, PDM vymaže jeho krokování vlákna.

## <a name="return-value"></a>Návratová hodnota

Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.

|Value|Popis|
|-----------|-----------------|
|`S_OK`|Metoda byla úspěšná.|

## <a name="see-also"></a>Viz také:

- [IRemoteDebugApplicationEx – rozhraní](iremotedebugapplicationex-interface.md)