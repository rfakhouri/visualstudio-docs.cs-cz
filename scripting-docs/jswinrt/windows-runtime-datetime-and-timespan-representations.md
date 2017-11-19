---
title: "Windows Runtime data a času a časového rozpětí reprezentace | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime dates and times
- TimeSpan [JavaScript]
- DateTime [JavaScript]
ms.assetid: 9743e9ac-9054-463e-8264-427183e4905f
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d7c394b57eb0215e3dff857d935b367e602c2b0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="windows-runtime-datetime-and-timespan-representations"></a>Windows Runtime DateTime a reprezentace časový interval
JavaScript reprezentace data a časy se liší od verze prostředí Windows Runtime. Prostředí Windows Runtime [data a času](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx) se struktura reprezentuje v jazyce JavaScript jako [datum](../javascript/reference/date-object-javascript.md) má záložnímu úložišti, který odpovídá `DateTime` dat (a má jiný rozsah a přesnost z jazyka JavaScript `Date`). Pokud změníte toto vlastní `Date` objektu, bude standardního JavaScriptu `Date` a ztráta přesnosti. JavaScript `Date` hodnot se dá předat do prostředí Windows Runtime `DateTime` a bude rozsah zaškrtnuto, což může vést ke kódování výjimky.  
  
 Prostředí Windows Runtime [časový interval](http://msdn.microsoft.com/en-us/c5defb66-819c-4796-85b5-07ed249a5d86) struktura je převést na milisekundách a vrátí jako číslo JavaScript.  
  
## <a name="see-also"></a>Viz také  
 [Pomocí prostředí Windows Runtime v jazyce JavaScript](../jswinrt/using-the-windows-runtime-in-javascript.md)