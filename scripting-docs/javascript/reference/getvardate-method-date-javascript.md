---
title: "getVarDate – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- getVarDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- getVarDate method
- dates, VT_DATE format
ms.assetid: 561238de-5c91-45a3-b839-a16910d3a1cf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d21394a5381653997a6b406537a6bde4f5266b97
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getvardate-method-date-javascript"></a>getVarDate – metoda (Date) (JavaScript)
Vrátí hodnotu VT_DATE – z `Date` objektu.  
  
> [!WARNING]
>  Tato metoda je podporovaná jenom v aplikaci Internet Explorer.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getVarDate()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí hodnotu VT_DATE –.  
  
## <a name="remarks"></a>Poznámky  
 `getVarDate` Metoda se používá, když kód jazyka JavaScript pracuje s objekty COM, objekty ActiveX nebo jiné objekty, které přijímají a návratové hodnoty date v VT_DATE – formát. Mezi ně patří objekty v jazyce Visual Basic a Visual Basic Scripting Edition (VBScript). Skutečný formát vrácená hodnota závisí na místní nastavení.  
  
## <a name="requirements"></a>Požadavky  
 Podporováno v následujících režimech dokumentů: Quirks, standardy aplikace Internet Explorer 6, standardy aplikace Internet Explorer 7, standardy aplikace Internet Explorer 8, standardy aplikace Internet Explorer 9 a standardy aplikace Internet Explorer 10. Není podporováno v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Viz [Informace o verzi](../../javascript/reference/javascript-version-information.md).  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getDate – metoda (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [Date.Parse – funkce](../../javascript/reference/date-parse-function-javascript.md)