---
title: IDiaPropertyStorage::ReadMultiple | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaPropertyStorage::ReadMultiple
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77ead9e28f86067c08aa610fc902f2a0847bfb25
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Idiapropertystorage –](../../debugger/debug-interface-access/idiapropertystorage.md)