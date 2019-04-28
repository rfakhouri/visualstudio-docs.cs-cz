---
title: Iperpropertybrowsing2 – rozhraní 1 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2 interface
ms.assetid: 1e50b3f7-cc1c-495a-93c7-3ee03aea0b8a
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 156cf9a1e104b8a2d7ffe4e48bd39642ef1abbd0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62944891"
---
# <a name="iperpropertybrowsing2-interface-1"></a>Iperpropertybrowsing2 – rozhraní 1
Přístupy nabízí informace na stránkách vlastností objektu.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|`GetDisplayString`|Vrátí textový řetězec s popisem zadanou vlastnost.|  
|`MapPropertyToPage`|Vrátí identifikátor CLSID stránky vlastností, který umožňuje manipulaci s zadané vlastnosti.|  
|`GetPredefinedStrings`|Vrátí spočítaný počet pole řetězců (`LPOLESTR` ukazatele) seznam popisů povolených hodnot, které může přijmout zadanou vlastnost.|  
|`SetPredefinedValue`|Nastaví hodnotu vlastnosti předdefinovanou hodnotu identifikovaný token `dwCookie.`|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dbgprop.h