---
title: "prototype – vlastnost (Intl.DateTimeFormat) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: e1e693ff-1775-407e-b655-18a60d238ded
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 64dff17e4aaf62940f4c9c5f8b422fcbceb7212a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-intldatetimeformat"></a>prototype – vlastnost (Intl.DateTimeFormat)
Vrátí odkaz na prototypu pro formátování.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
dateTimeFormat.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `dateTimeFormat` Argument je název formátování.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `Intl.DateTimeFormat` objektu, který vrátí hodnotu největší prvku sady, deklarovat funkci, přidejte ho do `Intl.DateTimeFormat.prototype`a pak jeho pomocí.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]