---
title: Sccgetversion – funkce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2b5c5e5e6035d6ce0b81ba747efa3cea65ab2f97
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42681972"
---
# <a name="sccgetversion-function"></a>SccGetVersion – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [sccgetversion – funkce](https://docs.microsoft.com/visualstudio/extensibility/sccgetversion-function).  
  
Tato funkce získá číslo verze rozhraní API modulu Plug-in zdroje ovládacího prvku podporuje modul plug-in správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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

