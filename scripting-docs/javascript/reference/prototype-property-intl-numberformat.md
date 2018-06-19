---
title: prototype – vlastnost (Intl.NumberFormat) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 7f6a7e26-108b-4b32-97c2-7f96b9252c50
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b037ce7476574252966e17fcf64246beeaaea1e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791214"
---
# <a name="prototype-property-intlnumberformat"></a>prototype – vlastnost (Intl.NumberFormat)
Vrátí odkaz na prototypu pro formátování.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
numberFormat.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `numberFormat` Argument je název formátování.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `Intl.NumberFormat` objektu, který vrátí hodnotu největší prvku sady, deklarovat funkci, přidejte ho do `Intl.NumberFormat.prototype`a pak jeho pomocí.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]