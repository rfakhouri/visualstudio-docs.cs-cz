---
title: IActiveScriptAuthor::AddNamedItem | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.AddNamedItem
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::AddNamedItem
ms.assetid: 951003b6-1c4a-4086-b7ce-2f128e007280
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 95bc529db8129c4e9af1ed9f9dc3d91de9686223
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58145652"
---
# <a name="iactivescriptauthoraddnameditem"></a>IActiveScriptAuthor::AddNamedItem
Přidá název položky kořenové úrovně skriptu pro vytváření oboru názvů vyhledávacího stroje. A *kořenovou položku* je objekt obsahující vlastnosti a metody a mohou obsahovat také zdroj událostí.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT AddNamedItem(  
   LPCOLESTR          pszName,  
   DWORD              dwFlags,  
   IDispatch          *pdisp  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszName`  
 [in] Název položky, jak zobrazit ze skriptu. Název musí být jedinečný a trvalé.  
  
 `dwFlags`  
 [in] Příznaky, které jsou spojeny s pojmenovanou položku. Může být kombinací následujícího:  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|SCRIPTITEM_ISVISIBLE|0x00000002|Označuje, zda je název položky k dispozici v oboru skriptu. To umožňuje přístup k události, metody a vlastnosti položky.<br /><br /> Podle konvence vlastnosti položky zahrnout členy podřízené položky. Proto všechny podřízený objekt vlastnosti a metody (a jejich podřízených členů, rekurzivně) jsou k dispozici.|  
|SCRIPTITEM_ISSOURCE|0x00000004|Určuje zdroj položky události, že skript může mít skript obslužných rutin událostí.|  
|SCRIPTITEM_GLOBALMEMBERS|0x00000008|Označuje, že položka je kolekce globálních vlastností a metod, které jsou spojeny pomocí skriptu. Její členy jsou vytvořené jako globální proměnné a metody.|  
|SCRIPTITEM_ISPERSISTENT|0x00000040|Označuje, že položky by měla uložit, pokud je uložený skript, modul pro vytváření.|  
|SCRIPTITEM_CODEONLY|0x00000200|Označuje, že pojmenovanou položku představuje objekt pouze kód a nemá žádné členy, aby mohli vytvářet.|  
|SCRIPTITEM_NOCODE|0x00000400|Označuje, že pojmenované položka je pouze název přidávané a nemá žádné položky k vytvoření.|  
  
 `pdisp`  
 [in] `IDispatch` z `NamedItem` objekt, který se používá ke shromažďování metody, vlastnosti nebo zdroj událostí.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthor Interface](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::RemoveNamedItem](../../winscript/reference/iactivescriptauthor-removenameditem.md)