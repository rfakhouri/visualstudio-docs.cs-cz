---
title: "prototype – vlastnost (WeakSet) | Microsoft Docs"
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
ms.assetid: 950e15a2-2f56-4cb9-8e48-020efd97f938
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c66c7854a83dcf3128025350a7fcdd17f4dfaf5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-weakset"></a>prototype – vlastnost (WeakSet)
Vrátí odkaz na prototypu pro `WeakSet`.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
weakset.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `weakset` Argument je název sady.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `WeakSet` objektu, který vrátí hodnotu největší prvku sady, deklarovat funkci, přidejte ho do `WeakSet.prototype`a pak jeho pomocí.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]