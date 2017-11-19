---
title: "prototype – vlastnost (Set) | Microsoft Docs"
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
ms.assetid: a075d5a6-e502-4636-85fc-1af001b8ac35
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8265d182562aee55f870fff4c3d5cbadf21402ac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-set"></a>prototype – vlastnost (Set)
Vrátí odkaz na prototypu pro sadu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
set.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `set` Argument je název sady.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `Set` objektu, který vrátí hodnotu největší prvku sady, deklarovat funkci, přidejte ho do `Set.prototype`a pak jeho pomocí.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]