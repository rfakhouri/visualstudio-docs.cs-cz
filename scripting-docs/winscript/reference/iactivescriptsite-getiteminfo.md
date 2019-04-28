---
title: IActiveScriptSite::GetItemInfo | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.GetItemInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_GetItemInfo
ms.assetid: f859ed3b-02c1-4924-99f8-5f5bf1bf8405
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 997245f8e4fd43ac2162587f07e4c8711af7caac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992735"
---
# <a name="iactivescriptsitegetiteminfo"></a>IActiveScriptSite::GetItemInfo
Umožňuje získat informace o položce přidán s skriptovací stroj [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetItemInfo(  
    LPCOLESTR pstrName,     // address of item name  
    DWORD dwReturnMask,     // bit mask for information retrieval  
    IUnknown **ppunkItem,   // address of pointer to item's IUnknown  
    ITypeInfo **ppTypeInfo  // address of pointer to item's ITypeInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrName`  
 [in] Název přidružený k položce, jak je uvedeno v [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) metody.  
  
 `dwReturnMask`  
 [in] Bitová maska určující, jaké informace o položce by měla být vrácena. Skriptovací modul by měl požádat o minimální množství informací je to možné, protože některé z návratových parametrů (například `ITypeInfo`) může trvat docela dlouho načíst nebo vytvořit. Může být kombinací následujícího:  
  
|Value|Význam|  
|-----------|-------------|  
|SCRIPTINFO_IUNKNOWN|Vrátí `IUnknown` rozhraní pro tuto položku.|  
|SCRIPTINFO_ITYPEINFO|Vrátí `ITypeInfo` rozhraní pro tuto položku.|  
  
 `ppunkItem`  
 [out] Adresa proměnné, která přijímá ukazatel `IUnknown` rozhraní přidružené k dané položce. Můžete používat skriptovací stroj `IUnknown::QueryInterface` metodu k získání `IDispatch` rozhraní pro položku. Tento parametr přijímá hodnotu NULL, pokud `dwReturnMask` nezahrnuje SCRIPTINFO_IUNKNOWN hodnotu. Také pokud neexistuje žádný objekt přidružený název položky; přijímá hodnotu NULL Tento mechanismus umožňuje vytvořit jednoduchou třídu při přidání pojmenované položky s příznakem SCRIPTITEM_CODEONLY nastavit [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) metody.  
  
 `ppTypeInfo`  
 [out] Adresa proměnné, která přijímá ukazatel `ITypeInfo` rozhraní přidružené k položce. Tento parametr přijímá hodnotu NULL, pokud `dwReturnMask` nezahrnuje SCRIPTINFO_ITYPEINFO hodnotu, nebo pokud informace o typu není k dispozici pro tuto položku. Pokud není k dispozici informace o typu, objektu nelze zdroje událostí a název vazby musí dají realizovat s využitím `IDispatch::GetIDsOfNames` metody. Všimněte si, `ITypeInfo` rozhraní načíst popisuje položky coclass (TKIND_COCLASS), protože objekt může podporovat více rozhraní a události. Pokud položka podporuje `IProvideMultipleTypeInfo` rozhraní, `ITypeInfo` načíst rozhraní je stejný jako pozici nula `ITypeInfo` , který by byl získán, pomocí `IProvideMultipleTypeInfo::GetInfoOfIndex` metody.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`TYPE_E_ELEMENTNOTFOUND`|Položka se zadaným názvem nebyla nalezena.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda načte jenom informace o indikován `dwReturnMask` parametr; to zvyšuje výkon. Například pokud `ITypeInfo` rozhraní není potřeba pro některou položku, se jednoduše nezadá v `dwReturnMask`.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)