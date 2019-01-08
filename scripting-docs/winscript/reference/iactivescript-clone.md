---
title: IActiveScript::Clone | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.Clone
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_Clone
ms.assetid: aa000b2a-7085-448d-a422-f7adac7851cb
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 084da486d2e5831176130ccd080b9e09a80c9bcc
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093662"
---
# <a name="iactivescriptclone"></a>IActiveScript::Clone
Klonuje aktuální skriptovací stroj (bez jakékoli aktuální stav provádění), vrátí načíst skriptovací stroj, který nemá žádná lokalita v aktuálním vlákně. Vlastnosti tohoto nového skriptovacího stroje budou stejné vlastnosti, které by měly být původní skriptovací stroj v Pokud byly postoupí zpět do stavu spuštění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Clone(  
    IActiveScript **ppscript  // receives pointer to IActiveScript  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppscript`  
 [out] Adresa proměnné, která přijímá ukazatel [IActiveScript –](../../winscript/reference/iactivescript.md) rozhraní klonovaný skriptovací stroj. Hostitel musí vytvořit web a volání [IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md) metoda u nového skriptovacího stroje předtím, než je v inicializovaném stavu a tedy použitelné.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_NOTIMPL`|Tato metoda není podporována.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj má ještě nebyly načteny nebo inicializován).|  
  
## <a name="remarks"></a>Poznámky  
 `IActiveScript::Clone` Je metoda optimalizace `IPersist*::Save`, `CoCreateInstance`, a `IPersist*::Load`, takže se stav nové skriptovací modul by měl být stejný jako kdyby byly stavu původní skriptovací stroj uložit a načíst do nového skriptovacího stroje. V klonovaném skriptovací stroj jsou duplicitní položky s názvem, ale konkrétní objekt ukazatele pro každou položku jsou zapomněli a jsou získány pomocí [IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md) metody. To umožňuje identické objektový model vlákno vstupní body (modelu objektu apartment) který se má použít.  
  
 Tato metoda se používá pro hostitele s více vlákny serverů, které můžete spouštět více instancí stejného skriptu. Skriptovací stroj může vrátit `E_NOTIMPL`, v takovém hostiteli stejného výsledku dosáhnout duplikování trvalý stav a vytvořte novou instanci třídy skriptovací stroj s `IPersist*` rozhraní.  
  
 Tuto metodu lze volat z vlákna znaky bez výsledkem znaky popisek hostitele objektů nebo [iactivescriptsite –](../../winscript/reference/iactivescriptsite.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)