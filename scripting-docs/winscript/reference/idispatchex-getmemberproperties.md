---
title: IDispatchEx::GetMemberProperties | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetMemberProperties
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetMemberProperties method
ms.assetid: 20d43209-12e2-472a-9bf3-81eced137b71
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f607e06fe3c898a6839c0bbd2d51edee1f0ffb2c
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160729"
---
# <a name="idispatchexgetmemberproperties"></a>IDispatchEx::GetMemberProperties
Načte vlastnosti člena.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetMemberProperties(  
   DISPID id,  
   DWORD grfdexFetch,  
   DWORD *pgrfdex  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `id`  
 Identifikuje člena. Používá `GetDispID` nebo `GetNextDispID` získat identifikátor odeslání.  
  
 `grfdexFetch`  
 Určuje vlastnosti, které chcete načíst. To může být kombinací hodnot uvedených v části `pgrfdex` a/nebo kombinaci těchto hodnot:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|grfdexPropCanAll|Kombinuje fdexPropCanGet, fdexPropCanPut, fdexPropCanPutRef, fdexPropCanCall, fdexPropCanConstruct a fdexPropCanSourceEvents.|  
|grfdexPropCannotAll|Kombinuje fdexPropCannotGet, fdexPropCannotPut, fdexPropCannotPutRef, fdexPropCannotCall, fdexPropCannotConstruct a fdexPropCannotSourceEvents.|  
|grfdexPropExtraAll|Kombinuje fdexPropNoSideEffects a fdexPropDynamicType.|  
|grfdexPropAll|Kombinuje grfdexPropCanAll grfdexPropCannotAll a grfdexPropExtraAll.|  
  
 `pgrfdex`  
 Adresa `DWORD` , která obdrží požadované vlastnosti. To může být kombinací následujícího:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|fdexPropCanGet|Člen nejde získat pomocí DISPATCH_PROPERTYGET.|  
|fdexPropCannotGet|Člen nejde zjistit pomocí DISPATCH_PROPERTYGET.|  
|fdexPropCanPut|Člen můžete nastavit pomocí DISPATCH_PROPERTYPUT.|  
|fdexPropCannotPut|Člen nejde nastavit pomocí DISPATCH_PROPERTYPUT.|  
|fdexPropCanPutRef|Člen můžete nastavit pomocí DISPATCH_PROPERTYPUTREF.|  
|fdexPropCannotPutRef|Člen nejde nastavit pomocí DISPATCH_PROPERTYPUTREF.|  
|fdexPropNoSideEffects|Člen nemá žádné vedlejší účinky. Například ladicí program může bezpečně get/set/volání tohoto členu beze změny stavu skriptu, který se právě ladí.|  
|fdexPropDynamicType|Člen je dynamický a můžete změnit po celou dobu životnosti objektu.|  
|fdexPropCanCall|Člen lze volat jako metodu pomocí DISPATCH_METHOD.|  
|fdexPropCannotCall|Člen nejde volat jako metodu pomocí DISPATCH_METHOD.|  
|fdexPropCanConstruct|Člen lze volat jako konstruktor pomocí DISPATCH_CONSTRUCT.|  
|fdexPropCannotConstruct|Člen nejde volat jako konstruktor pomocí DISPATCH_CONSTRUCT.|  
|fdexPropCanSourceEvents|Člen můžete aktivovat události.|  
|fdexPropCannotSourceEvents|Člen nejde aktivovat události.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|||  
|-|-|  
|`S_OK`|Úspěch.|  
|`DISP_E_UNKNOWNNAME`|Název nebyl znám.|  
  
## <a name="example"></a>Příklad  
  
```cpp
BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;   
   DWORD dwProps;  
  
   // Assign to pdex and bstrName  
   if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)) &&  
      SUCCEEDED(pdex->GetMemberProperties(dispid, grfdexPropAll, &dwProps)) &&  
         (dwProps & fdexPropCanPut))  
   {  
      // Assign to member  
   }  
```  
  
## <a name="see-also"></a>Viz také  
 [IDispatchEx – rozhraní](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)