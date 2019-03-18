---
title: IScriptEntry::SetItemName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetItemName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetItemName
ms.assetid: 9551a7ec-38f8-466a-9722-09367763f380
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d25ac4977f1fca44d63767c372db169f8cb61ea6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160547"
---
# <a name="iscriptentrysetitemname"></a>IScriptEntry::SetItemName
Nastaví název položky, který identifikuje `IScriptEntry` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetItemName(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `psz`  
 [in] Adresa vyrovnávací paměti, který obsahuje název položky. Název položky se hostitel používá k identifikaci položky.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_FAIL`|Metoda nebylo úspěšné.|  
  
## <a name="remarks"></a>Poznámky  
 Pro `IScriptEntry` objekty, vrátí tato metoda `S_OK`.  
  
 Pro `IScriptScriptlet` objekty (které jsou odvozeny z `IScriptEntry`), vrátí tato metoda `E_FAIL`. Pro `IScriptScriptlet` objekty, název položky je nastavený [IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md) a nedá se změnit.  
  
## <a name="see-also"></a>Viz také  
 [Iscriptentry – rozhraní](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetItemName](../../winscript/reference/iscriptentry-getitemname.md)