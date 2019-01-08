---
title: IDispatchEx::DeleteMemberByName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 1866b5135d2c98ccacb34c2c776c69dd7d25db3f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096431"
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