---
title: Sccgetversion – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b997f3724dc3d1bb0f9155f3b575fef3ce9f2802
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53879624"
---
# <a name="sccgetversion-function"></a>SccGetVersion – funkce
Tato funkce získá číslo verze rozhraní API modulu Plug-in zdroje ovládacího prvku podporuje modul plug-in správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
LONG SccGetVersion(void);  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="return-value"></a>Návratová hodnota  
 A `LONG` datový typ, který obsahuje číslo verze rozhraní API podporované zdrojového ovládacího prvku modulu Plug-in:  
  
|WORD|Popis|  
|----------|-----------------|  
|HIWORD|Hlavní verze|  
|LOWORD|Podverze|  
  
## <a name="remarks"></a>Poznámky  
 Například pokud modul plug-in správy zdrojového kódu podporuje verze 1.3 rozhraní API modulu Plug-in zdroje ovládacího prvku, vrátila by tato funkce 0x0103.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)