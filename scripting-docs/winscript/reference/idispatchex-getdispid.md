---
title: IDispatchEx::GetDispID | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetDispID
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetDispID method
ms.assetid: a288d63d-b08a-4540-9d9d-0bcd182eff9a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c466ec767be53d100b970314bf0d81d5dd9dfb20
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097536"
---
# <a name="idispatchexgetdispid"></a>IDispatchEx::GetDispID
Název jednoho člena se mapuje na jeho odpovídající identifikátor DISPID, který můžete použít v následných voláních na `IDispatchEx::InvokeEx`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDispID(  
   BSTR bstrName,  
   DWORD grfdex,  
   DISPID *pid  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `bstrName`  
 Předaný název má být namapována.  
  
 `grfdex`  
 Určuje možnosti pro získání identifikátor členu. To může být kombinací následujícího:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|fdexNameCaseSensitive|Požadavky, které vyhledávání názvů provést způsobem malá a velká písmena. Mohou být ignorovány objektem, který nepodporuje vyhledávání malá a velká písmena.|  
|fdexNameEnsure|Požadavky, že člen vytvoří, pokud ještě neexistuje. Nový člen by měl být vytvořen s hodnotou `VT_EMPTY`.|  
|fdexNameImplicit|Označuje, že je volající hledání členem konkrétní název objekty při základního objektu nebyl explicitně zadán.|  
|fdexNameCaseInsensitive|Požadavky, které provést vyhledávání názvů písmen. Mohou být ignorovány objektem, který nepodporuje vyhledávání velká a malá písmena.|  
  
 `pid`  
 Ukazatel na volající – přidělené místo pro příjem DISPID výsledek. Pokud dojde k chybě, `pid` obsahuje DISPID_UNKNOWN.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|||  
|-|-|  
|`S_OK`|Úspěch.|  
|`E_OUTOFMEMORY`|Nedostatek paměti.|  
|`DISP_E_UNKNOWNNAME`|Název nebyl znám.|  
  
## <a name="remarks"></a>Poznámky  
 `GetDispID` je možné místo `GetIDsOfNames` získat hodnota DISPID pro daného člena.  
  
 Protože `IDispatchEx` umožňuje přidávání a odstraňování členů sadu hodnoty dispID není zůstal neměnný po dobu životnosti objektu.  
  
 Nevyužité `riid` parametr `IDispatch::GetIDsOfNames` byla odebrána.  
  
## <a name="example"></a>Příklad  
  
```cpp
BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;   
  
   // Assign to pdex and bstrName  
   pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid);  
   // Use dispid  
```  
  
## <a name="see-also"></a>Viz také  
 [IDispatchEx – rozhraní](../../winscript/reference/idispatchex-interface.md)