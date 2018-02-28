---
title: IDiaPropertyStorage::ReadMultiple | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadMultiple
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ffa66117095ef73ac9d25ce8117431f03ba0ad57
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiapropertystoragereadmultiple"></a>IDiaPropertyStorage::ReadMultiple
Čtení zadat vlastnosti z aktuální sadu vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT ReadMultiple(   
   ULONG          cpspec,  
   PROPSPEC const rgpspec,  
   PROPVARIANT    rgvar  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cpspec`  
 [v] Počet zadaný ve vlastnosti `rgpspec` pole. Pokud nula, metoda vrátí žádné vlastnosti, ale nevrátí `S_OK` jako kód úspěch.  
  
 `rgpspec`  
 [v] Pole vlastnosti, které chcete přečíst. Vlastnosti lze zadat, a vlastnost ID nebo názvem volitelný řetězec. Není potřeba zadat vlastnosti v libovolném pořadí v poli. Pole může obsahovat duplicitní vlastnosti, což vede k duplicitní vlastnost hodnot návratovou hodnotu pro jednoduché vlastnosti. Vlastnosti non jednoduché by měl vrátit odepřen přístup při pokusu o jejich otevření ještě jednou. Pole může obsahovat kombinaci vlastnost ID a řetězec ID. Toto pole musí mít minimálně `cpspec` počet hodnot vlastností.  
  
 `rgvar`  
 [ve out] Pole `PROPVARIANT` struktury (v oboru názvů sestavení Microsoft.VisualStudio.OLE.Interop) pro vyplnění hodnoty pro každou vlastnost. Pole musí být minimálně `cpspec` elementy velikost. Volající není nutné k chybě při inicializaci hodnoty v poli.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud jeden nebo více vlastností nebyl nalezen. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud nebyla nalezena vlastnost, odpovídající položku v `rgvar` obsahuje pole `VARIANT` s typem `VT_EMPTY`.  
  
## <a name="see-also"></a>Viz také  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)