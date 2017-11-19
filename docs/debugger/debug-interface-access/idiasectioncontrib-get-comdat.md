---
title: "Idiasectioncontrib::get_comdat – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSectionContrib::get_comdat method
ms.assetid: 8bd9be8d-59ee-4698-b055-daba354b8dcc
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3797f60e9ca6e97da3b7b6e44c89f802b086d13
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasectioncontribgetcomdat"></a>IDiaSectionContrib::get_comdat
Získá příznak označující, zda je daný oddíl sekvence COMDAT záznam.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_comdat (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` oddíl je záznam sekvence COMDAT; jinak vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Záznam sekvence COMDAT je běžné objekt souboru formátu (COFF) záznam, který zviditelní zabalené funkce pro linkeru.  
  
## <a name="see-also"></a>Viz také  
 [Idiasectioncontrib –](../../debugger/debug-interface-access/idiasectioncontrib.md)