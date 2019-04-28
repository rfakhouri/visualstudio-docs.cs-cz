---
title: IActiveScriptAuthor::GetLanguageFlags | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: d9f1a68db05ac0d909108ce77587ae4b071c9a2b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935468"
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
  
|Konstanta|Value|Popis|  
|--------------|-----------|-----------------|  
|fasaPreferInternalHandler|0x0001|Jazyk upřednostňuje skript vytvoření obslužné rutiny událostí ve skriptu pro vytváření modulu namísto aplikace.|  
|fasaSupportInternalHandler|0x0002|Jazyk podporuje vytvořen skriptem modul pro vytváření obslužných rutin událostí skriptu.|  
|fasaCaseSensitive|0x0004|Skriptovací jazyk je velká a malá písmena.|  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud skript pro tvorbu modul spravuje obslužné rutiny událostí, vaše aplikace měla zavolat `CreateChildHandler` ze `IScriptEntry` objektu. Tím se vytvoří `IScriptScriptlet` objekt, který odpovídá obslužné rutiny události. Modul také přidá obslužnou rutinu události k položce skriptu. Obslužná rutina události je prázdná funkce, která obsahuje informace o zadané podpisu.  
  
 Pokud vaše aplikace spravuje obslužné rutiny událostí, měla by volat `CreateChildHandler` ze `IScriptNode` objekt, který reprezentuje skriptletu obslužné rutiny události. Tím se vytvoří `IScriptScriptlet` objekt, který je spojen se skriptletem obslužné rutiny události. Aplikace má také přidejte prázdnou funkci jako událost obslužné rutiny na nový nebo existující `IScriptEntry` objektu.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthor – rozhraní](../../winscript/reference/iactivescriptauthor-interface.md)