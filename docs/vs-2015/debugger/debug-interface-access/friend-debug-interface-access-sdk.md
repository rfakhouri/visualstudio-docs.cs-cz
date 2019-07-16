---
title: Friend (přístup k rozhraní ladění SDK) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- friend functions [DIA SDK]
- friend classes [DIA SDK]
- Friend symbol
ms.assetid: 5147a170-41ce-4727-8ace-c318e8d11647
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ab8892bdf0caaa61a4b60fab10a5fecfb115e7f1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164212"
---
# <a name="friend-debug-interface-access-sdk"></a>Přítel (Přístup k rozhraní ladění SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Spřátelené třídy a spřátelené funkce jsou určeny `SymTagFriend` symboly. Uživatelem definované typy (UDT) jsou podřízené objekty nadřazeného objektu a mít [idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md) vlastnost.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny další platné vlastnosti pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Symbol pro UDT nadřazenou položku.|  
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|ID symbolu nadřazené třídy.|  
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název třídy nebo funkce.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagFriend` (jeden z [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Symbol pro dané třídy nebo funkce.|  
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|ID typu symbol.|  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)
