---
title: "setYear – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Year method
- setYear method
ms.assetid: 36431050-e0ec-45ee-830d-0d7c20e207ea
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5a9318de4a9420e0518dcd7f00a51c7161a8f92c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setyear-method-date-javascript"></a>setYear – metoda (Date) (JavaScript)
Nastaví hodnotu roku v `Date` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setYear(numYear)   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numYear`  
 Požadováno. Let 1900 až 1999 jde číselnou hodnotu, která je rovna roku minus 1900. Pro data mimo tento rozsah jde číselnou hodnotu 4 číslice.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je zastaralá a bude zachována pro účely zpětné kompatibility jenom. Použití `setFullYear` metoda místo.  
  
 Chcete-li nastavit rok `Date` objekt, který chcete 1997, volání **setYear(97)**. Chcete-li nastavit v roce 2010, volejte **setYear(2010)**. Nakonec pokud chcete nastavit roku roku v rozsahu 0-99, použijte `setFullYear` metoda.  
  
> [!NOTE]
>  Pro [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] verze 1.0, `setYear` používá hodnotu, která je výsledkem přidání 1900 hodnotu roku poskytované `numYear`bez ohledu hodnotu roku. Chcete-li například nastavit roku na 1899 `numYear` je -1 a nastavit v roce 2000 `numYear` je 100.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getFullYear – metoda (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear – metoda (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [getYear – metoda (Date)](../../javascript/reference/getyear-method-date-javascript.md)   
 [setFullYear – metoda (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear – metoda (Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)