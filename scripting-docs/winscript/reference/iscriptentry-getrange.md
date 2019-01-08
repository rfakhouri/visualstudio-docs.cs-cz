---
title: IScriptEntry::GetRange | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetRange
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetRange
ms.assetid: 3ac18f0a-b470-4f4d-b8f5-2da3fdef74f1
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a4e053817ed4c503ebb41e2f3828da421e69ec7
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088735"
---
# <a name="iscriptentrygetrange"></a>IScriptEntry::GetRange
Vrátí počáteční pozice a délka položky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetRange(  
   ULONG              *pichMin  
   ULONG              *pcch  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pichMin`  
 [out] Pro `IScriptEntry` objekty, které určují blok skriptu, vrátí hodnotu 0.  
  
 Pro `IScriptEntry` objekty, které určují objektu funkce vrátí počáteční pozici funkce v aktuálním bloku skriptu.  
  
 Pro `IScriptScriptlet` objekty, vrátí hodnotu 0.  
  
 `pcch`  
 [out] Pro `IScriptEntry` objekty, které určují blok skriptu, vrátí délku textu.  
  
 Pro `IScriptEntry` objekty, které určují funkce objektu, vrátí délku v definici funkce.  
  
 Pro `IScriptScriptlet` objekty, vrátí délku vstupu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IScriptEntry – rozhraní](../../winscript/reference/iscriptentry-interface.md)