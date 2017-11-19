---
title: "Idiaenumsectioncontribs::Next – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSectionContribs::Next method
ms.assetid: a6bb2adb-ee6d-4f3c-ab5b-e89361c8880e
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50682486041327270b69c6ec86b81a2df2b3a426
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsectioncontribsnext"></a>IDiaEnumSectionContribs::Next
Načte zadaný počet příspěvky oddíl v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Next(   
   ULONG                celt,   
   IDiaSectionContrib** rgelt,  
   ULONG*               pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [v] Číslo oddílu příspěvky v enumerátor mají být načteny.  
  
 rgelt  
 [out] Pole, které má být vyplněny [idiasectioncontrib –](../../debugger/debug-interface-access/idiasectioncontrib.md) objekty, které představují požadované části příspěvky.  
  
 pceltFetched  
 [out] Vrátí číslo oddílu příspěvků v načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistují žádné další části příspěvky. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsectioncontribs –](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)   
 [Idiasectioncontrib –](../../debugger/debug-interface-access/idiasectioncontrib.md)