---
title: "Idiaenumsectioncontribs::Item – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSectionContribs::Item method
ms.assetid: 63a28f23-0ca0-44a7-b11b-ca0206d642a0
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8434ab31e8a597b37f6ee10b9334ce02777d272a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumsectioncontribsitem"></a>IDiaEnumSectionContribs::Item
Načte část příspěvky prostřednictvím indexu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   DWORD                index,  
   IDiaSectionContrib** section  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 index  
 [v] Z indexu [idiasectioncontrib –](../../debugger/debug-interface-access/idiasectioncontrib.md) objekt, který má být načtena. Index je v rozsahu od 0 do `count`-1, kde `count` je vrácený [idiaenumsectioncontribs::get_count –](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md) metoda.  
  
 section  
 [out] Vrátí [idiasectioncontrib –](../../debugger/debug-interface-access/idiasectioncontrib.md) objekt reprezentující příspěvku požadované části.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsectioncontribs::get_count –](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md)   
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)