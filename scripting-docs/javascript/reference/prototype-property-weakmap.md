---
title: "prototype – vlastnost (WeakMap) | Microsoft Docs"
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
ms.assetid: d28b8a9b-38c9-443d-9586-7cc74784bd99
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5cc1bff0d62f2aeb8d6fb78a0857f287fb34078c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-weakmap"></a>prototype – vlastnost (WeakMap)
Vrátí odkaz na prototypu pro `WeakMap` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
weakmap.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `weakmap` Argument je název `WeakMap` objektu.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `WeakMap` objekt, který vrátí hodnotu největší elementu `WeakMap`, deklarovat funkci, přidejte ho do `WeakMap.prototype`a pak jeho pomocí.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]