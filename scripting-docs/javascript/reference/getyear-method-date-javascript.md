---
title: "getYear – metoda (Date) (JavaScript) | Microsoft Docs"
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
- getYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, returning year
- GetYear method
ms.assetid: 0e23e832-acd4-49a9-a175-515d0094f172
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0e08fae8da1b102918de70650d09080a7ff7ebd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getyear-method-date-javascript"></a>getYear – metoda (Date) (JavaScript)
Získá rok `Date` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getYear()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí rok.  
  
## <a name="remarks"></a>Poznámky  
  
> [!IMPORTANT]
>  Tato metoda je zastaralá a se poskytuje pouze z důvodů zpětné kompatibility. Použití `getFullYear` metoda místo.  
  
 V [!INCLUDE[jsv1textspecific](../../javascript/reference/includes/jsv1textspecific-md.md)]a potom v prohlížeči Internet Explorer verze počínaje [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)], je hodnota vrácená uložené rok minus 1900. Například v roce 1899 se vrátí hodnotu -1 a v roce 2000 se vrátí jako 100.  
  
 V [!INCLUDE[jsv3textspecific](../../javascript/reference/includes/jsv3textspecific-md.md)] prostřednictvím [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)], vzorec závisí na rok. Hodnota vrácená let 1900 až 1999 je číslice 2 hodnotu, která je uložená rok minus 1900. Pro data mimo tento rozsah je vrácen rok 4 číslice. Například 1996 se vrátí jako 96, ale 1825 a 2025 se vrátí jako je.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getFullYear – metoda (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear – metoda (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear – metoda (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear – metoda (Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)   
 [setYear – metoda (Date)](../../javascript/reference/setyear-method-date-javascript.md)