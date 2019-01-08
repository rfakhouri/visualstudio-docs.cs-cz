---
title: IActiveScriptAuthor::GetLanguageFlags | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetLanguageFlags
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetLanguageFlags
ms.assetid: eb244452-62f7-4a73-b48f-1aa05cbcc32d
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dca878d6d4fd15db4b516e37932fbfebd30607a2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093194"
---
# <a name="iactivescriptauthorgetlanguageflags"></a>IActiveScriptAuthor::GetLanguageFlags
Vrátí informace o jazyce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetLanguageFlags(  
   DWORD              *pgrfasa  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pgrfasa`  
 [out] Příznaky, které obsahují informace o jazyce. Může být kombinací následujícího:  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|fasaPreferInternalHandler|0x0001|Jazyk upřednostňuje skript vytvoření obslužné rutiny událostí ve skriptu pro vytváření modulu namísto aplikace.|  
|fasaSupportInternalHandler|0x0002|Jazyk podporuje vytvořen skriptem modul pro vytváření obslužných rutin událostí skriptu.|  
|fasaCaseSensitive|0x0004|Skriptovací jazyk je velká a malá písmena.|  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud skript pro tvorbu modul spravuje obslužné rutiny událostí, vaše aplikace měla zavolat `CreateChildHandler` ze `IScriptEntry` objektu. Tím se vytvoří `IScriptScriptlet` objekt, který odpovídá obslužné rutiny události. Modul také přidá obslužnou rutinu události k položce skriptu. Obslužná rutina události je prázdná funkce, která obsahuje informace o zadané podpisu.  
  
 Pokud vaše aplikace spravuje obslužné rutiny událostí, měla by volat `CreateChildHandler` ze `IScriptNode` objekt, který reprezentuje skriptletu obslužné rutiny události. Tím se vytvoří `IScriptScriptlet` objekt, který je spojen se skriptletem obslužné rutiny události. Aplikace má také přidejte prázdnou funkci jako událost obslužné rutiny na nový nebo existující `IScriptEntry` objektu.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthor – rozhraní](../../winscript/reference/iactivescriptauthor-interface.md)