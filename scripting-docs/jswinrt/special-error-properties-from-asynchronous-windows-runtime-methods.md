---
title: "Zvláštní Chyba vlastnosti z metod asynchronní Windows Runtime | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 120d8f699c8bedd0fe5762300203c5d5ec18e73e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="special-error-properties-from-asynchronous-windows-runtime-methods"></a>Zvláštní Chyba vlastnosti z metod asynchronní Windows Runtime
Může být obtížné ladění asynchronních metod prostředí Windows Runtime v jazyce JavaScript, protože chyba může být vyvolána z hloubkové někde v zásobníku volání. Jazyk JavaScript `Error` objekt má zvláštních vlastností, které se zobrazují pouze pokud je vyvolána chyba z asynchronní metodu prostředí Windows Runtime když aplikace běží v režimu ladění.  
  
## <a name="special-error-properties"></a>Zvláštní Chyba vlastnosti  
 Objekt error, která je výsledkem neúspěšné asynchronní operaci prostředí Windows Runtime v režimu ladění má následující vlastnosti speciální:  
  
-   `asyncOpSource`(Objekt) Získá informace o do původního umístění, kde bylo provedeno volání, která je chyba. Vlastnost `asyncOpSource.originatingCall` (String) zobrazí umístění v kódu uživatele, která pochází asynchronní operaci.  
  
-   asyncOpType (String) získá název typu asynchronní operaci, která vyvolala chybu.  
  
 Další informace o chybách s asynchronních operací najdete v tématu:  
  
-   [Nabízí způsob zpracování chyb s](https://msdn.microsoft.com/en-us/library/windows/apps/hh700337.aspx)  
  
-   [Řešení potíží s chybami prostředí Windows Runtime](http://msdn.microsoft.com/en-us/1ef7d7df-82ac-441d-8ad0-54ab1318de64)