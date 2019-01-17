---
title: Iperpropertybrowsing2 – rozhraní 1 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: bded7159b72fc8c1ae8408611ce858105e6734da
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344021"
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