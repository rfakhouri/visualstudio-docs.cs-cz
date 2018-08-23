---
title: Idiaenumsectioncontribs::Next – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Next method
ms.assetid: a6bb2adb-ee6d-4f3c-ab5b-e89361c8880e
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 01b09f132d7afadc5462602bde2eeb0a3da3bead
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671883"
---
# <a name="idiaenumsectioncontribsnext"></a>IDiaEnumSectionContribs::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaenumsectioncontribs::Next –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumsectioncontribs-next).  
  
Načte zadaný počet příspěvků oddíl v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Next(   
   ULONG                celt,   
   IDiaSectionContrib** rgelt,  
   ULONG*               pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [in] Číslo části příspěvků v enumerátor, který se má načíst.  
  
 rgelt  
 [out] Pole, které má být vyplněny [idiasectioncontrib –](../../debugger/debug-interface-access/idiasectioncontrib.md) objekty, které představují požadované části příspěvků.  
  
 pceltFetched  
 [out] Vrátí číslo části příspěvků v načtení enumerátoru.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistují žádné příspěvky v další části. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsectioncontribs –](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)   
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)



