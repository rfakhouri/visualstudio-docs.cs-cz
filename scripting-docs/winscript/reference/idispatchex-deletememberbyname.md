---
title: IDispatchEx::DeleteMemberByName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.DeleteMemberByName
apilocation:
- scrobj.dll
helpviewer_keywords:
- DeleteMemberByName method
ms.assetid: a01b4e6a-d989-4b29-bb3f-04554f8c39f7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc7c8db4ab28e0bd0fcb48f352cb07595f72fd17
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58153822"
---
# <a name="idispatchexdeletememberbyname"></a>IDispatchEx::DeleteMemberByName
Odstraní člena podle názvu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT DeleteMemberByName(  
   BSTR bstrName,  
   DWORD grfdex  
  
```  
  
#### <a name="parameters"></a>Parametry  
 `bstrName`  
 Název člena, která se má odstranit.  
  
 `grfdex`  
 Určuje, zda je název člena malá a velká písmena. Může to být jedna z následujících hodnot:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|fdexNameCaseSensitive|Požadavky, které vyhledávání názvů provést způsobem malá a velká písmena. Můžete ignorovat objektem, který nepodporuje vyhledávání malá a velká písmena.|  
|fdexNameCaseInsensitive|Požadavky, které provést vyhledávání názvů písmen. Můžete ignorovat objektem, který nepodporuje vyhledávání velká a malá písmena.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|||  
|-|-|  
|`S_OK`|Úspěch.|  
|`S_FALSE`|Člen existuje, ale nejde odstranit.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud je člen odstraněn, je potřeba hodnota DISPID jsou dál platné pro `GetNextDispID`.  
  
 Pokud člen se zadaným názvem se odstraní a později je znovu vytvořit člena se stejným názvem, hodnota DISPID by měl být stejný. (Ať už jsou členy, které se liší pouze velikostí písma "stejné" závisí na objektu.)  
  
## <a name="example"></a>Příklad  
  
```cpp
BSTR bstrName;  
IDispatchEx *pdex;  
  
// Assign to pdex and bstrName  
pdex->DeleteMemberByName(bstrName, fdexNameCaseSensitive);  
```  
  
## <a name="see-also"></a>Viz také  
 [IDispatchEx – rozhraní](../../winscript/reference/idispatchex-interface.md)